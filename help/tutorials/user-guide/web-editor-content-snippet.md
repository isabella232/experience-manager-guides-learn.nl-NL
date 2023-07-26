---
title: Een inhoudsfragment uit uw gegevensbron invoegen
description: Leer hoe u een inhoudsfragment uit uw gegevensbron kunt invoegen
source-git-commit: 0f1c9d545dfc6dc53742c6f8d89cd48d33de2681
workflow-type: tm+mt
source-wordcount: '1549'
ht-degree: 0%

---


# Gegevens uit uw gegevensbron gebruiken

A **gegevensbron** is een systeem waarin u de gegevens voor uw organisatie opslaat en beheert. Dit zijn uw systemen van verslag zoals JIRA, SQL Gegevensbestanden, PIM, of PLM. AEM de Gidsen verstrekt de eigenschap om met uw gegevensbron te verbinden en de gegevens van hen te gebruiken.

## Deelvenster Gegevensbronnen

Selecteren **Gegevensbronnen** ![](images/data-source-icon.svg) in het linkerpaneel om de verbonden gegevensbronnen te bekijken. Het paneel van Gegevensbronnen opent en toont alle verbonden gegevensbronnen. Voor meer informatie, bekijkt u [Een gegevensbronaansluiting configureren](../install-guide/conf-data-source-connector.md).

>[!NOTE]
>
> U zult de gegevensbronnen zien waarvoor uw beheerder de schakelaar heeft gevormd.


## Lijstweergave of Tegelweergave tonen

U kunt schakelen tussen de Lijstweergave of de Tegelweergave om de verschillende gegevensbronnen weer te geven in de vorm van een lijst of als tegels.

Selecteer een gegevensbron om de generators van het inhoudsfragment en de onderwerpgenerators te bekijken beschikbaar voor de geselecteerde gegevensbron.

### Lijstweergave  ![](images/data-sources-list-view-icon.svg)

![](images/data-sources-list-view.png){width="300" align="left"}


### Tegelweergave   ![](images/data-sources-tile-view-icon.svg)

![](images/data-sources-tile-view.png){width="300" align="left"}

U kunt de gegevens van gegevensbronnen op twee manieren gebruiken:
- Een inhoudsfragment invoegen
- Een onderwerp maken


## Een inhoudsfragment uit uw gegevensbron invoegen

AEM Hulplijnen bieden de functie om verbinding te maken met uw gegevensbron. U kunt uw gegevens ophalen, het opnemen in uw onderwerpen, en het uitgeven. U kunt een inhoudsfragment gemakkelijk tot stand brengen gebruikend de inhoudsfragmentgenerator en het binnen uw onderwerpen opnieuw gebruiken.

Voer de volgende stappen uit om een inhoudsfragment tot stand te brengen gebruikend de generator van het inhoudsfragment en neem het in uw onderwerp op:

1. Selecteren **Gegevensbronnen** ![](images/data-source-icon.svg)   in het linkerpaneel om de verbonden gegevensbronnen te bekijken.

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
      - Als u de sjabloon voor de sql-tabel hebt geselecteerd, kunt u de SQL-gegevens weergeven in een tabelindeling.
      - Als u de sjabloon voor jira-geordende lijsten hebt geselecteerd, kunt u een geordende lijst weergeven voor de Jira-problemen.

   1. De bronweergave toont de gegevens in de DITA-bronweergave.
      ![](images/add-content-snippet-generator.png){width="800" align="left"}
1. Om de resultaten van de vraag te bewaren, ga de naam van de generator in en klik dan **ADD**.   Er wordt een nieuwe inhoudsfragmentgenerator toegevoegd aan de lijst.

   >[!NOTE]
   >
   > U moet de naamgevingsconventie voor bestanden volgen voor de naam van de nieuwe inhoudsgenerator. U kunt geen ruimte hebben in de naam van de inhoudsfragmentgenerator. U kunt ook geen nieuwe inhoudsgenerator opslaan met de naam van een bestaande inhoudsgenerator. Er treedt een fout op.

### Opties voor een inhoudsfragmentgenerator

Klik met de rechtermuisknop op een inhoudsfragmentgenerator om de opties te openen. Met de opties kunt u de volgende bewerkingen uitvoeren:

