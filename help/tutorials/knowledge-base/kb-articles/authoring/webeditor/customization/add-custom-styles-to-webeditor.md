---
title: Aangepaste stijlen toevoegen aan webeditor van hulplijnen
description: Leer hoe u aangepaste stijlen toevoegt om de vormgeving van de gulden-webeditor te wijzigen.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Aangepaste stijlen toevoegen aan webeditor van hulplijnen

In dit artikel leert u hoe u aangepaste stijlen kunt toevoegen om de standaardweergave en het standaarduiterlijk van de spaander te wijzigen.

Dit omvat de volgende stappen:
- Aangepaste stijlen toevoegen via Configuratie XML-editor voor mapprofiel
- Het respectievelijke mapprofiel kiezen in de webbrowser en de wijzigingen testen


## Implementeren door een voorbeeld te nemen

Laten we dit begrijpen met een voorbeeld waarin we de korte beschrijving en titel als een apart blok willen weergeven met bepaalde stijlaspecten in de redactie.

![Een voorvertoning van de sprite weergeven met aangepaste stijlen](../../../assets/authoring/webeditor-customstyles-preview.png)


## Dit implementeren


### De aangepaste CSS toevoegen aan het mappenprofiel

Gebruik de mapprofielen om de *css_layout.css* onder het tabblad &quot;XML Editor Configuration&quot; en voegt u de CSS met aangepaste stijlen toe

[Gebruik deze koppeling voor meer informatie over het mapprofiel en het configureren van de CSS-sjabloonlay-out](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

Gebruik het volgende om bovenstaande stijl in uw webeditor in te stellen:
- Gebruiken [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) en uploadt u het naar het gewenste mapprofiel
- Het bijgevoegde pakket installeren [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) het gebruiken van AEM pakketmanager om de middelen te installeren die in het bovengenoemde CSS dossier worden gebruikt

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Testen

- Webeditor openen
- Kies in de gebruikersvoorkeuren het mapprofiel waaraan u de aangepaste stijlen hebt toegevoegd. Als u het aan het Globale Profiel hebt toegevoegd, dan gebruikt u waarschijnlijk reeds dat.
- Open een onderwerp, zult u merken dat het het uitgeven gebied aangepaste UI zou moeten hebben

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## Verwijzingen

U kunt ook geïnteresseerd zijn in de sessie met experts over webeditor-configuraties en aanpassingen die in [Expertsessie voor spetters](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=en)
