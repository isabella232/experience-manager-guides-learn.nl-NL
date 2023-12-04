---
title: Opmerkingen bij de release | Nieuwe functies in Adobe Experience Manager-hulplijnen, release van september 2023
description: Leer de nieuwe en verbeterde functies in de release van Adobe Experience Manager Guides van september 2023 as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 0%

---

# Nieuwe functies in de release van Adobe Experience Manager Guides in september 2023 as a Cloud Service

Dit artikel behandelt de nieuwe en verbeterde functies in versie september 2023 van Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u [Opmerkingen bij de release](release-notes-2023.9.0.md).

## Verbind met een gegevensbron en neem de onderwerpen op

AEM de Gidsen verstrekt uit-van-de-doosschakelaars die u met uw gegevensbronnen helpen verbinden, die tot AEMGidsen een ware inhoudshub maken. Dit geeft u het voordeel om u tijd en inspanning te besparen die anders aan handgegevenstoevoeging of replicatie zouden worden besteed.

Samen met de bestaande uit-van-de-doos schakelaars zoals JIRA en SQL (MySQL, PostgreSQL, SQL Server, SQLite), kan uw beheerder schakelaars voor MariaDB, H2DB, de Uitwisseling van Adobe, en de gegevensbestanden van de Elasticsearch ook vormen. Zij kunnen andere schakelaars ook toevoegen door de standaardinterfaces uit te breiden.

U kunt de gevormde schakelaars onder bekijken **Gegevensbronnen** in de webeditor.

<img src="assets/data-sources.png" alt="Lijst met gegevensbronnen in het deelvenster" width="300">

*Bekijk de verbonden gegevensbronnen.*

U kunt nu ook een onderwerp van een verbonden gegevensbron tot stand brengen. Een onderwerp kan gegevens in diverse formaten, zoals lijsten, lijsten, en paragrafen bevatten. Het staat u ook toe om een kaart DITA voor alle onderwerpen tot stand te brengen. U kunt meta-gegevens aan het onderwerp associëren wanneer het trekken uit een gegevensbron.

Voor meer informatie, bekijkt u [Gegevens uit uw gegevensbron gebruiken](../user-guide/web-editor-content-snippet.md).

## citaten toevoegen aan uw inhoud

Bijschriften zijn verwijzingen naar de informatiebron die aan de inhoud is toegevoegd. Met uitnodigingen kunt u uw geloofwaardigheid herstellen en plagiaat voorkomen. Met uitnodigingen kunnen de lezers de bron vinden en de informatie in de tekst controleren.

In AEM hulplijnen kunt u citaten toevoegen of citaten importeren en deze op de inhoud toepassen. U kunt deze citaten toevoegen vanuit elke bron van boeken, websites en tijdschriften.

Na het opnemen van uw citaten aan uw onderwerpen, kunt u voorproef hen in de Redacteur van het Web. U kunt inhoud met citaten ook publiceren gebruikend Eigen PDF.

![In een deelvenster weergegeven uitnodigingen](assets/citation-panel.png){width="300" align="left"}

*De lijst met citaten weergeven in het deelvenster Cites.*

Voor meer informatie, bekijkt u [Citaten in uw inhoud toevoegen en beheren](../user-guide/web-editor-apply-citations.md).


## Publiceren naar een inhoudsfragment

Inhoudsfragmenten zijn afzonderlijke stukken inhoud in AEM. Het zijn gestructureerde inhoud die is gebaseerd op een inhoudsmodel. Inhoudsfragmenten zijn zuivere inhoud zonder ontwerp- of layoutgegevens. Ze kunnen onafhankelijk van de kanalen worden ontworpen en beheerd die AEM ondersteunen. De modulariteit en de herbruikbaarheid van de inhoudsfragmenten leiden tot meer flexibiliteit, consistentie, efficiëntie en eenvoudiger beheer.

Nu AEM Gidsen een manier biedt om een onderwerp of de elementen binnen een onderwerp aan een inhoudsfragment te publiceren. U kunt een op JSON-Gebaseerde afbeelding tussen een onderwerp en een model van het inhoudsfragment tot stand brengen. Gebruik deze toewijzing om inhoud die in sommige of alle elementen binnen een onderwerp aanwezig is, naar een inhoudsfragment te publiceren.

Maak een hoofdletter van AEM hulplijnen en inhoudsfragmenten en gebruik inhoudsfragmenten op een AEM site. U kunt de details ook extraheren via API&#39;s die worden ondersteund door inhoudsfragmenten.

![optie voor het publiceren van een inhoudsfragment](assets/content-fragment-publish.png){width="550" align="left"}

*Een onderwerp naar een inhoudsfragment publiceren.*

