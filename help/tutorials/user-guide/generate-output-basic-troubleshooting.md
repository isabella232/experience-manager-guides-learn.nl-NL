---
title: Basisprobleemoplossing
description: Los problemen op met het basisoplossen van problemen in AEM hulplijnen. Leer om, het logboekdossier in een tekstredacteur te bekijken te kopiëren en te controleren en JSP compilatiefouten op te lossen.
exl-id: b5ab2618-6f11-4aaa-8471-09521f8bb512
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Basisprobleemoplossing {#id1821I0Y0G0A}

Wanneer u werkt met AEM hulplijnen, kunnen er fouten optreden wanneer u het document publiceert of opent. Dergelijke fouten zouden in de kaart DITA, onderwerp, of in AEM proces van Gidsen zelf kunnen zijn. Deze sectie verstrekt informatie over hoe te om tot informatie in het dossier van het het logboekdossier van de outputgeneratie toegang te hebben en te ontleden. Ook, als uw onderwerp DITA te groot is, dan zou u de JSP compilatiefout kunnen zien. Deze sectie verstrekt ook informatie over hoe te om de JSP compilatiefout op te lossen.

## Logbestand weergeven en controleren {#id1822G0P0CHS}

Voer de volgende stappen uit om het logboekbestand van de outputgeneratie te bekijken en te controleren:

1. Als u het productieproces voor de uitvoer hebt gestart, klikt u op **Uitvoer** in de DITA kaartconsole.

   De **Algemeen** kolom van de **Gegenereerde uitvoer** toont de pictogrammen om visuele aanwijzing over het succes of het mislukken van de outputproductie te geven.

   ![](images/output-general-settings.png){width="300" align="left"}

   In de bovenstaande schermafbeelding geven het eerste en derde pictogram een mislukte uitvoergeneratie aan. Het tweede pictogram toont een succesvolle outputgeneratie maar met berichten. De laatste is een geslaagde outputgeneratie zonder enig bericht.

1. Klik op de koppeling in het dialoogvenster **Gegenereerd op** kolom nadat de taak is voltooid.

   Het logbestand wordt op een nieuw tabblad geopend.

   ![](images/log-file.png){width="800" align="left"}

1. Pas de volgende filters toe om de tekst in het logbestand te markeren:
   - Onherstelbaar: hiermee worden de fatale fouten in het logbestand met roze kleur gemarkeerd.
   - Fout: markeert de fouten in het logbestand met oranje kleur.
   - Waarschuwing: hiermee worden de waarschuwingen in het logbestand gemarkeerd met paarse kleur.
   - Info: hiermee worden de informatieberichten in het logbestand gemarkeerd met een blauwe kleur.
   - Uitzondering: markeert de uitzonderingen in het logbestand met een gele kleur.
1. Met de navigatieknoppen Omhoog en Omlaag kunt u naar de gemarkeerde tekst in het logbestand gaan.

   U kunt ook door het logbestand bladeren en de berichten controleren.


## Het logbestand kopiëren en controleren in een teksteditor

Voer de volgende stappen uit om het logboekdossier van de outputgeneratie in een tekstredacteur te kopiëren en te controleren:

1. Als u het productieproces voor de uitvoer hebt gestart, klikt u op **Uitvoer** in de DITA kaartconsole.

1. Klik op de koppeling in het dialoogvenster **Gegenereerd op** kolom nadat de taak is voltooid.

   Het logbestand wordt op een nieuw tabblad geopend.

1. Klikken **Logboek kopiëren** knop. Het logbestand wordt naar het klembord gekopieerd.
1. Open een teksteditor en plak het logbestand in de editor.

1. Blader door het logbestand en controleer op berichten.

   Aan de hand van de volgende informatie kunt u bepalen of er een fout optreedt in het DITA-bestand of in het proces AEM hulplijnen:

   - *Aan het DITA-kaartbestand gerelateerde fout*: Als er een fout wordt gevonden in het DITA-kaartbestand of een ander bestand in de DITA-kaart, bevat het logbestand de tekenreeks BUILD FAILED. U kunt de informatie in het logbestand controleren om het onjuiste bestand te zoeken en het probleem op te lossen.

   In het volgende voorbeeldfragment van het logboekdossier, kunt u zien `BUILD FAILED` samen met de reden voor de fout.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *Aan hulplijnen gerelateerde fout AEM*: Het andere type fout dat u in het logbestand kunt identificeren, is gerelateerd aan AEM proces Hulplijnen zelf. In dit geval wordt het DITA-toewijzingsbestand geparseerd, maar mislukt het genereren van de uitvoer door een interne fout in AEM hulplijnen. Voor dergelijke fouten moet u hulp vragen bij het team voor technische ondersteuning.

   In het volgende voorbeeldfragment van het logboekdossier, kunt u zien `BUILD SUCCESSFUL` bericht, gevolgd door een andere technische fout.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## JSP-compilatiefout oplossen

Als uw onderwerp DITA te groot is, dan zou u de JSP compilatiefout \ ( kunnen zien`org.apache.sling.api.request.TooManyCallsException`\) in uw browser. Deze fout kan optreden wanneer u een onderwerp opent voor bewerken, reviseren of publiceren.

Voer de volgende stappen uit om dit probleem op te lossen:

1. Selecteer in de globale navigatie Gereedschappen en kies Bewerkingen \> Webconsole.

   De Adobe Experience Manager Web Console Configuration-pagina wordt weergegeven.

1. Zoeken naar en klikken op de knop *Apache Sling Main Servlet* component.

   De configureerbare opties voor de Apache Sling Main Servlet worden weergegeven.

1. Verhoog de waarde voor de *Aantal Vraag per Verzoek* op basis van uw vereisten.


**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)
