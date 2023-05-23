---
title: XML-editors die zijn gebaseerd op een desktopcomputer integreren
description: Leer hoe u op bureaublad gebaseerde XML-editors kunt integreren
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---


# XML-editors die zijn gebaseerd op een desktopcomputer integreren {#id181GB01G0HS}

Er zijn veel XML-editors beschikbaar op de markt en u kunt er al een gebruiken. Adobe FrameMaker is een van de krachtigste XML-editors en wordt geleverd met AEM connector. Gebruikend de AEM schakelaar in FrameMaker, kunt u met de AEM bewaarplaats, controle en controle dossiers gemakkelijk verbinden, en dossiers direct in FrameMaker uitgeven. U kunt AEM Gidsen ook vormen om FrameMaker van de Redacteur van het Web te lanceren. Zodra u het dossier hebt dat in FrameMaker wordt geopend, kunt u het dossier in de AEM bewaarplaats uitgeven en controleren.

## Laat dossier het uitgeven in FrameMaker van de Redacteur van het Web toe

U kunt FrameMaker of een andere redacteur gebruiken DITA om inhoud tot stand te brengen en bij te werken DITA. Nochtans, als uw organisatie FrameMaker als redacteur DITA gebruikt, dan kunt u uw gebruikers een optie geven om documenten DITA direct in FrameMaker van AEM te openen.

Uw gebruikers zien standaard de **Openen in FrameMaker** op de AEM werkbalk. Voer de volgende stappen uit om deze knop toe te voegen aan de werkbalk AEM:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundel.

   ![](assets/open-in-fm-toolbar.png){width="550" align="left"}

1. Selecteer **Toon Open in Knoop FrameMaker** optie.

1. Klikken **Opslaan**.


Wanneer u de optie **Toon Open in Knoop FrameMaker** en vervolgens de **Openen in FrameMaker** wordt weergegeven bij het selecteren van een DITA-bestand in de AEM opslagplaats. Wanneer deze optie *niet ingeschakeld* de **Openen in FrameMaker** wordt alleen weergegeven wanneer u een .fm- of een .book-bestand selecteert in de opslagplaats.

