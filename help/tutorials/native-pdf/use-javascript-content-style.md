---
title: Native PDF-publicatiefunctie | JavaScript gebruiken om met inhoud of stijl te werken
description: Leer hoe u gebruiksstijlen maakt en stijlen voor uw inhoud maakt.
exl-id: 2f301f6a-0d1c-4194-84c2-0fddaef8d3ec
source-git-commit: 99ca14a816630f5f0ec1dc72ba77994ffa71dff6
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---

# JavaScript gebruiken om met inhoud of stijl te werken

Met de functie Native PDF Publishing kunt u JavaScript uitvoeren om de inhoud of stijl die op de inhoud is toegepast, te bewerken voordat de uiteindelijke PDF wordt gegenereerd. Met deze functie hebt u volledige controle over de manier waarop de uiteindelijke uitvoer wordt gegenereerd. U kunt bijvoorbeeld informatie over juridische kennisgevingen toevoegen aan de uitvoer van de PDF, die zich in een andere PDF bevindt. Met JavaScript kunt u de informatie over de juridische kennisgeving toevoegen zodra de PDF voor de basisinhoud is gemaakt, maar voordat de laatste PDF wordt gegenereerd.\
De functie Native PDF Publishing biedt u de volgende callback-functies om JavaScript-uitvoering te ondersteunen:

* `window.pdfLayout.onBeforeCreateTOC(callback)`: Deze callback functie wordt uitgevoerd alvorens TOC wordt geproduceerd.
* `window.pdfLayout.onBeforePagination(callback)`: Deze callback-functie wordt uitgevoerd nadat de inhoudsopgave is gegenereerd, maar voordat pagina-einden in de PDF worden toegevoegd.
* `window.pdfLayout.onAfterPagination(callback)`: Deze callback-functie wordt uitgevoerd nadat de inhoudsopgave en de pagina-einden in de PDF zijn toegevoegd.

>[!NOTE]
>
>Intern, wordt een uitvoeringsopeenvolging gehandhaafd voor deze callout functies. Eerst wordt onBeforeCreateTOC uitgevoerd, gevolgd door onBeforePagination, en ten slotte wordt onAfterPagination uitgevoerd.

Op basis van het type inhoud of stijlwijziging dat u wilt uitvoeren, kunt u kiezen welke callback-functie u wilt gebruiken. Als u bijvoorbeeld inhoud wilt toevoegen, is het raadzaam dit te doen voordat de inhoudsopgave wordt gegenereerd. En als u bepaalde stijleffouten wilt maken, kunt u die voor of na de paginering uitvoeren.

In het volgende voorbeeld wordt de positie van de figuurtitels gewijzigd van boven naar onder de afbeeldingen naar onder de afbeeldingen. Hiervoor moet u de optie JavaScript-uitvoering inschakelen in de voorinstelling. Voer hiertoe de volgende stappen uit:

1. Open de voorinstelling voor bewerken.
1. Ga naar de **Geavanceerd** tab.
1. Selecteer **JavaScript inschakelen** optie.
1. Sla de voorinstelling op en sluit deze.

Maak vervolgens een JavaScript-bestand met de volgende code en sla dit op in de map Resources van de sjabloon:

```css
...
/*
* DITA only allows the figure title to be placed above images 
* This JavaScript code is used to move the figure title below the image
* */
window.addEventListener('DOMContentLoaded', function () {
    window.pdfLayout.onBeforeCreateTOC(function() {
        var titleNodes = document.querySelectorAll('.fig > .title')
        for (var i = 0; i < titleNodes.length; i++) {
            var titleNode = titleNodes[i]
            var figNode = titleNode.parentNode
            var imageNode = figNode.querySelector('.image')
            if(imageNode && imageNode.parentNode !== figNode) {
              imageNode = imageNode.parentNode
            }
            if (figNode && imageNode && imageNode.parentNode === figNode) {
                figNode.insertBefore(imageNode, titleNode)
            }
        }
    })
});
...
```

>[!NOTE]
>
>De `window.addEventListener('DOMContentLoaded', function ()` Deze functie moet worden aangeroepen voordat de callback-functies worden gebruikt.

Vervolgens moet dit script worden aangeroepen vanuit een sjabloonbestand dat wordt gebruikt om de PDF-uitvoer te genereren. Voor ons voorbeeld, zullen wij het in het malplaatje van TOC toevoegen. Zorg ervoor dat de `<script>` -tag wordt toegevoegd binnen een vooraf gedefinieerde `<div>` tag in de `<body>` tag. Als u deze in het dialoogvenster `<head>` of buiten de `<body>` -tag, wordt het script niet uitgevoerd.

<img src="./assets/js-added-resources-template.png" width="500">

De uitvoer die met deze code wordt gegenereerd en de sjabloon geeft de figuurtitel onder de afbeelding weer:

<img src="./assets/fig-title-below-image.png" width="500">

## Een watermerk toevoegen aan de PDF-uitvoer voor conceptdocumenten {#watermark-draft-document}

U kunt JavaScript ook gebruiken om voorwaardelijke watermerken toe te voegen. Deze watermerken worden aan het document toegevoegd wanneer aan de gedefinieerde voorwaarde is voldaan.\
U kunt bijvoorbeeld een JavaScript-bestand met de volgende code maken om een watermerk te maken voor de PDF-uitvoer van het document dat nog niet is goedgekeurd. Dit watermerk wordt niet weergegeven als u de PDF voor het document genereert in de documentstatus &quot;Goedgekeurd&quot;.

```css
...
/*
* This file can be used to add a watermark to the PDF output
* */

window.addEventListener('DOMContentLoaded', function () {
    var watermark = 'Draft'
    var metaTag = document.getElementsByTagName('meta')
    css = "@page {\n  @left-middle {\n    content: \"".concat(watermark, "\";\n    z-index: 100;\n    font-family: sans-serif;\n    font-size: 80pt;\n    font-weight: bold;\n    color: gray(0, 0.3);\n    text-align: center;\n    transform: rotate(-54.7deg);\n    position: absolute;\n    left: 0;\n    top: 0;\n    width: 100%;\n    height: 100%;\n  }\n}")
    head = document.head || document.getElementsByTagName('head')[0], style = document.createElement('style');
    style.appendChild(document.createTextNode(css));
    window.pdfLayout.onBeforePagination(function () {
        for (let i = 0; i < metaTag.length; i++) {
            if (metaTag[i].getAttribute('name') === 'docstate' && metaTag[i].getAttribute('value') !== 'Approved') {
                head.appendChild(style);
            }
        }
    })
});
...
```

De uitvoer van de PDF die met deze code wordt gegenereerd, geeft een watermerk weer *Concept* op de omslag van uw document:

<img src="./assets/draft-watermark.png" width="500">
