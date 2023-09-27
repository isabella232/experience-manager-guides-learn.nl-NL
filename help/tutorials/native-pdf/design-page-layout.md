---
title: Native PDF-publicatiefunctie | Een pagina-indeling ontwerpen
description: Leer hoe u uw paginalay-out kunt ontwerpen om informatie in verschillende gedeelten van uw PDF-uitvoer weer te geven.
exl-id: b4d3bdc4-0d01-46eb-b182-540380220485
source-git-commit: 5abcc887a24d838caabdf9a34a84ebc851ed4cbf
workflow-type: tm+mt
source-wordcount: '4807'
ht-degree: 0%

---


# Een pagina-indeling ontwerpen {#design-page-layout}

Bij het maken van een PDF-document hebt u verschillende secties voor het weergeven van verschillende soorten informatie. Een PDF-document begint bijvoorbeeld op een voor- of omslagpagina, waarop het logo, de boektitel of de versiegegevens van uw bedrijf staan. Dan zouden er hoofdstukken, aanhangsels, of verklarende woordenlijstpagina&#39;s zijn. Elke sectie in een PDF-document ziet er anders uit en dat wordt bereikt door het maken en aanpassen van de paginalay-out.

Wanneer u de pagina-indeling ontwerpt, kunt u de verschillende elementen definiëren die samen een pagina vormen. U kunt bijvoorbeeld het paginaformaat, de marges, de kop- en voettekst, de afdrukstand en andere paginaspecificaties op een pagina definiëren. Met de functie Eigen PDF publiceren kunt u uw pagina ontwerpen op basis van de [Paginamedia, standaarden](https://www.w3.org/TR/css-page-3/). De meeste instellingen die onder de normen voor gepagineerde media vallen, kunnen eenvoudig worden aangepast met de gebruikersinterface van de functie Native PDF Publishing. Voor sommige andere opmaak op geavanceerd niveau kunt u de Bronweergave gebruiken om uw eigen CSS-code te schrijven.

Nadat u de paginalay-outs hebt ontworpen, moet u deze lay-outs koppelen aan de desbetreffende secties in de instellingen voor Pagina-indeling PDF. Zie de [Paginalay-outs maken en aanpassen](components-pdf-template.md#create-customize-page-layout) voor meer informatie over het maken en openen van een pagina-indeling voor aanpassing.

## Typen paginalay-outs {#types-of-page-layout}

Een PDF-document bevat doorgaans de volgende secties:

* Voorblad
* Inhoudsopgave
* Opheffing van cijfers
* Tabellen optillen
* Hoofdstuk- of onderwerppagina&#39;s
* Verklarende woordenlijst
* Index
* Vorige pagina

Deze secties hebben een overeenkomstige paginalay-out nodig om de informatie in een specifiek formaat voor te stellen. Bovendien kunt u ook een lege pagina hebben die als vulteken wordt gebruikt om een nieuw hoofdstuk van een oneven of even pagina te beginnen. In dat geval kunt u de standaardpagina-indeling gebruiken of een pagina-indeling voor een lege pagina maken. Zie [Een nieuwe pagina-indeling maken](components-pdf-template.md#create-page-layout) voor meer informatie .

De instellingen voor Pagina-indelingen onder het dialoogvenster **Sjabloon>Instellingen** kunt u definiëren welke paginalay-out moet worden gebruikt voor verschillende gedeelten van uw PDF. Elke paginalay-out kan nog andere varianten van de eerste, rechter of linkerpagina hebben.

### De eerste, rechter of linkerpaginalay-outvarianten maken {#page-layout-variants}

De verschillende paginalay-outs in uw PDF sjabloon kunnen verder worden aangepast door verschillende lay-outvarianten voor de eerste, rechter of linkerpagina te hebben. U kunt deze pagina&#39;s anders ontwerpen met de ontwerper van de paginalay-out.

>[!NOTE]
>
>Als u voor een sectie in uw boek één pagina-indeling wilt gebruiken, hoeft u de paginalay-outs Eerste, Rechts of Links niet te maken.

Houd rekening met de volgende punten bij het maken van de paginalay-outs:

>[!NOTE]
>
>De volgende punten hebben de pagina van het Hoofdstuk lay-out als voorbeeld genomen. Deze punten zijn echter ook geldig voor andere paginalay-outs.

* Als u één paginalay-out voor alle pagina&#39;s binnen een hoofdstuk wilt gebruiken, dan zou u slechts één enkele lay-out van de hoofdstukpagina zonder enige variant creëren.

* Als u voor de eerste pagina voor hoofdstukken in uw boek een andere look en feel wilt hebben, moet u een variant voor de eerste paginalay-out voor de hoofdstukken maken.

* Als u voor elke linker- en rechterpagina van uw boek een andere vormgeving wilt gebruiken, moet u voor de lay-out van de hoofdstukpagina de varianten Links en Rechts maken.

* Als u de hoofdstukken van een oneven of even pagina wilt beginnen, kunt u ervoor kiezen om een paginalay-out voor de lege pagina te maken. Deze paginalay-out wordt gebruikt om de hiaat tussen twee hoofdstukken te vullen om ervoor te zorgen dat het hoofdstuk van de gewenste oneven of even pagina begint.

  >[!NOTE]
  >
  >Als u geen afzonderlijke lege pagina-indeling maakt, wordt de standaardpagina-indeling gebruikt. Zie voor het maken van een pagina-indeling [Een nieuwe pagina-indeling maken](components-pdf-template.md#create-page-layout).

In het volgende voorbeeld wordt het maken van varianten van een paginalay-out doorlopen:

1. Maak een pagina-indeling Hoofdstuk met de stappen onder &quot;Een nieuwe pagina-indeling maken&quot;.

   Er wordt een lege pagina-indeling voor het hoofdstuk gemaakt en toegevoegd onder Paginalay-outs.

   Wanneer u een paginalay-out maakt, wordt deze standaard ook geopend voor bewerking. In de volgende schermafbeelding wordt een lege (standaard)paginalay-out weergegeven:

   <img src="./assets/default-blank-page-layout.png" width="300">

   Standaard worden de kop-, voettekst- en inhoudsgebieden in een sjabloon gemaakt. U kunt deze gebieden eenvoudig aanpassen met de pagina-eigenschappen, de inhoudseigenschappen en verschillende gereedschappen (zoals het invoegen van afbeeldingen, velden en meer) die in de gebruikersinterface zijn opgegeven.

   >[!NOTE]
   >
   >Voor geavanceerde configuratie kunt u de Bronweergave gebruiken en uw aangepaste HTML- en CSS-code toevoegen.

1. Muisknop boven de **Hoofdstuk** lay-out, en klik **Opties** om het contextmenu weer te geven.

1. Klikken of muisaanwijzer **Lay-outvariabele toevoegen** en kiest u de gewenste pagina-indeling (Eerste, Links of Rechts) die u wilt maken.

De geselecteerde paginalay-out wordt gecreeerd gebruikend een exemplaar van de lay-out van het basisHoofdstuk. Dit betekent dat als u wijzigingen hebt aangebracht in de standaardpagina-indeling van het hoofdstuk, dezelfde wijzigingen worden overgenomen in de variant-paginalay-out op het moment dat u de pagina-indeling maakt.

## Werken met de pagina-eigenschappen van een pagina-indeling {#page-props-page-layout}

Bij het ontwerpen van een pagina-indeling is het van essentieel belang dat u controle hebt over verschillende pagina-eigenschappen. Met de functie Native PDF publiceren worden alle pagina-eigenschappen onder het deelvenster Pagina-eigenschappen ingekapseld. In het deelvenster Pagina-eigenschappen hebt u toegang tot verschillende eigenschappen onder de volgende secties:

>[!NOTE]
>
>In het deelvenster Pagina-eigenschappen worden de eigenschappen ingekapseld en worden de regels gevolgd die zijn gedefinieerd onder de [Paginamedia, standaarden](https://www.w3.org/TR/css-page-3/).

* **Paginaformaat** : Geef het paginaformaat op dat u wilt gebruiken voor de paginalay-out. In de vervolgkeuzelijst Paginaformaat kunt u kiezen uit meer dan 15 pagina-formaten. U kunt ook een pagina-indeling maken met een aangepast paginaformaat. Zie [Paginaformaat instellen](#set-page-size) voor meer informatie .

* **Afdrukstand** : Geef de afdrukstand op die u voor de paginalay-out wilt gebruiken. U kunt kiezen uit de stand Staand of Liggend. U kunt verschillende richtingen toepassen op verschillende paginariabelen in een paginalay-out. Als uw inhoud bijvoorbeeld een brede tabel of een grote afbeelding bevat, kunt u een liggende paginalay-out maken en die lay-out toepassen op de bredere tabel of afbeelding.

* **Weergave roteren** : Geef de zijde of richting op waarin de oorspronkelijke bovenzijde wordt weergegeven na de rotatie. U kunt kiezen uit 90 graden rechtsom, 90 graden linksom of 180 graden linksom. Dit is zeer nuttig in een situatie waarin u een combinatie van de lay-outs Staand en Liggend in uw output wilt gebruiken. U kunt bijvoorbeeld Staand gebruiken als de algemene pagina-indeling en u kunt een liggende pagina-indeling instellen voor het weergeven van brede tabellen. In dat geval kunt u instellen dat de tabelinhoud 90 graden rechtsom wordt weergegeven. Op die manier wordt de pagina liggend georiënteerd en wordt de inhoud 90 graden gedraaid om de continuïteit in de weergave te behouden. We zullen later in dit gedeelte zien hoe dit wordt bereikt als voorbeeld.

* **Pagina-nummering** :De paginanummering is standaard doorlopend in een PDF. Een PDF van 100 pagina&#39;s kan bijvoorbeeld een doorlopend paginanummer van 1 tot en met 100 bevatten. U kunt de nummering ook opnieuw starten vanaf een bepaald nummer in alle verschillende secties of vanaf het eerste exemplaar van een sectie.
   * **Opnieuw starten vanaf** : Geef het paginanummer op vanaf waar de nummering voor deze paginalay-out begint. U kunt bijvoorbeeld voor elk hoofdstuk het paginanummer instellen om opnieuw te beginnen. In dat geval, moet u het nieuwe begin van bezit aan 1 op de Eerste variant van de paginalay-out van de lay-out van de hoofdstukpagina plaatsen. De paginanummering gaat standaard verder vanaf de vorige pagina.

   * **Alleen toepassen op de eerste instantie**: U kunt ook alleen beginnen met een specifiek nummer voor de eerste instantie van een sectie. U kunt bijvoorbeeld alleen het eerste hoofdstuk starten vanuit 1 en de paginanummers voor andere hoofdstukken voortzetten.

* **Layout** : Geef paginamarges op samen met opvulling voor de boven-, onder-, linker- en rechterzijde. In de volgende afbeelding wordt uitgelegd hoe marges, opvulling en randen rondom de inhoud worden weergegeven. De marge boven en onder aan een pagina bevat de kop- en voettekst.

  <img src="./assets/margins-padding-illustration.png" width="300">

* **Achtergrond** : Neem een afbeelding of kleur op als de achtergrond van de paginalay-out. Voor een afbeelding kunt u de hoogte en breedte van de afbeelding opgeven, samen met de eigenschappen voor herhaling en positie.

* **Voetnoot** : Geef de eigenschappen op om voetnoten in de uitvoer weer te geven. U kunt de eigenschappen voor marges en opvulling en een randstijl opgeven.

### Paginaformaat instellen {#set-page-size}

Het allereerste dat u in een paginalay-out moet bepalen is de paginagrootte. In de Pagina-eigenschappen zijn er meer dan 15 pagina-formaten die u kunt kiezen voor een pagina-indeling. U kunt ook een aangepast paginaformaat maken door de volgende stappen uit te voeren:

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie [Een pagina-indeling aanpassen](components-pdf-template.md#customize-page-layout) voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Klik in het rechterdeelvenster op **Pagina-eigenschappen**.
1. In de **Paginaformaat** vervolgkeuzelijst, selecteert u **Aangepast**.

   De velden Paginabreedte en Paginahoogte worden weergegeven.

1. Geef de gewenste pagina-afmetingen op in het dialoogvenster **Paginabreedte** en **Paginahoogte** velden.

   >[!NOTE]
   >
   >Enkele van de meest gebruikte eenheden zijn px (pixels), pt (punten), rem, em, % (percentage) en in (inches).

### Oriëntatie en rotatie van de pagina gebruiken {#page-orientation-rotation}

Kijk naar een voorbeeld waarin een combinatie van de afdrukstand Staand en Liggend wordt gebruikt en rotatie-eigenschappen worden weergegeven. In dit voorbeeld maken we een PDF met de standaardoriëntatie Staand, maar een tabel wordt liggend weergegeven met inhoud in de 90 graden rechtsom. De uiteindelijke uitvoer ziet er ongeveer als volgt uit:

<img src="./assets/portrait-landscape-page-layouts.png" width="400">

In de bovenstaande uitvoer wordt de contactlijst weergegeven in de modus Liggend, waarbij de inhoud ook 90 graden wordt gedraaid. De resterende inhoud wordt weergegeven in de modus Normaal staand.

Om dit soort output te bereiken, moeten wij de volgende belangrijkste taken uitvoeren:

1. Maak een pagina-indeling met de stand Liggend.

1. Wijzig de **Weergave roteren** eigenschap om inhoud weer te geven in 90°.

1. Maak een aangepaste stijl voor de nieuwe pagina-indeling.

1. Voeg de stijl in de definitie van de outputklasse van de lijst toe die wij in de liggende paginalay-out willen teruggeven.

Voer de volgende stappen uit om bovenstaande taken te verwezenlijken:

1. Maak een pagina-indeling met de stand Liggend.
   1. Maak een pagina-indeling &quot;Liggend&quot; met de stappen onder &quot;Een nieuwe pagina-indeling maken&quot;.

   1. Klik in het rechterdeelvenster op **Pagina-eigenschappen**.

      <img src="./assets/page-properties-panel.png" width="300">
   1. Wijzig de **Afdrukstand** tot **Liggend**.

1. Wijzig de eigenschap Weergave rotatie om inhoud met de wijzers van de klok mee weer te geven in 90°.

   1. Selecteren **90° rechtsom** in de vervolgkeuzelijst Weergave roteren.
   <img src="./assets/view-rotation-page-props.png" width="300">

   1. Klikken **Alles opslaan** om de bijgewerkte eigenschappen van de paginalay-out op te slaan.

1. Maak een aangepaste stijl voor de nieuwe pagina-indeling.
   1. Vouw de linkerzijbalk uit en dubbelklik op de sjabloon waarin u de stijl wilt maken.

   1. Vouw de sectie Stijlbladen uit.

   1. Houd de muisaanwijzer boven de lay-outstijlpagina en klik op de knop (_Opties_ pictogram) ... en kies Bewerken.

      De lay-outstijlpagina wordt geopend voor bewerking.

   1. Rechtsklik ingeschakeld **Overige stijlen** en kiest u **Nieuwe stijl**.
      <img src="./assets/stylesheet-other-new-style.png" width="300">

   1. Typ in het pop-upmenu Stijl toevoegen **landschapsstijl** in de **klassenaam**.
      <img src="./assets/stylesheet-new-landscape-style.png" width="400">

   1. Klikken **Gereed**.

      Een nieuwe stijl met de naam `.landscape-style` wordt gemaakt en toegevoegd aan het einde van de lijst Andere stijlen.

   1. Dubbelklik op de knop `.landscape-style` stijl om deze te openen voor bewerking.

   1. Breid uit **Paginering** eigenschap.

   1. Enter `Landscape` in de **Pagina-indeling** eigenschap.

      <img src="./assets/new-style-with-landscape-layout.png" width="500">

   1. Klikken **Alles opslaan** om de bijgewerkte stijleigenschappen op te slaan.

1. Voeg de stijl toe in het dialoogvenster `outputclass` De definitie van de tabel die u wilt weergeven in de liggende pagina-indeling.
   1. Open in een DITA-bestandseditor het bestand waarop u de nieuwe paginalay-out wilt toepassen.

   1. Zoek de `<table>` -element, dat moet worden weergegeven in de modus Liggend.

   1. Klik in de breadcrumb op het tabelelement om de tabel te selecteren.

      <img src="./assets/new-style-table-element.png" width="400">

   1. Klik in het rechterdeelvenster en open het deelvenster Eigenschappen van inhoud.

   1. Voeg een nieuwe **outputklasse** eigenschap met **landschapsstijl** als eigenschapswaarde.

      <img src="./assets/new-style-table-outputclass.png" width="300">

1. Klikken **Alles opslaan** om het bijgewerkte bestand op te slaan.
1. Genereer de PDF-uitvoer.

In de uiteindelijke PDF wordt de tabelinhoud liggend weergegeven, zoals in het begin van het voorbeeld wordt getoond.

### Een achtergrondafbeelding toevoegen {#add-bg-image}

Gebaseerd op uw vereisten, zou u een achtergrondbeeld kunnen willen toevoegen dat op elke eerste pagina van de output van het Hoofdstuk (PDF) verschijnt. Met de eigenschappen Achtergrond onder Pagina-eigenschappen kunt u eenvoudig een achtergrondafbeelding toevoegen. U kunt ervoor kiezen deze afbeelding over een pagina te repliceren en de afbeelding op een willekeurige positie boven, onder of in het midden van de pagina te plaatsen.

Als u bijvoorbeeld een achtergrondafbeelding wilt invoegen in het middelste gedeelte van het inhoudsgebied, voert u de volgende stappen uit:

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie [Een pagina-indeling aanpassen](components-pdf-template.md#customize-page-layout) voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Klik ergens in het inhoudsgebied.

1. Klik in het rechterdeelvenster op **Pagina-eigenschappen**.

1. Breid uit **Achtergrond** sectie.

1. Klik op de knop Bladeren in het dialoogvenster **Pad afbeelding** locatieveld

1. Blader naar de afbeelding die u als achtergrondafbeelding wilt gebruiken en selecteer deze.

   De afbeelding wordt ingevoegd en gerepliceerd om de hele pagina te bedekken.

1. Wijzig de afbeeldingsgrootte door de eigenschappen voor hoogte en breedte aan te passen.

   >[!NOTE]
   >
   >U kunt een van de eigenschappen voor hoogte of breedte invoeren, omdat de afbeelding automatisch wordt geschaald om de hoogte-breedteverhouding te behouden.

1. Stel de andere eigenschappen in om de manier aan te passen waarop de achtergrondafbeelding moet worden weergegeven.

   * **Achtergrond herhalen** : Geef op of de achtergrond moet worden herhaald.

   * **Achtergrondpositie** : Geef een positie op voor de achtergrondafbeelding op de pagina.

In de volgende schermafbeelding wordt de achtergrondafbeelding weergegeven met de eigenschap Achtergrond herhalen ingesteld op _niet herhalen_ en de eigenschap Achtergrondpositie is ingesteld op _middelpunt_.

<img src="./assets/background-image.png" width="500">

## Werken met koptekst en voettekst voor pagina {#work-header-footer}

Wanneer u informatie opneemt in een kop- of voettekst in een paginalay-out, wordt die informatie herhaald op alle pagina&#39;s die die paginalay-out gebruiken. Doorgaans wordt het koptekstgebied gebruikt voor hoofdstuk- of onderwerptitel en wordt het voettekstgebied gebruikt voor het weergeven van paginanummers.

Wanneer u een nieuwe paginalay-out maakt, worden standaard de kop- en voettekstgebieden gemaakt. U kunt een groot aantal aanpassingen uitvoeren in de kop- en voettekst van een pagina-indeling. U kunt bijvoorbeeld een afbeelding (zoals een logo), variabelen (met dynamische informatie) of statische inhoud invoegen.

### De kop- en voettekstmarges en -lijnen wijzigen {#header-footer-margins}

Standaard zijn de kop- en voettekstmarges ingesteld op 1 inch. U kunt deze standaardwaarde wijzigen door de instelling Marge te wijzigen in het deelvenster Pagina-eigenschappen. Voer de volgende stappen uit om de grootte van de kop- en voettekst te wijzigen:

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie [Een pagina-indeling aanpassen](components-pdf-template.md#customize-page-layout) voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Klik in het rechterdeelvenster op **Pagina-eigenschappen**.
1. Breid uit **Layout** sectie.
1. Klik op het slotpictogram naast het pictogram **Marge** eigenschap.
1. Als u de headergrootte wilt wijzigen, voert u de gewenste waarde in in het veld Bovenmarge.

   >[!NOTE]
   >
   >Enkele van de meest gebruikte eenheden zijn px (pixels), pt (punten), rem, em, % (percentage) en in (inches).

1. Als u de voettekstgrootte wilt wijzigen, voert u de gewenste waarde in het veld Ondermarge in.

U kunt de kop- en voettekst zo ontwerpen dat deze meerdere regels bevatten. Voeg hiertoe een \&lt;p> tag met gebruik van Insert HTML Elements (<img src="./assets/insert-html-element-2.svg" width="25">) in het kop- of voettekstgebied.

| _Hoek ontwikkelaar_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Als u rechtstreeks met de CSS- en HTML-code wilt werken, kunt u de margewaarden wijzigen, zoals in het volgende codefragment wordt getoond:

```css
…

<meta name="page-style" content="size:A4 portrait;margin-top:3cm;margin-right:30pt;margin-bottom:1in;margin-left:90px;" />

…
```

>[!NOTE]
>
>In het bovenstaande voorbeeld worden verschillende eenheden gebruikt om de margewaarden op te geven.

### De kop- en voettekst verwijderen {#remove-header-footer}

De kop- en voettekstbedekking in de boven- en ondermarge. Technisch gezien betekent dit dat als u een kop- en voettekst in uw paginalay-out wilt opnemen, u de vereiste ruimte in de boven- en ondermarge moet reserveren.

Als u niet wilt dat een paginalay-out een kop- en voettekst heeft, zijn er twee manieren om dit te bereiken:

* Als u de boven- en ondermarge wilt behouden, laat u het kop- en voettekstgebied leeg.
* Als u de boven- en ondermarge niet wilt behouden (zoals u de voor- en achteromslag van een tijdschrift ontwerpt), kunt u de marges verwijderen door de eigenschappen voor de boven- en ondermarge in te stellen op 0. Er blijft dan geen ruimte over voor de kop- en voettekst.

### Een afbeelding of een logo in de koptekst toevoegen {#add-image-header}

Op basis van uw vereisten kunt u een afbeelding toevoegen die in het koptekstgebied (of een ander deel) van de pagina-indeling wordt weergegeven. Er zijn twee manieren waarop u een afbeelding in uw paginalay-out kunt toevoegen:

* Gebruik een afbeelding uit de sjabloonbronnen.
* Gebruik de \&lt;add image=&quot;&quot;> in de paginaopmaakeditor.

>[!NOTE]
>
>U wordt aangeraden de map Bronnen te gebruiken voor het beheer van al uw sjabloonelementen, zoals afbeeldingen of lettertypen.

Voer de volgende stappen uit om een afbeelding in te voegen zoals het logo van uw bedrijf in het koptekstgebied:

1. Open de vereiste pagina-indeling voor bewerking.

>[!NOTE]
>
>Zie [Een pagina-indeling aanpassen](components-pdf-template.md#customize-page-layout) voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Klik op Koptekst bewerken (<img src="./assets/header-icon.svg" width="25">) om de cursor in het koptekstgebied te plaatsen.

   U kunt ook in het koptekstgebied klikken.

1. Kies een van de volgende methoden om een afbeelding toe te voegen:
1. Klik op de knop **Afbeelding invoegen** (<img src="./assets/insert-image-icon.svg" width="25">) op de werkbalk; in de **Pad selecteren** naar de afbeeldingslocatie bladeren en op **Selecteren** om het in het koptekstgebied op te nemen.
1. Sleep een afbeelding uit de map Resources naar het koptekstgebied.

In de volgende schermafbeelding ziet u een voorbeeldafbeelding die in het koptekstgebied is toegevoegd.

<img src="./assets/image-in-header-area.png" width="500">

Nadat een afbeelding is ingevoegd, kunt u de kenmerken ervan wijzigen om de afbeelding de gewenste vormgeving te geven. De eenvoudigste manier om de manier te wijzigen waarop een afbeelding of een ander element in de paginalay-out eruitziet, is via het deelvenster Eigenschappen van inhoud. Zie [Werken met het deelvenster Eigenschappen van inhoud](#work-with-content-props) voor de diverse eigenschappen die via UI beschikbaar zijn om aan te passen.

### Velden en metagegevens toevoegen {#add-fields-metadata}

Velden zijn erg handig wanneer u een vooraf gedefinieerde informatie wilt invoegen. U kunt bijvoorbeeld een veld Titel hoofdstuk opnemen in het koptekstgebied van uw hoofdstuk dat wordt vervangen door de titel van het hoofdstuk wanneer het wordt gepubliceerd.

Er zijn de volgende categorieën voor gebieden die u in uw paginalay-out kunt opnemen:

* Datum
* Tijd
* Onderwerptitel
* Projecttitel
* Paginanummer
* Totaal pagina
* Titel hoofdstuk
* Hoofdstuknummer
* Metagegevens

Elk van deze veldcategorieën bevat verschillende variaties waarin de veldinformatie kan worden ingevoegd. Een datumveld kan bijvoorbeeld verschillende variaties hebben, zoals `YYYY-MM-DD`, `MM/DD/YY`, `MM/DD/YYYY` enzovoort. Op dezelfde manier kan het paginanummer variaties hebben in de vorm van Romeinse, decimale of zelfs landspecifieke notaties, zoals _Arabisch_, _Devanagari_, _Hebreeuws_ en meer.

Naast de vooraf gedefinieerde velden kunt u ook metagegevens toevoegen als variabelen of velden in de paginalay-out. Deze metagegevens worden opgeslagen in de inhoud van de DITA-bronkaart en kunnen gemakkelijk worden ingevoegd in uw paginalay-out.

U kunt ook de eigenschappen van metagegevens selecteren uit uw elementen en deze toevoegen aan de pagina-indeling. De metagegevens van de elementen worden vervolgens gepubliceerd voor uw PDF-uitvoer. Deze metagegevenseigenschappen van de elementen worden ingesteld op basis van de **Eigenschappen** pagina van de DITA-kaart of het bladwijzerbestand.

>[!NOTE]
>
> De metagegevensvelden worden weergegeven op basis van uw selectie van element of kaart in het deelvenster **Van** vervolgkeuzelijst.


<!--For more information, see [Add fields and metadata](design-page-layout.md#add-fields-and-metadata).-->

In het volgende voorbeeld worden een paginanummer en een hoofdstuktitel ingevoegd in het voettekstgebied van een paginalay-out.

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie [Een pagina-indeling aanpassen](components-pdf-template.md#customize-page-layout) voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Klik op de knop **Voettekst bewerken** (![](./assets/footer-icon.svg)) om de cursor in het voettekstgebied te plaatsen.

   U kunt ook in het voettekstgebied klikken.

1. Voeg een alinea-element in door op de knop **HTML-elementen invoegen** (<img src="./assets/insert-html-element-2.svg" width="25">) en selecteert u Alinea in de lijst met elementen.

1. Klik op de knop **Velden invoegen** (![](./assets/insert-fields-icon.svg)).

   De pop-up Velden verschijnt.

1. Selecteer de **Paginanummer** categorie in de lijst Veld, de **default(1)** paginanummerindeling in de lijst Indeling en klik op **Invoegen**.

   <img src="./assets/insert-page-number-field.svg" width="400">

   >[!NOTE]
   >
   >U kunt ook de opmaak van alle velden bewerken, behalve de standaardindeling. Klik hiertoe op het pictogram Bewerken naast de indeling die u wilt bewerken, breng wijzigingen aan en klik op OK. Zie voor meer informatie [Velden en metagegevens toevoegen](#add-fields-metadata).

   Het veld Standaardpaginanummer wordt ingevoegd in het voettekstgebied van de pagina-indeling.

   <img src="./assets/page-number-field-in-footer.png" width="400">

   De bovenste broodkruimel geeft een overzicht van de elementen waarin de informatie is opgeslagen.

1. Voer een lege spatie in na het veld Paginanummer en klik op de knop **Velden invoegen** pictogram.

1. Selecteer de **Titel hoofdstuk** categorie in de lijst Veld, de **Titel hoofdstuk** formatteren van de lijst van het Formaat, en klik **Invoegen**.

   De _Titel hoofdstuk_ wordt in het voettekstgebied ingevoegd, dat op het moment van publicatie wordt gevuld met de titel van het hoofdstuk. Op dit moment worden het paginanummer en de hoofdstuktitelvelden gescheiden door een spatie.

   <img src="./assets/page-number-topic-title-near-footer.png" width="400">

1. Voer de volgende stappen uit om de hoofdstuktitel rechts uit te lijnen:

   1. Klik op het element Veld op de broodkruimel om het veld Hoofdstuktitel te selecteren.

   1. Klik in het rechterdeelvenster op de knop **Eigenschappen van inhoud** (<img src="./assets/content-properties-icon.png" width="25">).

   1. Breid uit **Layout** eigenschappensectie en stel de **Float** eigenschapswaarde naar **right**.
      <img src="./assets/float-prop-html-content.png" width="400">

      Het veld Titel hoofdstuk wordt rechts van de voettekst van de pagina uitgelijnd.
      <img src="./assets/topic-title-moved-right-footer.png" width="500">


| _Hoek ontwikkelaar_: <img src="./assets/developer-corner-icon.svg" width="25"> |
|---|

Als u direct met de CSS en code van de HTML wilt werken, dan kunt u dit ook bereiken door naar de Bronmening van de paginalay-out te gaan en veranderingen in de code aan te brengen. Het volgende codefragment toont de zelfde footer die door de code wordt geplaatst:

```css
…
<p>

<span data-field="page-number" data-format="default">1</span>

<span data-field="chapter-title" data-format="default" style="float: right">Chapter Title</span>

</p>
…
```

## Werken met inhoudsgebied {#content-area}

Het inhoudsgebied is het grootste gebied in termen van inhoudsruimte. Het inhoudsgebied wordt gevuld met de inhoud van uw onderwerp. In bepaalde speciale gevallen kunt u vaste inhoud toevoegen aan het inhoudsgebied. Deze inhoud wordt gepubliceerd op de opgegeven locatie in de paginalay-out. De kop in de inhoudsopgave, de woordenlijst en de index kunnen bijvoorbeeld worden toegevoegd als tekstbouwsteeninhoud. Deze wordt in de uiteindelijke uitvoer ongewijzigd gepubliceerd. Een ander voorbeeld is de hoofdstukTOC, die typisch op de eerste pagina van elk hoofdstuk wordt toegevoegd.

Een van de meest gebruikte aanpassingen in het inhoudsgebied is de lay-out met meerdere kolommen. Met de krachtige ontwerper van de paginalay-out, kunt u specifieke pagina&#39;s aanpassen om in veelvoudige kolommen terug te geven, terwijl het houden van de inhoud in andere pagina&#39;s in één enkele kolom.

In de volgende secties worden verschillende scenario&#39;s behandeld om het inhoudsgebied aan te passen.

### Een hoofdstuk-inhoudsopgave toevoegen {#add-chapter-toc}

Een inhoudsopgave van een hoofdstuk dient als een snelle referentie voor de lezers om te weten wat er in het hoofdstuk staat. Doorgaans wordt een hoofdstuk-TOC toegevoegd helemaal aan het begin van een hoofdstuk. Dus als u een hoofdstuk-inhoudsopgave wilt gebruiken, kunt u deze toevoegen in het inhoudsgebied van de hoofdstukpaginalay-out of de eerste paginalay-outvariant van een hoofdstuk.

In het volgende voorbeeld wordt een hoofdstuk-TOC ingevoegd in de indeling van de eerste pagina van een hoofdstuk:

>[!NOTE]
>
>Voor deze procedure, wordt verondersteld dat u de Eerste paginariant voor een lay-out van de hoofdstukpagina hebt gecreeerd. Ga voor instructies over het maken van een paginariant naar [De eerste, rechter of linkerpaginalay-outvarianten maken](#page-layout-variants).

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie [Een pagina-indeling aanpassen](components-pdf-template.md#customize-a-page-layout) voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Plaats de cursor in het inhoudsgebied van de pagina-indeling.

1. Klik op de inhoudsopgave Hoofdstuk (<img src="./assets/chapter-toc-icon.svg">).

   De standaardhoofdstukinhoudsopgave wordt ingevoegd in het inhoudsgebied.

   <img src="./assets/chapter-toc-default.png" width="400">

   >[!NOTE]
   >
   >De standaardhoofdstukinhoudsopgave bevat de koppen 1 tot en met 4. Hier is rubriek 1 de titel van het hoofdstuk zelf. Het kan dus zijn dat u de titel van het hoofdstuk niet opnieuw wilt opnemen in de inhoudsopgave of dat u het gewenste niveau van de koppen in de inhoudsopgave wilt verhogen. U kunt de inhoudsopgave aanpassen door de eigenschappen te wijzigen.

1. Open het deelvenster Eigenschappen van inhoud om de niveaus van de koppen van de inhoudsopgave aan te passen.

   Bijvoorbeeld, als u van Rubriek 2 wilt beginnen, dan verander de eerste drop-down lijst in begin 2.

   <img src="./assets/customize-chapter-toc.png" width="400">

   En als u rubrieken tot niveau 5 wilt hebben, dan verander de tweede drop-down lijst in 5. De bijgewerkte inhoudsopgave ziet er als volgt uit:

   <img src="./assets/chapter-toc-updated.png" width="400">

   >[!NOTE]
   >
   >De definitieve gepubliceerde PDF zal slechts de ingangen tonen TOC die op de inhoud in uw hoofdstukken worden gebaseerd. Als u geen niveau 5 rubrieken in een hoofdstuk hebt, zal het niet in de definitieve output worden getoond.

De blik en het gevoel van standaardTOC kunnen worden aangepast gebruikend de stijlbladen. De stijl die begint met `chaptoc-level-#` (zoals `chaptoc-level-1`, `chaptoc-level-2`, enzovoort) worden gebruikt om de stijlen voor de inhoudsopgave van het hoofdstuk aan te passen. <!--For more details on the stylesheet elements used in the TOC and how to customize them, see _Customize default chapter TOC_-->.

>[!IMPORTANT]
>
>Als u momenteel een stijl-update maakt in een stijlpagina, wordt deze mogelijk niet weergegeven in de voorvertoning van de inhoud. De uitvoer wordt echter gerenderd met de bijgewerkte stijlen.

### Werken met paginalay-out met meerdere kolommen {#multi-column-layout}

Paginalay-outs met meerdere kolommen worden veel gebruikt voor het publiceren van tijdschriften of indexen in een boek. Met de functie Eigen PDF publiceren kunt u uw document eenvoudig in meerdere kolommen splitsen. Met verschillende paginalay-outs kunt u ervoor kiezen om alleen een specifieke sectie in meerdere kolommen te verdelen en de andere secties in één (of normale) kolomlay-out te laten.

Voer de volgende stappen uit om een paginalay-out met meerdere kolommen te maken:

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   >Zie [Een pagina-indeling aanpassen](components-pdf-template.md#customize-a-page-layout) voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Als de lay-out met meerdere kolommen wordt toegepast op de inhoud, met uitzondering van de kop- en voettekst, moet u het inhoudselement in de breadcrumb selecteren.

   Wanneer u de inhoudspagina selecteert, worden in het deelvenster Eigenschappen van inhoud de eigenschappen voor Meerdere kolommen weergegeven.

   <img src="./assets/multiple-columns-properties.png" width="400">

1. Gebruik de eigenschappen van meerdere kolommen om de paginalay-out met meerdere kolommen aan te passen:

   * **Aantal kolommen:** Geef het aantal kolommen op dat u de pagina wilt verdelen. Gebruik de pictogrammen Pijl-omhoog en Pijl-omlaag of voer een getal in om het aantal kolommen in te stellen.

   * **Kolombreedte:** Geef de breedte van een kolom op in een lay-out met meerdere kolommen. De grootte wordt standaard ingesteld in pixels (px). U kunt de grootte ook opgeven in pt, rem, em, % of in eenheden.

     >[!NOTE]
     >
     >Als u geen grootte opgeeft, worden de kolommen gelijkmatig verdeeld om in de opgegeven pagina te passen. In de meeste gevallen hoeft u deze waarde niet op te geven.

   * **Tussenruimte kolom** : Geef de ruimte tussen afzonderlijke kolommen op.

   * **Kolombereik** : Als u wilt dat een element in de paginalay-out zich over meerdere kolommen uitstrekt, moet u deze eigenschap gebruiken. Dit wordt bereikt door de stijl van het gewenste element te wijzigen met behulp van de stijlpagina&#39;s. <!--for more information see _Section explaining style customization_-->.

   Als u in uw paginalay-out een bepaalde tekst op de eerste pagina van alle lay-outs van de hoofdstukpagina wilt verschijnen, dan kunt u het aan de Eerste paginafout van de de paginalay-out van het Hoofdstuk toevoegen.

   Zoals in het volgende voorbeeld wordt getoond, wordt de eigenschap Meerdere kolommen voor de koptekst ingesteld op Alles. Dit zorgt ervoor dat, ook al is het document meerdere kolommen, de kop zich over meerdere kolommen beslaat.

   <img src="./assets/element-span-across-columns.png" width="400">

   >[!IMPORTANT]
   >
   >U kunt het bezit van de Kolom van de Breedte op om het even welk element toepassen DITA gebruikend het attribuut van de outputklasse.

   * **Kolomvulling** : Geef op hoe de inhoud kolommen vult. Standaard is dit Balans, waarbij elke kolom wordt gevuld met dezelfde hoeveelheid inhoud.

   * **Kolomregel** : Als u een lijn tussen kolommen wilt hebben, dan gebruik dit bezit om de lijn of de heersende stijlen te bepalen. Geef de waarden op voor Stijl, Kleur en Breedte met liniëring om een lijn tussen kolommen toe te voegen.

## Werken met het deelvenster Eigenschappen van inhoud {#work-with-content-props}

Met het deelvenster Eigenschappen voor inhoud kunt u de vormgeving van de elementen in de paginalay-out eenvoudig bijwerken. De eigenschappen in het deelvenster Eigenschappen van inhoud zijn onderverdeeld in de volgende secties:

* **Lettertype** : Bevat tekstgerelateerde eigenschappen. U kunt Lettertypefamilie, Dikte, Grootte, Tekstdecoratie (als onderstreping, overlijn, doorhaling), Tekststijl (als Vet, Cursief en meer), Tekstuitlijning (als links, rechts, midden of uitgevuld), Wit-spaties afhandelen (als vooraf gedefinieerde indeling, geen tekstomloop, eindspatie en meer), Lijnhoogte, Letterspatiëring en Tekstinspringing instellen.

* **Rand** : Bevat eigenschappen om een rand toe te voegen en op te maken aan een element in uw paginalay-out. U kunt de volgende opties instellen: Rand (als alles, boven, onder, rechts of links), Randstijl (als Effen, Onderbroken, Stippellijnen of meer), Randkleur, Breedte en Straal voor een gebogen rand. In het volgende voorbeeld is een gebogen rand toegevoegd aan het koptekstgebied van de pagina.

  <img src="./assets/border-properties.png" width="500">

* **Layout** : Bevat eigenschappen om de lay-out van een element in uw paginalay-out te vormen. U kunt Hoogte, Breedte, Marges en Opvulling (voor boven, onder, links of rechts), Horizontale of Verticale uitlijning, Zwevend (als Links, Rechts of Geen), Wissen (zoals links, rechts, beide of geen), Positie van element (als absoluut, vast, relatief of meer), Weergeven (als blok, inhoud, repareren of meer), Z Index, Transparantie (door te roteren of schalen) en Oorsprong transformeren (met X- en Y-verschuiving).

* **Achtergrond** : Bevat eigenschappen die een achtergrondafbeelding of kleurschaduw bevatten. U kunt de Afbeeldingsgrootte instellen (door Hoogte of Breedte in te stellen), Achtergrond herhalen (zoals herhalen, niet herhalen, rond of meer) en Achtergrondpositie (zoals links boven, rechts midden, onder of meer).
* **Meerdere kolommen** : Bevat eigenschappen om eigenschappen met meerdere kolommen voor de pagina of om het even welk specifiek element, zoals Hoofdstuk TOC te vormen. Zie voor meer informatie over de eigenschappen en hoe u deze kunt gebruiken [Werken met paginalay-out met meerdere kolommen](#multi-column-layout).
