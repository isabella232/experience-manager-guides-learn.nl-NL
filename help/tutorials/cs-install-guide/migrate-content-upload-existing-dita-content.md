---
title: Bestaande DITA-inhoud uploaden
description: Leer hoe u bestaande DITA-inhoud kunt uploaden
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 0%

---

# Bestaande DITA-inhoud uploaden {#id176FF000JUI}

U hebt waarschijnlijk een opslagplaats voor bestaande DITA-inhoud die u wilt gebruiken met de AEM. Voor dergelijke bestaande inhoud kunt u de ondersteunde methoden gebruiken die worden beschreven in [Digitale middelen toevoegen aan Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html).

## Patroon UUID-bestandsnaam configureren

Wanneer u inhoud importeert, is het niet nodig dat de bestandsnamen worden gebaseerd op de UUID. In een systeem dat op UUID-Gebaseerde dossiernamen gebruikt, is het verplicht dat alle dossiers worden bedoeld gebruikend hun UUIDs eerder dan hun originele dossiernamen. Als een geïmporteerd bestand geen op UUID gebaseerde bestandsnamen heeft, kunt u het systeem zo configureren dat een UUID wordt toegevoegd aan de eigenschap file. Deze UUID wordt vervolgens gebruikt om te verwijzen naar bestanden waarin UUID niet wordt gebruikt voor het benoemen van de bestanden.

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\) gegevens op om het patroon van de UUID-bestandsnaam te configureren:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `uuid.regex` | String specifying the regex for UID filename pattern. <br> Als een bestand het opgegeven patroon niet volgt, wordt een UUID toegevoegd aan de eigenschap van het bestand en worden alle verwijzingen naar het bestand bijgewerkt met de UUID die aan het bestand is toegewezen. <br> **Standaardwaarde**: `"^GUID-(?<id>.*)"` |

## Krullopdrachten gebruiken

U kunt ook curl-opdrachten gebruiken om een map in DAM te maken, bestanden te uploaden en metagegevens toe te voegen aan de geüploade inhoud.

**Een map maken**

Voer de volgende opdracht uit om een map in AEM opslagplaats te maken:

```
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Geef de volgende parameters op om een map te maken:

- `<username>:<passowrd>`: Geef de gebruikersnaam en het wachtwoord op voor toegang tot de AEM. Deze gebruiker moet over de rechten voor het maken van mappen beschikken.

- `jcr:primaryType=sling:Folder`: Geef deze parameter op *ongewijzigd* om een bron van het omslagtype te creëren.

- `<server folder path>`: Volledig mappad inclusief de naam van de nieuwe map die u wilt maken in de AEM. Als u bijvoorbeeld het pad opgeeft als `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`en vervolgens de map `AEM-Guides` wordt gemaakt in het dialoogvenster `projects` map in DAM.


**Een bestand uploaden**

Voer de volgende opdracht uit om een bestand te uploaden in de AEM opslagplaats:

```
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Geef de volgende parameters op om een bestand te uploaden:

- `<username>:<passowrd>`: Geef de gebruikersnaam en het wachtwoord op voor toegang tot de AEM. Deze gebruiker moet schrijfrechten hebben op de `server folder path`.

- ``local file path``: Voltooi het bestandspad op uw lokale systeem dat u wilt uploaden.

- `<server folder path>`: Volledig mappad op de AEM server waar u het bestand wilt uploaden.


**Metagegevens toevoegen**

Voer de volgende opdracht uit om metagegevens toe te voegen aan een bestand:

```
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Geef de volgende parameters op om metagegevensinformatie toe te voegen:

- `<username>:<passowrd>`: Geef de gebruikersnaam en het wachtwoord op voor toegang tot de AEM. Deze gebruiker moet schrijfrechten hebben op de ``metadata node path``.

- ``-F<attribute name>=<value>``: De `<attribute name>` is de naam van het metagegevenskenmerk, zoals `audience` en de `<value>` kan `internal`. U kunt meerdere naam-waardeparen voor kenmerken opgeven, gescheiden door spatie.

- `<metadata node path>`: Volledig mappad inclusief bestandsnaam en het bijbehorende metagegevensknooppunt. Als u bijvoorbeeld het pad opgeeft als `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, wordt de opgegeven metagegevens ingesteld op `intro.xml` bestand.


**Bovenliggend onderwerp:**[ Bestaande inhoud migreren](migrate-content.md)
