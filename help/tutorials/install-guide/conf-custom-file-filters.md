---
title: Filters configureren voor het dialoogvenster Bladeren van bestanden
description: Leer hoe u filters voor bladeren door bestanden kunt configureren
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---


# Filters configureren voor het dialoogvenster Bladeren van bestanden {#id20CIL7009GN}

Wanneer u werkt in de webeditor, moet u het bladerdialoogvenster voor bestanden gebruiken om elementen in te voegen, zoals een afbeelding, verwijzing of een toetsverwijzing. Het standaarddialoogvenster voor bladeren naar bestanden biedt geen filteroptie. U kunt uw eigen filters toevoegen waarmee u de vereiste bestanden snel en gemakkelijk kunt openen.

Voer de volgende stappen uit om uw aangepaste filteropties voor bestanden toe te voegen aan het bladerdialoogvenster van het bestand:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het standaardconfiguratiebestand dat beschikbaar is op de volgende locatie:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Maak een kopie van het standaardconfiguratiebestand op de volgende locatie:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigeer naar de `ui_config.json` in het `apps` knooppunt voor bewerken.

1. In de `ui_config.json` voegt u de definitie toe van de filters die u wilt toevoegen.

   In het volgende codefragment ziet u hoe u twee filteropties kunt toevoegen: DITA-bestanden en afbeeldingsbestanden.

   ```json
   "browseFilters": [
       {
         "title": "DITA Files",
         "property": "jcr:content/metadata/dita_class",
         "operation": "exists"
       },
       {
         "title": "Image Files",
         "property": "jcr:content/metadata/dc:format",
         "value": [        
           "image/jpeg",
           "image/gif",
           "image/png"
         ]
       }
   ]
   ```

   In het bovenstaande codefragment is het eerste filter voor DITA-bestanden. De filterdefinitie heeft de volgende parameters:

   - **titel:**   De weergavenaam van het filter. Deze titel wordt weergegeven als filteroptie in het bladerdialoogvenster van het bestand.

   - **eigenschap:**   De eigenschap die moet overeenkomen met de metagegevens van het bestand. Als u bijvoorbeeld alleen de bestanden wilt toestaan die de `dita_class` metagegevens in de eigenschap, neemt het eigenschapfilter &quot;`jcr:content/metadata/dita_class`&quot; als waarde.

   - **bewerking:**   Opgeven &quot;`exists`&quot; om overeen te komen met het bestaan van de waarde die is opgegeven in de parameter property.

   Het tweede filter is voor de Dossiers van het Beeld. De parameters zijn vergelijkbaar met het eerste filter, behalve `value` parameter. De `value` parameter neemt een array van afbeeldingstypen als waarde. Alle bestandstypen die in de parameter value zijn opgegeven, worden doorzocht en weergegeven in het bladerdialoogvenster. Alle andere bestandstypen worden genegeerd.

1. Sla de *ui\_config.json* bestand en laad de webeditor opnieuw.

   Wanneer u het bladerdialoogvenster start, worden de filteropties weergegeven die in het bestand ui\_config.json zijn geconfigureerd.

   ![](assets/file-browse-custom-filters.png){width="300" align="left"}


