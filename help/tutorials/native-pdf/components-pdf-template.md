---
title: Native PDF-publicatiefunctie | Componenten van een PDF-sjabloon
description: Leer de diverse componenten van een malplaatje van de PDF en hoe te om hen aan te passen en te vormen.
exl-id: 0ddb3b81-42ca-4a66-be7d-051a5175d53a
source-git-commit: e8a912b0f8bc690fceade0b54bb36057a727ab33
workflow-type: tm+mt
source-wordcount: '4947'
ht-degree: 0%

---

# Componenten van een PDF-sjabloon {#components-pdf-template}

Een PDF-sjabloon heeft vier componenten: Pagina-indelingen, Stijlbladen, Bronnen en Instellingen. U kunt een sjabloon maken door deze afzonderlijke componenten aan te passen en de sjabloon aan een uitvoervoorinstelling te koppelen tijdens het genereren van een PDF-uitvoer. In de volgende secties worden deze componenten en hun aanpassingsproces uitgebreid besproken.


## Paginalay-outs maken en aanpassen {#create-customize-page-layout}

Met de instellingen in de component Pagina-indelingen kunt u de structuur van een pagina ontwerpen door de koptekst, voettekst en het inhoudsgebied op een pagina te definiëren. Met behulp van de WYSIWYG-paginaopmaakeditor kunt u een paginalay-out maken voor verschillende secties in een PDF, zoals de voorpagina&#39;s en de achteromslag, het hoofdstuk, de inhoudsopgave, de index, de lege pagina, de voorpagina&#39;s, de achterste basispagina&#39;s, de lijst met figuren (LOF), de lijst met tabellen (LOT), de woordenlijst of een indeling voor een aangepaste pagina maken. In de het malplaatjemontages van de PDF, kunt u een paginalay-out met verschillende secties binnen een PDF toewijzen, die dan worden gebruikt om de output van de PDF te produceren.

### Een nieuwe pagina-indeling maken {#create-page-layout}

>[!NOTE]
>
>Er zijn voorbeeldpaginalay-outs die uit de doos worden verzonden. U kunt deze aanpassen of nieuwe paginalay-outs maken.

1. Ga in de webeditor naar de **Uitvoer** tab.
1. Vouw de linkerzijbalk uit en klik op **Sjablonen**.
1. Open de sjabloon waarmee u wilt werken.

   >[!NOTE]
   >
   >U kunt een sjabloon openen door te dubbelklikken op de naam of op het pictogram > naast de naam.

1. Voer een van de volgende handelingen uit om een nieuwe pagina-indeling te maken:

   * Overslaan **Pagina-indelingen** en klik op de knop (*Opties* pictogram) **...** en kiest u **Nieuwe paginalay-out**.


   * In de **Sjablonen** klikt u op de knop **+** pictogram naast **Sjablonen** en kiest u **Pagina-indeling** in het contextmenu.


     Hierdoor wordt het **Lay-out toevoegen** in.

     <img src="assets/add-layout-2.png" alt="Dialoogvenster Lay-out toevoegen" width="250">

1. Geef een naam op voor de nieuwe pagina-indeling.
   >[!NOTE]
   >
   >Gebruik geen speciale tekens wanneer u een paginalay-out een naam geeft. Een spatie in de naam wordt vervangen door een onderstrepingsteken &quot;_&quot;.

1. Klikken **Gereed**.

   De nieuwe indeling wordt gemaakt en toegevoegd onder Pagina-indelingen.


### Een pagina-indeling dupliceren {#duplicate-page-layout}

1. In de **Sjablonen** van de sjabloon die u wilt dupliceren, dubbelklikt u  **Pagina-indelingen** of klik op de knop **>** pictogram voor **Pagina-indelingen**.

   Hiermee wordt de lijst met paginalay-outs in de sjabloon weergegeven.

1. Houd de muis boven de pagina-indeling die u wilt dupliceren en klik op de knop (*Opties* pictogram) **...** en selecteert u **Dupliceren** in het contextmenu.

1. In de _Layout dupliceren_ voert u een naam in voor de pagina-indeling.

1. Klikken **Gereed**.
Onder Pagina-indelingen wordt een kopie van de geselecteerde pagina-indeling gemaakt en toegevoegd.

### Een pagina-indeling aanpassen {#customize-page-layout}

1. In de **Sjablonen** van de sjabloon die u wilt bewerken, dubbelklikt u op **Pagina-indelingen** of klik op de knop **>** pictogram voor **Pagina-indelingen**.

   Hiermee wordt de lijst met paginalay-outs in de sjabloon weergegeven.
1. Voer een van de volgende handelingen uit om een pagina-indeling aan te passen:
   * Dubbelklik op een pagina-indeling.
   * Houd de muisaanwijzer boven een willekeurige pagina-indeling en klik op de knop (*Opties* pictogram) **...** en selecteert u **Bewerken** in het contextmenu.

   Hiermee opent u de pagina-indeling-editor voor aanpassing.
1. Als u de gewenste wijzigingen hebt aangebracht, klikt u op *Alles opslaan* (of `Crl+S`).

   Ga voor meer informatie over het definiëren van afzonderlijke lay-outelementen, zoals kop- en voettekst, paginanummer, titel en meer naar [Een pagina-indeling ontwerpen](design-page-layout.md).

## Stylesheets gebruiken om PDF aan te passen {#stylesheet-customization}

