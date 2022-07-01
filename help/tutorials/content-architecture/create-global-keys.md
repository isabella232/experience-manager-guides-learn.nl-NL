---
title: Algemene toetsen maken
description: Hoe te om globale sleutels tot stand te brengen die over organisatie inhoud moeten worden gebruikt
role: Admin
exl-id: b8e3a6d2-ea82-4fdb-bd16-3f4b6594af52
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Algemene toetsen maken

Organisaties dienen toetsen te gebruiken in gevallen waarin ze herbruikbare en gangbare tekst hebben, zoals productnaam of producttoonhoogte, die op veel plaatsen wordt gebruikt maar waarvan het risico groot is dat deze wordt gewijzigd. Met de toetsen voor herbruikbare tekst kunt u een update op meerdere plaatsen uitvoeren door de wijziging op één locatie aan te brengen, bijvoorbeeld in de sleutelwaarde.

## Stap 1: Een algemene kaart maken om uw sleutels op te slaan

Een kaart maken en de [!UICONTROL keyref] -element.

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_ffbdbf06-8658-4311-ad84-1c631bba904f">
  <title>global-keys-map</title>
  <keydefkeys="adobe">
    <topicmeta>
      <linktext>Adobe Systems</linktext>
    </topicmeta>
  </keydef>
  <keydefkeys="AEM">
    <topicmeta>
      <linktext>Adobe Experience Manager</linktext>
    </topicmeta>
  </keydef>
</map>
```

Hier hebt u twee definities gedefinieerd, zoals hierboven is weergegeven, op basis van een [!UICONTROL keyref] als _AEM_ voor de _Adobe Experience Manager_ tekst.

## Stap 2: Deze kaart toevoegen aan uw publicatieoverzicht

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_cbf4a96d-e382-4e8c-8830-bcc093fe6638">
  <title>sample-map</title>
  <topicrefhref="sample-topic-using-the-keys.dita"type="topic">
  </topicref>
  <maprefformat="ditamap"href="global-keys-map.ditamap"type="map">
  </mapref>
</map>
```

## Stap 3: Gebruik de toetsen om te verwijzen naar de variabelen die zijn gedefinieerd in de algemene hoofdmap

+ Bewerk het onderwerp en voeg de hoofdwaarde toe met de opdracht [!UICONTROL keyref].
+ Zoals getoond in het schermafbeelding, zal een klein venster verschijnen van waar de sleutelwoorden kunnen worden gekozen. Dit wordt weergegeven wanneer u het element &quot;trefwoord&quot; toevoegt.
   ![Element invoegen](assets/insert_element.png)
   ![Sleutelverwijzing](assets/key_ref.png)

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "technicalContent/dtd/topic.dtd">
<topicid="topic.dita_31b00e61-04b5-4193-af7a-68503e88b087">
  <title>sample-topic-using-the-keys</title>
  <shortdesc></shortdesc>
  <body>
    <p>This is a sample topic using the keys defined in the global map</p>
    <p>here i am using the key definition for AEM :<keywordkeyref="AEM"></keyword></p>
  </body>
</topic>
```
