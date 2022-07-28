---
title: Native PDF-publicatiefunctie | Een pagina-indeling ontwerpen
description: Leer hoe u uw paginalay-out kunt ontwerpen om informatie in verschillende gedeelten van uw PDF-uitvoer weer te geven.
hide: true
hidefromtoc: true
exl-id: b4d3bdc4-0d01-46eb-b182-540380220485
source-git-commit: 651409beb88468bfb5ab35e45028b01fccd91cd5
workflow-type: tm+mt
source-wordcount: '3289'
ht-degree: 0%

---


# Een pagina-indeling ontwerpen

Bij het maken van een PDF-document hebt u verschillende secties voor het weergeven van verschillende soorten informatie. Een PDF-document begint bijvoorbeeld op een voor- of omslagpagina, waarop het logo, de boektitel of de versiegegevens van uw bedrijf staan. Dan zouden er hoofdstukken, aanhangsels, of verklarende woordenlijstpagina&#39;s zijn. Elke sectie in een PDF-document ziet er anders uit en dat wordt bereikt door het maken en aanpassen van de paginalay-out.

Wanneer u de pagina-indeling ontwerpt, kunt u de verschillende elementen definiëren die samen een pagina vormen. U kunt bijvoorbeeld het paginaformaat, de marges, de kop- en voettekst, de afdrukstand en andere paginaspecificaties op een pagina definiëren. Met de functie Native PDF Publishing kunt u uw pagina ontwerpen volgens de CSS-normen voor gepagineerde media. De meeste instellingen die onder de CSS-paginamedia vallen, kunnen eenvoudig worden aangepast met de gebruikersinterface van de functie Native PDF. Voor sommige andere opmaak op geavanceerd niveau kunt u de Bronweergave gebruiken om uw eigen CSS-code te schrijven.

Nadat u de paginalay-outs hebt ontworpen, moet u deze lay-outs koppelen aan de desbetreffende secties in de instellingen voor Pagina-indeling PDF. Zie de _Paginalay-outs maken en aanpassen_ voor meer informatie over het maken en openen van een pagina-indeling voor aanpassing.

## Typen paginalay-outs en hun varianten

Een PDF-document bevat doorgaans de volgende secties:

* Voorblad
* Inhoudsopgave
* Opheffing van cijfers
* Tabellen optillen
* Hoofdstuk- of onderwerppagina&#39;s
* Verklarende woordenlijst
* Index
* Vorige pagina

Deze secties hebben een overeenkomstige pagina-indeling nodig om de informatie in een specifieke indeling weer te geven. Bovendien kunt u ook een lege pagina hebben die als vulteken wordt gebruikt om een nieuw hoofdstuk van een oneven of even pagina te beginnen. In dat geval hebt u een lege paginalay-out nodig.

De instellingen voor Pagina-indelingen onder het dialoogvenster **Sjabloon > Instellingen** kunt u definiëren welke sjabloon moet worden gebruikt voor verschillende gedeelten van uw PDF. Elke paginalay-out kan nog andere combinaties van de eerste, rechter of linkerpagina hebben. Deze worden beheerst door de regels die zijn vastgelegd in de *CSS-paginamedia* normen.

## De eerste, rechter of linkerpaginalay-out maken

De verschillende paginalay-outs in uw PDF sjabloon kunnen verder worden aangepast door verschillende lay-outs voor de eerste, rechter of linkerpagina te hebben. U kunt deze pagina&#39;s anders ontwerpen met de ontwerper van de paginalay-out.

>[!NOTE]
>
>Als u voor een sectie in uw boek één pagina-indeling wilt gebruiken, hoeft u de lay-outs Eerste, Rechts of Links niet te maken.


Houd rekening met de volgende punten bij het maken van de paginalay-outs:

