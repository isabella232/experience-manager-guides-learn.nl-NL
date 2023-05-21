---
title: Native PDF-publicatiefunctie | JavaScript gebruiken om met inhoud of stijl te werken
description: Leer hoe u gebruiksstijlen maakt en stijlen voor uw inhoud maakt.
exl-id: 2f301f6a-0d1c-4194-84c2-0fddaef8d3ec
source-git-commit: e2349fc14143e5e49f8672ef1bfa48984df3b1c7
workflow-type: tm+mt
source-wordcount: '425'
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
