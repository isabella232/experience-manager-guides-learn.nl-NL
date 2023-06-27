---
title: Een inhoudsfragment uit uw gegevensbron invoegen
description: Leer hoe u een inhoudsfragment uit uw gegevensbron kunt invoegen
source-git-commit: 84dbcd80d8b41ae52ec7389dd0d0a750ea8d6c65
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 0%

---


# Een inhoudsfragment uit uw gegevensbron invoegen

AEM Hulplijnen bieden de functie om verbinding te maken met uw gegevensbron. U kunt uw gegevens ophalen, het opnemen in uw onderwerpen, en het uitgeven. U kunt een inhoudsfragment gemakkelijk tot stand brengen gebruikend de inhoudsfragmentgenerator en het binnen uw onderwerpen opnieuw gebruiken.

Voer de volgende stappen uit om een inhoudsfragment tot stand te brengen gebruikend de inhoudsfragmentgenerator en neem het in uw onderwerp op:

1. Selecteren **Gegevensbronnen** ![](images/data-source-icon.svg)   in het linkerpaneel om de verbonden gegevensbronnen te bekijken. Het paneel van Gegevensbronnen opent en toont alle verbonden gegevensbronnen. Voor meer informatie, bekijkt u [Een gegevensbronaansluiting configureren](../cs-install-guide/conf-data-source-connector.md).
   >[!NOTE]
   >
   > U zult de gegevensbronnen zien waarvoor uw beheerder de schakelaar heeft gevormd.

1. Selecteer een gegevensbron om de inhoudsfragmentgenerators te bekijken beschikbaar voor de geselecteerde gegevensbron.
   ![](images/code-snippet-generator.png){width="300" align="left"}
1. Selecteren **Toevoegen** om een nieuwe inhoudsfragmentgenerator toe te voegen. De **Generator voor inhoudsfragmenten toevoegen** wordt geopend.

1. Voer de query in het tekstvak Gegevensquery in.
1. Selecteer in het menu van het palet **Gegevenstoewijzingssjabloon** vervolgkeuzelijst.
De out-of-the-box malplaatjes voor de geselecteerde gegevensbron worden getoond in drop-down. Bijvoorbeeld, kunt u het &quot;sql-lijst&quot;malplaatje voor datasource bekijken genoemd &quot;PostSQL&quot;gegevensbron.

   >[!NOTE]
   >  
   > Als uw beheerder aangepaste sjablonen heeft geconfigureerd, worden deze sjablonen ook weergegeven in de vervolgkeuzelijst (op basis van de sjabloonpadconfiguraties die de beheerder heeft uitgevoerd).
1. Klikken **Ophalen** om de gegevens van de gegevensbron te halen en het malplaatje op de gegevens toe te passen die uit de SQL vraag voortvloeien.
1. U kunt de gegevens weergeven in de voorvertoning of in de DITA-bronweergave.

   1. In het voorbeeld ziet u hoe de gegevens worden weergegeven wanneer ze in de inhoud worden ingevoegd. In de voorvertoning wordt een klein deel van de gegevens weergegeven in de indeling van de geselecteerde sjabloon.
Bijvoorbeeld:
      * Als u de sjabloon voor de sql-tabel hebt geselecteerd, kunt u de SQL-gegevens weergeven in een tabelindeling.
      * Als u de sjabloon voor jira-geordende lijsten hebt geselecteerd, kunt u een geordende lijst weergeven voor de Jira-problemen.

   1. De bronweergave toont de gegevens in de DITA-bronweergave.
      ![](images/add-content-snippet-generator.png){width="800" align="left"}
1. Om de resultaten van de vraag te bewaren, ga de naam van de generator in en klik dan **TOEVOEGEN**.   Er wordt een nieuwe inhoudsfragmentgenerator toegevoegd aan de lijst.

   >[!NOTE]
   >
   > U moet de naamgevingsconventie voor bestanden volgen voor de naam van de nieuwe inhoudsgenerator. U kunt geen ruimte hebben in de naam van de inhoudsfragmentgenerator. U kunt ook geen nieuwe inhoudsgenerator opslaan met de naam van een bestaande inhoudsgenerator. Er treedt een fout op.

## Opties voor een inhoudsfragmentgenerator

Klik met de rechtermuisknop op een inhoudsfragmentgenerator om de opties te openen. Met de opties kunt u de volgende bewerkingen uitvoeren:
* **Invoegen**: Gebruik deze optie om het geselecteerde inhoudsfragment in te voegen in het onderwerp dat voor het uitgeven in de Redacteur van het Web wordt geopend. Aangezien het gegeven als fragment wordt opgenomen, kunt u de gegevens binnen uw onderwerp in de Redacteur van het Web ook uitgeven.

  >[!NOTE]
  > 
  > De optie Invoegen wordt alleen weergegeven als u een onderwerp bewerkt.

* **Bewerken**: Gebruik deze optie om wijzigingen aan te brengen in de inhoudsfragmentgenerator en deze op te slaan.
* **Verwijderen**: Gebruik deze optie om de geselecteerde inhoudsfragmentgenerator te verwijderen.
* **Dupliceren**: Gebruik deze optie om een duplicaat of een kopie van de geselecteerde inhoudsfragmentgenerator te maken. Het duplicaat wordt standaard gemaakt met een achtervoegsel (zoals generator_1).

### Een queryfragment invoegen

U kunt ook de opdracht **Zoekfragment invoegen** ![](images/data-source-icon.svg)   van de belangrijkste toolbar om het gegevensfragment in de onderwerpen op te nemen.  U kunt een generator van dropdown selecteren, uw vraag uitgeven, of het malplaatje veranderen en de gegevens in uw onderwerp opnemen.

![](images/insert-content-snippet.png){width="800" align="left"}




