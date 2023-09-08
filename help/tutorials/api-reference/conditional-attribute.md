---
title: REST API voor werken met voorwaardelijke kenmerken
description: Meer informatie over de REST API om met voorwaardelijke kenmerken te werken
source-git-commit: fad5049962f258bbe59c7d172436d82b3d6cd68f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 0%

---


# REST API voor werken met voorwaardelijke kenmerken {#id175UB30E05Z}

Met de volgende REST API kunt u voorwaardelijke kenmerken toevoegen aan een mappenprofiel.

## Voorwaardelijk kenmerk toevoegen in een profiel op mapniveau

Een methode van de POST die voorwaardelijke attributen aan een bepaald omslag-vlakke profiel toevoegt.

**Aanvraag-URL**:\
http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/folderprofiles

**Parameters**:\
|Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`:operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is ``ADDATTRIBUTEPROFILES``. <br> **Opmerking:** De waarde is niet hoofdlettergevoelig.| |`profilename`|Tekenreeks|Ja|Naam weergeven van het profiel op mapniveau waarin de voorwaardelijke kenmerken moeten worden toegevoegd.| |`conditionalprofiles`|JSON-array|Yes|A JSON-array bestaande uit de voorwaardelijke kenmerknaam en -waarden. Het volgende codefragment van het voorbeeld toont de serie JSON met twee attributen - `platform` en `product` waarbij er meerdere waarden aan zijn toegewezen.|

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
```

**Responswaarden**:\
Retourneert een HTTP 200 \(Successful\) reactie.

