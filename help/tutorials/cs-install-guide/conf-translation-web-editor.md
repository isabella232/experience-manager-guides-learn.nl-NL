---
title: Vertaal in de Redacteur van het Web vormen
description: Leer hoe te om de eigenschap van de Vertaling in de Redacteur van het Web te vormen
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Vertaal in de Redacteur van het Web vormen {#id21BONI0J0YR}

De redacteur van het Web verstrekt een krachtige vertaaleigenschap om uw inhoud in veelvoudige talen te vertalen.

U kunt de **Beheren** in de webeditor om uw inhoud te vertalen. Dit tabblad is standaard beschikbaar.

Als u de opdracht **Beheren** in de Redacteur van het Web, voer de volgende stappen uit:

1. Aanmelden **Adobe Experience Manager** als beheerder.
1. Klik op de knop **Adobe Experience Manager** koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen en klik op de knop **Mapprofielen**.
1. Klik op de knop **Globaal profiel** tegel.
1. Klikken op **XML Editor-configuratie**.
1. Klikken op **Bewerken** bovenaan.
1. Download de `ui\_config.json` bestand.Verwijder het volgende codefragment uit het gedownloade bestand:

   ```json
   {
       "component":"tab",
       "id":"workflow",
       "title":"Manage",
       "on-click":"APP_MODE_CHANGE",
       "items":
       [
           {
               "component":"label",
               "label":"Manage"
           }
       ]
   },
   ```

1. Upload het bijgewerkte bestand ui\_config.json.

Let erop dat de **Beheren** is niet meer beschikbaar.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
