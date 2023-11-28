---
sidebar_position: 1
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---


# Eenvoudige aanpassing, voorbeeld

Laat ons nu hoe te om deze aanpassingen in onze app van de Gidsen van de AEM te integreren.

We willen deze knop bijvoorbeeld toevoegen aan een bestaande weergave van de app.
Hiervoor moeten drie fundamentele dingen worden gedaan:

1. De `id` In de weergave willen we onze component toevoegen.
2. De `target`, dat wil zeggen de locatie in de JSON waaraan we de nieuwe component willen toevoegen. De `target` wordt gedefinieerd met een `key` en `value`. Het sleutelwaardepaar kan om het even welk attribuut zijn dat wordt gebruikt om de component te bepalen die in unieke identificatie van het kan helpen.
We kunnen indexen ook gebruiken om naar het doel te verwijzen.
We hebben drie visies:  `APPEND`, `PREPEND`, `REPLACE`.
3. De JSON van de nieuw gemaakte component en de bijbehorende methoden.

Stel dat u een knop wilt toevoegen aan de gereedschapset voor annotaties die wordt gebruikt in de revisie, waarmee het bestand in AEM wordt geopend.

```typescript
export default {
  id: 'annotation_toolbox', 
  view: {
    items: [
      {
        component: 'button',
        icon: 'linkOut',
        title: 'Open topic in Assets view',
        'on-click': 'openTopicInAEM',
        target: {
          key: 'value',
          value: 'addcomment',
          viewState: VIEW_STATE.APPEND

        },
      },
    ],
  },
  controller: {
    openTopicInAEM: function (args) {
        const topicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC)
        const {allTopics = {}} = tcx.model.getValue(tcx.model.KEYS.REVIEW_DATA) || {}
        tcx.appGet('util').openInAEM(allTopics[topicIndex])
    },
  },
}
```

In het bovenstaande voorbeeld hebben we:

1. de `id` van de JSON waarin we onze component willen invoegen, dat wil zeggen `annotation_toolbox`
2. het doel is `addcomment` knop. We voegen onze knop toe na de `addcomment` knop met de viewState `append`.
3. De gebeurtenis on-click van de knop in de controller wordt gedefinieerd.

De JSON voor de [`annotation_toolbox`](./../../../jsons/review_app/annotation_toolbox.json)

Voordat de annotatietoolbox werd aangepast, zag deze er als volgt uit:

![annotation-toolbox](imgs/annotation_toolbox.png "Gereedschap Annotatie")

Na de aanpassing ziet de gereedschapset voor annotaties er als volgt uit:

![aangepaste annotation-toolbox](imgs/customised_annotation_toolbox.png "Aangepaste gereedschapset voor annotaties")

## CSS toevoegen

Voor de consistentie bieden we de component die al is opgemaakt. Op de ingevoegde JSON worden inherente stijlen toegepast. De primaire manier om CSS te beheren is via de toets extraClass in de extensies.

```js
{    
    "view":{
        items:[
            {
                compoenent:"button",
                extraClass:"underline bg-red",
            }
        ]
    }
}
```

U kunt aangepaste stijlen met CSS-klassen plaatsen door een CSS-bestand toe te voegen aan [clientlibs](#clientlibs). Tijdens de bouw creëren wij ook [Tailwind](https://tailwindcss.com/docs/utility-first) output voor de nutsklassen in staarwind. De config voor het zelfde kan worden gevonden bij [tailwind.config.js](../../../tailwind.config.js)