Met de instellingen in de component Stylesheets kunt u de paginalay-outcomponenten en DITA-inhoud opmaken met de WYSIWYG-editor of rechtstreeks met het CSS-bestand werken. U kunt uw eigen stijlen maken of de standaardstijleigenschappen aanpassen. De redacteur WYSIWYG geeft u de toegang tot de meeste eigenschappen die u uw paginalay-out of inhoud DITA zou moeten opmaken. Voor geavanceerde aanpassingen kunt u rechtstreeks in de bronweergave werken.

### Een nieuw stijlblad maken {#create-stylesheet}

Terwijl CSS-bestanden worden geleverd voor inhoud en lay-out, kunt u een nieuwe stijlpagina maken om meerdere aanpassingen toe te passen op een specifiek stijltype dat vervolgens kan worden toegepast op een doelcomponent. Standaard worden CSS-voorbeeldbestanden gebundeld in het product. Deze CSS-bestanden zijn bedoeld om u te helpen bij het ordenen van uw opmaakgegevens over inhoud en lay-outs. U kunt deze stijlen samenvoegen in één CSS-bestand of in meerdere bestanden.

Wanneer u een nieuwe pagina-indeling maakt, worden standaard de `layout.css` wordt opgenomen in de nieuwe pagina-indeling. Als u wilt dat de paginalay-out stijlen uit een ander CSS-bestand bevat, kunt u het gewenste CSS-bestand gewoon slepen en neerzetten in het inhoudsbewerkingsgebied van de nieuwe paginalay-out. Als u wilt controleren of het CSS-bestand is ingesloten in de paginalay-out, schakelt u over naar de bronweergave en vindt u een koppeling naar het CSS-bestand in het dialoogvenster `<head>` element.


Voer de volgende stappen uit om een stijlpagina te maken:
1. In de **Sjablonen** voert u een van de volgende handelingen uit:
   * Houd de aanwijzer boven de **Stijlvoorstellingen** en klik op de knop (*Opties* pictogram) **...** en kiest u **Nieuw stijlblad**.
   * Klik op de knop **+** pictogram naast **Sjablonen** en kiest u **Stijlblad** in het contextmenu.

   Hiermee wordt het dialoogvenster Stijlpagina toevoegen geopend.

   <img src="assets/add-stylesheet.png" alt="Stijlpagina toevoegen" width="250">
1. Geef een naam op voor de nieuwe stijlpagina.
1. Klikken **Gereed**.

   Er wordt een nieuwe stijlpagina gemaakt en toegevoegd onder de sectie Stijlvoorbladen.

### Een nieuwe stijl maken {#create-style}

Standaard bevatten de CSS-bestanden die bij de sjabloon horen stijlen voor kop, alinea, teken, hyperlink, afbeelding, tabel, div, pagina en andere stijlen. U kunt de standaardopmaak overschrijven of een nieuwe stijl maken.


U kunt een nieuwe stijl tot stand brengen om het in de paginalay-out van het malplaatje te gebruiken of een douanestijl voor om het even welk element toepassen DITA. Als u deze aangepaste stijlen op het DITA-element wilt toepassen, moet u ervoor zorgen dat de klassenaam van de stijl gelijk is aan de naam van het DITA-element of aan de naam van `outputclass` kenmerk.  Bijvoorbeeld: `<div>` in DITA wordt beheerst door de `.div {}` in CSS of `outputclass` kenmerk. Indien van toepassing `<div outputclass="my-div">` in DITA wordt het geleid door de `.div {}` of `.my-div {}` in de CSS.



Voer de volgende stappen uit om een nieuwe stijl te maken:
1. Vouw de linkerzijbalk uit en dubbelklik op de sjabloon waarin u de stijl wilt maken.
1. Breid uit **Stijlvoorstellingen** sectie. Het opent de **Stijlen** dat alle opmaakopties bevat.
1. Selecteer + pictogram om een nieuwe stijl toe te voegen.

   **Stijl toevoegen** wordt geopend.


   <img src="assets/add-style.png" alt="Nieuwe stijl toevoegen" width="500"/>

1. Geef een **Klasse** naam. Als u een stijl wilt toepassen op het DITA-element, moet u ervoor zorgen dat de klassenaam van de stijl gelijk is aan de naam van het DITA-element of aan de naam van `outputclass` kenmerk.
1. In de **Tag** (optioneel), kiest u een tag waarvoor u een nieuwe stijl wilt maken.


1. Selecteer een **Pseudo-klasse** om een element op te maken. Met een pseudoklasse kunt u een speciale status van het element definiëren. Gebruik bijvoorbeeld de pseudo-klasse om een element op te maken wanneer u de muisaanwijzer op het element plaatst of wanneer u de focus op het element plaatst. U kunt ook meerdere pseudoklassen selecteren. U kunt bijvoorbeeld pseudo-klasse gebruiken `a::visited {color: blue;}` om de bezochte koppelingen op te maken.

