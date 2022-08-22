---
title: Opmerkingen bij de release | Adobe Experience Manager Guides as a Cloud Service, release augustus 2022
description: Laatste release van Adobe Experience Manager-hulplijnen as a Cloud Service
source-git-commit: 7cc33e4621c2bfbf08a720f173e8e419c5424a6c
workflow-type: tm+mt
source-wordcount: '1156'
ht-degree: 1%

---

# Laatste release van Adobe Experience Manager-hulplijnen as a Cloud Service

## Upgrade naar de nieuwste versie

Upgrade uw huidige as a Cloud Service Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*) door de volgende stappen uit te voeren:
1. Controle uit de Cloud Services Gespitcode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2022.8.167.
3. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om naar de nieuwste versie van AEM as a Cloud Service hulplijnen te upgraden.

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM Guides, as a Cloud Service in de release van augustus 2022.

### FrameMaker en het Publiceren FrameMaker Server

| FMPS | FrameMaker |
| --- | --- |
| Niet compatibel | 2020-update 4 en hoger |
|  |  |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac |
| --- | --- | --- |
| 2022,8,0 | 2.7.5. | 2.7.5. |
|  |  |  |


## Nieuwe en verbeterde functies

AEM de as a Cloud Service Gidsen verstrekt vele verhogingen en nieuwe eigenschappen in de recentste versie:

### Layoutweergave in de Kaarteditor

Nu kunt u de volledige lay-out van een kaart DITA in de Redacteur van de Kaart bekijken. Wanneer u een kaart opent om te bewerken, wordt het dialoogvenster **Layout** weergave van de Kaarteditor. In deze weergave kunt u de kaarthiërarchie in een boomstructuurweergave zien en de onderwerpen in een kaart ordenen of structureren.

![layoutweergave](assets/layout-view-map.png)

De layoutweergave bevat een aparte werkbalk waarmee u veel taken kunt uitvoeren met betrekking tot de onderwerpen in een kaart.
U kunt onderwerpverwijzingen, onderwerpgroep, zeer belangrijke definities in een kaart opnemen. U kunt de onderwerpen in een kaart reorganiseren door ze omhoog, omlaag, links of rechts te verplaatsen. U kunt de onderwerpen ook slepen en neerzetten om ze in een kaart te verplaatsen. De Kaarteditor verstrekt ook de pictogrammen om dossiers te sluiten of te ontgrendelen, de versiegeschiedenis te controleren, en een beheer van het versielabel te doen.


De layoutweergave bevat ook de **Weergaveopties** om regelnummer weer te geven of te verbergen, schakelt u het selectievakje uit of toont u de bestandsnaam of titel voor de onderwerpen in een kaart.


![weergaveopties](assets/view-options.png)

U kunt de onderwerpen ook bekijken die op de voorwaardelijke filters worden gebaseerd die op hen worden toegepast.

Naast het organiseren van onderwerpen in het kaartdossier, kunt u verwijzingen ook toevoegen, bewegen, kopiëren, kleven, of schrappen gebruikend **Opties** beschikbaar voor een element in de layoutweergave. U kunt ook een onderwerp of een kaart van het paneel van de bewaarplaats aan de kaart slepen en neerzetten die in de Redacteur van de Kaart wordt geopend.

In het rechterdeelvenster worden de eigenschappen Inhoud en Kaart weergegeven in de layoutweergave van de Kaarteditor. De gealigneerde Attributen die voor het geselecteerde onderwerp worden bepaald worden getoond tegen het onderwerp in de mening van de Lay-out. U kunt bijvoorbeeld snel alle onderwerpen vinden waarvoor het platformkenmerk is gedefinieerd als `IOS`.

Nu kunt u de meta-gegevensinformatie voor de onderwerpen of de kaart ook plaatsen. U kunt de Titel Nav, de Tekst van de Verbinding, Korte Beschrijving, en Sleutelwoorden voor het geselecteerde onderwerp of de kaart bepalen.

![layoutweergave, rechts deelvenster](assets/layout-inline-attributes.png)

Zie voor meer informatie *Layoutweergave* in Adobe Experience Manager-hulplijnen as a Cloud Service gebruiken.

### Inline-kenmerken in de Editor-instellingen

Met AEM hulplijnen kunt u nu de configuratie van **Inline-kenmerken** door uw beheerder van de **Editor-instellingen**. U kunt ook nieuwe inline-kenmerken toevoegen of de bestaande kenmerken verwijderen uit de **Inline-kenmerken** in de Editor Settings.
De gevormde Inline Attributen die voor een onderwerp worden bepaald worden getoond tegen het onderwerp in de mening van de Lay-out.

