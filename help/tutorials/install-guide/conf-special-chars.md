---
title: Toegestane speciale tekens configureren
description: Leer hoe u toegestane speciale tekens kunt configureren
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---


# Toegestane speciale tekens configureren {#id20CIL600035}

Met de webeditor kunt u bepaalde speciale tekens in het vak invoegen. U kunt echter wel de lijst met speciale tekens aanpassen die uw auteurs in hun documenten kunnen invoegen. Als u de lijst met speciale tekens aanpast, wordt de standaardset met speciale tekens overschreven. Alleen de speciale tekens die u in de configuratie toevoegt, worden ter beschikking gesteld van de auteurs.

Voer de volgende stappen uit om de standaardlijst met speciale tekens te overschrijven:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. maken `symbols.json` bestand op de volgende locatie:

   ```json
   /apps/fmdita/xmleditor/
   ```

1. Voeg de speciale tekendefinitie toe in het dialoogvenster `symbols.json` bestand als:

   ```json
   {"symbols": [{"label": "Arrows",
      "items": [
      {   "name": "←",   "title": "Left Arrow"   } 
      ,   
      {   "name": "↑",   "title": "Up Arrow"      } 
      ]   
      }   ]   }
   ```


De structuur van de `symbols.json` Het bestand wordt hieronder uitgelegd:

- `"label": "Arrows"`: Hiermee geeft u de categorie voor de speciale tekens op. In het fragment, een categorie met de naam `"Arrows"` is gedefinieerd.
- `"items"`: Hiermee definieert u de verzameling speciale tekens in de categorie.
- `"name": "←", "title": "Left Arrow"`: Dit is de definitie van het speciale teken. Het begint met de `"name"` -label, dat niet mag worden gewijzigd. De naam wordt gevolgd door het speciale teken. De `"title"` Dit is de naam of titel van het speciale teken dat als knopinfo voor dat speciale teken wordt weergegeven.

   U kunt meerdere definities definiëren voor speciale tekens in een categorie.


**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)