* Als u één pagina-indeling wilt gebruiken voor alle pagina&#39;s in een hoofdstuk, maakt u slechts één pagina-indeling voor het hoofdstuk.
* Als u voor de eerste pagina voor hoofdstukken in uw boek een andere vormgeving wilt hebben, moet u een lay-out Eerste pagina voor de hoofdstukken maken.
* Als u voor elke linker- en rechterpagina van uw boek een andere vormgeving wilt gebruiken, moet u voor de lay-out van de hoofdstukpagina de varianten Links en Rechts maken.
* Als u de hoofdstukken van een oneven of even pagina wilt beginnen, dan zult u een Lege paginalay-out moeten creëren. Deze paginalay-out wordt gebruikt om de hiaat tussen twee hoofdstukken te vullen om ervoor te zorgen dat het hoofdstuk van de gewenste oneven of even pagina begint.

In het volgende voorbeeld wordt het maken van varianten van een paginalay-out doorlopen:

1. Een pagina-indeling &quot;Hoofdstuk&quot; maken met de stappen die onder *Een nieuwe pagina-indeling maken* procedure.

   Er wordt een lege pagina-indeling voor het hoofdstuk gemaakt en toegevoegd onder Paginalay-outs.

   Wanneer u een pagina-indeling maakt, wordt deze standaard ook geopend voor bewerking. In de volgende schermafbeelding wordt een lege (standaard)paginalay-out weergegeven:

   <img src="./assets/default-blank-page-layout.png" width="300">

   Standaard worden de kop-, voettekst- en inhoudsgebieden in een sjabloon gemaakt. U kunt deze gebieden eenvoudig aanpassen met de gereedschappen, pagina-eigenschappen en inhoudseigenschappen in de gebruikersinterface. Voor geavanceerde configuratie kunt u de Bronweergave gebruiken en uw aangepaste HTML- en CSS-code toevoegen.

1. Een variant maken voor de pagina-indeling Hoofdstuk:

   1. Muisknop boven de **Hoofdstuk** lay-out, en klik **Opties** om het contextmenu weer te geven.

   1. Klikken of muisaanwijzer **Lay-outvariabele toevoegen** en kiest u de gewenste pagina-indeling (Eerste, Links of Rechts) die u wilt maken.

   De geselecteerde paginalay-out wordt gecreeerd gebruikend een exemplaar van de lay-out van het basisHoofdstuk. Dit betekent dat als u wijzigingen hebt aangebracht in de standaardpagina-indeling van het hoofdstuk, dezelfde wijzigingen worden overgenomen in de paginalay-out van de variant.

## Werken met afbeeldingen in een paginalay-out

Gebaseerd op uw vereisten, zou u een beeld kunnen willen toevoegen dat op elke eerste pagina van de output van het Hoofdstuk (PDF) verschijnt. De <u>**Afbeelding toevoegen**</u> wordt gebruikt om afbeeldingen in te voegen in een pagina-indeling.

Als u bijvoorbeeld een afbeelding wilt invoegen in het koptekstgebied van de eerste pagina van de hoofdstukuitvoer, voert u de volgende stappen uit:

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie _Een pagina-indeling aanpassen_ voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Klik op Koptekst bewerken (<img src="./assets/header-icon.svg" width="25">) om de cursor in het koptekstgebied te plaatsen.

1. Klik op de inerte afbeelding (<img src="./assets/insert-image-icon.svg" width="25">).

   Het pop-upvenster Pad selecteren wordt weergegeven.

1. Blader naar de afbeeldingslocatie en klik op Selecteren om deze in te voegen in het koptekstgebied.

   In de volgende schermafbeelding ziet u een voorbeeldafbeelding die in het koptekstgebied is toegevoegd.

   <img src="./assets/image-in-header-area.png" width="500">

   Nadat een afbeelding is ingevoegd, kunt u de kenmerken ervan wijzigen om de afbeelding de gewenste vormgeving te geven. De eenvoudigste manier om de manier te wijzigen waarop een afbeelding of een ander element in de paginalay-out eruitziet, gebruikt u daarvoor het deelvenster Eigenschappen van inhoud. Zie _Werken met het deelvenster Eigenschappen van inhoud_ voor de diverse eigenschappen die via UI beschikbaar zijn om aan te passen.

## Werken met velden

