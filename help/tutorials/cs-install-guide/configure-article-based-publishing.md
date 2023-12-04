---
title: Pakketten installeren voor publiceren op basis van artikel
description: Leer hoe u pakketten installeert voor publicaties op basis van artikelen
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Pakketten installeren voor publiceren op basis van artikel {#id21BNL02052Z}

AEM Gidsen verstrekt een krachtige op artikel-gebaseerde het publiceren eigenschap die met de Redacteur van het Web wordt geïntegreerd. Gebruikend deze eigenschap, kunt u één of meerdere onderwerpen gelijktijdig publiceren. Nadat u een kaart hebt geopend in de Kaarteditor, kunt u naar het tabblad Uitvoer navigeren om een voorinstelling te maken en vervolgens een of meer onderwerpen kiezen om de uitvoer te genereren. U kunt de op artikel-gebaseerde het publiceren eigenschap gebruiken om output van één of meerdere onderwerpen stapsgewijs te produceren of uw inhoud aan een kennisbasisplatform op een artikel-door-artikel wijze te publiceren. Zie voor meer informatie *Op artikel gebaseerde publicaties vanuit de sectie Webeditor* in de gebruikershandleiding.

Voer de volgende stappen uit om een AEM site te maken voor het publiceren van op artikelen gebaseerde uitvoer:

1. Downloaden **XML Documentation Components Content Package voor Cloud Service** van uw [Distributieportaal voor software voor Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Open AEM Package Manager. De standaard-URL voor toegang tot pakketbeheer is: `https://<hostname>/crx/packmgr/index.jsp`
1. Upload XML Documentation Components Content Package voor Cloud Service en installeer deze.
1. Download de `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` bestand van uw [Distributieportaal voor software voor Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).
1. Selecteer in de globale navigatie de optie **Sites**.
1. Klik in de gebruikersinterface Sites op **Maken** in de rechterbovenhoek.
1. Selecteren **Site van sjabloon** van de **Maken** vervolgkeuzelijst.
1. Klik op de knop **Importeren** en selecteert u vervolgens de knop `Knowledge-base-template-for-article-based-publishing-for-cloud-service.zip` gedownload op uw systeem. Als de sitesjabloon eenmaal is geïmporteerd, wordt deze onderaan weergegeven.

   >[!NOTE]
   >
   > U hoeft het ZIP-bestand alleen voor de eerste keer te importeren. Nadat de sitesjabloon is geïmporteerd, is deze beschikbaar in de lijst.

   Selecteren **Kennisbasissjabloon voor op artikelen gebaseerde publicaties** om de AEM site te maken en klik op **Volgende** in de rechterbovenhoek.

1. Voer de **Titel van site** en de **Sitenaam** en klik op **Maken** in de rechterbovenhoek. Er wordt een AEM site gemaakt met de Tragopan-sitesjabloon. \(Tragopan-site is een voorbeeldkennissite AEM sjablonen voor een categorie, sectie en artikelpagina.\)

   >[!NOTE]
   >
   > U kunt meerdere AEM sites maken met dezelfde sjabloon.


U kunt de AEM gebruiken om uw artikel te publiceren gebruikend de output vooraf instelt van de Redacteur van het Web.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