- **Voorvertoning**: Gebruik deze optie om een venster te openen en een klein deel van de weergave van de gegevens in de uitvoer weer te geven.
- **Invoegen**: Gebruik deze optie om het geselecteerde inhoudsfragment in te voegen in het onderwerp dat voor het uitgeven in de Redacteur van het Web wordt geopend. Aangezien het gegeven als fragment wordt opgenomen, kunt u de gegevens binnen uw onderwerp in de Redacteur van het Web ook uitgeven.

  >[!NOTE]
  > 
  > De optie Invoegen wordt alleen weergegeven als u een onderwerp bewerkt.

- **Bewerken**: Gebruik deze optie om wijzigingen aan te brengen in de inhoudsfragmentgenerator en deze op te slaan.
- **Verwijderen**: Gebruik deze optie om de geselecteerde inhoudsfragmentgenerator te verwijderen.
- **Dupliceren**: Gebruik deze optie om een duplicaat of kopie van de geselecteerde inhoudsfragmentgenerator te maken. Het duplicaat wordt standaard gemaakt met een achtervoegsel (zoals generator_1).

### Een queryfragment invoegen

U kunt ook de opdracht **Zoekfragment invoegen** ![](images/data-source-icon.svg)   van de belangrijkste toolbar om het gegevensfragment in de onderwerpen op te nemen.  U kunt een generator van dropdown selecteren, uw vraag uitgeven, of het malplaatje veranderen en de gegevens in uw onderwerp opnemen.

![](images/insert-content-snippet.png){width="800" align="left"}


## Creeer een onderwerp gebruikend de onderwerpgenerator

Een onderwerpgenerator helpt u onderwerpen tot stand brengen die gegevens van uw bronnen bevatten. U kunt snel een onderwerpgenerator tot stand brengen en dan de onderwerpen produceren gebruikend de generator. Elk onderwerp kan gegevens in diverse formaten, zoals lijsten, lijsten, en paragrafen bevatten.   In een onderwerp kunt u bijvoorbeeld een tabel toevoegen met de details van alle nieuwe producten en een lijst met alle producten die worden afgezet voor verkoop.

De onderwerpgenerator kan de onderwerpen tot stand brengen die de gegevens en een kaart DITA voor alle onderwerpen bevatten. U kunt ook `<conref>` Deze onderwerpen in uw inhoud. Zo kunt u uw gegevens synchroon houden met de gegevensbron en deze eenvoudig bijwerken.



### Een onderwerp maken

Voer de volgende stappen uit om een onderwerp tot stand te brengen gebruikend de onderwerpgenerator:

1. Selecteer een gegevensbron om de generators van het inhoudsfragment en de onderwerpgenerators te bekijken beschikbaar voor de geselecteerde gegevensbron.

   ![](images/data-sources.png){width="300" align="left"}
1. Selecteren **Toevoegen** ![](images/Add_icon.svg) en selecteert u **Topgenerator** van dropdown om een nieuwe onderwerpgenerator toe te voegen. De **Onderwerpgenerator toevoegen** wordt geopend.