Velden zijn erg handig wanneer u een vooraf gedefinieerde informatie wilt invoegen. U kunt bijvoorbeeld een veld Titel hoofdstuk opnemen in het koptekstgebied van uw hoofdstuk dat wordt vervangen door de titel van het hoofdstuk wanneer het wordt gepubliceerd.

Er zijn de volgende categorieën voor gebieden die u in uw paginalay-out kunt opnemen:

* Date
* Time
* Onderwerptitel
* Projecttitel
* Paginanummer
* Totaal pagina
* Titel hoofdstuk
* Hoofdstuknummer
* Metagegevens

Elk van deze veldcategorieën bevat verschillende variaties waarin de veldinformatie kan worden ingevoegd. Een datumveld kan bijvoorbeeld verschillende variaties hebben, zoals `YYYY-MM-DD`, `MM/DD/YY`, `MM/DD/YYYY` enzovoort.

In het volgende voorbeeld voegen we een paginanummer en een onderwerptitel in in het voettekstgebied van onze paginalay-out.

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie _Een pagina-indeling aanpassen_ voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Klik op Voettekst bewerken (![](./assets/footer-icon.svg)) om de cursor in het voettekstgebied te plaatsen.

1. Een alinea-element invoegen door op HTML Elements invoegen te klikken <img src="./assets/insert-html-element-2.svg" width="25"> en selecteert u Alinea in de lijst met elementen.

1. Klik op Velden invoegen ( ![](./assets/insert-fields-icon.svg)).

   De pop-up Velden verschijnt.

1. Selecteer **Paginanummer** categorie in de lijst Veld, de **default(1)** paginanummerindeling in de lijst Indeling en klik op **Invoegen**.

   <img src="./assets/insert-page-number-field.svg" width="400">

   <img src="./assets/transparent-background.png" width="70">

   >[!NOTE]
   >
   >U kunt ook de opmaak van alle velden bewerken, behalve de standaardindeling. Klik hiertoe op het pictogram Bewerken naast de indeling die u wilt bewerken, breng wijzigingen aan en klik op OK.

   Het veld Standaardpaginanummer wordt ingevoegd in het voettekstgebied van de paginalay-out.

   <img src="./assets/page-number-field-in-footer.png" width="400">

   De bovenste broodkruimel geeft een overzicht van de elementen waarin de informatie is opgeslagen.

1. Voer een lege spatie in na het veld Paginanummer en klik op de knop **Velden invoegen** pictogram.

1. Selecteer **Onderwerptitel** categorie in de lijst Veld, de **Hoofdstuk.ptl** titelformaat van de lijst van het Formaat, en klik Tussenvoegsel.

   De `Chapter.ptl` veld, dat wordt gevuld met de titel van het onderwerp op het moment van publicatie, wordt ingevoegd in het voettekstgebied. Op dit moment worden het paginanummer en de onderwerptitelvelden gescheiden door een spatie.

   <img src="./assets/page-number-topic-title-near-footer.png" width="400">

1. Voer de volgende stappen uit om de onderwerptitel rechts uit te lijnen:

   1. Klik op het element van het Gebied op breadcrumb om het gebied van de onderwerptitel te selecteren.

   1. Klik in het rechterdeelvenster op Eigenschappen van inhoud HTML.

      <img src="./assets/right-pane-content-properties.png" width="350">

   1. Breid uit **Layout** eigenschappensectie en stel de **Float** eigenschapswaarde naar **right**.

      <img src="./assets/float-prop-html-content.png" width="350">

      Het veld Onderwerptitel wordt rechts van de voettekst van de pagina uitgelijnd.

      <img src="./assets/topic-title-moved-right-footer.png" width="500">

| _Hoek ontwikkelaar_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Als u direct met de CSS en code van de HTML wilt werken, dan kunt u dit ook bereiken door naar de Bronmening van de paginalay-out te gaan en veranderingen in de code aan te brengen. Het volgende codefragment toont de zelfde footer die door de code wordt geplaatst:

```md
…
<div data-region="footer">
	<p>
		<span data-field="page-number" data-format="default">1</span>
		<span data-field="title" data-format="default" style="float: right">Chapter.plt</span>
	</p>
</div>
…
```