1. Voeg de kiezer voor de nieuwe stijl toe. De **Kiezer** in het veld kunt u naast de combinatie Klasse, Tag en Pseudo-klasse ook aangepaste kiezers toevoegen. U kunt bijvoorbeeld `table a.link` stijl voor alle hyperlinks in een tabel.

   Voor meer informatie over CSS-tags raadpleegt u [Verwijs naar de grammatica van de CSS stijl](https://www.w3.org/TR/CSS21/syndata.html#characters).

1. Klikken **Gereed**.

   Er wordt een nieuwe stijl gemaakt en toegevoegd aan de lijst met stijlen.

### Een vooraf gedefinieerde of nieuwe stijl aanpassen {#customize-style}

Nadat u een nieuw CSS-bestand met standaardstijlen hebt gemaakt of stijlen in een bestaand CSS-bestand wilt aanpassen, kunt u hiervoor de stijleneditor gebruiken.

Voer de volgende stappen uit om een stijl aan te passen:
1. Dubbelklikken **Stijlvoorstellingen** of klik op de knop **>** pictogram voor **Stijlvoorstellingen**.

   Hiermee worden de standaard (Inhoud en Lay-out) en aangepaste CSS-bestanden weergegeven.
1. Open een stijlpagina om te bewerken.

   Voer een van de volgende handelingen uit om stijlpagina te openen voor bewerken:
   * Dubbelklik op de naam van het stijlblad.
   * Houd de muisaanwijzer boven de naam van het stijlblad en klik op (pictogram Opties) ... en kies Bewerken.

   Hiermee wordt het stijlblad geopend voor bewerking en wordt de lijst met stijlen weergegeven in het deelvenster Stijlen.

   <img src="assets/customize-style.png" alt="Stijl aanpassen" width="800">

1. Als u een stijl wilt aanpassen, selecteert u de stijl die u wilt weergeven en past u deze aan met de Stijleditor.


### Eigenschappen van stijlen

In het middelste deelvenster kunt u de eigenschappen bewerken, maar het kan lastig zijn om een opname te krijgen van alle waarden.  De **Eigenschappen** geeft een snelle weergave van alle kenmerken en waarden van de stijl.

In het middelste deelvenster kunt u de veelgebruikte eigenschappen bewerken, maar niet alle eigenschappen die CSS ondersteunt. In de **Eigenschappen** kunt u alle eigenschappen bewerken die CSS ondersteunt en er een voorvertoning van weergeven. U hoeft niet over te schakelen naar de bronweergave om eigenschappen te bewerken.


Meer informatie over het gebruik van de stijleditor voor [werken met algemene inhoudsstijlen](stylesheet.md).

## Werken met bronnen {#work-with-resources}

Dit is een container voor alle elementen die worden gebruikt om een sjabloon te ontwerpen. U kunt de map beschouwen als een map die elementen bevat zoals achtergrondafbeeldingen, aangepaste lettertypen, logo&#39;s en meer. Telkens wanneer u middelen in uw malplaatje toevoegt, wordt het geupload of controleert in de activaomslag. Vervolgens kunt u deze elementen gebruiken om uw PDF-sjablonen aan te passen of te ontwerpen.

Voer de volgende stappen uit om een elementbestand toe te voegen aan de map Resources:

1. Houd de cursor boven het tabblad Bronnen, klik op het pictogram Opties ... en kies Importeren.

   Hiermee wordt het dialoogvenster Elementen uploaden geopend.

   <img src="assets/resources-import-assets.png" alt="Elementen uploaden" width="300">

   Het pad waar het elementbestand wordt geüpload, wordt weergegeven in het dialoogvenster **Map voor middelen selecteren** veld.
   >[!NOTE]
   >
   >U kunt het pad voor het uploaden van elementen niet wijzigen. Standaard worden alle elementen opgeslagen onder de `/content/dam/dita-templates/pdf/<PDF-template-name>` map.

1. Klikken **Bestanden kiezen** om het elementbestand op uw lokale computer te zoeken

1. Klikken **Uploaden**.
Het geselecteerde bestand wordt geïmporteerd en vermeld in de map Bronnen.

## Geavanceerde PDF-instellingen {#advanced-pdf-settings}

Met de sectie Instellingen kunt u de geavanceerde instellingen voor de paginalay-out configureren, de PDF of even pagina starten, de kruisverwijzingen opmaken en drukkermarkeringen inschakelen in de uiteindelijke PDF die de sjabloon gebruikt.

Om te vormen, klik **Instellingen** in de **Sjablonen** voor het weergeven van de volgende opties:

### Algemeen

Stel de basisconfiguratie-instellingen in voor het starten van een hoofdstuk van een oneven of even pagina, de inhoudsopgavestructuur en definieer de opmaak van de leaderregel voor de inhoudsopgave-items. U kunt de volgende instelling definiëren:

* **Een nieuw hoofdstuk starten vanuit**: Hiermee kunt u definiëren hoe elk hoofdstuk in de uiteindelijke PDF wordt gepubliceerd. U kunt kiezen uit een **Nieuwe pagina**, **Oneven pagina**, **Even pagina**, of **Huidige pagina**  opties. Als u ervoor kiest om een nieuw hoofdstuk te beginnen vanaf een oneven pagina, wordt een lege pagina ingevoegd na een hoofdstuk dat op een oneven pagina eindigt. Als uw hoofdstuk bijvoorbeeld eindigt op pagina 15, wordt een lege pagina 16 ingevoegd tijdens het publicatieproces<sup>th</sup> pagina zodat het nieuwe hoofdstuk kan beginnen vanaf de 17<sup>th</sup> pagina.  Als u **Huidige pagina** , worden alle hoofdstukken zonder pagina-einden gepubliceerd. Als een hoofdstuk bijvoorbeeld halverwege pagina 15 eindigt, wordt het volgende hoofdstuk ook vanaf de 15e pagina zelf gestart.

* **Begin elk onderwerp van een nieuwe pagina**: Als u elk onderwerp in uw hoofdstuk van een nieuwe pagina wilt beginnen, dan uitgezocht **Begin elk onderwerp van een nieuwe pagina** -optie. Schakel deze optie uit als u uw onderwerpen wilt voortzetten zonder tussenruimten op de pagina.

* **Structuur van inhoudsopgave**: Hiermee kunt u de hiërarchie van de inhoudsopgave aanpassen. Hiervoor worden de volgende aanvullende instellingen gebruikt:

   * **Koppen tot niveau gebruiken**: Hiermee kunt u het aantal kopniveaus aanpassen dat in de inhoudsopgavestructuur van de PDF moet worden weergegeven.
   * **Geen paginanummer tonen voor eerste niveau in inhoudsopgave**: Selecteer deze optie om de bijbehorende paginanummers te verbergen voor alle hoofdstukken die geneste of onderliggende onderwerpen bevatten. Bekijk het volgende voorbeeld waarin een uitvoer wordt gemaakt zonder deze optie te selecteren.

  <img src="assets/page-number-in-toc.png" alt="Elementen uploaden" width="250">

  In het bovenstaande voorbeeld zijn Geavanceerde instellingen voor PDF, Bijlage en Juridisch het eerste niveau van onderwerpkoppen of hoofdstuktitels. Aan al deze koppen wordt een paginanummer toegewezen.

  Nu, als u deze optie selecteert en de output produceert, dan zult u volgende TOC krijgen:

  <img src="assets/page-number-missing-in-toc.png" alt="Elementen uploaden" width="250">

  Hier kunt u opmerken dat het eerste hoofdstuk Geavanceerde PDF-instellingen geen paginanummer krijgt, aangezien het geneste of onderliggende onderwerpen heeft. Terwijl een paginanummer indien toegewezen aan Bijlage en Juridisch omdat zij standalone onderwerpen zonder enig kindonderwerp zijn.

* **Hoofdstuknummer niet tonen in de inhoudsopgave** : Selecteer deze optie om de hoofdstuknamen weer te geven zonder de hoofdstuknummers in de inhoudsopgave.   Standaard worden de hoofdstuknummers weergegeven in de inhoudsopgave van de uitvoer van de PDF.
* **Leader-indeling**: Gebruik de vervolgkeuzelijst om lijnen met stippen, ononderbroken lijnen of opvultekens te selecteren om kopniveaus te verbinden met de corresponderende paginanummers.
Voor het toepassen van de inhoudsopgavestructuur en de vormkopniveaus raadpleegt u [Een hoofdstuk-inhoudsopgave toevoegen](design-page-layout.md#add-chapter-toc).

  >[!NOTE]
  >
  >Als u een CSS-ontwikkelaar bent, kunt u de leaderindeling ook rechtstreeks in het CSS-bestand definiëren.

* **Vervolgmarkering tabel gebruiken**: Selecteer deze optie als u markeertekens wilt definiëren voor lange tabellen die zich over meerdere pagina&#39;s uitstrekken.
U kunt de tekst definiëren die voor en na het einde moet worden weergegeven. Een tabel wordt bijvoorbeeld afgebroken op pagina 5 en u definieert `<Continued on page %page-num%>` for **Tekst voor einde**.  Onder aan pagina 5 wordt &quot;Vervolg op pagina 6&quot; weergegeven.

  Taalvariabelen gebruiken om de tekst voor en na het einde van de vervolgmarkering te definiëren. Afhankelijk van de gekozen taal wordt de gelokaliseerde waarde automatisch gekozen in de uitvoer van de PDF. U kunt bijvoorbeeld publiceren `Continued on page %page-num%` als tekst in het Engels en `Fortsetzung auf Seite %page-num%` Duits.

  Overslaan <img src="./assets/info-details.svg" alt= "info icon" width="25"> in de buurt van de optie voor meer informatie over de optie.
* **De verklarende woordenlijsttermijnen van de verbinding aan de verklarende woordenlijstpagina**: Selecteer deze optie om de termen in de woordenlijst als hyperlinks in de inhoud weer te geven en deze te koppelen aan de termen op de woordenlijstpagina. Hierdoor kunnen lezers snel de definitie bekijken van een term die is gedefinieerd in de woordenlijst.

  Als u de termen in de woordenlijst wilt omzetten in hyperlinks, moet u:
   * Inschakelen **Verklarende woordenlijst** in de **Volgorde pagina-indeling** voor een DITA-kaart.
   * Voeg de Verklarende woordenlijst in de Achterpagina&#39;s van de Matter voor een kaart van het Boek toe.

  Als u de pagina Woordenlijst niet inschakelt, worden de termen in de woordenlijst in de inhoud niet geconverteerd naar hyperlinks in de uitvoer van de PDF.
  <!--For more information on using table continuation markers, see Use table continuation markers.-->

### Pagina-indelingen {#page-layouts}

Met de instellingen voor Pagina-indelingen hebt u volledige controle over het opgeven van de paginalay-out die moet worden gebruikt voor een bepaalde sectie van het document. Als u bijvoorbeeld een indeling voor de inhoudsopgave wilt selecteren, klikt u op het vervolgkeuzemenu onder het veld Inhoudsopgave en selecteert u de indeling die u hebt ontworpen om de inhoudsopgave te genereren.

Het is belangrijk om op te merken dat de montages van de boekenkaart een belangrijkheid over de montages van de paginalay-out nemen.

De volgende instellingen zijn beschikbaar in de sectie Pagina-indeling:

<img src="assets/template-page-layout.png" alt="Paginalay-outs" width="550">


**Standaardpagina-indeling**: Selecteer een paginalay-out die als standaardlay-out voor alle pagina&#39;s in uw PDF dienst doet. Dit is de lay-out van de basispagina die op die secties of onderwerpen wordt toegepast waar u geen specifieke paginalay-out hebt gecreeerd.

**Paginalay-out voor verschillende secties**: U kunt een paginalay-out toewijzen met de volgende secties van uw uitvoer van PDF. Als u een paginalay-out voor de verwante sectie hebt ontworpen, dan selecteer het van de drop-down lijst. Als er geen paginalay-outs zijn gemaakt voor een bepaalde sectie, wordt de standaardpagina-indeling toegepast.

* **Hoofdstuk en onderwerp**: U kunt de paginalay-out voor de hoofdstukken en onderwerpen specificeren. De geselecteerde lay-out wordt toegepast op alle hoofdstukken en onderwerpen.

* **Inhoudsopgave**: Als u de indeling van de inhoudsopgavepagina hebt ontworpen, selecteert u **Inhoudsopgave** in de vervolgkeuzelijst en alle inhoudsopgavepagina&#39;s in het document hebben de indeling van de inhoudsopgavepagina.

* **Lijst met figuren en tabellen**: U kunt ook de paginalay-out voor figuren en tabellen opgeven. De geselecteerde lay-out wordt toegepast op alle figuren en tabellen.

* **Index**: Als u een indeling van de indexpagina hebt ontworpen, wijst u deze toe aan de optie Index. Met behulp van de opmaakmodellen kunt u verschillende indexelementen opmaken in de PDF-uitvoer. Indexstijlen gebruiken `.idx-header`, `.idx-footer`, `.idx-body`, `.idx-title`, `.idx-keyword-group`, `.idx-unit`,  `.idx-keyword`, `.idx-name`, `.idx-link` en `.idx-child` om de stijlen voor de elementen van de index aan te passen.

* **Verklarende woordenlijst**: Als u een paginalay-out Woordenlijst hebt, wijst u deze toe aan de optie Woordenlijst.

  De termen in de woordenlijst van de uitvoer van de PDF worden altijd in alfabetische volgorde gesorteerd.

  U kunt ook de tag toevoegen `sort-as` om een sorteersleutel voor de verklarende woordenlijsttermijnen te bepalen. De Gidsen van de Experience Manager gebruikt dan de soortsleutel om de verklarende woordenlijsttermijnen in plaats van de verklarende woordenlijsttermijnen te sorteren. Als u de sorteersleutel niet hebt gedefinieerd, worden de termen in de woordenlijst gebruikt om te sorteren. U kunt bijvoorbeeld de tag toevoegen `sort-as` aan de `glossterm` en stel de waarde in op `A` voor de term &quot;USB&quot; (bijvoorbeeld `<glossterm>USB<sort-as>A</sort-as></glossterm>`). Op dezelfde manier kunt u `sort-as` -tag en de waarde ervan instellen op `B` voor de term &quot;Pen Drive&quot;. Wanneer u deze verklarende woordenlijsttermijnen sorteert, de soortsleutel `A` voor de verklarende woordenlijst verschijnt de term &quot;USB&quot; vóór de soortsleutel `B` voor de verklarende woordenlijst &quot;Pengas&quot;. In de uitvoer van de PDF komt &#39;USB&#39; dus voor &#39;Pen Drive&#39; op de woordenlijstpagina.

  Met behulp van de opmaakmodellen kunt u verschillende woordenboekelementen opmaken in de PDF-uitvoer. De verklarende woordenlijststijlen gebruiken `.glo-header`, `.glo-footer`, `.glo-body`, `.glo-title`, `.glo-unit`, `.glo-link`, en `.glo-term` om de stijlen voor de elementen van de verklarende woordenlijst aan te passen.

  Meer informatie over het gebruik van de stijleditor voor [werken met algemene inhoudsstijlen](stylesheet.md).

* **Voorste basispagina&#39;s en basispagina&#39;s op achtergrond**: Deze paginalay-outs definiëren de opmaak voor de voor- en achterpagina&#39;s in uw boek. Als u de lay-out van de voormaterie hebt ontworpen, kaart het aan **Voorste basispagina&#39;s** -optie. Wanneer u de lay-out van de voormaterie van dropdown selecteert, wordt de voorproeflay-out toegepast op alle onderwerpen in de voorkwestie.

  Als u de lay-out van de achtermaterie hebt ontworpen, kaart het aan **Achterste basispagina&#39;s** -optie. Wanneer u de lay-out van de achtermaterie van dropdown selecteert, wordt de achtermaterialenlay-out toegepast op alle onderwerpen in de achterzaak.

  **Voorste basispagina&#39;s** wordt ook gebruikt als fallback-indeling voor de **Inhoudsopgave**, **Lijst met figuren** en Lijst met tabellen.  Op dezelfde manier **Achterste basispagina&#39;s** wordt ook gebruikt als fallback-indeling voor de **Index** en **Verklarende woordenlijst** schermindelingen. Als u de lay-out voor deze pagina&#39;s niet hebt geselecteerd, wordt de geselecteerde lay-out Pagina&#39;s vóór of achter toegepast.  Als u de lay-out Pagina&#39;s vóór of achter niet hebt geselecteerd, wordt de standaardpaginalay-out op hen toegepast.

* **Pagina-indeling voor lege pagina&#39;s**: U kunt ook de pagina-indeling voor de lege pagina&#39;s opgeven. De geselecteerde indeling wordt toegepast op alle lege pagina&#39;s. Als u bijvoorbeeld een lege paginalay-out hebt ontworpen voor alle lege pagina&#39;s, selecteert u **Leeg** in de vervolgkeuzelijst en alle lege pagina&#39;s in het document hebben de indeling Lege pagina.

* **Voorblad en pagina op achtergrond**: Als u een indeling van de omslagpagina hebt ontworpen, wijst u deze toe aan de **Voorblad** -optie. En als u een lay-out voor de achterpagina hebt, wijst u deze toe aan de **Vorige pagina** -optie. Als er geen lay-outs voor de omslag- of achtergrondpagina zijn gemaakt, wordt de standaardpagina-indeling toegepast.



Zie voor meer informatie over paginalay-outs [Een pagina-indeling ontwerpen](design-page-layout.md).

### Volgorde pagina-indeling {#page-order}

U kunt de volgende secties in uw PDF tonen of verbergen en ook de orde schikken waarin zij in uw definitieve output van de PDF zouden moeten verschijnen:



* Inhoudsopgave
* Hoofdstuk en onderwerp
* Lijst met figuren
* Lijst met tabellen
* Index
* Verklarende woordenlijst
* Visum

  <img src="assets/page-order-advance-settings.png" alt="Paginalay-outvolgorde" width="550">

  Als u geen bepaalde sectie in de uitvoer van PDF wilt tonen, kunt u dat verbergen door de schakeloptie uit te schakelen.

  U kunt ook de volgorde definiëren waarin deze verschillende secties in uw PDF worden gegenereerd. Als u de standaardvolgorde van deze secties wilt wijzigen, selecteert u de stippelbalken om de secties naar de gewenste locatie te slepen.

  >[!NOTE]
  >
  > De instellingen voor volgorde en opname zijn alleen van toepassing op een DITA-kaart. Deze instellingen zijn niet van toepassing op een bladwijzer. De pagina&#39;s in een bladwijzer worden weergegeven in de volgorde van de secties in de bladwijzer.


.
**Hoofdstuk en onderwerpen** layout is altijd standaard ingeschakeld. U kunt niet schakelen.

**Pagina&#39;s samenvoegen**

Standaard beginnen alle secties op een nieuwe pagina. Selecteer de **Vorige pagina** of **Volgende pagina** van de **Samenvoegen met** vervolgkeuzelijst om een sectie samen te voegen met een vorige of volgende pagina. Hierdoor wordt de sectie gepubliceerd in overeenstemming met de geselecteerde pagina in de uitvoer van de PDF. Hierdoor is er geen pagina-einde tussen.

>[!NOTE]
>
> Deze instelling is alleen van toepassing op de sectie en niet op de componenten ervan.  Als u bijvoorbeeld de optie **Vorige pagina** optie voor **Hoofdstuk en onderwerp** de **Hoofdstuk en onderwerp** wordt samengevoegd met de vorige pagina. De verschillende hoofdstukken en onderwerpen worden gepubliceerd volgens de **Algemeen** settings.Bijvoorbeeld in **Nieuwe hoofdstukken starten vanuit de instelling** selecteert u **Oneven pagina** Vervolgens wordt een lege pagina ingevoegd na een hoofdstuk dat op een oneven pagina eindigt.

Wanneer u een sectie samenvoegt tot de vorige of volgende pagina, wordt de inhoud samengevoegd en wordt de stijl toegepast van de doelsectie waarin de inhoud is samengevoegd.

Als u bijvoorbeeld **Inhoudsopgave** en **Hoofdstuk en onderwerpen** en selecteert u de **Volgende pagina** for **Inhoudsopgave** de **Inhoudsopgave** wordt samengevoegd met de volgende sectie, de **Hoofdstuk en onderwerpen**. De stijl van de **Hoofdstuk en onderwerpen** wordt toegepast op de samengevoegde inhoud van beide secties.

De optie Samenvoegen werkt achtereenvolgens, dus als u **Volgende pagina** voor meerdere doorlopende secties worden ze allemaal samengevoegd met de eerste sectie (in de volgende richting), waarvoor deze eigenschap niet is ingesteld. U schakelt bijvoorbeeld **Inhoudsopgave**, **Hoofdstuk en onderwerpen**, **Lijst met figuren**, en **Index**. Als u vervolgens **Volgende pagina** for **Inhoudsopgave**, **Hoofdstuk en onderwerpen**, **Lijst met figuren**, en **Geen** for **Index**, worden ze allemaal samengevoegd met  **Index**.


**Statische pagina&#39;s**

De verschillende paginalay-outs helpen u de output van de diverse secties ontwerpen. Deze secties worden geproduceerd van de kaart DITA terwijl u de output publiceert.
U kunt ook aangepaste paginalay-outs maken en deze als statische pagina&#39;s publiceren in de PDF-uitvoer. Zo kunt u statische inhoud toevoegen, zoals notities of lege pagina&#39;s.

Voer de volgende stappen uit om een aangepaste pagina-indeling toe te voegen:

1. Selecteren **Toevoegen** ![](assets/add-icon.svg) om een nieuwe pagina-indeling toe te voegen. Het deelvenster Paginalay-out toevoegen wordt geopend.
2. Selecteer de pagina-indeling in de lijst en klik op Toevoegen. De nieuwe paginalay-out wordt toegevoegd aan de lijst met paginalay-outs.


U kunt ook de volgende handelingen uitvoeren:

* Selecteer de stippelbalken om de paginalay-out naar de gewenste locatie te slepen.

* Selecteren **Lay-out verwijderen** ![](assets/delete-icon.svg)  om een layout te verwijderen.

* U kunt ook een statische pagina samenvoegen met de vorige of de volgende pagina.

* U kunt ook meerdere keren een aangepaste indeling toevoegen en bestellen. Hierdoor kunt u de statische inhoud op de juiste wijze publiceren.

  U kunt bijvoorbeeld een aangepaste indeling gebruiken om meerdere keren een statische waarschuwing te publiceren in de uitvoer van PDF.



### Paginaorganisatie

De pagina&#39;s in een PDF-document worden doorgaans gepubliceerd op basis van de inhoud die is geordend in de DITA-kaart of het bladwijzerbestand. U kunt echter ook de volgorde van pagina&#39;s in het PDF-document wijzigen. U kunt bijvoorbeeld een document met meerdere pagina&#39;s afdrukken als een boekje. Wanneer u de vellen sorteert, vouwt en niet, is het resultaat één boek met de juiste paginavolgorde.  Je kan het gepubliceerde boek dan lezen als een boek.

<img src="assets/template-page-organization.png" alt="Paginaorganisatie" width="550">


De volgende instellingen zijn beschikbaar onder **Paginaorganisatie** sectie:

#### Paginavolgorde

Selecteer een paginavolgorde die de volgorde bepaalt van de pagina&#39;s in uw PDF-document. U kunt de volgende opties kiezen in het vervolgkeuzemenu:

* **Standaard**: De standaardvolgorde van de pagina&#39;s volgens het bronbestand.
* **Oneven pagina&#39;s eerst**: Alle oneven pagina&#39;s worden vóór alle even pagina&#39;s geplaatst.
* **Even pagina&#39;s eerst**: Alle even pagina&#39;s worden vóór alle oneven pagina&#39;s geplaatst.
* **Omkeren**: De paginavolgorde wordt omgekeerd.
* **Boek**: Alle pagina&#39;s worden geordend als in een boekje.
* **Van rechts naar links**: Alle pagina&#39;s staan in boekvolgorde van rechts naar links.
* **Aangepast**: Definieer een aangepaste volgorde van pagina&#39;s in plaats van een vooraf gedefinieerde volgorde.
   * &quot;a..b&quot; — Alle opeenvolgende pagina&#39;s van a tot en met b.
   * &quot;a,b,c&quot; — Nieuwe paginavolgorde a, b, c.
   * &quot;a*b&quot; — De pagina a wordt telkens herhaald.
   * &quot;-a&quot; — Negatieve paginanummers worden vanaf de laatste pagina teruggeteld en kunnen met andere aangepaste bestellingen worden gecombineerd.
   * &quot;X&quot; — Alle pagina&#39;s van het document. Hetzelfde resultaat als &quot;1..-1&quot;.

U kunt bijvoorbeeld een aangepaste volgorde geven zoals &quot;2,3,5*2,7.10,-1,-2.
De gegeven paginaorde resulteert in een PDF die de volgende paginaaantallen van het originele document heeft, veronderstellend dat het 25 pagina&#39;s totaal heeft: 2, 3, 5, 5,7, 8, 9, 10, 25, 24.

#### Meer dan één pagina per vel configureren

Kies deze optie als u meerdere pagina&#39;s op één vel papier wilt publiceren.  Selecteer vervolgens het aantal rijen en kolommen en publiceer de pagina&#39;s als een raster op één blad. U kunt de pagina&#39;s bijvoorbeeld publiceren als een raster van 2 rijen en 4 kolommen.

Definieer de grootte van het doelblad en de afdrukstand waarin u het blad wilt publiceren. U kunt ook de marge- en opvullingseigenschappen van het blad opgeven.




### Afdrukken

Configureer de afdrukproductie-instellingen om drukkermarkeringen toe te wijzen, selecteer kleurmodellen en geef eigenschappen op voor het afdrukken van de PDF-uitvoer.

* **Drukkermarkeringen**: Wanneer u een document voorbereidt voor afdrukproductie, worden drukkermarkeringen toegevoegd aan de paginagrens om het document tijdens het afdrukken op de juiste wijze uit te lijnen, bij te snijden en kleuren te selecteren. Door een drukkermarkering te selecteren, wordt de paginagrens uitgebreid om de markering aan te passen, die tijdens het afdrukken wordt bijgesneden. U kunt de volgende drukkermarkeringen weergeven in de PDF-uitvoer:
   * **Snijtekens**: Selecteer de optie om een markering in elke hoek van het snijgebied te plaatsen om aan te geven waar het papier na het afdrukken moet worden bijgesneden.
   * **Aflooptekens**: Selecteer deze optie om een markering op elke hoek van het afloopvak te plaatsen om het snijgebied voor de uitgebreide afbeelding aan te geven.
   * **Registratietekens**: Selecteer deze optie om een markering buiten het snijgebied te plaatsen voor het uitlijnen van de verschillende scheidingen in een kleurdocument.
   * **Kleurenbalken**: Selecteer deze optie om een kleurenstrip buiten het bijsnijdgebied toe te voegen om de kleurconsistentie te behouden en de inktdichtheid bij het afdrukken aan te passen.

  De afmetingen van de geselecteerde drukkermarkeringen instellen met de **Lijnbreedte**, **Lijnkleur**, en **Breedte van afloopvak** opties.

* **Grootte van mediavak**: Dit is de algemene paginagrootte inclusief het uitgebreide gebied dat wordt ingenomen door drukkermarkeringen. Gebruik de vervolgkeuzelijst om het paginaformaat te selecteren voor de PDF-uitvoer of om uw eigen aangepaste grootte te maken.

* **Kleurruimte**: U kunt kiezen uit RGB- of CMYK-kleurruimten om het PDF-document af te drukken. Kies RGB om de gegenereerde PDF digitaal en CMYK weer te geven voor fysiek afdrukken. Kleuren die in het document zijn gedefinieerd, worden omgezet in de gekozen kleurruimte.
  >[!NOTE]
  >
  >Een ICC-kleurprofiel is vereist voor het maken van PDF/A-kleuren als u CMYK-kleurruimte gebruikt.

  <!--For more information on applying these print settings, see *Printing preferences*.-->

### Kruisverwijzingen {#cross-references}

Gebruik de **Kruisverwijzing** om te definiëren hoe de kruisverwijzingen worden gepubliceerd in de PDF. U kunt de kruisverwijzingen opmaken voor onderwerptitel, tabellen, figuren en meer.

>[!NOTE]
>
> Als u de koppelingstekst hebt gedefinieerd terwijl u de kruisverwijzing invoegt, heeft deze voorrang op de opmaak voor kruisverwijzingen die is gedefinieerd in de sjabloon Native PDF.

U kunt ook variabelen gebruiken om een kruisverwijzing te definiëren.  Wanneer u een variabele gebruikt, wordt de waarde ervan gekozen uit de eigenschappen. U kunt een kruisverwijzing definiëren met behulp van één variabele of een combinatie van variabelen. U kunt ook een combinatie van een tekenreeks en een variabele gebruiken.

U kunt bijvoorbeeld `View details on {chapter}`. Als de naam van het Hoofdstuk &quot;Algemene montages is,&quot;is de verwijzing in de output &quot;zie details op Algemene montages.&quot;

AEM de Gidsen verstrekt de volgende uit-van-de-doos variabelen:

* {title}: Hiermee maakt u een kruisverwijzing naar de titel van het onderwerp. Zie bijvoorbeeld Nuttige koppelingen op pagina 2.
* {page} Hiermee voegt u een kruisverwijzing toe aan de paginanummers. Zie bijvoorbeeld op pagina 1.
* {description}: Voegt een kruisverwijzing toe aan de tekst van de beschrijving. Zie bijvoorbeeld de details van AEM hulplijnen.
* {chapter}: Voegt een kruisverwijzing toe aan de hoofdstuknummers. Zie bijvoorbeeld hoofdstuk 1.
* {bookmarkText}: hiermee maakt u een kruisverwijzing naar de tekst met bladwijzer. Zie stop_words bijvoorbeeld op pagina 5.
* {captionText}: Hiermee maakt u een kruisverwijzing naar het bijschrift van de figuur of tabel in het onderwerp. Zie bijvoorbeeld Airflow op pagina 2.
* {figure}: Voegt een kruisverwijzing toe aan het figuurnummer. Kies deze optie om het figuurnummer te kiezen uit de stijlen voor automatische nummering die u voor figuren hebt gedefinieerd.  U kunt bijvoorbeeld &quot;Zie {figure} op pagina {page}&quot;. De kruisverwijzing in de uitvoer bevat het automatisch gegenereerde figuurnummer en het bijbehorende paginanummer &quot;Zie Figuur 1 op pagina 5&quot;.
* {table}: Voegt een kruisverwijzing toe aan het tabelnummer. Hiermee selecteert u het tabelnummer op basis van de stijlen voor automatische nummering die u voor het bijschrift hebt gedefinieerd. U kunt bijvoorbeeld &quot;Zie {table} op pagina {page}&quot;. De kruisverwijzing in de uitvoer bevat het automatisch gegenereerde tabelnummer en het bijbehorende paginanummer &quot;Zie Tabel 1 op pagina 5&quot;.



  >[!NOTE]
  >
  >U kunt automatische nummerstijlen maken voor bijschrift- en figuurcodes.

#### Standaardindeling voor kruisverwijzing

Als u het tekstveld leeg laat en u de koppelingstekst niet hebt gedefinieerd terwijl u een kruisverwijzing invoegt, voegt de Experience Manager Guides de volgende variabelen toe voor de desbetreffende kruisverwijzingen:

* **Titel**: `{title}`
* **Beschrijving**: `{description}`
* **Alinea**: `{bookmarkText}`
* **Bladwijzer**: `{bookmarkText}`
* **Figuur**: `{captionText}`
* **Tabel**: `{captionText}`

De prioriteitsvolgorde voor kruisverwijzingen is:
* Tekst koppelen die is toegevoegd aan de kruisverwijzingen
* Opmaak voor kruisverwijzingen gedefinieerd in de sjabloon Native PDF
* Standaardindeling voor kruisverwijzing


#### Taalvariabelen in kruisverwijzingen

U kunt ook taalvariabelen gebruiken om gelokaliseerde kruisverwijzingen te definiëren. Afhankelijk van de gekozen taal wordt de gelokaliseerde waarde automatisch gekozen in de uitvoer van de PDF.

U kunt bijvoorbeeld een taalvariabele &quot;reference-label&quot; toevoegen en de waarden in het Engels en het Duits definiëren.

* Engels - &quot;View on page {page}&quot;
* Duits - &quot;Einzelheiten finden Sie auf der Seite {page}&quot;


Wanneer u `${lng:<variable name>}` in de sectie Alinea bevatten de kruisverwijzingen in de alinea&#39;s van de uitvoer de gelokaliseerde tekst en het paginanummer.\
In de volgende schermafbeeldingen ziet u bijvoorbeeld de kruisverwijzingen &quot;Weergeven op pagina 1&quot; in het Engels en &quot;Einzelheiten finden Sie auf der Seite 1&quot; in het Duits.

<img src="./assets/english-output-corss-reference.png" alt="Engelse uitvoer van een kruisverwijzing in een alinea" width ="800" border="2px">

*Een kruisverwijzing in een alinea die wordt gepubliceerd in de Engelse taal.*

<img src="./assets/german-output-corss-reference.png" alt="Duitse uitvoer van een kruisverwijzing in een alinea" width ="800" border="2px">


*Een kruisverwijzing in een alinea die in het Duits wordt gepubliceerd.*

<!--For more information, see *Format cross-references*.-->