1. Voer de waarden in de velden in onder de volgende drie tabbladen van het dialoogvenster **Onderwerpgenerator toevoegen** paneel:

   **Ophaalconfiguratie**

   ![](images/topic-generator-fetch-configuration.png){width="300" align="left"}


   1. Voer de query in het dialoogvenster **Gegevensquery** tekstvak.
   1. Selecteer in het menu van het palet **Gegevenstoewijzingssjabloon** vervolgkeuzelijst.

   >[!NOTE]
   >
   > Als uw beheerder aangepaste malplaatjes heeft gevormd, dan wordt u ook getoond die malplaatjes in de drop-down lijst (die op de configuraties van de malplaatjeweg door uw beheerder wordt gebaseerd). U kunt bijvoorbeeld een onderwerpsjabloon maken met een geordende lijst, tabellen, alinea&#39;s of andere DITA-elementen.

   1. Voer de **Basisknooppunt**. Dit is de knoop waarbij u tot uw gegevens wilt toegang hebben. De onderwerpgenerator leidt dan tot elk onderwerp op het niveau dat in de wortelknoop wordt bepaald. U kunt bijvoorbeeld &quot;issues&quot; toevoegen als het hoofdknooppunt in Jira. Zo, als een vraag 13 kwesties terugkeert, zult u 13 onderwerpen, één onderwerp voor elke kwestie krijgen.

   1. Klikken **Ophalen** om de gegevens van de gegevensbron te halen en het malplaatje op de gegevens toe te passen die uit de SQL vraag voortvloeien. In de voorvertoning wordt een klein gedeelte weergegeven van de manier waarop het onderwerp wordt weergegeven in de indeling van de geselecteerde sjabloon. U kunt bijvoorbeeld één Jira-uitgave weergeven met alle velden die het resultaat zijn van de query.
   1. Ga de naam van de onderwerpgenerator in.

      >[!NOTE]
      > 
      > U moet de dossier noemende overeenkomst voor de naam van de nieuwe onderwerpgenerator volgen. U kunt geen ruimte in de naam van de onderwerpgenerator hebben. Ook, kunt u geen nieuwe onderwerpgenerator met de naam van een bestaande onderwerpgenerator bewaren. Er treedt een fout op.

   **Uitvoerconfiguratie**

   ![](images/topic-generator-output-configuration.png){width="300" align="left"}

   1. Voer de **Uitvoerpad** details waar u uw onderwerpen wilt bewaren.
   1. In de **Naamgevingsconventie voor onderwerpen** kunt u een waarde of een variabele met snelheidstags invoeren. De nieuwe onderwerpen volgen de conventie. U kunt bijvoorbeeld het dialoogvenster `$key` om onderwerpen te maken op basis van Jira-sleutels.
   1. De optie inschakelen **Een kaart genereren** als u een kaart wilt creëren die alle geproduceerde onderwerpen bevat.
   1. Ga de naam van de nieuwe kaart DITA in.

   >[!NOTE]
   >
   > De generator van het Onderwerp produceert de kaart DITA op de zelfde outputweg zoals de onderwerpen.

   **Metagegevens**

   Selecteer de eigenschappen van meta-gegevens van drop-down om tot de onderwerpen over te gaan. **Naam** in het vervolgkeuzemenu worden zowel de aangepaste als de standaardeigenschappen weergegeven.

   In de volgende schermafbeelding bijvoorbeeld: `dc:description`, `dc:language`, `dc:title`, en `docstate` Dit zijn de standaardeigenschappen waarvoor u de waarden kunt definiëren. U kunt een aangepaste eigenschap maken, zoals een auteur, en de waarde ervan definiëren.

   ![](images/topic-generator-metadata.png){width="300" align="left"}



1. Voer de naam van de generator in en klik op **Opslaan** om de queryresultaten op te slaan. Een nieuwe onderwerpgenerator wordt toegevoegd aan de lijst.

1. Klikken **Opslaan en genereren** om de onderwerpgenerator te bewaren en nieuwe onderwerpen van de onderwerpgenerator te produceren.



   ![](images/edit-topic-generator.png){width="650" align="left"}

   >[!NOTE]
   >
   > Als de onderwerpen reeds bestaan, dan werkt de generator de gegevens in de bestaande onderwerpen bij.

### Opties voor een onderwerpgenerator

Klik met de rechtermuisknop op een onderwerpgenerator om de **Opties**. Met de opties kunt u de volgende bewerkingen uitvoeren:

- **Voorvertoning**: Gebruik deze optie om een venster te openen en een klein deel van de weergave van de gegevens in de uitvoer weer te geven.
- **Inhoud genereren**: Deze optie produceert de onderwerpen voor de geselecteerde onderwerpgenerator. U kunt deze optie ook gebruiken om de bestaande onderwerpen bij te werken. Het verbindt met de gegevensbron en haalt de bijgewerkte gegevens.

  >[!NOTE]
  >
  >Als uw onderwerp reeds bestaat, kunt u of de gegevens in het onderwerp overschrijven of het opslaan als nieuwe versie.

  ![](images/generate-topic-options.png)

- **Bewerken**: Gebruik deze optie om de onderwerpgenerator te veranderen en te bewaren.
- **Verwijderen**: Gebruik deze optie om de geselecteerde onderwerpgenerator te schrappen.
- **Dupliceren**: Met deze optie maakt u een kopie of kopie van de geselecteerde onderwerpgenerator. Het duplicaat wordt gemaakt met een achtervoegsel (zoals `topic-sample_1`) standaard.




