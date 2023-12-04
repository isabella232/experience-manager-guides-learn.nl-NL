---
title: Automatische bestandsnamen configureren op basis van UUID
description: Leer hoe u automatische bestandsnamen kunt configureren op basis van UUID
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 0%

---

# Automatische bestandsnamen configureren op basis van UUID {#id205QG070D5Z}

Wanneer een onderwerp- of kaartbestand wordt gemaakt, krijgen auteurs standaard de mogelijkheid om ook de bestandsnaam op te geven. Auteurs kunnen de bestandsnamen naar wens toewijzen. Dit kan echter leiden tot inconsistentie en een groot aantal bestanden kan in een groot documentatiesysteem worden weergegeven. Als beheerder kunt u de auteurs beperken in het toewijzen van bestandsnamen voor de bestanden die ze in uw systeem maken. Voor elk nieuw onderwerp of kaartdossier, kunt u verkiezen om op UUID-Gebaseerde dossiernamen automatisch toe te wijzen.

Voer de volgende stappen uit om automatisch de op UUID gebaseerde bestandsnaam toe te wijzen voor alle nieuwe bestanden die in het systeem zijn gemaakt:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* bundel.

1. Selecteer de **Systeembestandsnamen op basis van UUID gebruiken** -optie.

1. Klikken **Opslaan**.


>[!NOTE]
>
> Deze optie is standaard uitgeschakeld. Als deze optie is ingeschakeld, zien auteurs niet de optie om de bestandsnaam op te geven tijdens het maken van een nieuw onderwerp- of kaartbestand. Een nieuw onderwerp of kaartdossier kan van de Activa UI en de Redacteur van het Web worden gecreeerd.

**Bovenliggend onderwerp:**[ Bestandsnamen configureren](conf-file-names.md)
