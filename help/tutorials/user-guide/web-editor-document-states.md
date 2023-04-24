---
title: Documentstatus
description: Leren hoe u de documentstatus kunt bepalen
source-git-commit: 13106cd1c7f6d38fecb67dd93eef66263eb29bae
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---


# Documentstatus {#id1821HC00URO}

Om de gereedheid van de documenten te beheren, AEM bevatten hulplijnen een documentstatuseigenschap waarmee de huidige status van het document wordt aangegeven. Met documentstatussen kunt u snel nagaan of een document nieuw is, in de revisie of de voltooide status van de revisie.

## Typen documentstatussen

Voor een document kunnen alle documentstatussen zijn gedefinieerd in het profiel Documentstatus. Een document kan bijvoorbeeld een van de volgende documentstatussen hebben:

- Concept - Geeft aan dat het document wordt gemaakt en opgeslagen met nieuwe wijzigingen.
- In-Review - Geeft aan dat een revisiewerkstroom is gestart voor het document.
- Gereviseerd - Geeft aan dat het document is gereviseerd door de bedoelde gebruikers.

Deze statussen worden handmatig of automatisch ingesteld op basis van de profielinstellingen van de documentstatussen. Bijvoorbeeld, als het profiel van de Staat van het Document met beginstaat als Ontwerp wordt gevormd, en de staat In-Overzicht wordt bepaald voor documenten onder overzicht. Wanneer u vervolgens een document maakt, wordt de documentstatus ingesteld op *Concept*. Als u een revisietaak start, wordt de status van het document gewijzigd in In-Review.

U kunt de documentstatus voor een of meerdere documenten ook handmatig wijzigen. Als u echter de documentstatus voor meerdere documenten wilt wijzigen, wordt de toegestane status bepaald door de algemene staten die zijn toegestaan voor de geselecteerde documenten. Stel bijvoorbeeld dat u de documentstatussen in dezelfde volgorde hebt gedefinieerd als Concept, In-Review, Reviewed en Ready to Publish. In document 1.dita wordt de status ingesteld op *Concept* en in document two.dita, wordt de staat geplaatst aan Gecontroleerd. Wanneer u zowel—one.dita als two.dita selecteert, dan zal de toegestane documentstaat zijn *Klaar voor publicatie*. Aangezien two.dita binnen is *Bekeken* staat, is de volgende mogelijke staat voor two.dita slechts *Klaar voor publicatie*, die wordt weergegeven wanneer beide documenten zijn geselecteerd.

>[!NOTE]
>
> Een document kan slechts in één frame tegelijk bestaan.

## Documentstatus wijzigen

Voer de volgende stappen uit om de status van een document te wijzigen:

1. Selecteer in de interface Elementen een of meer documenten waarvan u de documentstatus wilt wijzigen.
1. Klik in de hoofdwerkbalk op **Eigenschappen**.
1. Selecteer het nieuwe frame in het menu **Documentstatus** vervolgkeuzelijst. U kunt alleen de documentstatussen selecteren die zijn toegestaan in het gedeelte Overgang status van het profiel Documentstatus.

   >[!NOTE]
   >
   >Beheerders kunnen alle documentstatussen weergeven en het document wijzigen in een willekeurige status.

1. Klikken **Opslaan en sluiten**.

## Documentstatus weergeven

De kaartmening van de Activa UI toont de huidige staat samen met de aanmaakdatum en de grootte van het respectieve DITA onderwerp of kaart DITA.

![](images/document_state.png){width="800" align="left"}

## Documentstatussen gebruiken in DDLC

Documentstatussen spelen een belangrijke rol bij het beheer van de levenscyclus van documenten in DDLC. Als uw organisatie strikt de DDLC volgt, dan wordt het hebben van een mechanisme om het uitgeven documenten te controleren die op hun staat worden gebaseerd een essentiële eigenschap. U kunt bijvoorbeeld het bewerken van documenten toestaan wanneer deze zich in *Concept* of *Herziening* staten. Als een document echter eenmaal is gereviseerd en klaar is om te publiceren, moet er een manier zijn om verdere wijzigingen van documenten te voorkomen.

AEM hulplijnen bieden een workflow voor documentgoedkeuring waarmee u de levenscyclus van het ontwikkelingsproces van uw document kunt bepalen. Als een document gereed is om te publiceren of de voorlaatste status heeft bereikt, kunt u het markeren als goedgekeurd. Nadat een document is goedgekeurd, wordt door AEM hulplijnen een nieuwe versie van het document gemaakt en wordt het alleen-lezen. Vervolgens kunt u het document verplaatsen voor publicatie of een basislijn maken voor verdere verwerking.

Een auteur moet een nieuwe versie starten om een nieuwe versie te starten van de documenten die zijn gemarkeerd als goedgekeurd. Als u een nieuwe versie start, verandert de documentstatus in *Concept* opnieuw. Door de documentstatus te wijzigen in *Concept*, wordt het document opnieuw bewerkbaar gemaakt en kunt u aan de volgende versie blijven werken.

Voer de volgende stappen uit om de functie voor documentgoedkeuring te gebruiken:

>[!NOTE]
>
> De beheerder moet de functie voor de goedkeuringswerkstroom inschakelen. Zie voor meer informatie *Goedkeuringswerkstroom inschakelen* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.

1. Open in de webeditor het document dat u ter goedkeuring wilt markeren.

1. Klik op de knop **Mark Approved**![](images/mark_approve_icon.svg) pictogram.

1. Als het document de status heeft die als goedgekeurd moet worden gemarkeerd, wordt het volgende dialoogvenster weergegeven:

   ![](images/mark-approved-correct-state.png){width="550" align="left"}

   Als uw document niet als goedgekeurd kan worden gemerkt, dan wordt het volgende bericht getoond:

   ![](images/mark-approved-incorrect-state.png){width="550" align="left"}

1. Als het document gereed is om te worden gemarkeerd als goedgekeurd, selecteert u een label in de vervolgkeuzelijst en klikt u op **Goedkeuren**.

   >[!NOTE]
   >
   > Als uw beheerder geen vooraf gedefinieerde lijst met labels heeft geconfigureerd, wordt u een tekstveld met een vrije vorm getoond waarin u een label kunt invoeren.

1. Als het document is gemarkeerd als goedgekeurd, wordt een **Voorvertoning** in het document wordt alleen-lezen weergegeven.

   ![](images/approved-doc-read-only.png){width="650" align="left"}

   >[!NOTE]
   >
   > In de modus Voorbeeld worden alle bewerkingsopties verwijderd van de werkbalk. Bovendien zijn de weergave Auteur en Bron van het document ook verwijderd uit de bovenste navigatie.


Als een document is gemarkeerd als goedgekeurd, kan het niet meer worden bewerkt. Als u het document voor de volgende versie wilt gebruiken, dan moet u het terugbrengen aan *Concept* status. De documentstatus van een goedgekeurd document wijzigen in *Concept* Voer de volgende stappen uit in de modus:

1. Klik in een goedgekeurd document op de knop **Een nieuwe versie starten** Pictogram ![](images/approved-restart-draft-mode-icon.svg).

   Het bericht Nieuwe release starten wordt weergegeven.

1. Klikken **Bevestigen**.

   De staat van het document wordt veranderd in Ontwerp en het document wordt geopend in de Redacteur van het Web op uitgeeft wijze.


**Bovenliggend onderwerp:**[ Werken met de webeditor](web-editor.md)

