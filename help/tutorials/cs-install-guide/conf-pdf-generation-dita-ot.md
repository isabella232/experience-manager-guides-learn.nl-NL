---
title: Eén onderwerp PDF genereren
description: Leer hoe te om enige onderwerpgeneratie te vormen PDF
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Eén onderwerp PDF genereren {#id22ADC70M0XA}

Met de AEMGidsen, kunt u de PDF van individuele onderwerpen of een volledig kaartdossier produceren. U kunt uw onderwerpen in een formaat van PDF publiceren gebruikend inheemse PDF of methode DITA-OT. Gebruik de native PDF-methode om een PDF-uitvoer met veel functies te genereren op basis van W3C CSS3 en CSS-normen voor gepagineerde media. U kunt de methode DITA-OT gebruiken om een output van PDF voor een kaart van het kaartdashboard te produceren.

>[!NOTE]
>
> Native PDF is de standaardmethode voor het genereren van een PDF in de huidige versie van AEM hulplijnen.

Om de oude generatie van PDF via DITA-OT van de wijze van de onderwerpvoorproef toe te laten, voer de volgende stappen uit:

1. Meld u aan bij Adobe Experience Manager als beheerder en download het configuratiebestand voor de gebruikersinterface.

1. Klik hiertoe bovenaan op de Adobe Experience Manager-koppeling en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen en klik op de knop **Mapprofielen**.
1. Klik op de knop **Globaal profiel** tegel.
1. Selecteer de **XML Editor-configuratie** en klik op **Bewerken** pictogram bovenaan
1. Klik op de knop **Downloaden** pictogram om het bestand ui\_config.json op uw lokale systeem te downloaden. Vervolgens kunt u wijzigingen in het bestand aanbrengen en het bestand vervolgens uploaden.
1. In de `ui_config.json` bestand, zoek de volgende configuratie:

   ```
   {
                           "component": "button",
                           "variant": "action",
                           "quiet": true,
                           "icon": "filePDF",
                           "title": "Download as PDF",
                           "on-click": "EDITOR_SAVE_AS_PDF"
                           }
   ```

   en vervangen door

   ```
   {
                           "component": "button",
                           "icon": "filePDF",
                           "variant": "action",
                           "quiet": true, "title": "Export as PDF",
                           "on-click": "DOWNLOAD_TOPIC_PDF",
                           "show" : ["@isPreviewMode", "@isXmlMode"]
                           }
   ```

1. Sla het bestand op en upload het.

Na het uitvoeren van de bovengenoemde stappen, als u het zelfde omslagprofiel van de Voorkeur van de Gebruiker in de Redacteur van het Web kiest, zult u dan de optie voor de generatie van PDF op de voorproefwijze van een onderwerp zien.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
