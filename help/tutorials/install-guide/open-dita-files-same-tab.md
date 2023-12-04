---
title: DITA-onderwerp of toewijzingsbestanden openen op hetzelfde tabblad
description: Leer hoe u DITA-onderwerp of toewijzingsbestanden op hetzelfde tabblad opent
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# DITA-onderwerp of toewijzingsbestanden openen op hetzelfde tabblad {#id223HI0P202H}

In sommige werkschema&#39;s, wanneer u op een verbinding van een onderwerp of een kaartdossier klikt, opent het in een nieuw lusje. Dit kan tot vele lusjes leiden die in uw browser worden geopend, die uw productiviteit kunnen beïnvloeden. U kunt dit gedrag wijzigen door een onderwerp- of kaartbestand op een nieuw tabblad te openen en dit op het huidige tabblad zelf te forceren. Hiervoor voert u de volgende configuratiewijzigingen uit:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundel.

1. Selecteer de **Open DITA Onderwerp/Kaart op Zelfde Lusje** -optie.

1. Klikken **Opslaan**.


Deze instelling is van invloed op de volgende plaatsen waar u toegang kunt krijgen tot het onderwerp- of kaartbestand:

- Maak DITA-onderwerp \(aan het einde van de workflow, wanneer u op de knop **Onderwerp openen** knop\)

- DITA-kaart maken \(aan het einde van de workflow, wanneer u op de knop **Kaart openen** knop\)

- Het lusje van onderwerpen in de DITA kaartconsole

- Het lusje van basislijnen in de DITA kaartconsole

- Het lusje van rapporten in de DITA kaartconsole


**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
