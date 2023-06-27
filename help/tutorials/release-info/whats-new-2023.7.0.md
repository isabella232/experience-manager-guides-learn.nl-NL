---
title: Opmerkingen bij de release | Nieuwe functies in Adobe Experience Manager-hulplijnen, release van juli 2023
description: Leer de nieuwe en verbeterde functies van de as a Cloud Service Adobe Experience Manager-hulplijnen in juli 2023
source-git-commit: 06bff798d2e745fae1c666353045cb4c6b040207
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---

# Nieuwe functies in juli 2023 as a Cloud Service Adobe Experience Manager-hulplijnen

Dit artikel behandelt de nieuwe en verbeterde functies in versie juli 2023 van Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u de [Opmerkingen bij de release](release-notes-2023.7.0.md) artikel.

## Verbind met een gegevensbron en neem gegevens in uw onderwerpen op

Nu kunt u snel verbinding maken met uw gegevensbronnen met behulp van kant-en-klare connectors van AEM hulplijnen. Wanneer u verbinding maakt met een gegevensbron, kunt u uw informatie synchroon houden met de bron. Updates van de gegevens worden dan automatisch weerspiegeld, waardoor AEM hulplijnen een echte inhoudshub worden. Met deze functie bespaart u tijd en moeite om de gegevens handmatig toe te voegen of te kopiëren.

Nu, staat AEM Gidsen uw beheerder toe om de uit-van-de-doosschakelaars voor JIRA en SQL (MySQL, PostgreSQL, SQL Server, SQLite) gegevensbestanden te vormen. Zij kunnen andere schakelaars ook toevoegen door de standaardinterfaces uit te breiden.

Zodra toegevoegd, kunt u de gevormde schakelaars bekijken die onder worden vermeld **Gegevensbronnen** in de webeditor.

![](assets/code-snippet-generator.png){width="300" align="left"}

U kunt een inhoudsfragmentgenerator tot stand brengen om de gegevens van een verbonden gegevensbron te halen. U kunt de gegevens in uw onderwerpen dan opnemen en het uitgeven.

Zodra u een inhoudsfragmentgenerator hebt gecreeerd, kunt u het opnieuw gebruiken om de gegevens in om het even welk onderwerp op te nemen. Voor meer informatie, bekijkt u [Een inhoudsfragment uit uw gegevensbron invoegen](../user-guide/web-editor-content-snippet.md).



## Deelvenster Controleren om revisieprojecten en de actieve revisietaken te presenteren

Met AEM hulplijnen kunt u uw beoordelingen nu naadloos uitvoeren. Het biedt het deelvenster Revisies in de webeditor. In het deelvenster Revisies worden alle revisieprojecten en de actieve revisietaken weergegeven in de revisieprojecten die u maakt.

Als auteur kunt u met deze functie gemakkelijk de revisietaken openen, de opmerkingen bekijken en de opmerkingen snel in een gecentraliseerde weergave adresseren.
![](assets/active-review-task-comments.png){width="800" align="left"}
Voor meer informatie bekijkt u de **Controleren** functiebeschrijving in het gedeelte [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.


## Verbeteringen voor kaartverzameling

Met een kaartverzameling kunt u meerdere toewijzingen ordenen en in batches publiceren. Er zijn veel nieuwe verbeteringen aangebracht in de kaartverzameling:

- Nu kunt u ook voorinstellingen voor eigen PDF-uitvoer toevoegen aan een kaartverzameling en deze gebruiken om de PDF-uitvoer te genereren.
- U kunt de algemene voorinstellingen en voorinstellingen van het mapprofiel die door de beheerder zijn gemaakt, weergeven en deze gebruiken om de PDF-uitvoer te genereren.
- U kunt nu niet alleen een individuele voorinstelling selecteren, maar u kunt ook alle voorinstellingen voor het mapprofiel voor een DITA-kaart in één keer inschakelen.
  ![](assets/edit-map-collection.png){width="800" align="left"}

Voor meer informatie, bekijkt u [Kaartverzameling gebruiken voor het genereren van uitvoer](../user-guide/generate-output-use-map-collection-output-generation.md).

## Mogelijkheid om toegang te krijgen tot tijdelijke HTML-bestanden terwijl de native PDF-uitvoer wordt gegenereerd

Met AEM hulplijnen kunt u nu de tijdelijke HTML-bestanden downloaden die zijn gemaakt tijdens het genereren van de native PDF-uitvoer. Selecteer in de instellingen van de uitvoervoorinstelling de optie om de tijdelijke bestanden te downloaden.  AEM Hulplijnen kunt u vervolgens de tijdelijke bestanden downloaden die zijn gemaakt tijdens het genereren van de uitvoer met behulp van die voorinstelling.

Met deze functie krijgt u meer inzicht in het generatieproces dankzij toegang tot tussentijdse stijlen en lay-outs en kunt u uw CSS-stijlen naar wens corrigeren of wijzigen.

![](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Voor meer informatie, bekijkt u [Een voorinstelling voor PDF-uitvoer maken](../web-editor/native-pdf-web-editor.md#create-output-preset).

## Op microservices gebaseerde publicaties om HTML5 en aangepaste uitvoer te genereren

Met de nieuwe publicatiemicroservice kunt u grote publicatiewerkbelastingen tegelijk uitvoeren op AEM as a Cloud Service hulplijnen en het toonaangevende Adobe I/O Runtime-serverplatform benutten. Nu gebruikend de microservice, kunt u HTML5 en de output van de Douane ook produceren.
U kunt meerdere publicatieverzoeken uitvoeren en de prestaties verbeteren om deze uitvoerindelingen te genereren.
Voor meer informatie, bekijkt u [Op microservice gebaseerde publicaties configureren voor as a Cloud Service AEM hulplijnen](../knowledge-base/publishing/configure-microservices.md).

## Versiegegevens van de versie van AEM hulplijnen weergeven in het venster Info

Samen met de AEM **Info** U kunt ook de versiedetails van de AEM hulplijnen bekijken. U kunt de huidige versiedetails bekijken in **Info** de **Help** op de AEM navigatiepagina.

![](assets/about-aem-help.png)(width=&quot;800&quot; align=&quot;left&quot;)