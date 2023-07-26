---
title: Opmerkingen bij de release | Nieuwe functies in de release van Adobe Experience Manager Guides 4.3.0
description: Leer de nieuwe en verbeterde functies in de 4.3.0-versies van Adobe Experience Manager Guides
source-git-commit: 7581085859785c5b8b597ecfeb7dbe58c7c9e2bc
workflow-type: tm+mt
source-wordcount: '2639'
ht-degree: 0%

---

# Nieuwe functies in de release 4.3.0 van Adobe Experience Manager Guides (juli 2023)

Dit artikel behandelt de nieuwe en verbeterde functies in versie 4.3.0 van de Gidsen van Adobe Experience Manager (later genoemd *Hulplijnen AEM*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u [Opmerkingen bij de release](./release-notes-4.3.md).


## Verbind met een gegevensbron en neem gegevens in uw onderwerpen op

Nu kunt u snel verbinding maken met uw gegevensbronnen met behulp van kant-en-klare connectors van AEM hulplijnen. Wanneer u verbinding maakt met een gegevensbron, kunt u uw informatie synchroon houden met de bron. Updates van de gegevens worden dan automatisch weerspiegeld, waardoor AEM hulplijnen een echte inhoudshub worden. Met deze functie bespaart u tijd en moeite om de gegevens handmatig toe te voegen of te kopiëren.

AEM de Gidsen staan uw beheerder toe om de uit-van-de-doosschakelaars voor JIRA en SQL (MySQL, PostgreSQL, SQL Server, SQLite) gegevensbestanden te vormen. Zij kunnen andere schakelaars ook toevoegen door de standaardinterfaces uit te breiden.
Zodra toegevoegd, kunt u de gevormde schakelaars bekijken die onder het paneel van Gegevensbronnen in de Redacteur van het Web worden vermeld.

<img src="assets/data-sources.png" alt="Lijst met gegevensbronnen in het deelvenster" width="300">

Maak een inhoudsfragment om de gegevens van een verbonden gegevensbron op te halen. U kunt de gegevens in uw onderwerpen dan opnemen en het uitgeven. Nadat u een inhoudsfragmentgenerator hebt gemaakt, kunt u deze opnieuw gebruiken om de gegevens in te voegen in een onderwerp.

Nu kunt u een onderwerp van een verbonden gegevensbron ook tot stand brengen. Een onderwerp kan gegevens in diverse formaten, zoals lijsten, lijsten, en paragrafen bevatten. Het staat u ook toe om een kaart DITA voor alle onderwerpen tot stand te brengen. U kunt meta-gegevens aan het onderwerp associëren wanneer het trekken uit een gegevensbron.

Voor meer informatie, bekijkt u [Gegevens uit uw gegevensbron gebruiken](../user-guide/web-editor-content-snippet.md).

## citaten toevoegen aan uw inhoud

Bijschriften zijn verwijzingen naar de informatiebron die aan de inhoud is toegevoegd. Met uitnodigingen kunt u uw geloofwaardigheid herstellen en plagiaat voorkomen. Met uitnodigingen kunnen de lezers de bron vinden en de informatie in de tekst controleren.

In AEM hulplijnen kunt u citaten toevoegen of citaten importeren en deze op de inhoud toepassen. U kunt deze citaten toevoegen vanuit elke bron van boeken, websites en tijdschriften.

Na het opnemen van uw citaten aan uw onderwerpen, kunt u voorproef hen in de Redacteur van het Web. U kunt inhoud met citaten ook publiceren gebruikend Eigen PDF.

![In een deelvenster weergegeven uitnodigingen](assets/citation-panel.png){width="300" align="left"}


Voor meer informatie, bekijkt u [Citaten in uw inhoud toevoegen en beheren](../user-guide/web-editor-apply-citations.md).

## Publiceren naar een inhoudsfragment

Inhoudsfragmenten zijn afzonderlijke stukken inhoud in AEM. Het zijn gestructureerde inhoud die is gebaseerd op een inhoudsmodel. Inhoudsfragmenten zijn zuivere inhoud zonder ontwerp- of layoutgegevens. Ze kunnen onafhankelijk van de kanalen worden ontworpen en beheerd die AEM ondersteunen. De modulariteit en de herbruikbaarheid van de inhoudsfragmenten leiden tot meer flexibiliteit, consistentie, efficiëntie en eenvoudiger beheer.

Nu AEM Gidsen een manier biedt om een onderwerp of de elementen binnen een onderwerp aan een inhoudsfragment te publiceren. U kunt een op JSON-Gebaseerde afbeelding tussen een onderwerp en een model van het inhoudsfragment tot stand brengen. Gebruik deze toewijzing om inhoud die in sommige of alle elementen binnen een onderwerp aanwezig is, naar een inhoudsfragment te publiceren.

Maak een hoofdletter van AEM hulplijnen en inhoudsfragmenten en gebruik inhoudsfragmenten op een AEM site. U kunt de details ook extraheren via API&#39;s die worden ondersteund door inhoudsfragmenten.

![optie voor het publiceren van een inhoudsfragment](assets/content-fragment-publish.png){width="550" align="left"}


## Verbeteringen voor revisie

AEM Hulplijnen bieden nu een verbeterde mogelijkheid voor revisie met de volgende functies:

### Deelvenster Controleren om revisieprojecten en de actieve revisietaken te presenteren

Met AEM hulplijnen kunt u uw beoordelingen nu naadloos uitvoeren. Het biedt het deelvenster Revisies in de webeditor. In het deelvenster Revisies worden alle revisieprojecten en de actieve revisietaken weergegeven in de revisieprojecten die u maakt.

Als auteur kunt u met deze functie gemakkelijk de revisietaken openen, de opmerkingen bekijken en de opmerkingen snel in een gecentraliseerde weergave adresseren.
![](assets/active-review-task-comments.png){width="800" align="left"}
Voor meer informatie bekijkt u de **Controleren** functiebeschrijving in het gedeelte [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.

### Zoeken in revisieonderwerpen

Het uitvoeren van revisies is een essentieel onderdeel van AEM hulplijnen. Hiermee kunnen de revisoren de documenten controleren die aan hen zijn toegewezen.
U kunt nu naar een onderwerp zoeken door een deel van de tekst van de titel of het bestandspad in te voeren in de zoekbalk van de onderwerpenweergave van het revisiepaneel. U kunt ook alle onderwerpen of onderwerpen met opmerkingen weergeven. Standaard kunt u alle onderwerpen in de overzichtstaak weergeven.


![Zoeken in een deelvenster met revisieonderwerpen](assets/review-search-topic.png){width="800" align="left"}

Voor meer informatie, bekijkt u [Onderwerpen bekijken](../user-guide/review-topics.md).

## Guides Extension Framework

Maak aangepaste pakketten boven op AEM hulplijnen voor uitbreidbaarheid met AEM Extension Framework. Deze pakketten zijn nuttig voor ontwikkelaars en consultants en geven ze uitbreidbaarheid aan de componenten in de Editor. Ze kunnen knoppen, dialoogvensters en dropdowns als doel hebben en aangepaste JavaScript toevoegen die eenvoudig kan samenwerken met de gebruikersinterface van AEM hulplijnen.



## Native PDF-verbeteringen

De volgende Native PDF-verbeteringen zijn doorgevoerd in de release 4.3.0 om van AEM hulplijnen een robuuster product te maken:

### Ondersteuning voor taalvariabelen

AEM hulplijnen bieden ondersteuning voor taalvariabelen. U kunt taalvariabelen gebruiken om een gelokaliseerde versie van de uit-van-de-doos etiketten zoals Nota, Voorzichtigheid, en Waarschuwing of statische tekst in de output van PDF te bepalen.
U kunt de taalvariabelen of de gelokaliseerde versie van de etiketten aan de aangewezen secties in uw output van PDF en in de outputmalplaatjes toevoegen.

#### Taalvariabelen in de PDF-uitvoer

U kunt de taalvariabelen gebruiken om gelokaliseerde etiketten voor elementen zoals Nota, Voorzichtigheid, en Waarschuwing te bepalen. U kunt de waarde voor deze variabelen bijwerken in een of meer talen en vervolgens wordt de gelokaliseerde waarde automatisch gekozen in de uitvoer van PDF.
U kunt bijvoorbeeld het label Notitie op de volgende manieren in uw PDF-uitvoer presenteren:

* Engels: Opmerking
* Frans: Opmerking
* Duits: Hinweis

#### Taalvariabelen in de uitvoersjablonen

Als u de PDF-uitvoer in verschillende talen wilt maken, moet u verschillende PDF-sjablonen maken die gelokaliseerde tekst voor elke taal bevatten. Nu met de eigenschap van taalvariabelen, moet u het malplaatje slechts eenmaal tot stand brengen. Vervolgens kunt u voor elke statische tekst die u wilt lokaliseren, overeenkomstige taalvariabelen maken en deze gebruiken in uw sjabloon.
U kunt taalvariabelen maken voor langere tekst, zoals een hele zin of zelfs een alinea. U kunt ook stijlen toepassen en markeringen voor HTML gebruiken om deze taalvariabelen op te maken.

Voor meer informatie, bekijkt u [Ondersteuning voor taalvariabelen](../native-pdf/native-pdf-language-variables.md).

### Een watermerk toevoegen aan de PDF-uitvoer voor conceptdocumenten

Nu kunt u een watermerk toevoegen aan de PDF-uitvoer van het document dat nog niet is goedgekeurd. Dit watermerk wordt niet weergegeven als u de PDF voor het document genereert in de documentstatus &quot;Goedgekeurd&quot;. U kunt bijvoorbeeld een watermerk Concept toevoegen voor uw PDF-uitvoer.

Voor meer informatie, bekijkt u [Een watermerk toevoegen aan de PDF-uitvoer voor conceptdocumenten](../native-pdf/use-javascript-content-style.md#watermark-draft-document).

### Mogelijkheid om AEM metagegevens te gebruiken in PDF-lay-outs

Metagegevens zijn de beschrijving of definitie van de inhoud. Deze metagegevens worden opgeslagen in de DITA-bronkaartinhoud.

In AEM hulplijnen kunt u ook de eigenschappen van de metagegevens van uw elementen selecteren en deze aan de pagina-indeling toevoegen. Vervolgens worden deze metagegevenseigenschappen van uw elementen door AEM hulplijnen geselecteerd en in de PDF-uitvoer gepubliceerd.


![metagegevens toevoegen voor de native PDF](assets/native-pdf-metadata-asset.png){width="300" align="left"}

>[!NOTE]
>
> AEM de Gidsen steunen ook de meta-gegevenseigenschappen voor uw kaarten DITA.

Voor meer informatie, bekijkt u [Velden en metagegevens toevoegen](../native-pdf/design-page-layout.md#add-fields-metadata).


### Pagina&#39;s bestellen in de PDF-uitvoer

U kunt de volgende secties in uw PDF tonen of verbergen en ook de orde schikken waarin zij in uw definitieve output van de PDF zouden moeten verschijnen:

* Inhoudsopgave
* Hoofdstuk en onderwerp
* Lijst met figuren
* Lijst met tabellen
* Index
* Verklarende woordenlijst
* Visum
* Paginalay-outs

Als u geen bepaalde sectie in de uitvoer van PDF wilt tonen, kunt u dat verbergen door de schakeloptie uit te schakelen.

Voor meer informatie, bekijkt u [Paginavolgorde](../native-pdf/components-pdf-template.md#page-order).

### Pagina&#39;s samenvoegen

In een native PDF-uitvoer beginnen standaard alle secties op een nieuwe pagina. Nu kunt u een sectie samenvoegen tot de vorige of volgende pagina. Hierdoor wordt de sectie gepubliceerd in overeenstemming met de geselecteerde pagina in de PDF-uitvoer en is er geen pagina-einde tussen de pagina&#39;s.

Voor meer details bekijkt u de beschrijving van de functie Pagina&#39;s samenvoegen in [Paginavolgorde](../native-pdf/components-pdf-template.md#page-order) sectie.

### Statische pagina&#39;s

U kunt ook aangepaste paginalay-outs maken en deze als statische pagina&#39;s publiceren in de PDF-uitvoer. Zo kunt u statische inhoud toevoegen, zoals notities of lege pagina&#39;s.

Voor meer informatie bekijkt u de beschrijving van de functie Statische pagina&#39;s in [Paginavolgorde](../native-pdf/components-pdf-template.md#page-order) sectie.


### Variabelen in kruisverwijzingen

U kunt variabelen gebruiken om een kruisverwijzing te definiëren. Wanneer u een variabele gebruikt, wordt de waarde ervan gekozen uit de eigenschappen.

U kunt nu ook {figure} en {table}.
Gebruiken {figure}om een kruisverwijzing naar het figuurnummer toe te voegen. Hierbij wordt het figuurnummer gekozen uit de stijlen voor automatische nummering die u hebt gedefinieerd voor figuren.

Gebruiken {table} om een kruisverwijzing naar het tabelnummer toe te voegen. Hierbij wordt het tabelnummer gekozen uit de stijlen voor automatische nummering die u voor het bijschrift hebt gedefinieerd.

Voor meer informatie, bekijkt u [Kruisverwijzingen](../native-pdf/components-pdf-template.md##cross-references).

### Een hoofdstuk vanaf de huidige pagina starten

U kunt de basisconfiguratiemontages voor de aanvang van een hoofdstuk van oneven of even pagina, de structuur van TOC, plaatsen en het formaat van de leaderlijn voor de ingangen van TOC bepalen.

Nu kunt u ook een hoofdstuk starten vanaf de huidige pagina. Als u dit wilt doen, worden alle hoofdstukken zonder pagina-einden verder gepubliceerd. Als een hoofdstuk bijvoorbeeld halverwege pagina 15 eindigt, begint het volgende hoofdstuk ook op de 15e pagina zelf.


### Mogelijkheid om toegang te krijgen tot tijdelijke HTML-bestanden terwijl de native PDF-uitvoer wordt gegenereerd

Met AEM hulplijnen kunt u nu de tijdelijke HTML-bestanden downloaden die zijn gemaakt tijdens het genereren van de native PDF-uitvoer. Selecteer in de instellingen van de uitvoervoorinstelling de optie om de tijdelijke bestanden te downloaden.  AEM Hulplijnen kunt u vervolgens de tijdelijke bestanden downloaden die zijn gemaakt terwijl u de uitvoer genereert met behulp van die voorinstelling.

Met deze functie krijgt u meer inzicht in het generatieproces dankzij toegang tot tussentijdse stijlen en lay-outs en kunt u uw CSS-stijlen naar wens corrigeren of wijzigen.

![het dialoogvenster Geavanceerde instellingen van native pdf](assets/native-pdf-advanced-settings.png){width="800" align="left"}

Voor meer informatie, bekijkt u [Een voorinstelling voor PDF-uitvoer maken](../web-editor/native-pdf-web-editor.md#create-output-preset).


### Opnieuw ontwerpen van CSS-editor

De CSS-editor is nu opnieuw ontworpen voor een betere gebruikerservaring met kiezers en stijleigenschappen.

#### Verbetering van dialoogvenster Stijl toevoegen

U kunt nu aangepaste kiezers gebruiken om complexe stijlen toe te voegen. Met het nieuwe veld Selector kunt u naast de combinatie Klasse, Tag en Pseudo-klasse ook aangepaste kiezers toevoegen. U kunt bijvoorbeeld `table a.link` stijl voor alle hyperlinks in een tabel.

![stijlen toevoegen in de native PDF-sjablonen](assets/add-styles-native-pdf.png){width="300" align="left"}

#### Stijleigenschappen aanpassen

AEM hulplijnen introduceert u nu een nieuw deelvenster met eigenschappen onder de voorvertoningssectie voor stijlen. U kunt de eigenschappen van de stijlen efficiënter en sneller bewerken in het deelvenster Eigenschappen.


## Bestanden hernoemen en verplaatsen in de weergave Opslagplaats

U kunt nu ook de naam van een bestand wijzigen of een bestand uit het deelvenster Opslagruimte verplaatsen. Deze functie is handig en helpt uw bestanden eenvoudig te beheren vanuit het deelvenster Opslag. U kunt een bestand selecteren en de naam ervan wijzigen of de naam ervan wijzigen met de **Opties** voor het geselecteerde bestand. AEM hulplijnen geven een bericht van slagen weer wanneer u een bestand verplaatst of de naam ervan wijzigt.

![optiemenu van een bestand](assets/rename-move-assets.png){width="550" align="left"}

Voor meer informatie over het menu Opties van een bestand bekijkt u de **Weergave opslagplaats** functiebeschrijving in het dialoogvenster [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.

## Verbroken rapport van Verbindingen in de Redacteur van het Web

AEM Gidsen staat u toe om de algemene volledigheid van uw technische documenten te controleren en rapporten van de Redacteur van het Web te produceren. In juni 2023 biedt de release AEM hulplijnen u nu de functie om verbroken koppelingen weer te geven en te herstellen. Dit is een handig rapport waarmee u verbroken koppelingen kunt beheren. U kunt de verbroken verbindingen gemakkelijk bekijken aanwezig in uw kaart DITA en hen ook bevestigen.
![verbroken koppelingsrapport](assets/broken-link-report.png){width="800" align="left"}

Als u een koppeling hebt hersteld, wordt deze niet weergegeven onder de lijst met verbroken koppelingen.

Zie voor meer informatie [verbroken koppelingen weergeven en corrigeren](../user-guide/reports-web-editor.md#report-broken-links).

## Verbeteringen aan schema

### Gebruik rapportinstructies om te controleren op regels in Schematron

AEM Guides steunt nu ook de verklaringen in het verslag met de Schematron. Een rapportverklaring produceert een bericht wanneer een testverklaring aan waar evalueert. Als u bijvoorbeeld wilt dat de korte beschrijving uit maximaal 150 tekens bestaat, kunt u een rapportinstructie definiëren om de onderwerpen te controleren waarvoor de korte beschrijving uit meer dan 150 tekens bestaat.

Voor meer informatie, bekijkt u [Instructies voor bevestigen en rapporteren gebruiken om op regels te controleren](../user-guide/support-schematron-file.md#schematron-assert-report).

### Regex-expressies gebruiken

U kunt Regex-expressies ook gebruiken om een regel met de functie match() te definiëren en vervolgens validatie uit te voeren met het Schematron-bestand.

Voor meer informatie, bekijkt u [Regex-expressies gebruiken](../user-guide/support-schematron-file.md#schematron-assert-report).


### abstracte patronen definiëren

AEM Hulplijnen ondersteunen ook abstracte patronen in Schematron. U kunt generische abstracte patronen definiëren en deze abstracte patronen opnieuw gebruiken. Abstracte patronen kunnen uw Schematron-schema vereenvoudigen en u helpen uw validatielogica te beheren en bij te werken.


Voor meer informatie, bekijkt u [abstracte patronen definiëren](../user-guide/support-schematron-file.md#schematron-abstract-patterns).

## Ondersteuning voor XLIFF-indeling in vertaling

AEM Hulplijnen bieden ook ondersteuning voor de XLIFF-indeling (XML Localization Interchange File Format) bij het vertalen. U kunt nu ook kiezen voor **Nieuw XLIFF-vertaalproject maken** om de XML-inhoud om te zetten in de XLIFF-indeling. AEM Hulplijnen ondersteunen XLIFF versie 1.2.

Met deze indeling kunt u de inhoud exporteren naar de industriestandaard XLIFF-indeling en deze indeling vervolgens aan de vertaalbureaus aanbieden. Voor meer informatie, bekijkt u [Een vertaalproject maken](../user-guide/translate-documents-web-editor.md#create-translation-project).

![soorten vertaalprojecten](assets/translation-project-types.png){width="350" align="left"}


## Verbeteringen voor kaartverzameling

Met een kaartverzameling kunt u meerdere toewijzingen ordenen en in batches publiceren. Er zijn veel nieuwe verbeteringen aangebracht in de kaartverzameling:

* Nu kunt u native voorinstellingen voor PDF-uitvoer toevoegen aan een kaartverzameling en deze gebruiken om de PDF-uitvoer te genereren.
* U kunt de algemene voorinstellingen en voorinstellingen van het mapprofiel die door de beheerder zijn gemaakt, weergeven en deze gebruiken om de PDF-uitvoer te genereren.
* U kunt nu niet alleen een individuele voorinstelling selecteren, maar u kunt ook alle voorinstellingen voor het mapprofiel voor een DITA-kaart in één keer inschakelen.
  ![een kaartverzameling bewerken](assets/edit-map-collection.png){width="800" align="left"}

Voor meer informatie, bekijkt u [Kaartverzameling gebruiken voor het genereren van uitvoer](../user-guide/generate-output-use-map-collection-output-generation.md).

## Native PDF-ondersteuning in Dashboard voor bulkpublicaties


Met de functie AEM bulkactivering van hulplijnen kunt u uw inhoud snel en eenvoudig activeren, van ontwerpen tot het publiceren van een exemplaar. In de kaart van de Activering van het Bulk, kunt u de Inheemse vooraf ingestelde PDF output, de AEM Plaats, PDF, HTML5, Douane, en output JSON omvatten.
Voor meer informatie, bekijkt u [Bulkactivering van gepubliceerde inhoud](../user-guide/conf-bulk-activation.md).

## Verbeterd gereedschap Bulk verplaatsen

Als beheerder kunt u nu het verbeterde gereedschap Bulkverplaatsing gebruiken om mappen met een groot aantal bestanden van de ene naar de andere locatie te verplaatsen.
In het dialoogvenster Bladeren kunt u de bronmappen selecteren die u wilt verplaatsen. U kunt ook bladeren om de bestemmingsplaats te selecteren om de bronomslagen te bewegen. Selecteren ![info icon](assets/info-icon.svg) {width="25" align="left"} in de buurt van een veld voor meer informatie.

Voor meer informatie, bekijkt u [Bestanden bulksgewijs verplaatsen](../user-guide/authoring-file-management.md#move-files-bulk).

## Verbeterd deelvenster Favorieten

Met AEM hulplijnen kunt u een verzameling of favoriete lijst met bestanden en mappen maken en deze gemakkelijk gebruiken. Nu **Opties** is ook beschikbaar in het dialoogvenster **Favorieten** deelvenster. U kunt de naam van de geselecteerde verzameling wijzigen of deze verwijderen uit het dialoogvenster **Opties** -menu. U kunt de **Vernieuwen** om een nieuwe lijst met bestanden of mappen op te halen uit de opslagplaats. U kunt de inhoud van de map ook weergeven in de interface Middelen.

![het deelvenster Favorieten](assets/favorites-options.png){width="650" align="left"}

>[!NOTE]
>
> U kunt de lijst ook vernieuwen met de opdracht **Vernieuwen** bovenaan.

Voor meer informatie over de **Opties** menu van een inzameling van Favorieten, bekijk **Favorieten** functiebeschrijving in het dialoogvenster [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.

## Overschakelen naar het systeemthema

U kunt nu ook het apparaatthema gebruiken. Met de **Gebruikersvoorkeuren** kunt u AEM hulplijnen configureren om automatisch te schakelen tussen lichte en donkere thema&#39;s op basis van het thema van uw apparaat.

![gebruikersvoorkeuren](assets/device-theme-user-preferences.png){width="550" align="left"}

Voor meer informatie bekijkt u de **Gebruikersvoorkeuren** functiebeschrijving in het dialoogvenster [Hoofdwerkbalk](../user-guide/web-editor-features.md#id2051EA0G05Z) sectie.
