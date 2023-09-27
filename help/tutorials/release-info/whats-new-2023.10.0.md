---
title: Opmerkingen bij de release | Nieuwe functies in Adobe Experience Manager-hulplijnen, release oktober 2023
description: Leer de nieuwe en verbeterde functies in de release van Adobe Experience Manager Guides van oktober 2023 as a Cloud Service.
source-git-commit: 18adbd41370d32b183cc4828d1d79b7183453f5e
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# Nieuwe functies in de release van Adobe Experience Manager Guides in oktober 2023 as a Cloud Service

Dit artikel behandelt de nieuwe en verbeterde functies in versie oktober 2023 van de Gidsen van Adobe Experience Manager (later genoemd als *Hulplijnen AEM as a Cloud Service*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u [Opmerkingen bij de release](release-notes-2023.10.0.md).


## Vorm een gegevensbronschakelaar gebruikend de hulpmiddelen

Experience Manager Guides biedt nu een **Gegevensbronnen** hulpmiddel dat u helpt uit-van-de-doosschakelaars voor gegevensbronnen vormen. U kunt de schakelaars voor JIRA, SQL (MySQL, PostgreSQL, de Server van Microsoft SQL, SQLite, MariaDB, H2DB), de gegevensbestanden van de Handel van Adobe, en van de Elasticsearch gemakkelijk tot stand brengen.

U kunt ook gemakkelijk een gegevensbronaansluiting bewerken, opnieuw verbinden, dupliceren of verwijderen. Leer hoe u [vorm een gegevensbronschakelaar gebruikend de hulpmiddelen](../install-guide/conf-data-source-connector.md).

![gegevensbronconnectors die worden vermeld in het deelvenster Gegevensbronnen](assets/data-sources-create-window.png){width="550" align="left"}

*Creeer en bekijk de gegevensbronschakelaars van het paneel van gegevensbronnen.*

## Logboeken van de mening voor de onderwerpgenerator

U kunt nu ook het logbestand voor het genereren van inhoud weergeven. Met dit logbestand kunt u de waarschuwingen, fouten en uitzonderingen controleren.  Meer informatie over hoe [opties voor een onderwerpgenerator](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) hulp u gemakkelijk produceert en beheert de onderwerpgenerators.

## Ondersteuning voor snelheidsgereedschappen in de gegevensbronsjablonen

U kunt nu de gereedschappen Snelheid gebruiken in de sjablonen voor hulplijnen voor Experience Managers. Met deze gereedschappen kunt u verschillende functies toepassen op de gegevens die u ophaalt van de gegevensbronnen. U kunt de sjablonen gebruiken tijdens het maken van een inhoudsfragment of onderwerp. Met deze functie bespaart u tijd en moeite om handmatig dezelfde functie toe te passen op elke gegevensset.  Het zorgt ook voor nauwkeurige resultaten.
U kunt bijvoorbeeld het gereedschap $mathTool gebruiken om wiskundige functies uit te voeren.
Meer informatie over hoe [De hulpmiddelen van de gebruikssnelheid in de gegevensbronmalplaatjes](../user-guide/web-editor-content-snippet.md##use-velocity-tools).


## Native PDF-verbeteringen

De volgende Native PDF-verbeteringen zijn doorgevoerd in de release van oktober 2023:

### Het paginanummer van de eerste pagina van een lay-out opnieuw instellen

In de native PDF-uitvoer kunt u de paginanummers opnieuw starten en het nummer opgeven waaruit de nummering begint. Nu kunt u de nummering ook alleen starten voor het eerste exemplaar van een sectie.
Meer informatie over hoe [werken met de pagina-eigenschappen van een pagina-indeling](../native-pdf/design-page-layout.md#page-props-page-layout).


### Hoofdstukken weergeven zonder automatische nummers in de inhoudsopgave

De Gidsen van de Experience Manager tonen de hoofdstukaantallen samen met de hoofdstuknamen in de Inhoudslijst (TOC). Nu kunt u verkiezen om slechts de hoofdstuknamen zonder de hoofdstukaantallen te publiceren. Bekijk meer details over hoe te om te vormen [geavanceerde PDF-instellingen van een sjabloon](../native-pdf/components-pdf-template.md#advanced-pdf-settings).

## Een kaart downloaden vanuit de webeditor

Nu kunt u niet alleen een kaart in de kaartweergave van de Redacteur van het Web uitgeven maar ook het downloaden. U kunt de kaart downloaden met een specifieke basislijn. U kunt de hiërarchie ook afvlakken en alle bestanden en mappen in één map opslaan.

Raadpleeg voor meer informatie de **Kaartweergave** functiebeschrijving in het gedeelte [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.

![optiemenu van een bestand in de dataweergave](assets/options-menu-repo-view-file-level-2310.png){width="550" align="left"}

*Selecteer een bestand in de dataweergave en kies de optie om een handeling op het bestand uit te voeren.*

## Een bestand bewerken in de plug-in voor de zuurstofaansluiting

Met de hulplijnen voor Experience Managers kunt u nu een bestand selecteren in de webeditor en het bestand vervolgens bewerken in de insteekmodule voor de zuurstofaansluiting. Deze optie wordt niet ingeschakeld als onderdeel van de out-of-the-box ondersteuning.

Raadpleeg voor meer informatie de **Opties voor een bestand** functiebeschrijving in het gedeelte [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.

