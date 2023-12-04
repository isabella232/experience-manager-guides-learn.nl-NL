---
title: Aanvullende speciale tekens op de werkbalk van de webeditor configureren
description: Leer hoe u extra speciale tekens configureert in de webeditor van AEM hulplijnen.
feature: Web Editor
role: User
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Hoe te om extra speciale karakters in de toolbar van de Redacteur van het Web te vormen

De werkbalk van de webeditor bevat een optie voor sneltoetsen waarmee de auteur de speciale tekens al kan invoegen.
Hetzelfde geldt voor onderstaande screenshot:

![Speciale tekens](assets/special-chars.png)


Deze lijst met tekens kan hier worden geconfigureerd. Voer de volgende stappen uit als u hier meer tekens aan wilt toevoegen:

+ Meld u aan bij AEM en open de modus CRXDE Lite.

+ Maak het bestand symbols.json op de volgende locatie: &#39;/apps/fmdita/xmleditor/&#39; (u kunt de standaardinstelling kopiëren vanuit de locatie &#39;/libs/fmdita/clientlibs/clientlibs/xmleditor/symbols.json&#39;).

+ Voeg de speciale tekendefinitie in het bestand symbols.json toe als:

```
{
      "label": "Logical Symbols",
      "items": [
        {
          "name": "≥",
          "title": "Greater-Than or Equal To"
        },
        {
          "name": "≤",
          "title": "Smaller-Than or Equal To"
        }
      ]
}
```

De structuur van het bestand symbols.json wordt hieronder uitgelegd:

+ &quot;label&quot;: &quot;Logical Symbols&quot;: hiermee wordt de categorie voor de speciale tekens aangegeven. In het fragment wordt een categorie met de naam &quot;Logisch symbool&quot; gedefinieerd.

+ &quot;items&quot;: hiermee wordt de verzameling speciale tekens in de categorie gedefinieerd.

+ &quot;name&quot;: &quot;≥&quot;, &quot;title&quot;: &quot;Groter dan of gelijk aan&quot;: Dit is de definitie van het speciale teken. Het begint met het label &#39;name&#39;, dat niet mag worden gewijzigd. De naam wordt gevolgd door het speciale teken. De titel is de naam of titel van het speciale teken dat als knopinfo voor dat speciale teken wordt weergegeven.

U kunt meerdere definities definiëren voor speciale tekens in een categorie.

Hiermee wordt een andere categorie toegevoegd in het dialoogvenster Speciale tekens:

![Speciale symboolcategorie](assets/special-char-category.png)

![Speciaal teken invoegen](assets/insert-special-char.png)

>[!MORELIKETHIS]
>
>+ [Installatie- en configuratiehandleiding](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)
