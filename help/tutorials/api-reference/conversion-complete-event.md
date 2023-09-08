---
title: Omzetproces, gebeurtenishandler
description: Meer informatie over de gebeurtenishandler voor het conversieproces
source-git-commit: 8707acf3ba01b7488eea6597c434da73a901d037
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Omzetproces, gebeurtenishandler {#id175UB30E05Z}

AEM Hulplijnen geven de gebeurtenis com/adobe/fmdita/conversion/complete weer die wordt gebruikt om naverwerkingshandelingen uit te voeren nadat een documentconversieproces is voltooid. Deze gebeurtenis wordt geactiveerd wanneer een niet-DITA-document wordt gemigreerd naar de DITA-bestandsindeling. Als u bijvoorbeeld een Word naar DITA-conversie of een InDesign naar DITA-conversieproces uitvoert, wordt deze gebeurtenis aangeroepen nadat het conversieproces is beëindigd.

U moet een AEM gebeurtenishandler maken om de eigenschappen te lezen die beschikbaar zijn in deze gebeurtenis en verdere verwerking uit te voeren.

De gebeurtenisdetails worden hieronder uitgelegd:

**Gebeurtenisnaam**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parameters**:\
|Naam|Type|Omschrijving| |—|—|—| |`status`|String|De geretourneerde status van de uitgevoerde bewerking. De mogelijke opties zijn: - SUCCESS: het conversieproces is voltooid. <br> - VOLTOOID MET FOUTEN: het conversieproces is voltooid, maar met enkele fouten. <br>- MISLUKT: het conversieproces is mislukt door een fatale fout.| |`filePath`|Tekenreeks|Absoluut pad van het bronbestand \(om te converteren\) in AEM opslagplaats.| |`outputPath`|String|Absoluut pad van de doellocatie waar de geconverteerde DITA-bestanden worden opgeslagen.| |`logPath`|String|Absolute weg van de knoop waar het omzettingslogboek zal worden bewaard.|

