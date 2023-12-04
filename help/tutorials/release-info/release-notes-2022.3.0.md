---
title: Opmerkingen bij de release [!DNL AEM Guides], release maart 2022
description: Release van maart [!DNL Adobe Experience Manager Guides] as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---

# Release van maart [!DNL Adobe Experience Manager Guides] as a Cloud Service

## Upgrade naar de release van maart

Upgrade uw huidige [!DNL Adobe Experience Manager Guides] as a Cloud Service (later *[!DNL AEM Guides]as a Cloud Service*) door de volgende stappen uit te voeren:
1. Controle uit de code van Git van Cloud Servicen en schakelaar aan de tak die in de pijpleiding van Cloud Servicen wordt gevormd die aan het milieu beantwoordt u wilt bevorderen.
1. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van uw Cloud Servicen: hiermee wordt de Git-code ingesteld op 2022.3.123.
1. Leg de wijzigingen vast en voer de pijplijn met Cloud Servicen uit om naar de release van maart van [!DNL AEM Guides] as a Cloud Service.

## Compatibiliteitsmatrix

In deze sectie wordt de compatibiliteitsmatrix weergegeven voor de softwaretoepassingen die worden ondersteund door [!DNL AEM Guides] as a Cloud Service release maart 2022.

### FrameMaker en FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Niet compatibel | 2020-update 4 en hoger |
| | |


### Zuurstofaansluiting

| [!DNL AEM Guides] Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac |
| --- | --- | --- |
| 2022,3,0 | 2.4.0. | 2.4.0. |
|  |  |  |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

## Nieuwe en verbeterde functies

### Nieuw basislijndashboard

[!DNL AEM Guides] De as a Cloud Service versie van de Maart verstrekt de eigenschap van de Basislijn die binnen de Redacteur van het Web wordt geïntegreerd. U kunt basislijnen van de Redacteur van het Web nu tot stand brengen en hen gebruiken om onderwerpen van verschillende versies te publiceren of te vertalen.

Opmerking: voor een geüpgraded systeem moet u de nieuwste **ui_config.json** voor Mapprofiel.

Gebruik deze functie om een basislijn met een specifieke versie van de onderwerpen tot stand te brengen beschikbaar op een specifieke datum en een tijd. Bovendien kunt u met de API-ondersteuning een basislijn maken of bijwerken met een label dat is gedefinieerd voor een versie van onderwerpen.

![tabblad voor basislijnbeheer](assets/baseline-manage.png)

U kunt de bestanden doorzoeken op bestandsnamen of op de bestandslocatie. U kunt ook de onderwerpen filteren die in het basislijnbewerkingsvenster moeten worden weergegeven en ze sorteren op basis van specifieke kolommen.

![tabblad voor basislijnbeheer](assets/baseline-filter.png)

De prestaties voor het basisproces voor het maken zijn verder verbeterd. Het proces om basislijnen tot stand te brengen is asynchroon, zodat kunt u andere dossiers in de Redacteur van het Web blijven uitgeven terwijl de basislijn wordt gecreeerd. Zie voor meer informatie *Basislijnen maken en beheren vanuit de webeditor* in de gebruikershandleiding.

Opmerking: het tabblad Basislijn op het kaartdashboard is standaard verborgen. Uw beheerder kan het lusje van de Basislijn op het kaartdashboard toelaten.

### Verbeterd gedrag voor vernieuwen van webeditor

De volgende verbeteringen zijn nu beschikbaar met browser verfrist verrichting in de Redacteur van het Web:

* Nu krijgt u de steun om browser te verfrissen terwijl u uw inhoud in de Redacteur van het Web bewerkt. Als u op het pictogram Vernieuwen klikt terwijl een of meer bestanden met niet-opgeslagen wijzigingen worden geopend voor bewerking, wordt u gevraagd uw bestanden op te slaan of de actie Vernieuwen te annuleren.

* Zelfs bij het vernieuwen van de browser blijven de weergaven van het linkerdeelvenster en het rechterdeelvenster behouden.

* Het actieve onderwerp of de kaart DITA wordt opnieuw geopend in het inhoudsuitgevende gebied.

### Verbeteringen voor publiceren

Het publicatieproces is verder verbeterd met de publicatie in maart van [!DNL AEM Guides] as a Cloud Service:

* De basislijnen zijn gerespecteerd voor de metagegevens van AEM site-uitvoer. U kunt de eigenschappen van een basislijnversie ook als metagegevens verwerken. Als geen basislijn wordt bepaald, dan worden de eigenschappen van de recentste versie verwerkt als meta-gegevens.

* De **Bestandsnaam** en **Argumenten DITA-OT-opdrachtregel** Er zijn opties toegevoegd voor HTML5-, EPUB- en aangepaste uitvoervoorinstellingen. U kunt nu de bestandsnaam opgeven waarmee u de uitvoer wilt opslaan. U kunt ook de aanvullende argumenten opgeven die u met DITA-OT wilt verwerken tijdens het genereren van uitvoer.

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

* Onbekwaam om voorgrond, achterstandselementen in een boekenkaart toe te voegen gebruikend de mening van de Auteur van de Redacteur van het Web. 7652
* De boomeinden van de verwijzing na het verwijderen van een onderwerp en het uitvoeren van een bewegingsverrichting. (8804)
* Er wordt een uitzondering ontvangen bij het weergeven van de inhoud na het uploaden van een element. 3638
* Er treedt een fout op wanneer bestanden waarvan de bovenliggende map speciale tekens in de bestandsnaam bevat, worden geopend in Zuurstof (met de opdracht **Bewerken in zuurstof** ). 8918
* De **Zoeken in opslagplaats** De DITA-kaart wordt niet in de XML-editor gezocht en gemarkeerd. 8796
* Filteren geeft niet de juiste resultaten wanneer meerdere kenmerken aan de inhoud in de XML-editor worden toegevoegd. 8795
* Er treedt een fout op bij het toevoegen van een gebruiker als beheerder in het mappenprofiel als de gebruiker-id numeriek is. 8908

## Bekende problemen

Adobe heeft het volgende bekende probleem in het [!DNL AEM Guides] as a Cloud Service release maart.

* Als u labels op directe verwijzingen verwijdert, worden de labels ook van indirecte verwijzingen verwijderd.

* Kan de bijgewerkte basislijntitel niet spiegelen zonder het basislijnvenster handmatig te vernieuwen.

* De functie voor versievoorvertoning in het deelvenster Versiehistorie geeft geen voorvertoning van een geselecteerd onderwerp weer.
