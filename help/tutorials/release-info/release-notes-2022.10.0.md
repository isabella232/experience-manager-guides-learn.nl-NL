---
title: Opmerkingen bij de release | as a Cloud Service Adobe Experience Manager-hulplijnen, release oktober 2022
description: Release van Adobe Experience Manager Guides as a Cloud Service in oktober
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 0%

---

# Release van Adobe Experience Manager Guides as a Cloud Service in oktober

## Upgrade naar de release van oktober

Upgrade uw huidige as a Cloud Service Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*) door de volgende stappen uit te voeren:
1. Controle uit de code van Git van Cloud Servicen en schakelaar aan de tak die in de pijpleiding van Cloud Servicen wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
1. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van uw Cloud Servicen: hiermee wordt de Git-code ingesteld op 2022.10.183.
1. Leg de wijzigingen vast en voer de pijplijn met Cloud Servicen uit om naar de release van oktober van AEM as a Cloud Service hulplijnen te upgraden.

## Compatibiliteitsmatrix

Deze sectie bevat een overzicht van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM in de release van oktober 2022 as a Cloud Service hulplijnen.

### FrameMaker en FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Niet compatibel | 2020-update 4 en hoger |
| | |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022 10,0 | 2.7.13. | 2.7.13. | 2,3 | 2,3 |
|  |  |  |  |


## Nieuwe en verbeterde functies

AEM as a Cloud Service hulplijnen biedt verbeteringen en nieuwe functies in de release van oktober:


### Deelvenster Snel genereren

AEM hulplijnen biedt nu de **Snel genereren** deelvenster waarin u snel de uitvoer kunt genereren en weergeven van voorinstellingen die voor uw DITA-kaart zijn gemaakt.

![Pictogram Snel genereren](assets/quick-generate-icon.png)

In de **Snel genereren** kunt u de lijst zien met alle uitvoervoorinstellingen die voor uw DITA-kaart zijn gemaakt.

![Deelvenster Snel genereren](assets/quick-generate-panel.png)

Selecteer een of meer voorinstellingen en genereer snel de uitvoer. U kunt ook snel de uitvoer weergeven die voor de voorinstellingen is gegenereerd. Er wordt een succesbericht weergegeven bij het genereren van de uitvoer. Er wordt een foutbericht weergegeven als het genereren van de uitvoer mislukt. U kunt het foutenlogboek ook bekijken om de details van de fout te zien die in het generatieproces voorkwam.


## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

* Native PDF | Fout bij het verwijderen van brononderwerpen uit de uitvoer van de PDF. (10554)
* Native PDF | Lege toetsaanslagen verschijnen in de uitvoer van de PDF. (10553)
* Native PDF | `navtitle` for `topichead` is niet geëerd. 10509
* Native PDF | Steun nodig voor amd64 JDK-aroma&#39;s. 10465
* Native PDF | Kan de onderwerpen over de voorgrond niet verbergen in de inhoudsopgave. 10355
* Native PDF | Als u het paginanummer in de hoofdstuklayout opnieuw opstart, wordt de nummering vanaf het einde van het vorige hoofdstuk gestart. 10154
* Chrome-browser | Het scherm wordt leeg wanneer u elementen uit de gebruikersinterface sleept en neerzet. Bijvoorbeeld bij het slepen van een voorwaarde vanuit het deelvenster Voorwaarden. 10524
* Node-eigenschappen worden verwijderd nadat een element is gekopieerd en geplakt. 10053
* Bij klikken  **Sluiten** gebruikers werden omgeleid naar middelen - de ervaring is gecorrigeerd om gebruikers naar de AEM homepage te brengen . 9654