![Editor-instellingen](assets/editor-settings-inline-attributes.png)


### Extra filters in de weergave Opslag

De filterzoekopdracht in de dataweergave is nu krachtiger gemaakt. Twee nieuwe zoekcriteria, **Laatst gewijzigd** en **Tags** zijn toegevoegd om de bestanden te filteren en uw zoekopdracht in de AEM opslagplaats te beperken:
* **Laatst gewijzigd**: U kunt zoeken naar bestanden die het laatst zijn gewijzigd na een geselecteerde datum, maar vóór een geselecteerde datum. U kunt ook de vooraf gedefinieerde criteria gebruiken en zoeken naar bestanden die de laatste twee uur, vorige week, vorige maand of vorig jaar zijn gewijzigd.
* **Tags**: U kunt ook zoeken naar bestanden waarop specifieke tags zijn toegepast. U kunt de tag typen of deze selecteren in de vervolgkeuzelijst.

![Weergavefilters voor opslagplaats](assets/repo-filter-search.png)


## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

* Vervangen Lucene-index wordt gebruikt in /core/article-publish/src/main/java/com/adobe/dxml/article/publish/util/DoxUtils.java (9291)
* Bijgewerkte Node.js wordt niet gebruikt voor het publiceren. (9835)
* Het DITA-onderwerp wordt niet automatisch bijgewerkt met de wijzigingen die op het tabblad **Eigenschappen** pagina. (8745)
* FrontMattelement wanneer toegevoegd aan een DITA-boekenkaart werkt niet correct. (9507)
* Native PDF | Bij gebruik wordt een lege PDF gegenereerd **Snel genereren** voor meerdere bestanden als er een leeg element is geselecteerd. (9822)
* Native PDF | Aanhangsel wordt gepubliceerd als een hoofdstuk in de PDF-uitvoer. (9829)
* Native PDF | Wanneer een SVG-afbeelding wordt bewerkt, wordt deze niet weergegeven in de paginalay-out. (9069)
* Een normaal afbreekstreepje wordt ingevoegd wanneer een `Nonbreaking Hyphen` teken wordt ingevoegd met de **Speciaal teken invoegen** . (8919)
* De Redacteur van XML toont geen bijgewerkte beelden in de onderwerpen als zij zijn uitgegeven. (9500)
* Wanneer u de uitvoer publiceert via de Editor, kunnen de voorinstellingen niet worden verwijderd uit het dialoogvenster **Uitvoer** tab. (9100)
* De submaps van een kaart DITA worden niet gecontroleerd gebruikend **Alles selecteren** in het menu voor ovaal. (9814)
* Kan kaart- of onderwerpsjablonen niet slepen vanuit de **Sjablonen** menu aan het malplaatje van de douanekaart in de redacteur van het Web. (9846)
* Onbekwaam om een nieuw onderwerp of kaartmalplaatje in subfolder van een kaart of onderwerpmalplaatje tot stand te brengen. (9888)
* Er is geen optie aanwezig om door de onderwerpen of kaarten te bladeren die aanwezig zijn in de submappen van een kaart of onderwerpsjabloon. (9889)
* Wanneer een Schematron-bestand samen met het DITA-bestand wordt bijgewerkt en opgeslagen, wordt het rechterdeelvenster niet weergegeven (als het DITA-bestand de validaties in het Schematron-bestand verbreekt). (9986)
* Er kan een nieuwe voorinstelling voor gedupliceerde uitvoer worden gemaakt als de naam van deze voorinstelling gelijk is aan die van een bestaande voorinstelling. (997)
* SVG-afbeeldingen worden beschadigd en publiceren niet correct wanneer de HTML-uitvoer wordt gegenereerd. (9949)


## Bekende problemen

Adobe heeft de volgende bekende problemen voor AEM Guides as a Cloud Service in de release van augustus 2022 geïdentificeerd.

### Bekende problemen met tijdelijke oplossing

Gebruik de opgegeven tijdelijke oplossing voor de volgende bekende problemen:

* De layoutweergave is niet zichtbaar in de Kaarteditor.

   **Workaround**: Werk ui_config.json in het Profiel van de Omslag bij.

* Symbols.json wordt overschreven, zodat uitgave 8919 voorkomt.

   **Workaround**: Bijgewerkte symbolen.json moet worden samengevoegd met overschreven symbolen.json.

### Andere bekende problemen

* Als er meerdere bestanden zijn geselecteerd in de resultatensectie die wordt weergegeven bij het uitvoeren van een zoekopdracht in de opslagplaats en vervolgens slepen en neerzetten in de auteurweergave, wordt slechts één bestand toegevoegd.
