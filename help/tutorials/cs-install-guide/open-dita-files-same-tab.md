---
title: DITA-onderwerp of toewijzingsbestanden openen op hetzelfde tabblad
description: Leer hoe u DITA-onderwerp of toewijzingsbestanden op hetzelfde tabblad opent
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 0%

---


# DITA-onderwerp of toewijzingsbestanden openen op hetzelfde tabblad {#id223HH0301J3}

In sommige werkschema&#39;s, wanneer u op een verbinding van een onderwerp of een kaartdossier klikt, opent het in een nieuw lusje. Dit kan tot vele lusjes leiden die in uw browser worden geopend, die uw productiviteit kunnen beïnvloeden. U kunt dit gedrag wijzigen door een onderwerp- of kaartbestand op een nieuw tabblad te openen en dit op het huidige tabblad zelf te forceren.

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. In het configuratiedossier, verstrek de volgende \(bezit \) details om een onderwerp of kaartdossier in een nieuw lusje te openen:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinsametab` | Booleaanse waarde \(true/false\). <br> **Standaardwaarde**: `false` |

Deze instelling is van invloed op de volgende plaatsen waar u toegang kunt krijgen tot het onderwerp- of kaartbestand:

- Maak DITA-onderwerp \(aan het einde van de workflow, wanneer u op de knop **Onderwerp openen** knop\)

- DITA-kaart maken \(aan het einde van de workflow, wanneer u op de knop **Kaart openen** knop\)

- Het lusje van onderwerpen in de DITA kaartconsole

- Het lusje van basislijnen in de DITA kaartconsole

- Het lusje van rapporten in de DITA kaartconsole


**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)

