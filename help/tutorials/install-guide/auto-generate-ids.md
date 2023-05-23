---
title: Element-id's automatisch genereren
description: Leer hoe u elementen-id's automatisch kunt genereren
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# Element-id&#39;s automatisch genereren {#id20CIL40016I}

AEM hulplijnen genereren een document-id voor elk nieuw document dat u maakt. Wanneer u bijvoorbeeld een DITA-kaart maakt, een id zoals `map.ditamap_random_digits` wordt toegewezen aan de kaart-id. U kunt ook elementen definiëren waarop automatisch een id wordt gegenereerd en toegewezen.

AEM de Gidsen verstrekt gemakkelijke configuratiemontages waar u de elementen moet bepalen waarop een identiteitskaart auto-geproduceerd en een patroon voor identiteitskaart is. Bepaalde elementen, zoals `section`, `table`, `ul`, `ol`, worden geconfigureerd voor automatische generatie van id. U kunt andere elementen aan deze lijst toevoegen zodat wanneer deze elementen in een document worden opgenomen, AEM de Gidsen produceert en een identiteitskaart toewijst die op het bepaalde patroon wordt gebaseerd

Voer de volgende stappen uit om elementen te configureren voor automatisch gegenereerde id:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundel.

1. In de *XmlEditorConfig* instellingen, geeft u een of meer elementen op in de **Automatisch id&#39;s genereren voor elementlabels** veld.

   >[!NOTE]
   >
   > Elementlabels zijn DITA-elementnamen zoals `body`, `title`, `codeblock`, enzovoort. Als u meerdere elementen wilt opgeven, scheidt u de elementnamen met een komma.

1. In de **Patroon voor genereren van id&#39;s** een patroon opgeven om een id te genereren.

   De standaardwaarde voor dit veld is ingesteld op `${elementName}_${id}`. De `${elementName}` wordt vervangen door de naam van het element. De `${id}` de variabele produceert opeenvolgend aantal voor het element. Als u bijvoorbeeld het alinea-element toewijst voor automatisch gegenereerde id&#39;s, krijgt de eerste alinea van het onderwerp of document een id zoals p\_1, de volgende alinea krijgt p\_2 enzovoort. In een ander document wordt het genereren van de id echter opnieuw gestart. Dit betekent dat id&#39;s zoals p\_1 en p\_2 in een ander document kunnen worden toegewezen aan alinea-elementen.

   Als uw document al id&#39;s bevat in het opgegeven patroon, worden deze id&#39;s door het proces voor automatisch genereren niet aan nieuwe elementen toegewezen.

1. Klikken **Opslaan**.


**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)

