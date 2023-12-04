---
title: Vraag configureren om bij het sluiten als een nieuwe versie op te slaan
description: Leer hoe te Vorm herinnering om als nieuwe versie bij dicht te bewaren
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Vraag configureren om bij het sluiten als een nieuwe versie op te slaan {#id222HBI00XXA}

Wanneer de gebruiker een dossier probeert te sluiten dat in de Redacteur van het Web gebruikend **Sluiten** op het tabblad van het bestand of op de knop **Sluiten** in het menu Opties wordt een dialoogvenster weergegeven als het bestand niet-opgeslagen gegevens of een niet-opgeslagen versie heeft. De gebruiker wordt gevraagd het bestand op te slaan als een nieuwe versie als de versie niet is opgeslagen.

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\)-details op om een vraag te configureren om bij het sluiten als een nieuwe versie op te slaan:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.savenewversion` | Boolean \( true/ false\). <br>  **Standaardwaarde**: true |

Wanneer deze configuratie wordt toegelaten, **Opslaan als nieuwe versie** Selectievakje is standaard geselecteerd in het dialoogvenster.

Zie voor meer informatie *Bestanden sluiten en scenario&#39;s opslaan* in de as a Cloud Service handleiding Adobe Experience Manager-hulplijnen gebruiken.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