Voor meer informatie, bekijkt u [Publiceren naar een inhoudsfragment](../user-guide//publish-content-fragment.md).

## Verbeteringen voor revisie

AEM Hulplijnen bieden nu een verbeterde mogelijkheid voor revisie met de volgende functies:

### Zoeken in revisieonderwerpen

Het uitvoeren van revisies is een essentieel onderdeel van AEM hulplijnen. Hiermee kunnen de revisoren de documenten controleren die aan hen zijn toegewezen.
U kunt nu naar een onderwerp zoeken door een deel van de tekst van de titel of het bestandspad in te voeren in de zoekbalk van de onderwerpenweergave van het revisiepaneel. U kunt ook alle onderwerpen of onderwerpen met opmerkingen weergeven. Standaard kunt u alle onderwerpen in de overzichtstaak weergeven. Voor meer informatie, bekijkt u [Onderwerpen bekijken](../user-guide/review-topics.md).

![Zoeken in een deelvenster met revisieonderwerpen](assets/review-search-topic.png){width="800" align="left"}

*Een revisieonderwerp zoeken in het deelvenster Review.*



## Guides Extension Framework

Maak aangepaste pakketten boven op AEM hulplijnen voor uitbreidbaarheid met AEM Extension Framework. Deze pakketten zijn nuttig voor ontwikkelaars en consultants en geven ze uitbreidbaarheid aan de componenten in de Editor. Ze kunnen knoppen, dialoogvensters en dropdowns als doel hebben en aangepaste JavaScript toevoegen die eenvoudig kan samenwerken met de gebruikersinterface van AEM hulplijnen.



## Native PDF-verbeteringen

De volgende Native PDF-verbeteringen zijn doorgevoerd in de release van september 2023 om van AEM hulplijnen een robuuster product te maken:



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

In een native PDF-uitvoer beginnen standaard alle secties op een nieuwe pagina. Nu kunt u een sectie samenvoegen tot de vorige of volgende pagina. Hiermee wordt de sectie gepubliceerd in overeenstemming met de geselecteerde pagina in de PDF-uitvoer en is er geen pagina-einde tussen.

Voor meer informatie bekijkt u de **Pagina&#39;s samenvoegen** functiebeschrijving in [Paginavolgorde](../native-pdf/components-pdf-template.md#page-order) sectie.

### Een hoofdstuk vanaf de huidige pagina starten

U kunt de basisconfiguratiemontages voor de aanvang van een hoofdstuk van oneven of even pagina, de structuur van TOC, plaatsen en het formaat van de leaderlijn voor de ingangen van TOC bepalen.

Nu kunt u ook een hoofdstuk starten vanaf de huidige pagina. Als u dit wilt doen, worden alle hoofdstukken zonder pagina-einden verder gepubliceerd. Als een hoofdstuk bijvoorbeeld halverwege pagina 15 eindigt, begint het volgende hoofdstuk ook op de 15e pagina zelf.

Voor meer informatie bekijkt u de **Algemeen** tabbeschrijving in  [Geavanceerde PDF-instellingen](../native-pdf/components-pdf-template.md#advanced-pdf-settings-advanced-pdf-settings).

### Statische pagina&#39;s

U kunt ook aangepaste paginalay-outs maken en deze als statische pagina&#39;s publiceren in de PDF-uitvoer. Zo kunt u statische inhoud toevoegen, zoals notities of lege pagina&#39;s.

Voor meer informatie bekijkt u de **Statische pagina&#39;s** functiebeschrijving in [Paginavolgorde](../native-pdf/components-pdf-template.md#page-order) sectie.


### Variabelen in kruisverwijzingen

U kunt variabelen gebruiken om een kruisverwijzing te definiëren. Wanneer u een variabele gebruikt, wordt de waarde ervan gekozen uit de eigenschappen.

U kunt nu ook {figure} en {table}.
Gebruiken {figure}om een kruisverwijzing naar het figuurnummer toe te voegen. Hierbij wordt het figuurnummer gekozen uit de stijlen voor automatische nummering die u hebt gedefinieerd voor figuren.

Gebruiken {table} om een kruisverwijzing naar het tabelnummer toe te voegen. Hierbij wordt het tabelnummer gekozen uit de stijlen voor automatische nummering die u voor het bijschrift hebt gedefinieerd.

Voor meer informatie, bekijkt u [Kruisverwijzingen](../native-pdf/components-pdf-template.md##cross-references).



### Opnieuw ontwerpen van CSS-editor

De CSS-editor is nu opnieuw ontworpen voor een betere gebruikerservaring met kiezers en stijleigenschappen.

#### Verbetering van dialoogvenster Stijl toevoegen

U kunt nu aangepaste kiezers gebruiken om complexe stijlen toe te voegen. Met het nieuwe veld Selector kunt u naast de combinatie Klasse, Tag en Pseudo-klasse ook aangepaste kiezers toevoegen. U kunt bijvoorbeeld `table a.link` stijl voor alle hyperlinks in een tabel.

![stijlen toevoegen in de native PDF-sjablonen](assets/add-styles-native-pdf.png){width="300" align="left"}

*Voeg de details voor de nieuwe stijl toe.*

#### Stijleigenschappen aanpassen

AEM hulplijnen introduceert u nu een nieuw deelvenster met eigenschappen onder de voorvertoningssectie voor stijlen. U kunt de eigenschappen van de stijlen efficiënter en sneller bewerken in het deelvenster Eigenschappen.


## Ondersteuning van meerdere onderwerpdefinities in één opsommingsdefinitie

U kunt nu een of meer onderwerpdefinities definiëren in een kaart en de opsommingsdefinities in een andere kaart en vervolgens de kaartverwijzing toevoegen. De verwijzingen naar onderwerpopsommingen worden opgelost in dezelfde kaart of in de kaart waarnaar wordt verwezen.

U kunt nu ook voorwaarden definiëren en deze toepassen op bepaalde specifieke elementen in een onderwerp.  De voorwaarden zijn alleen zichtbaar voor die specifieke elementen en niet voor alle andere elementen.

Voor meer details over de behandeling van hiërarchische definities van onderwerpdefinities en opsommingen, bekijk de de eigenschapbeschrijving van de Onderwerpregeling in [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.





## Alle voorinstellingen in een kaartverzameling selecteren

U kunt niet alleen een individuele voorinstelling en alle voorinstellingen van het mapprofiel inschakelen, maar ook alle voorinstellingen voor een DITA-kaart in één keer.
![een kaartverzameling bewerken](assets/edit-map-collection-cs.png){width="800" align="left"}\
*Selecteer alle voorinstellingen in een kaartverzameling.*

Voor meer informatie, bekijkt u [Kaartverzameling gebruiken voor het genereren van uitvoer](../user-guide/generate-output-use-map-collection-output-generation.md).


## Native PDF-ondersteuning in Dashboard voor bulkpublicaties


Met de functie AEM bulkactivering van hulplijnen kunt u uw inhoud snel en eenvoudig activeren, van ontwerpen tot het publiceren van een exemplaar. In de kaart van de Activering van het Bulk, kunt u de Inheemse vooraf ingestelde PDF output, de AEM Plaats, PDF, HTML5, Douane, en output JSON omvatten.
Voor meer informatie, bekijkt u [Bulkactivering van gepubliceerde inhoud](../user-guide/conf-bulk-activation.md).

## Verbeterd gereedschap Bulk verplaatsen

Als beheerder kunt u nu het verbeterde gereedschap Bulkverplaatsing gebruiken om mappen met een groot aantal bestanden van de ene naar de andere locatie te verplaatsen.
In het dialoogvenster Bladeren kunt u de bronmappen selecteren die u wilt verplaatsen. U kunt ook bladeren om de bestemmingsplaats te selecteren om de bronomslagen te bewegen. Selecteren ![info icon](assets/info-icon.svg) {width="25" align="left"} in de buurt van een veld voor meer informatie.

Voor meer informatie, bekijkt u [Bestanden bulksgewijs verplaatsen](../user-guide/authoring-file-management.md#move-files-bulk).


## Verbeterde voorvertoning via het contextmenu

Gebruik het contextmenu om snel een voorvertoning van het bestand weer te geven (.dita, .xml, audio, video of afbeelding) zonder het te openen. U kunt nu het formaat van het voorvertoningsvenster wijzigen. Als de inhoud een referentiekoppeling bevat, kunt u het venster selecteren en openen op een nieuw tabblad.

![Voorvertoningsvenster ](assets/quick-preview_cs.png){width="800" align="left"}

*Geef een voorvertoning van het bestand weer in het deelvenster.*

Zie voor meer informatie over het contextmenu de **Opties voor een bestand** functiebeschrijving in het dialoogvenster [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.


## Variabelen voor huidige datum en tijd gebruiken in de opties Doelpad, Sitenaam of Bestandsnaam

Tijdens het genereren van uitvoer in AEM Site of PDF kunt u variabelen gebruiken voor het instellen van de **Doelpad**, **Sitenaam**, of **Bestandsnaam** opties. U kunt nu ook de opdracht `${system_date}`en `${system_time}` variabelen. Met deze variabelen kunt u de huidige datum en tijd aan deze opties toevoegen.

Leer hoe u [variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam](../user-guide/generate-output-use-variables.md).
