---
title: Variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam
description: Leer hoe te variabelen gebruiken voor het plaatsen van de Pad van de Bestemming, de Naam van de Plaats, of de opties van de Naam van het Dossier
source-git-commit: 8b6294425c6e60d1c5b37d98e99114014a104ee6
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam


Tijdens het genereren van uitvoer in AEM Site of PDF kunt u variabelen gebruiken om de opties Doelpad, AEM Sitenaam of Bestandsnaam van PDF te definiëren. U kunt een enkele of een combinatie van variabelen gebruiken om deze opties te definiëren.

In de volgende tabel worden de variabelen weergegeven die uit het vak worden ondersteund:

| Variabele | Definitief doelpad | Voorbeeld |
| --- | --- | --- |
| `${map_filename}` | Gebruikt de naam van de DITA kaartdossiers om de bestemmingspad tot stand te brengen. | **DITA-mapbestandsnaam**:<br>`AEMGuides.ditamap`<br><br>**Doelpad** geconfigureerd als:<br>`/content/output/sites/${map_filename}`<br><br>**Uiteindelijke uitvoerlocatie**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Gebruikt de DITA kaarttitel om de bestemmingsweg tot stand te brengen. | **DITA-mapbestandsnaam**:<br>`AEMGuides.ditamap`<br><br>**Titel DITA-kaart**:<br>`AEMGuides`<br><br>**Doelpad** geconfigureerd als:<br>`/content/output/sites/${map_title}`<br><br>**Uiteindelijke uitvoerlocatie**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Gebruikt de naam van de uitvoervoorinstelling om het doelpad te maken. | **Naam uitvoervoorinstelling**:<br>`AEM Guides PDF Output`<br><br>**DITA-mapbestandsnaam**:<br>`SampleDita.ditamap`<br><br>**Doelpad** geconfigureerd als:<br>`/content/output/sites/${preset_name}`<br><br>**Uiteindelijke uitvoerlocatie**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Gebruikt de taalcode waar het kaartdossier wordt gevestigd om de bestemmingspad tot stand te brengen. | **DITA-mapbestandsnaam**:<br>`SampleDita.ditamap`<br><br>**Pad DITA-kaartbestand**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Doelpad** geconfigureerd als:<br>`/content/output/sites/${language_code}`<br><br>**Uiteindelijke uitvoerlocatie**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Gebruikt het volledige pad van het kaartbestand om het doelpad te maken.<br><br>**Opmerking**:Deze variabele kan niet worden gebruikt om de Naam van de AEMPlaats of de Naam van het Dossier van de PDF te specificeren. | **DITA-mapbestandsnaam**:<br>`SampleDita.ditamap`<br><br>**Pad DITA-kaartbestand**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Doelpad** geconfigureerd als:<br>`/content/output/sites/${map_parentpath}`<br><br>**Uiteindelijke uitvoerlocatie**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Gebruikt het pad van het kaartbestand na de taalmap om het doelpad te maken.<br><br>**Opmerking**: Deze variabele kan niet worden gebruikt om de AEM Sitenaam of de Naam van het Dossier van de PDF te specificeren. | **DITA-mapbestandsnaam**:<br>`SampleDita.ditamap`<br><br>**Pad DITA-kaartbestand**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Doelpad** geconfigureerd als:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Uiteindelijke uitvoerlocatie**:<br>`/content/output/sites/user-guide/SampleDita.html` |

Daarnaast kunt u de metagegevens die voor de DITA-kaart of het bladwijzerbestand zijn gedefinieerd, ook als variabelen gebruiken. De metagegevens vindt u onder de `/jcr:content/metadata` knooppunt van de DITA-kaart of het bladwijzerbestand. Een van de metagegevenseigenschappen die bijvoorbeeld zijn gedefinieerd in het dialoogvenster `/jcr:content/metadata` node is `dc:title`. U kunt `${dc:title}` en de titelwaarde wordt gebruikt in de definitieve output.
**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)

