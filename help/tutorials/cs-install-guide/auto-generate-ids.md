---
title: Element-id's automatisch genereren
description: Leer hoe u elementen-id's automatisch kunt genereren
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---


# Element-id&#39;s automatisch genereren {#id20CIL40016I}

AEM hulplijnen genereren een document-id voor elk nieuw document dat u maakt. Wanneer u bijvoorbeeld een DITA-kaart maakt, een id zoals `map.ditamap_random_digits` wordt toegewezen aan de kaart-id. U kunt ook elementen definiëren waarop automatisch een id wordt gegenereerd en toegewezen.

AEM de Gidsen verstrekt gemakkelijke configuratiemontages waar u de elementen moet bepalen waarop een identiteitskaart auto-geproduceerd en een patroon voor identiteitskaart is. Bepaalde elementen, zoals `section`, `table`, `ul`, `ol`, worden geconfigureerd voor automatische generatie van id. U kunt andere elementen aan deze lijst toevoegen zodat wanneer deze elementen in een document worden opgenomen, AEM de Gidsen produceert en een identiteitskaart toewijst die op het bepaalde patroon wordt gebaseerd

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\)-details op om automatisch gegenereerde element-id&#39;s te configureren:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.classes` | Geef een door komma&#39;s gescheiden lijst met elementen op. <br> **Standaardwaarde**: `"topic, section, table, simpletable, fig, image, ul, ol"` |

Als u een patroon voor automatisch gegenereerde id wilt configureren, maakt u een configuratiebestand met de volgende eigenschappen:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.pattern` | De standaardwaarde voor dit veld is ingesteld op `${elementName}_${id}`. De `${elementName}` wordt vervangen door de naam van het element. De `${id}` de variabele produceert opeenvolgend aantal voor het element. Als u bijvoorbeeld het alinea-element toewijst voor automatisch gegenereerde id&#39;s, krijgt de eerste alinea van het onderwerp of document een id zoals p\_1, de volgende alinea krijgt p\_2 enzovoort. In een ander document wordt het genereren van de id echter opnieuw gestart. Dit betekent dat id&#39;s zoals p\_1 en p\_2 in een ander document kunnen worden toegewezen aan alinea-elementen. **Standaardwaarde**: ``${elementName}_${id}`` |

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)