## Een hoofdstuk-inhoudsopgave toevoegen

Een hoofdstuk of een miniinhoudsopgave dient als een snelle referentie voor de lezers om te weten wat er in het hoofdstuk staat. Doorgaans wordt een hoofdstuk-TOC toegevoegd helemaal aan het begin van een hoofdstuk. Dus als u een hoofdstuk-inhoudsopgave wilt gebruiken, kunt u deze toevoegen aan de hoofdpagina-indeling van het hoofdstuk of aan de indeling van de eerste pagina van een hoofdstuk.

In het volgende voorbeeld wordt een hoofdstuk-TOC ingevoegd in de indeling Eerste pagina van een hoofdstuk:

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie _Een pagina-indeling aanpassen_ voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Plaats de cursor in het inhoudsgebied van de paginalay-out.
1. Klik op de inhoudsopgave Hoofdstuk (<img src="./assets/chapter-toc-icon.svg">).

   De standaardhoofdstukinhoudsopgave wordt ingevoegd in het inhoudsgebied.

   <img src="./assets/chapter-toc-default.png" width="400">
    <img src="./assets/transparent-background.png" width="70">

   >[!NOTE]
   >
   >De standaardhoofdstukinhoudsopgave bevat de koppen 1 tot en met 4. Hier, is Rubriek 1 de Titel van het Hoofdstuk zelf. Het kan dus zijn dat u de titel van het hoofdstuk niet opnieuw wilt opnemen in de inhoudsopgave of dat u het gewenste niveau van de koppen in de inhoudsopgave wilt verhogen. U kunt de inhoudsopgave aanpassen door de eigenschappen te wijzigen.

1. Open het deelvenster Eigenschappen voor inhoud HTML om de niveaus van de koppen van de inhoudsopgave aan te passen.

   Bijvoorbeeld, als u van Rubriek 2 wilt beginnen, dan verander de eerste drop-down lijst om van 2 te beginnen.

   <img src="./assets/customize-chapter-toc.png" width="400">

   En als u rubrieken tot niveau 5 wilt hebben, dan verander de tweede drop-down lijst in 5. De bijgewerkte inhoudsopgave ziet er als volgt uit:

   <img src="./assets/chapter-toc-updated.png" width="400">

   <img src="./assets/transparent-background.png" width="70">

   >[!NOTE]
   >
   >De definitieve gepubliceerde PDF zal slechts de ingangen tonen TOC die op de inhoud in uw hoofdstukken worden gebaseerd. Als u geen niveau 5 rubrieken in een hoofdstuk hebt, zal het niet in de definitieve output worden getoond.

## Werken met paginalay-out met meerdere kolommen

Paginalay-outs met meerdere kolommen worden veel gebruikt voor het publiceren van tijdschriften of indexen in een boek. Met de publicatiefunctie Native PDF kunt u uw document eenvoudig in meerdere kolommen splitsen. Met verschillende paginalay-outs kunt u ervoor kiezen om alleen een specifieke sectie in meerdere kolommen te verdelen en de andere secties in één (of normale) kolomlay-out te laten.

Voer de volgende stappen uit om een paginalay-out met meerdere kolommen te maken:

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie _Een pagina-indeling aanpassen_ voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Als de lay-out met meerdere kolommen wordt toegepast op de inhoud, met uitzondering van de kop- en voettekst, moet u het inhoudselement in de breadcrumb selecteren.

   Nadat u de inhoudspagina hebt geselecteerd, worden in het deelvenster Eigenschappen voor HTML-inhoud de eigenschappen voor Meerdere kolommen weergegeven.

   <img src="./assets/multiple-columns-properties.png" width="400">

