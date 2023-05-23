---
title: Native PDF-publicatiefunctie | Streepjescode toevoegen
description: Leer hoe u streepjescodes kunt toevoegen.
source-git-commit: 6cea7a92eed8f7b1d4a0763baae65ccccd71790e
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Een streepjescode toevoegen aan de PDF-uitvoer

Streepjescodes zijn handig om informatie op te nemen die eenvoudig door machines kan worden verwerkt. Op dezelfde manier worden QR-codes gebruikt voor de koppelingen die lezers met hun mobiele apparaten kunnen openen.

Deze zelfstudie helpt u streepjescodes toe te voegen vóór elke pagina in de uitvoer van de PDF.

## Stappen om een streepjescode te genereren

Voer de volgende stappen uit om een streepjescode te genereren:

### Voeg een middelidentiteitskaart aan de kaart DITA toe

Voeg een element van middelidentiteitskaart aan de kaart DITA toe. De bron-id fungeert als de belangrijkste invoer voor het genereren van de streepjescode.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<map id="GUID-3c330691-4dac-4020-904a-d2d6246aeeb1-en">
  <title>Barcode Sample</title>
  <topicmeta>
    <resourceid id="7a5bda1c-b1db-4fd8-8763-a731e2e8abba">
    </resourceid>
  </topicmeta>
  <topicref href="GUID-139f6c64-bea3-4f17-8b22-ee131557e249-en.dita" type="topic">
  </topicref>
</map>  
```

U kunt de bron-id ook bewerken in de ontwerpmodus.

<img src="./assets/barcode-map.png" alt="Voorbeeld van uitvoer met streepjescode" width="700">


### Een tijdelijke aanduiding voor streepjescodes toevoegen aan de sjabloonkoptekst

De `Common.plt` in het **Basis** sjabloon om een streepjescode toe te voegen na de projecttitel.

```html
...
  <div data-region="header">
    <p class="chapter-header"><span data-field="project-title" data-format="default">Project Title</span> </p>
    <p><span class="barcode" data-field="metadata" data-format="default" data-subtype="//resourceid/@id">Resource ID (barcode)</span></p>
  </div>
} 
...
```


### De CSS van de sjabloon bijwerken om een streepjescodewaarde te renderen

De `content.css` bestand om een streepjescode te renderen tijdens het genereren van de PDF. Verschillende typen streepjescodes, zoals &#39;qrcode&#39; en &#39;pdf417&#39;, worden ondersteund.  Zie voor meer informatie [Typen streepjescodes](#barcode-types).



```css
...
.barcode {
  -ro-replacedelement: barcode;
  -ro-barcode-type: code128;
}
...
```

Nadat u de vorige stappen hebt uitgevoerd, kunt u de PDF-uitvoer genereren met een streepjescode.

In de volgende schermafbeelding wordt een voorbeeldstreepjescode weergegeven in een PDF-uitvoer.

<img src="./assets/barcode-output-sample.png" alt="Voorbeeld van uitvoer met streepjescode" width="700">


## Typen streepjescodes {#barcode-types}

| Type | CSS-kenmerk | Extra kenmerken |
| ------------------------------- | ----------------------- | -------------------------- |
| QR-code | qrcode |  |
| PDF417 | pdf417 |  |
| DataMatrix | data-matrix |  |
| Aztec-code | aztec-code |  |
| Rastermatrix | raster-matrix |  |
| Maxicode | maxicodemodus-4 |  |
| Micro QR | microqr |  |
| Code One | code-on |  |
| Codablock F | codablockf |  |
| GS1 Databar Limited | beperkt tot databases |  |
| GS1-database Omnidirectioneel | Omnidirectioneel gegevensbestand |  |
| EAN-13 | ean-13 |  |
| GS1-128 (EAN-128) | code128 | -ro-streepjescode-codering: g1; |
| ITF-14 | itf14 |  |
| UPC-A | upc-a |  |
| Code 128 | code128 |  |
| Interleaved 2 of 5 | code2of5 interleaved |  |
| POSTNET | postnet |  |
| Nederlandse postcode | kixcode |  |
| Korea Post | korea-post |  |
| Deutsche Post Leitcode | dp-leitcode |  |
| Australia Post | auspost |  |
| Logmars | logmars |  |
| Farmacode | farmacode |  |
| USPS OneCode (Intelligent Mail) | usps-onecode |  |


