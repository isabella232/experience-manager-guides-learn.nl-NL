---
title: '@navtitle-kenmerk standaard opnemen'
description: Leer hoe u standaard @navtitle-kenmerk kunt opnemen
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# @navtitle-kenmerk standaard opnemen {#id2115BC0J0XA}

U kunt verschillende soorten verwijzingsdossiers in een kaart toevoegen, bijvoorbeeld onderwerp, verwijzing, taak, \(sub\) kaarten, etc. De meeste van deze bestanden ondersteunen de `@navtitle` kenmerk. Niet veel auteurs gebruiken het echter consistent. Als u het gebruik van de `@navtitle` in alle bestanden waarnaar wordt verwezen in een kaart, kunt u dit doen met een eenvoudige configuratie.

Als deze optie is ingeschakeld, krijgt elk referentiebestand dat u in een kaart toevoegt automatisch de opdracht `@navtitle` aan de eigenschappen ervan toegevoegd. De `@navtitle` krijgt ook de waarde van `title` element of the referenced content.

Opnemen `@navtitle` Voer standaard de volgende stappen uit in de eigenschappen van referentiebestanden:

1. Download het bestand ui\_config.json.

   U kunt deze wijziging doorvoeren op algemeen niveau of op een mapniveau. Afhankelijk van waar u deze wijziging wilt aanbrengen, moet u het respectievelijke bestand ui\_config.json downloaden. Voor meer informatie over het downloaden van het bestand ui\_config.json raadpleegt u [De XML-webeditor configureren en aanpassen](conf-folder-level.md#id2065G300O5Z).

1. Zoeken naar `ditaAttributes` definitie.

   De standaarddefinitie van `ditaAttributes` is:

   ```json
   "ditaAttributes": {
   "attributes": [],
   "constraint": false,
   "required": {}
   },
   ```

1. Wijzig de `required` parameter as:

   ```json
   "required": {"navtitle": true}
   ```

1. Sla het bestand op.

1. Upload het bestand in het bijbehorende profiel \(Algemeen of Map\).


Met deze configuratie bevat elk referentiebestand dat u toevoegt aan een kaart de `@navtitle` standaard is ingesteld.
