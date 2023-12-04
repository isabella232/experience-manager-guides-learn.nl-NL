---
title: Opmerkingen bij de release | Nieuwe functies in de release van Adobe Experience Manager Guides 4.3.1
description: Meer informatie over de nieuwe en verbeterde functies in de 4.3.1-releases van Adobe Experience Manager Guides
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 0%

---

# Nieuwe functies in versie 4.3.1 van Adobe Experience Manager-hulplijnen (oktober 2023)

Dit artikel behandelt de nieuwe en verbeterde functies in versie 4.3.1 van de Gidsen van Adobe Experience Manager (later genoemd *Hulplijnen Experience Manager*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u [Opmerkingen bij de release](./release-notes-4.3.1.md).

## Verbind met een gegevensbron en neem de onderwerpen op

De Gidsen van de Experience Manager verstrekt uit-van-de-doosschakelaars die u met uw gegevensbronnen helpen verbinden, die tot de Gidsen van de Experience Manager een ware inhoudshub maken. Dit geeft u het voordeel om u tijd en inspanning te besparen die anders aan handgegevenstoevoeging of replicatie zouden worden besteed.

Samen met de bestaande uit-van-de-doos schakelaars zoals JIRA en SQL (MySQL, PostgreSQL, SQL Server, SQLite), kan uw beheerder schakelaars voor MariaDB, H2DB, de Uitwisseling van Adobe, en de gegevensbestanden van de Elasticsearch ook vormen. Zij kunnen andere schakelaars ook toevoegen door de standaardinterfaces uit te breiden.

U kunt de gevormde schakelaars onder bekijken **Gegevensbronnen** in de webeditor.

<img src="assets/data-sources.png" alt="Lijst met gegevensbronnen in het deelvenster" width="300">

*Bekijk de verbonden gegevensbronnen.*

U kunt nu ook een onderwerp van een verbonden gegevensbron tot stand brengen. Een onderwerp kan gegevens in diverse formaten, zoals lijsten, lijsten, en paragrafen bevatten. Het staat u ook toe om een kaart DITA voor alle onderwerpen tot stand te brengen. U kunt meta-gegevens aan het onderwerp associëren wanneer het trekken uit een gegevensbron.

Voor meer informatie, bekijkt u [Gegevens uit uw gegevensbron gebruiken](../user-guide/web-editor-content-snippet.md).

## Vorm een gegevensbronschakelaar van het gebruikersinterface

Experience Manager Guides biedt nu ook een **Gegevensbronnen** hulpmiddel dat u helpt uit-van-de-doosschakelaars voor gegevensbronnen vormen. U kunt de schakelaars voor JIRA, SQL (MySQL, PostgreSQL, de Server van Microsoft SQL, SQLite, MariaDB, H2DB), de gegevensbestanden van de Handel van Adobe, en van de Elasticsearch gemakkelijk tot stand brengen.

U kunt ook gemakkelijk een gegevensbronaansluiting bewerken, opnieuw verbinden, dupliceren of verwijderen. Meer informatie over hoe [vormt gemakkelijk een gegevensbronschakelaar van het gebruikersinterface](../install-guide/conf-data-source-connector-tools.md).

![gegevensbronconnectors die worden vermeld in het deelvenster Gegevensbronnen](assets/data-sources-create-window.png){width="550" align="left"}

*Creeer en bekijk de gegevensbronschakelaars van het paneel van gegevensbronnen.*

## Logboeken van de mening voor de onderwerpgenerator

U kunt nu ook het logbestand voor het genereren van inhoud weergeven. Met dit logbestand kunt u de waarschuwingen, fouten en uitzonderingen controleren.  Meer informatie over hoe [opties voor een onderwerpgenerator](../user-guide/web-editor-content-snippet.md#options-for-a-topic-generator) hulp u gemakkelijk produceert en beheert de onderwerpgenerators.

## Ondersteuning voor snelheidsgereedschappen in de gegevensbronsjablonen

U kunt nu de gereedschappen Snelheid gebruiken in de sjablonen voor hulplijnen voor Experience Managers. Met deze gereedschappen kunt u verschillende functies toepassen op de gegevens die u ophaalt van de gegevensbronnen. U kunt de sjablonen gebruiken tijdens het maken van een inhoudsfragment of onderwerp. Met deze functie bespaart u tijd en moeite om handmatig dezelfde functie toe te passen op elke gegevensset.  Het zorgt ook voor nauwkeurige resultaten.
U kunt bijvoorbeeld het gereedschap $mathTool gebruiken om wiskundige functies uit te voeren.
Meer informatie over hoe [De hulpmiddelen van de gebruikssnelheid in de gegevensbronmalplaatjes](../user-guide/web-editor-content-snippet.md#use-velocity-tools).


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


## Ondersteuning van meerdere onderwerpdefinities in één opsommingsdefinitie

U kunt nu een of meer onderwerpdefinities definiëren in een kaart en de opsommingsdefinities in een andere kaart en vervolgens de kaartverwijzing toevoegen. De verwijzingen naar onderwerpopsommingen worden opgelost in dezelfde kaart of in de kaart waarnaar wordt verwezen.

U kunt nu ook voorwaarden definiëren en deze toepassen op bepaalde specifieke elementen in een onderwerp.  De voorwaarden zijn alleen zichtbaar voor die specifieke elementen en niet voor alle andere elementen.

Voor meer details over de behandeling van hiërarchische definities van onderwerpdefinities en opsommingen, bekijk de de eigenschapbeschrijving van de Onderwerpregeling in [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.




## Verbeterde voorvertoning via het contextmenu

Gebruik het contextmenu om snel een voorvertoning van het bestand weer te geven (.dita, .xml, audio, video of afbeelding) zonder het te openen. U kunt nu het formaat van het voorvertoningsvenster wijzigen. Als de inhoud een referentiekoppeling bevat, kunt u het venster selecteren en openen op een nieuw tabblad.

![Voorvertoningsvenster ](assets/quick-preview_cs.png){width="800" align="left"}

*Geef een voorvertoning van het bestand weer in het deelvenster.*

Zie voor meer informatie over het contextmenu de **Opties voor een bestand** functiebeschrijving in het dialoogvenster [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.

## Een bestand bewerken in de plug-in voor de zuurstofaansluiting

Met de hulplijnen voor Experience Managers kunt u nu een bestand selecteren in de webeditor en het bestand vervolgens bewerken in de insteekmodule voor de zuurstofaansluiting. Deze optie wordt niet ingeschakeld als onderdeel van de out-of-the-box ondersteuning.

Raadpleeg voor meer informatie de **Opties voor een bestand** functiebeschrijving in het gedeelte [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.

## Variabelen voor huidige datum en tijd gebruiken in de opties Doelpad, Sitenaam of Bestandsnaam

Tijdens het genereren van uitvoer in AEM Site of PDF kunt u variabelen gebruiken voor het instellen van de **Doelpad**, **Sitenaam**, of **Bestandsnaam** opties. U kunt nu ook de opdracht `${system_date}`en `${system_time}` variabelen. Met deze variabelen kunt u de huidige datum en tijd aan deze opties toevoegen.

Leer hoe u [variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam](../user-guide/generate-output-use-variables.md).


## Sneltoetsen om de cursor in de webeditor te verplaatsen

Met de hulplijnen voor Experience Managers kunt u nu ook sneltoetsen gebruiken om de cursor in de webeditor te verplaatsen. Met de sneltoetsen kunt u snel één woord naar links of rechts verplaatsen. U kunt ook naar het begin of einde van de regel gaan met behulp van de sneltoetsen.

Meer informatie over de [sneltoetsen in de webeditor](../user-guide/web-editor-keyboard-shortcuts.md).
