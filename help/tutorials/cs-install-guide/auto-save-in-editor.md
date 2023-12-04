---
title: Bestanden automatisch opslaan in de webeditor configureren
description: Leer hoe te om dossier te vormen automatisch sparen in de Redacteur van het Web
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Bestanden automatisch opslaan in de webeditor configureren {#id199CC0J0M5Z}

Een van de meest gebruikte functies in de op een browser gebaseerde editor is de mogelijkheid om gegevens na een bepaalde tijdsperiode op te slaan. De redacteur van het Web van de Gidsen van AEM steunt ook auto-sparen van onderwerp en kaartdossiers bij het gespecificeerde tijdinterval. Wanneer deze eigenschap wordt teweeggebracht, wordt het werkende exemplaar van het onderwerp of de kaart bewaard. Er wordt geen nieuwe versie van het onderwerp of de kaart gemaakt. Als u een nieuwe versie wilt maken, klikt u op het pictogram Revisie opslaan op de werkbalk van de webeditor.

De functie voor automatisch opslaan is niet standaard ingeschakeld en u moet deze functie inschakelen met behulp van het configuratiebestand.

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\) gegevens op om het automatisch opslaan van het bestand en het automatisch opslaan van het tijdinterval te configureren:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autosave` | Boolean \(true/false\).<br> **Standaardwaarde**: false |
| `xmleditor.autosaveinterval` | Geef het tijdsinterval in seconden op om de functie voor automatisch opslaan te activeren. |

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
