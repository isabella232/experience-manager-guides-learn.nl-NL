---
title: Verwijderen AEM hulplijnen
description: Leer hoe u AEM hulplijnen kunt verwijderen
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Verwijderen AEM hulplijnen {#id21BHG0C0SXA}

U kunt AEM hulplijnen verwijderen met behulp van CRX Package Manager. Tijdens het verwijderen wordt de inhoud van de opslagplaats teruggezet naar de momentopname die vlak voor de installatie van het pakket is gemaakt.

Voer de volgende stappen uit om AEM hulplijnen te verwijderen:

1. Meld u aan bij de AEM en navigeer naar de CRX Package Manager. De standaard-URL voor toegang tot pakketbeheer is:

   ```http
   http://<server name>:<port>/crx/packmgr/index.jsp
   ```

1. Zoek naar het pakket com.adobe.fmdita.
1. Klik op het pakket om het uit te vouwen.
1. Klikken **Meer** om de vervolgkeuzelijst te openen.
1. Klikken **Verwijderen** en wacht tot het verwijderen is voltooid.
1. Als u dit pakket niet meer nodig hebt, klikt u op **Verwijderen** na het verwijderen van het pakket.

## Na verwijderen

Voer de volgende stappen uit om de resterende bestanden op te schonen nadat u deze hebt verwijderd:

1. Maak de scriptcache leeg met:

   ```http
   http://<host>:<port>/system/console/scriptcache
   ```

1. U kunt de cache ongeldig maken met:

   ```http
   http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
   ```

1. Klikken **Cache ongeldig maken**.
1. Maak de cache van de browser leeg.

**Bovenliggend onderwerp:**[ Downloaden en installeren](download-install.md)
