---
title: REST API voor werken met DITA-kaarten
description: Meer informatie over de REST API voor werken met DITA-kaarten
source-git-commit: fad5049962f258bbe59c7d172436d82b3d6cd68f
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---


# REST API voor werken met DITA-kaarten {#id175UB30E05Z}

Met de volgende REST API kunt u werken met DITA-kaarten in AEM hulplijnen.

## DITA-kaart met afhankelijke personen downloaden

Een methode van GET die een kaart DITA met al zijn gebiedsdelen zoals referenced onderwerpen, sub-maps, beelden, en DTDs downloadt die in de kaart en onderwerpen wordt gebruikt.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/exportditamap

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`ditamap`|Tekenreeks|Ja|Absoluut pad van het DITA-kaartbestand in AEM opslagplaats.| |`baseline`|String|Yes|The title of the baseline that is used to retrieve the versioned content. <br> **Opmerking:** De waarde is hoofdlettergevoelig. |

**Responswaarden**: Een ZIP-bestand waarvan de inhoud naar de uitvoerstream van het antwoord wordt geschreven.

## Exporteren voor DITA-kaart met afhankelijke personen starten

Een methode van de POST die de uitvoer voor een kaart DITA met al zijn gebiedsdelen zoals referenced onderwerpen, sub-maps, beelden, en DTDs in werking stelt die in de kaart en onderwerpen wordt gebruikt. De status kan later worden opgevraagd en de download-URL kan worden opgehaald zodra deze is voltooid.

**Aanvraag-URL**: http:*//&lt;aem-guides-server>: &lt;port-number>/bin/dxml/async-export*

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`ditamap`|Tekenreeks|Ja|Absoluut pad van het DITA-kaartbestand in AEM opslagplaats.| |`baseline`|String|Nr|De titel van de basislijn die wordt gebruikt om de versioned inhoud terug te winnen. <br> **Opmerking:** De waarde is hoofdlettergevoelig.| |`flatFS`|Boolean|No|\(Optioneel\) Als deze waarde is ingesteld op true, wordt een platte structuur van bestanden geretourneerd in het ZIP-bestand. Als uw DITA-kaart bijvoorbeeld verwijst naar inhoud in meerdere mappen, worden alle bestanden waarnaar wordt verwezen, in één map geplaatst. Als er bestanden met dezelfde naam zijn, wordt de naam van deze bestanden gewijzigd door een numeriek achtervoegsel toe te voegen. Alle verwijzingen \(in kaart DITA en onderwerpen \) worden automatisch behandeld, aangezien zij gebaseerd op de nieuwe plaats van dossiers in de vlakke omslagstructuur worden bijgewerkt. Als de waarde false is, blijft de mapstructuur ongewijzigd in het ZIP-bestand. Als de DITA-kaart verwijst naar bestanden van meerdere locaties, worden al deze locaties ook gemaakt in het ZIP-bestand. Wanneer u het ZIP-bestand herstelt, wordt de exacte mapstructuur gemaakt op de doellocatie. <br> De standaardwaarde voor deze parameter is false.|

**Responswaarden**: |Element|Beschrijving| |—|—| |`status`|De status van de geretourneerde waarde van de uitgevoerde bewerking. De mogelijke opties zijn: GESTART, MISLUKT, INPROGRESS, SUCCEED, ONTBREEKT, VERWIJDERD| |`jobId`|De unieke id van de taak. Kan later worden gebruikt om te zoeken naar de status.| |errorMessage|The error message of the job in case of a failure \(if the status is FAILED, MISSING or DELETED\).| |`filePath`|Het bestandspad van het ZIP-bestand. Het is alleen aanwezig als de taak is voltooid en de status SUCCEED is. Hiermee kunt u het ZIP-bestand downloaden.|

## DITA-toewijzingsstatus voor query exporteren

Een methode van de GET die de status van uitvoer voor een kaart DITA met al zijn gebiedsdelen terugwint. De instructie kan met een interval worden opgevraagd als de status STARTED of INPROGRESS is totdat deze is voltooid \(geslaagd of met een fout\).

**Aanvraag-URL**: http:*//&lt;aem-guides-server>: &lt;port-number>/bin/dxml/async-export*

**Parameters**
|Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`jobId`|Tekenreeks|Ja|De taak-id die wordt opgehaald wanneer de exporttaak wordt gestart.|

**Responswaarden**: |Element|Beschrijving| |—|—| |`status`|De status van de exporttaak. De mogelijke opties zijn: GESTART, MISLUKT, INPROGRESS, SUCCEED, ONTBREEKT, VERWIJDERD| |`jobId`|De unieke id van de taak. Kan later worden gebruikt om te zoeken naar de status.| |`errorMessage`|The error message of the job in case of a failure \(if the status is FAILED, MISSING or DELETED\).| |`filePath`|Het bestandspad van het ZIP-bestand. Het is alleen aanwezig als de taak is voltooid en de status SUCCEED is. Hiermee kunt u het ZIP-bestand downloaden.|