1. Gebruik de eigenschappen van meerdere kolommen om de paginalay-out met meerdere kolommen aan te passen:

   * **Aantal kolommen:** Geef het aantal kolommen op dat u de pagina wilt verdelen. Gebruik de pictogrammen Pijl-omhoog en Pijl-omlaag of voer een getal in om het aantal kolommen in te stellen.

   * **Kolombreedte:** Geef de breedte van een kolom op in een lay-out met meerdere kolommen. De grootte wordt standaard ingesteld in pixels (px). U kunt de grootte ook opgeven in pt, rem, em, % of in eenheden.

      >[!NOTE]
      >
      >Als u geen grootte opgeeft, wordt de grootte van de kolommen automatisch aangepast aan de opgegeven paginamarges.

   * **Tussenruimte kolom** : Geef de ruimte tussen afzonderlijke kolommen op.

   * **Kolombereik** : Als u wilt dat een element in de paginalay-out zich over meerdere kolommen uitstrekt, moet u deze eigenschap gebruiken. Dit wordt bereikt door de stijl van het gewenste element te wijzigen gebruikend Stylesheets, voor meer informatie zie _\&lt;section explaining=&quot;&quot; style=&quot;&quot; customization=&quot;&quot;>_.

   Als u in uw paginalay-out een bepaalde tekst op de eerste pagina van alle lay-outs van de hoofdstukpagina wilt verschijnen, dan kunt u het aan de Eerste paginafout van de de paginalay-out van het Hoofdstuk toevoegen.

   Zoals in het volgende voorbeeld wordt getoond, wordt de eigenschap Kolom uitstrekken voor de koptekst ingesteld op Alles. Dit zorgt ervoor dat, ook al is het document meerdere kolommen, de kop zich over meerdere kolommen beslaat.

   <img src="./assets/element-span-across-columns.png" width="400">

   <img src="./assets/transparent-background.png" width="70">

   >[!IMPORTANT]
   U kunt het bezit van de Kolom van de Breedte op om het even welk element toepassen DITA.

   * **Kolomvulling** : Geef op hoe kolommen worden gevuld door inhoud. Standaard is dit Balans, waarbij elke kolom wordt gevuld met dezelfde hoeveelheid inhoud.

   * **Kolomregel** : Als u een lijn tussen kolommen wilt hebben, dan gebruik dit bezit om de lijn of heersende stijlen te bepalen. Geef de waarden op voor Stijl, Kleur en Breedte met liniëring om een lijn tussen kolommen toe te voegen.


## Pagina-eigenschappen gebruiken voor andere afdrukstand van de pagina

Bij het ontwerpen van een pagina-indeling is het van essentieel belang dat u controle hebt over verschillende pagina-eigenschappen. Met de functie Native PDF worden alle eigenschappen van de hoofdpagina ingekapseld in het deelvenster Pagina-eigenschappen. In het deelvenster Pagina-eigenschappen hebt u toegang tot verschillende eigenschappen onder de volgende secties:

* **Paginaformaat**: Geef het paginaformaat op dat u voor de paginalay-out wilt gebruiken. In de vervolgkeuzelijst Paginaformaat kunt u kiezen uit meer dan 15 pagina-formaten.

* **Afdrukstand**: Geef de afdrukstand op die u voor de pagina-indeling wilt gebruiken. U kunt kiezen uit de stand Staand of Liggend. U kunt verschillende richtingen toepassen op verschillende paginariabelen in een paginalay-out. U kunt bijvoorbeeld de afdrukstand Staand instellen op de eerste pagina en Liggend op de pagina-indelingen Links en Rechts.

* **Weergave roteren**: Geef de weergave of richting op waarin de inhoud op de pagina wordt weergegeven. U kunt kiezen uit 90 graden rechtsom, 90 graden linksom of 180 graden linksom. Dit is zeer nuttig in een situatie waarin u een combinatie van de lay-outs Staand en Liggend in uw output wilt gebruiken. U kunt bijvoorbeeld Staand gebruiken als de algemene pagina-indeling en u kunt de liggende pagina-indeling instellen voor het vastleggen van lange tabellen. In dat geval kunt u ervoor kiezen de tabelinhoud 90 graden rechtsom weer te geven. Op die manier wordt de pagina liggend georiënteerd en wordt de inhoud 90 graden gedraaid om de continuïteit in de weergave te behouden. We zullen later in dit gedeelte zien hoe dit wordt bereikt.

