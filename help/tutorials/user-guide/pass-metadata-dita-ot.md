---
title: Geef de metagegevens door aan de uitvoer met DITA-OT
description: Leer hoe u de metagegevens aan de uitvoer kunt doorgeven met DITA-OT
source-git-commit: 8b6294425c6e60d1c5b37d98e99114014a104ee6
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---


# Geef de metagegevens door aan de uitvoer met DITA-OT {#id21BJ00QD0XA}

Metagegevens zijn aanvullende informatie over de uitvoer. In AEM hulplijnen kunt u de bestaande metagegevens doorgeven of aangepaste metagegevenstags maken. U kunt metagegevens doorgeven aan AEM, PDF, HTML,, EPUB en aangepaste uitvoerbestanden met DITA-OT-publicatie.

Voer de volgende stappen uit om de metagegevens door te geven aan de uitvoer met DITA-OT-publicatie:

1. In de **UI Middelen** Navigeer naar en klik op het DITA-kaartbestand waarvoor u de metagegevens wilt doorgeven aan de DITA-OT.
1. Selecteer en bewerk een uitvoervoorinstelling waaraan u de metagegevensvelden wilt doorgeven. Selecteer bijvoorbeeld de uitvoervoorinstelling PDF.
1. Selecteren **DITA-OT** onder Genereren &lt;output> Optie gebruiken in de geselecteerde uitvoervoorinstelling.

   ![](images/custom-meta-data-output-preset.png)

1. Selecteer in het keuzemenu Eigenschappen de metagegevens die u wilt doorgeven aan DITA-OT-publicaties.

   In het vervolgkeuzemenu Eigenschappen worden zowel de aangepaste als de standaardeigenschappen weergegeven. In het bovenstaande screenshot is de auteur bijvoorbeeld de aangepaste eigenschap while `dc:description`, `dc:language`, `dc:title`, en `docstate` Dit zijn de standaardeigenschappen.

   >[!NOTE]
   >
   > Deze eigenschappen worden gekozen uit het bestand metadataList dat beschikbaar is op de volgende locatie:`/libs/fmdita/config/metadataList`. Standaard worden in dit bestand vier eigenschappen vermeld: `dc:description`, `dc:language`, `dc:title`, en `docstate`.

   Dit bestand kan worden bedekt door: `/apps/fmdita/config/metadataList`.

   Als u een aangepaste eigenschap wilt doorgeven waarvoor u de waarden al hebt gedefinieerd, raadpleegt u [AEM metagegevens gebruiken in DITA-OT-PDF-uitvoer](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1. Van de **Eigenschappen** selecteert u de gewenste aangepaste en standaardeigenschappen. Selecteer bijvoorbeeld `author`, `dc:title`, en `dc:description`. Dit is de standaard `metadata/properties` dat wordt gemaakt wanneer we een bestand maken. De geselecteerde eigenschappen worden onder de dropbox weergegeven.

   ![](images/selected-metadata-properties.png)

1. Klikken **Gereed** bovenaan links om de wijzigingen op te slaan.
1. Genereer de uitvoer.

De geselecteerde eigenschappen van metagegevens worden doorgegeven aan de uitvoer die wordt gegenereerd met DITA-OT.

**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)

