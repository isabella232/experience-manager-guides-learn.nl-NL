---
sidebar_position: 8
source-git-commit: d99be38f5d69a7472909511faad230bea9bc435b
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---


# Voorbeelden

In dit pakket hebben we ook enkele voorbeelden van aanpassingen gegeven (beschikbaar op `guides_extension/src`). Hieronder vindt u een korte beschrijving van elk van deze aspecten.

1. [Contextmenu](./../../src/file_options.ts)
In dit voorbeeld hebben we de `file_options` contextmenu, om de `Delete` en `Edit` en vervangt u de `Duplicate` optie met een `Download` -optie.

2. [Linkerdeelvenster](../../src/left_panel_container.ts)
In dit voorbeeld hebben we de `left tab panel` om een andere`tab` met de titel &quot;TEST EXTENSION&quot; en een bijbehorende `tab panel` met een etiket: `Test Tab Panel`

3. [Rechterdeelvenster](../../src/right_panel_container.ts)
In dit voorbeeld hebben we de `right tab panel` om een andere `tab` met de titel &quot;TEST EXTENSION&quot; en een bijbehorende `tab panel` met een etiket: `New Tab Panel`

4. [Deelvenster Opslagplaats](../../src/repository_panel.ts)

5. [Werkbalk](../../src/toolbar.ts)
In dit voorbeeld hebben we de `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` knoppen met één `More Insert Options` knop met al deze elementen.

[App-voorbeelden bekijken]

1. [Gereedschap Annotatie](../../src/review_app_examples/annotation_extension.ts)
In dit voorbeeld hebben we een andere knop toegevoegd aan de gereedschapset voor annotaties waarmee het huidige revisieonderwerp in AEM wordt geopend.

2. [Opmerking bekijken](../../src/review_app_examples/review_comment.ts)
In dit voorbeeld hebben we de gebruikersnaam vervangen door gebruikersgegevens (bestaande uit de volledige naam en titel van de opmerking), een unieke opmerking-id, een mailpictogram en invoervelden toegevoegd voor het vermelden van de ernst en de motivering van de opmerking.
We hebben ook een `accept with modification` op opmerkingen aan de zijde van XMLEditor die een dialoogvenster opent.

3. [Reageren met opmerkingen](../../src/review_app_examples/comment_reply.ts)
In dit voorbeeld hebben we de gebruikersnaam vervangen door gebruikersgegevens (bestaande uit de volledige naam en titel van de opmerking) en een pictogram mailto toegevoegd aan de koptekst van de opmerking.

4. [Deelvenster Inline revisie](../../src/review_app_examples/inline_review_panel.ts)
In dit bestand berekenen en toewijzen we de unieke opmerking-id die in het dialoogvenster `Review Comment` en `Comment Reply` voorbeelden.
   - De `setCommentId` De methode stelt de unieke opmerking-id in op elke opmerking, afhankelijk van het aantal opmerkingen.

   - De `setUserInfo` Hiermee wordt de waarde van userInfo ingesteld, waarbij de volledige naam en titel voor elke opmerking worden gebruikt.

   - De `onNewCommentEvent` zorgt ervoor dat `setUserInfo` voor elke nieuwe opmerking of elk nieuw antwoord wordt een methode aangeroepen.

   - De `updatedProcessComments` functie wordt uitgevoerd voor elke nieuwe opmerkingsgebeurtenis en zorgt ervoor dat `setCommentId` wordt opgeroepen als we een nieuwe opmerkingsgebeurtenis krijgen.

5. [Deelvenster Onderwerpbeoordelingen](../../src/review_app_examples/topic_reviews.ts): Dit bestand is uitgebreid [Deelvenster Inline revisie](../../src/review_app_examples/inline_review_panel.ts) zodat toegevoegde aanpassingen ook aan de revisie-app werken.

6. [Accepteren met dialoogvenster Wijzigen](../../src/review_app_examples/accept_with_modification_dialog.ts)
Dit is een voorbeeld van het toevoegen van een nieuwe widget aan de app. Hier hebben we een nieuw dialoogvenster gemaakt met twee invoertekstvelden: `Revised Text` en `Adjudicator Comment Rationale`

![Accepteren met dialoogvenster Wijzigen](./imgs/accept_with_modification_dialogue.png)

Hier volgt het revisievenster voor en na de aanpassing:

![Controlepanel;](./imgs/review_panel.png)
![Accepteren met dialoogvenster Wijzigen](./imgs/customised_review_panel.png)