* **Nummering opnieuw beginnen vanaf**: Geef het paginanummer op vanaf waar de nummering voor deze paginalay-out begint. U kunt bijvoorbeeld een paginalay-out maken voor de sectie Bijlage in uw boek en de nummering instellen om opnieuw te beginnen vanaf 1.

* **Layout**: Geef paginamarges en opvulling op voor de boven-, onder-, linker- en rechterzijde.

* **Achtergrond**: Neem een afbeelding op als achtergrondafbeelding in de paginalay-out. U kunt de hoogte en breedte van de afbeelding opgeven, samen met de eigenschappen voor herhaling en positie.

* **Voetnoot**: Geef de eigenschappen op om voetnoten in de uitvoer weer te geven. U kunt de eigenschappen voor marges en opvulling en een randstijl opgeven.

Zie een voorbeeld waarin een combinatie van de afdrukstand Staand en Liggend wordt gebruikt en rotatie-eigenschappen worden weergegeven. In dit voorbeeld maken we een PDF met de standaardoriëntatie Staand, maar een tabel wordt liggend weergegeven met inhoud in de 90 graden rechtsom. De uiteindelijke uitvoer ziet er ongeveer als volgt uit:

<img src="./assets/portrait-landscape-page-layouts.png" width="400">

In de bovenstaande uitvoer wordt de contactlijst weergegeven in de modus Liggend, waarbij de inhoud ook 90 graden wordt gedraaid. De resterende inhoud wordt weergegeven in de modus Normaal staand.

Om dit soort output te bereiken, moeten wij de volgende belangrijkste taken uitvoeren:

1. Maak een pagina-indeling met de stand Liggend.
1. Wijzig de eigenschap Weergave rotatie om inhoud 90 graden rechtsom te renderen.
1. Maak een aangepaste stijl voor de nieuwe pagina-indeling.
1. Voeg de stijl in de outputklassendefinitie van de lijst toe die wij in de liggende paginalay-out willen teruggeven.

Voer de volgende stappen uit om bovenstaande taken te verwezenlijken:

1. Maak een pagina-indeling met de stand Liggend.
   1. Maak een pagina-indeling &quot;Liggend&quot; met de stappen onder &quot;Een nieuwe pagina-indeling maken&quot;.

   1. Klik in het rechterdeelvenster op **Pagina-eigenschappen**.

      <img src="./assets/page-properties-panel.png" width="300">
   1. Wijzig de **Afdrukstand** tot **Liggend**.

1. Wijzig de eigenschap Weergave rotatie om inhoud 90 graden rechtsom te renderen.

   1. Selecteren **90° rechtsom** in de vervolgkeuzelijst Weergave roteren.

   1. Klikken **Alles opslaan** om de bijgewerkte eigenschappen van de paginalay-out op te slaan.

1. Maak een aangepaste stijl voor de nieuwe pagina-indeling.
   1. Vouw de linkerzijbalk uit en dubbelklik op de sjabloon waarin u de stijl wilt maken.

   1. Vouw de sectie Stijlbladen uit.

   1. Houd de muisaanwijzer boven de lay-outstijlpagina en klik op de knop (_Opties_ pictogram) **...** en kiest u **Bewerken**.

      De lay-outstijlpagina wordt geopend voor bewerking.

   1. Rechtsklik ingeschakeld **Overige stijlen** en kiest u **Nieuwe stijl**.

      <img src="./assets/stylesheet-other-new-style.png" width="300">

   1. In de **Stijl toevoegen** popup, enter `landscape-style` in de **Klasse** naamveld.

      <img src="./assets/stylesheet-new-landscape-style.png" width="400">

   1. Klikken **Gereed**.

      Een nieuwe stijl met de naam `.landscape-style` wordt gemaakt en toegevoegd aan het einde van **Overige stijlen** lijst.

   1. Dubbelklik op de knop `.landscape-style` stijl om deze te openen voor bewerking.

   1. Breid uit **Paginering** eigenschap.

   1. Enter `Landscape` in de **Pagina-indeling** eigenschap.

      <img src="./assets/new-style-with-landscape-layout.png" width="500">

