---
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---
# De revisie-app aanpassen

Om de aanpassing van de revisie-app te vereenvoudigen, hebben we enkele haken weergegeven die hieronder worden beschreven en uitgelegd:

## Reviseren-opmerking

- id: `review_comment`
- haak: `this.updateExtraProps`:

Zoals besproken [hier](../../aem_guides_framework/basic_customisation.md)Alle nieuwe kenmerken die tijdens de aanpassing zijn toegevoegd, worden onder `this.model.extraProps`. De methode `updateExtraProps` Hiermee kunt u kenmerken toevoegen aan een revisieopmerking, waarbij u ook de update en opslag van het toegevoegde kenmerk op de server afhandelt.

### Voorbeeld van gebruik

U wilt bijvoorbeeld velden toevoegen `commentRationale` en `severity` op uw opmerkingen.
Laten we de `commentRationale` naar &quot;Dit is een belangrijke zin.&quot; en de `severity` naar &quot;KRITIEK&quot;.
Dit kan worden gedaan gebruikend de syntaxis:

```typescript
 this.updateExtraProps(
        {'commentRationale': 'This is an important sentence.',
        'severity': 'CRITICAL'}
      )
```

In het bovenstaande codefragment worden de waarden bijgewerkt en opgeslagen. De opgeslagen waarden kunnen worden weergegeven in de gebruikersinterface door de weergave te definiëren.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Deelvenster Inline revisie

- id: `inline_review_panel`

1. haak: `onNewCommentEvent`
De haak `onNewCommentEvent` kunt u een gebeurtenis genereren of een methode aanroepen voor een nieuwe opmerking- of antwoordgebeurtenis.
De args die in het `onNewCommentEvent` omvatten:
   - gebeurtenissen: de opmerking-/antwoordgebeurtenis die is verzonden.
   - newComment: Boolean Als de verzonden gebeurtenis een nieuwe opmerkingsgebeurtenis was, d.w.z. `highlight`, `insertion`, `deletion`, `sticky note comment`
   - newReply: boolean Als de verzonden gebeurtenis een nieuwe reactiegebeurtenis was.

2. haak: `sendExtraProps`

Deze haak is nuttig als u een `event` en verzenden `extraProps` in het deelvenster Inline-revisie. We zullen het gebruik van deze twee haken hieronder toelichten.

### Voorbeeld van het deelvenster Inline Review

Zeg dat we een extraProp willen sturen, `userInfo`, telkens wanneer een nieuwe opmerking of reactie wordt verzonden. Dit gebeurt nu via het deelvenster voor inline revisie, maar we hebben geen verwijzing naar de opmerking-id van de zojuist gegenereerde opmerking. Daarom kunnen we de volgende code schrijven.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.model.currTopicIndex || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

In het bovenstaande codefragment controleren we of de verzonden gebeurtenis een nieuwe opmerking of een nieuw antwoord is. In het geval van een nieuwe opmerking of een nieuw antwoord noemen wij de methode `setUserInfo`

```typescript
    setUserInfo(event) {
      this.loader?.getUserInfo(event.user).subscribe(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.sendExtraProps(
          data
        )
      })
    },
```

In de bovenstaande methode breiden we de gebeurtenis uit om extraProps te verzenden, inclusief de voornaam, e-mail, titel, enzovoort. Als u de gebeurtenis op deze manier uitbreidt, zorgt u ervoor dat de extraProps met de juiste commentId worden verzonden, zodat deze aan de juiste opmerking worden gekoppeld.

De haak `updateExtraProps` roept inherent de haak `sendExtraProps`Wanneer moet je dus gebruiken?

We gebruiken `updateExtraProps` in de `review_comment` controller, die al beschikt over de `id` en daarom moet u alleen de `extraProps.`

De `inline_review_panel` heeft echter geen toegang tot de id van de opmerking. Daarom moet u altijd een gebeurtenis verzenden vanuit het deelvenster voor inline revisie, het dialoogvenster `sendExtraProps` zal handig zijn.
