---
title: REST API's voor conversieworkflow
description: Meer informatie over de REST API's voor de conversieworkflow
source-git-commit: 8707acf3ba01b7488eea6597c434da73a901d037
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 0%

---


# REST API&#39;s voor conversieworkflow {#id175UB30E05Z}

Met de volgende REST API&#39;s kunt u Word-, HTML- en InDesign-documenten converteren naar DITA-indeling.

## Word-documenten converteren

A GET method that converts Word documents into DITA format.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |``operation``|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is ``word2dita``. <br> **Opmerking:** De waarde is niet hoofdlettergevoelig. | |`inputFile`|Tekenreeks|Ja|Absoluut pad van de Word-bronbestanden in AEM opslagplaats.| |`destPath`|Tekenreeks|Ja|Absoluut pad van de doellocatie waar de geconverteerde DITA-bestanden worden opgeslagen.| |`createRev`|Boolean|Ja|Opgeven of een revisie van de bestanden wordt gemaakt \( `true`\) op het opgegeven doel of niet \( `false`\). Dit wordt alleen overwogen wanneer de doellocatie een bestaande versie van de omgezette bestanden bevat.| |`style2tagMap`|Tekenreeks|Ja|Absoluut pad van het stijltoewijzingsbestand dat wordt gebruikt voor conversie.|

**Responswaarden**: Retourneert een HTTP 200 \(Successful\) reactie.

## HTML-documenten converteren

A GET method that converts HTML documents into DITA format.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is ``html2dita``. <br> **Opmerking:** De waarde is niet hoofdlettergevoelig.| |`inputFile`|Tekenreeks|Ja|Absoluut pad van de HTML-bronbestanden in AEM opslagplaats.| |`destPath`|Tekenreeks|Ja|Absoluut pad van de doellocatie waar de geconverteerde DITA-bestanden worden opgeslagen.| |`createRev`|Boolean|Ja|Opgeven of een revisie van de bestanden wordt gemaakt \( `true`\) op het opgegeven doel of niet \( `false`\). Dit wordt alleen overwogen wanneer de doellocatie een bestaande versie van de omgezette bestanden bevat.|

**Responswaarden**: Retourneert een HTTP 200 \(Successful\) reactie.

## InDesign-documenten converteren

A GET method that converts InDesign documents into DITA format.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/conversion

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |``operation``|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is ``idml2dita``. <br> **Opmerking:** De waarde is niet hoofdlettergevoelig.| |`inputFile`|Tekenreeks|Ja|Absoluut pad van de bronbestanden van het InDesign in AEM opslagplaats.| |`destPath`|Tekenreeks|Ja|Absoluut pad van de doellocatie waar de geconverteerde DITA-bestanden worden opgeslagen.| |`createRev`|Boolean|Ja|Opgeven of een revisie van de bestanden wordt gemaakt \( `true`\) op het opgegeven doel of niet \( `false`\). Dit wordt alleen overwogen wanneer de doellocatie een bestaande versie van de omgezette bestanden bevat.|

**Responswaarden**: Retourneert een HTTP 200 \(Successful\) reactie.

