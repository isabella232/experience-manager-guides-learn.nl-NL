---
title: Weergave van op UUID gebaseerde koppelingen configureren
description: Leer hoe u weergave van UUID-koppelingen kunt configureren
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Weergave van op UUID gebaseerde koppelingen configureren {#id2035G20M0QN}

Wanneer u een koppeling maakt met de optie Referentie invoegen of Inhoud hergebruiken invoegen in de webeditor, wordt de koppeling standaard gemaakt met de UUID van de inhoud waarnaar wordt verwezen. De **Koppeling** eigenschap \(in deelvenster Eigenschappen\) van de inhoud waarnaar wordt verwezen, kan worden geconfigureerd om het relatieve bestandspad van de inhoud waarnaar wordt verwezen of de UUID weer te geven. Dit scherm wordt bestuurd door de **UUID&#39;s inschakelen** in configMgr. De optie is standaard ingeschakeld, wat betekent dat de UUID van de inhoud waarnaar wordt verwezen, wordt weergegeven in het deelvenster Eigenschappen.

Voer de volgende stappen uit om de relatieve weg of UUID van de referenced inhoud in de Redacteur van het Web te tonen:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundel.

1. In de *XmlEditorConfig* instellingen, de **UUID&#39;s inschakelen** is standaard ingeschakeld. Dit betekent dat UUID van de inhoud waarnaar wordt verwezen wordt weergegeven in het dialoogvenster **Koppeling** in het deelvenster Eigenschappen.

   Als u het relatieve pad van de gekoppelde inhoud wilt weergeven, schakelt u de optie **UUID&#39;s inschakelen** -optie.

1. Klikken **Opslaan**.


**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