1. Voeg de stijl in de outputklassendefinitie van de lijst toe die wij in de liggende paginalay-out willen teruggeven.

   1. Open in de webeditor het bestand waarop u de nieuwe paginalay-out wilt toepassen.

   1. Zoek de `<table>` -element, dat moet worden weergegeven in de modus Liggend.

   1. Klik in het breadcrumb op de knop `table` -element om de tabel te selecteren.

      <img src="./assets/new-style-table-element.png" width="400">

   1. Klik in het rechterdeelvenster op de knop **Eigenschappen van inhoud** deelvenster.

   1. In de **Eigenschappen van inhoud** een nieuw deelvenster toevoegen `outputclass` eigenschap met `landscape-style` als eigenschapswaarde.

      <img src="./assets/new-style-table-outputclass.png" width="300">

   1. Klikken **Alles opslaan** om het bijgewerkte bestand op te slaan.

   1. Genereer de PDF-uitvoer.

In de uiteindelijke PDF wordt de tabelinhoud liggend weergegeven, zoals in het begin van het voorbeeld wordt getoond.

## Werken met het deelvenster Eigenschappen van inhoud

Met het deelvenster Eigenschappen voor inhoud kunt u de vormgeving van de elementen in de paginalay-out eenvoudig bijwerken. De eigenschappen in het deelvenster Eigenschappen van inhoud zijn onderverdeeld in de volgende secties:

>[!NOTE]
Zie de documentatie bij W3C CSS Page Media Standards voor meer informatie over het gebruik van deze eigenschappen.

* **Attributen**: Bevat eigenschappen ID, Class en Translate. Als u de eigenschap Translate instelt op Nee, wordt de inhoud in dat specifieke element niet vertaald.

* **Lettertype**: Bevat eigenschappen die betrekking hebben op fonts. U kunt Lettertypefamilie, Dikte, Grootte, Tekstdecoratie (als onderstreping, overlijn, doorhaling), Tekststijl (als Vet, Cursief en meer), Tekstuitlijning (als links, rechts, midden of uitgevuld), Wit-spaties afhandelen (als vooraf gedefinieerde indeling, geen tekstomloop, eindspatie en meer), Lijnhoogte, Letterspatiëring en Tekstinspringing instellen.

* **Rand**: Bevat eigenschappen om een grens aan een element in uw paginalay-out toe te voegen en te formatteren. U kunt de volgende opties instellen: Rand (als alles, boven, onder, rechts of links), Randstijl (als Effen, Onderbroken, Stippellijnen of meer), Randkleur, Breedte en Straal voor een gebogen rand. In het volgende voorbeeld is een gebogen rand toegevoegd aan het koptekstgebied van de pagina.

   <img src="./assets/border-properties.png" width="500">

* **Layout**: Bevat eigenschappen om de lay-out van een element in uw paginalay-out te vormen. U kunt Hoogte, Breedte, Marges en Opvulling (voor boven, onder, links of rechts), Horizontale of Verticale uitlijning, Zwevend (als Links, Rechts of Geen), Wissen (als links, rechts, beide of geen), Positie van element (als absoluut, vast, relatief of meer), Weergeven (als blok, inhoud, repareren of meer), Z Index, Transparantie (door te roteren of schalen) en Oorsprong transformeren (met X- en Y-verschuiving).

* **Achtergrond**: Bevat eigenschappen waarmee een achtergrondafbeelding of kleurschaduw wordt opgenomen. U kunt de Afbeeldingsgrootte instellen (door Hoogte of Breedte in te stellen), Achtergrond herhalen (zoals herhalen, niet herhalen, rond of meer) en Achtergrondpositie (zoals links boven, rechts midden, onder of meer).

* **Meerdere kolommen**: Bevat eigenschappen om multi-kolomeigenschappen voor de pagina of om het even welk specifiek element, zoals Hoofdstuk TOC te vormen. Zie voor meer informatie over de eigenschappen en hoe u deze kunt gebruiken _Werken met paginalay-out met meerdere kolommen_.
