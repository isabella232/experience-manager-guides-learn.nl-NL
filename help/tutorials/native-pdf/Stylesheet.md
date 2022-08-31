---
title: Native PDF-publicatiefunctie | Werken met algemene inhoudsstijlen
description: Leer hoe u gebruiksstijlen maakt en stijlen voor uw inhoud maakt.
hide: true
hidefromtoc: true
source-git-commit: fb341dab718b8ae64578748d54a40df7e71af223
workflow-type: tm+mt
source-wordcount: '3500'
ht-degree: 0%

---


# Werken met algemene inhoudsstijlen

Een stijlpagina bevat de definities van stijlen voor de elementen die in uw uitvoer van PDF worden gebruikt. U kunt ervoor kiezen om met de voorbeeldopmaakmodellen te werken of nieuwe opmaakmodellen te maken. In de meeste gevallen kunt u snel aan de slag door een kopie van de OOTB-voorbeeldstijlpagina te maken.

De stijleneditor is een WYSIWYG-editor die alle complexe aspecten van een CSS-code achter de gebruikersinterface verbergt. Met de stijleditor kunt u de stijlen voor de elementen van uw keuze gemakkelijk en zeer snel aanpassen. De stijlen worden onder de volgende koppen gecategoriseerd:

* Kopstijlen
* Alineastijlen
* Tekenstijlen
* Hyperlinkstijlen
* Afbeeldingsstijlen
* Lijststijlen
* Tabelstijlen
* Div-stijlen
* Paginastijlen
* Overige stijlen

Wanneer het werken met gestructureerde inhoud DITA, is de stijlafbeelding voor de meeste elementen DITA op zijn plaats in het standaardstijlblad. Als u met standaard-DITA-elementen werkt, kunt u hun uiterlijk wijzigen door de stijldefinitie rechtstreeks te wijzigen. Deze stijldefinities zijn beschikbaar onder de categorie Andere stijl. Zie voor meer informatie *Werken met andere stijlen* later in dit onderwerp.

In de volgende secties worden de meest gebruikte stijlinstellingen in de vorm van voorbeelden besproken.

>[!NOTE]
>
>In de volgende voorbeelden wordt aangenomen dat u werkt met het voorbeeldstijlblad dat bij het product wordt geleverd.

## Werken met kopstijlen

Met de kopstijlen worden alle basisstijlen ingekapseld voor de koppen die in de inhoud worden gebruikt. OOTB u zult 6 stijlen van de basisrubriek en een kopstijl voor het onderwerp/het hoofdstuk en de titelrubriek van het bijlage krijgen. In een gestructureerd document, vertegenwoordigt H1 de titel van het onderwerp of van het hoofdstuk en H2 door H6 worden gebruikt voor subonderwerpen of secties binnen een onderwerp/hoofdstuk. Deze hiërarchie van koppen wordt automatisch toegepast op uw inhoud wanneer de overeenkomstige rubriek wordt gevonden.

>[!NOTE]
>
>U kunt uw eigen stijlen van de douanekop tot stand brengen en die kunnen in uw inhoud worden gebruikt gebruikend de outputklasse. Voor meer details, zie Stap 4 in *Oriëntatie en rotatie van de pagina gebruiken* voorbeeld.

### Aangepaste koppen op hoofdstukniveau maken

In een boek (of een boekenkaart), werkt u met Hoofdstuk. De stijlen van de basiskop zijn zodanig ontworpen dat ze zonder aanpassingen op hoofdstukniveau worden toegepast. Als u echter speciale koppen voor uw inhoud wilt maken, moet u die koppen maken. De standaardinstelling `h1.chapter` de kop wordt toegepast op de titel van uw hoofdstuk. Als u de hoofdstuktitel in een andere stijl wilt weergeven, moet u de `h1.chapter` stijl. Op dezelfde manier kunt u aangepaste stijlen voor subkoppen in uw hoofdstuk maken. Als u bijvoorbeeld een aangepaste stijl voor alle twee wilt maken<sup>en</sup> en 3<sup>rd</sup> niveau koppen in uw hoofdstuk, dan moet u een nieuwe stijl tot stand brengen zoals `h2.chatper` en `h3.chatper`.

Aangezien de functie Native PDF Publishing de basisstijldefinities bevat voor de meest voorkomende stijlen, wordt de standaardstijl toegepast op de inhoud, zelfs als u per ongeluk een stijl verwijdert. Als er bijvoorbeeld geen stijldefinitie voor h2-stijl voorkomt in uw stijlblad, wordt met de functie Native PDF publiceren een basisstijl toegepast op h2-inhoud.

In dit voorbeeld maken we een hoofdstukstijl op het tweede niveau:

1. Open de vereiste stijlpagina voor bewerking.
   >[!NOTE]
   >
   >Zie *Een vooraf gedefinieerde of nieuwe stijl aanpassen* voor het openen van een opmaakmodel voor aanpassen of bewerken.

1. In de **Stijlen** lijst, vouw de **Kopstijlen**.
1. Klikken met rechtermuisknop aan op **Kopstijlen** stijl en kies **Nieuwe stijl**.
1. In de *Stijl toevoegen* het dialoogvenster **Tag** name as `h2` en betreden `chapter` in de **Klasse** naamveld.
1. Klikken **Gereed**.

Een nieuwe kopstijl genaamd `h2.chapter` wordt gemaakt en toegevoegd onder de lijst Kopstijlen.

Nadat u een stijl hebt gemaakt, kunt u de vereiste eigenschappen van de stijl aanpassen met de stijleditor.

### Koppen met automatische nummering maken

Één van de het meest algemeen gebruikte outputstijlen is autonumbered rubrieken. Deze rubrieken vertegenwoordigen het hoofdstukaantal, onderwerp en subonderwerpaantallen. De auto-aantalrubrieken zijn verschillend van de lijststijlen waar een lijst van punten binnen een onderwerp auto-aantallen wordt toegewezen.

In dit voorbeeld zullen we de koppen van niveau 1 tot niveau 3 aanpassen om automatische getallen in verschillende indelingen te gebruiken.

1. Open de vereiste stijlpagina voor bewerking.

   >[!NOTE]
   >
   >Zie *Een vooraf gedefinieerde of nieuwe stijl aanpassen* voor het openen van een opmaakmodel voor aanpassen of bewerken.

1. In de **Stijlen** lijst, vouw de **Kopstijlen**.

1. Selecteer **h1** in de lijst.
De eigenschappen voor de h1-stijl worden samen met de voorvertoning weergegeven in het deelvenster Eigenschappen.

   >[!NOTE]
   >
   >In het deelvenster Voorvertoning krijgt u een real-time weergave van alle stijtupdates die u op elk element toepast.

1. Selecteer **Autonumber** eigenschap.

   De stijlen die u op de auto-aantallijst kunt toepassen worden getoond onder het bezit Autonumber.

1. Stel de volgende eigenschappen in:
   * **Stijl**: Maak een keuze uit een groot aantal verschillende, landspecifieke of algemene nummeringsstijlen. U kunt stijlen kiezen zoals Arabisch-Indic, Devanagari, Georgisch, Decimaal, Lower-Alpha en meer. In het huidige voorbeeld selecteert u `upper-alpha`.

   * **Indeling**: De standaardindeling is ingesteld op `<x>`, waarin `x` Deze waarde wordt vervangen door de nummeringsstijl die u in de eigenschap Stijl hebt geselecteerd. Als u bijvoorbeeld `decimal` (1), dan de waarde van `x` auto-stijgingen voor elke instantie van `h1` stijl en heeft de waarde 2, 3 enzovoort. U kunt ook aangepaste tekst in het veld toevoegen om de kopstijl op te maken. Als u bijvoorbeeld wilt dat alle h1-koppen een voorvoegsel hebben van `Chapter`moet u dit veld instellen als `Chapter <x>`.

   * **Teken invoegen**: Als u een speciaal teken wilt toevoegen aan de indeling, klikt u op Teken invoegen (<img src="./assets/insert-chars.png" width="25">). Selecteer het gewenste teken dat u in de stijlindeling wilt toevoegen en klik op Invoegen. Er zijn verschillende typen speciale tekens die u kunt kiezen in de vervolgkeuzelijst Categorie selecteren. In ons voorbeeld selecteert u het rechter aanwijsteken voor dubbele hoek in de categorie Leestekens.

      <img src="./assets/insert-special-chars.png" width="400">


   * **Nummering beginnen vanaf**: Geef die waarde op als u de nummering vanaf een bepaald nummer wilt laten beginnen. Voor ons voorbeeld, houd de standaardwaarde van 1.

   * **Inspringen**: Als u de kop wilt laten inspringen, moet u de waarde voor Inspringen instellen. Stel het bijvoorbeeld in op 0 px.

      >[!NOTE]
      >
      >U kunt de waarde invoeren in px (pixels), pt (punten), rem, em, % (percentage) of in (inches) eenheden.

   * **Breedte voorvoegsel**: Dit is het gebied dat wordt bezet door het auto-aantalformaat. De stijl wordt automatisch ingesteld op een grootte die gemakkelijk geschikt is voor de geselecteerde stijlindeling. Als u de grootte wilt vergroten, kunt u de standaardwaarde vervangen.

      Wanneer u deze waarde handmatig instelt, wijzigt u de andere eigenschappen die van invloed zijn op de breedte. Wijzig bijvoorbeeld de tekengrootte, de opmaak met het voorvoegsel (Hoofdstuk) of een achtervoegsel (:) en stel de maximale waarde in in het dialoogvenster *Nummering beginnen vanaf* en de verschillende fonteigenschappen die de optimale grootte opleveren.

      Voor ons voorbeeld, houd de standaardwaarde.

   * **Tussenruimte**: Geef de horizontale en verticale afstand op. Behoud de standaardwaarden voor ons voorbeeld.

      Met de bovenstaande aanpassingen wordt de stijl aangepast zoals hieronder wordt weergegeven:

      <img src="./assets/h1-style-custmization.png" width="500">

   * **Opmaak toepassen op**: Met de eigenschappen onder de categorie Herfst kunt u de nummeringsstijl definiëren. Als u de nummeringsstijl of de inhoud van de kopindeling verder wilt aanpassen, kiest u Nummering of Alinea in dit veld. Als u Nummering kiest, worden wijzigingen in lettertype, rand, layout en andere categorieën alleen toegepast op de nummeringsstijl in de kop. Als u echter Alinea kiest, worden de wijzigingen toegepast op de inhoud van de kop en niet op de nummeringsstijl.

   Gebruik de volgende instellingen om een uitvoer te genereren die in de volgende schermafbeelding wordt getoond:

   |**Stijl kop**|**Eigenschap**|**Waarde**|**Aanvullende opmerkingen**| | :- | :- | :- | :- | |h1|Stijl|Decimaal|Deze eigenschappen vallen onder de categorie Autonumber | ||Indeling|`Capter <x>:`|| ||Breedte voorvoegsel|160 px|| ||Lettertype > Tekstuitlijning|Links|Zorg dat Opmaak toepassen op is ingesteld op Nummering| |h2|Stijl|Decimaal|Deze eigenschappen vallen onder de categorie Autonumber | ||Indeling|`Section <x>:`|| ||Breedte voorvoegsel|125 px|| ||Lettertype > Tekstuitlijning|Links|Zorg dat Opmaak toepassen op is ingesteld op Nummering| |h3|Stijl|Decimaal|Deze eigenschappen vallen onder de categorie Autonumber | ||Niveau invoegen|2|| ||Indeling|`Section <2>.<x>:`|| ||Breedte voorvoegsel|125 px|| ||Lettertype > Tekstuitlijning|Links|Zorg dat Opmaak toepassen op is ingesteld op Nummering| ||

   <img src="./assets/auto-number-output.png" width="500">

## Werken met alineastijlen

U kunt een alineastijl maken om speciale opmaak toe te passen op een hele alinea. Met de pseudo-klasse kunt u echter een stijl alleen op een bepaald deel van de tekst toepassen. In het volgende voorbeeld maken we een alineastijl die de initiaalstijl gebruikt.

### De stijl van de initiaal maken

In tijdschriften wordt een initiaal (of een vervallen hoofdletter) gebruikt en in literaire documenten waarin het eerste teken van een alinea of sectie een speciale opmaak krijgt. Met de functie Native PDF Publishing kunt u hetzelfde effect bereiken.

In het volgende voorbeeld wordt een initiaalstijl gemaakt:

1. Open de vereiste stijlpagina voor bewerking.

   >[!NOTE]
   Zie *Een vooraf gedefinieerde of nieuwe stijl aanpassen* voor het openen van een opmaakmodel voor aanpassen of bewerken.

1. In de **Stijlen** lijst, vouw de **Alineastijlen**.

1. Klik met de rechtermuisknop op de knop **Alineastijl** en kiest u **Nieuwe stijl**.

1. In de *Stijl toevoegen* het dialoogvenster **Tag** naam als p en in de **Pseudo** **Klasse** veld, selecteren `::first-letter`.

1. Klikken **Gereed**.

   Een nieuwe alineastijl met de naam `::first-letter`  wordt gemaakt en toegevoegd onder de **Alineastijlen** lijst.

1. Selecteren `::first-letter` onder de p-stijl en stel de volgende eigenschappen in:

   * **Lettertype**: Stel het gewenste lettertype in voor de eerste letter in de alinea. Stel de lettertypefamilie bijvoorbeeld in op krompen, tekendikte op 500, tekengrootte op 30 pt en kies een lettertypekleur.

   * **Layout**: Stel de verticale uitlijning van de tekst rond de initiaalstijl in. In ons voorbeeld wordt de verticale uitlijning ingesteld op Onder.

Als de `p` -tag wordt toegewezen aan de `<p>` in DITA, hoeft u deze stijl niet expliciet toe te voegen met het kenmerk outputklasse. Waar in uw inhoud a `<p>` -element wordt gebruikt, wordt de initiaalstijl er automatisch op toegepast. In de volgende schermafbeelding zijn de titel van het hoofdstuk, de korte beschrijving en de elementen uit de definitielijst niet opgemaakt met de initiaalstijl. Alleen de alineastijl wordt opgemaakt met de initiaalstijl:

<img src="./assets/char-style-drop-cap.png" width="500">

## Werken met tekenstijlen

Met behulp van de tekenstijlen kunt u stijlen maken voor het opmaken van tekens of woorden binnen de inhoud. U kunt bijvoorbeeld een tekenstijl voor inline code of bestandsnaam maken of een stijl met meerdere opmaakindelingen voor geselecteerde inhoud.

### Een inline-tekenstijl maken

Het opmaken van inline-tekens of woorden in een alinea komt veel voor. Bij het maken van een inline stijl zijn twee taken betrokken: eerst een nieuwe stijl in het stijlblad maken en vervolgens de stijl in de inhoud toepassen met de opdracht `outputclass` kenmerk.

In het volgende voorbeeld wordt een inline tekenstijl gemaakt:

1. Open de vereiste stijlpagina voor bewerking.

   >[!NOTE]
   Zie *Een vooraf gedefinieerde of nieuwe stijl aanpassen* voor het openen van een opmaakmodel voor aanpassen of bewerken.

1. In de **Stijlen** lijst, vouw de **Tekenstijlen**.

1. Klik met de rechtermuisknop op de knop **Tekenstijl** en kiest u **Nieuwe stijl**.

1. Houd in het dialoogvenster Stijl toevoegen het **Tag** naam als bereik en voer in `BoldItalic` in de **Klasse** naamveld.

   <img src="./assets/create-char-style.png" width="400">

1. Klikken **Gereed**.

   Er wordt een nieuwe tekenstijl met de naam code gemaakt en toegevoegd onder de lijst Tekenstijlen.

1. Selecteren `span.BoldItalic` van de **Tekenstijl** en stel de volgende eigenschappen in:

   * **Lettertype**: Alle eigenschappen met betrekking tot lettertypen kunnen in deze sectie worden aangepast. Standaard worden sommige lettertypen in het product opgenomen. U kunt het gewenste lettertype voor de tekenstijl kiezen. Stel bijvoorbeeld de lettertypefamilie in op *Serif,* en selecteert u *Vet* en *Cursief* in de eigenschap Lettertypestijl. U kunt ook andere lettertype-eigenschappen aanpassen, zoals Dikte lettertypen (zoals vet, lichter), Tekstdecoratie (zoals onderstrepen, onderstrepen), Tekengrootte, Lettertypekleur, Tekstuitlijning, enzovoort.

      >[!NOTE]
      U kunt ook lettertypen toevoegen aan uw sjabloon. Deze lettertypen worden opgeslagen in het gedeelte Bronnen van uw sjabloon. Voor meer informatie over het toevoegen van doopvonten en het werken met Middelen, zie **Een koppeling toevoegen aan de sectie Bronnen**.

   * **Layout**: U kunt indelingseigenschappen instellen, zoals Hoogte en Breedte, Marge, Opvulling, Uitlijning en nog veel meer.

   * **Achtergrond**: Met de Achtergrondeigenschappen kunt u de achtergrondkleur van een bepaalde stijl opmaken. U kunt de achtergrondkleur of afbeelding voor elke stijl definiëren.

Nadat u de inline tekenstijl hebt gemaakt, moet u deze toepassen in de inhoud. Ga naar de bronweergave en voeg de `outputclass` kenmerk in de gewenste inhoud:

`outputclass="BoldItalic"`

In het volgende voorbeeld wordt de indeling Vet-cursief weergegeven die op verschillende plaatsen in de actieve tekst wordt toegepast:

<img src="./assets/char-format-applied.png" width="500">

## Lijststijl aanpassen

De lijststijlen bevatten de standaardstijlinstellingen voor de geordende en ongeordende lijsten. U kunt deze lijststijlen gemakkelijk aanpassen om aan uw documentatievereisten te voldoen.

In het volgende voorbeeld wordt de stijl van de genummerde of geordende lijst aangepast:

1. Open de vereiste stijlpagina voor bewerking.

   >[!NOTE]
   Zie *Een vooraf gedefinieerde of nieuwe stijl aanpassen* voor het openen van een opmaakmodel voor aanpassen of bewerken.

1. In de **Stijlen** lijst, vouw de **Lijststijlen**.

1. Selecteer **ol** in de lijst.

   De eigenschappen voor de oliestijl worden samen met de voorvertoning weergegeven in het deelvenster Eigenschappen.

   <img src="./assets/list-style-default.png" width="500">

1. Selecteer **Geavanceerde opmaak** optie.

   Er wordt een bevestigingsbericht weergegeven.

1. Klikken **Ja** op de *Bevestiging* bericht om de **Geavanceerde opmaak** eigenschappen.

   De volgende eigenschappen zijn standaard beschikbaar:

   * **Niveau**: Standaard zijn er 6 niveaus genummerde lijsten. Het niveau dat u in deze drop-down controles selecteert de stijlveranderingen op het geselecteerde niveau en alle verdere niveaus. Als u bijvoorbeeld niveau 4 selecteert, worden alle stijlwijzigingen die u toepast, ingesteld op niveaus 4, 5 en 6.

   * **Type lijststijl**: Er zijn een aantal lijstnummeringsstijlen waaruit u kunt kiezen. De lijst bevat landspecifieke en generieke nummeringsstijlen waarmee een genummerde lijst wordt gemaakt. Sommige lijststijltypen zijn Arabisch, Cambodjaans, Devanagari, Ethiopic, Hangul, Hebreeuws, Japans, Koreaans, Eenvoudig Chinees, Urdu en meer.

   Verder kunt u met de volgende eigenschappen voor Geavanceerde opmaak werken:

   * **Getalnotatie**: De standaardindeling is ingesteld op `<x>`, waarin `x` De waarde wordt vervangen door de nummeringsstijl die u hebt geselecteerd in de eigenschap Type lijststijl. Als u bijvoorbeeld `decimal` (1), dan de waarde van `x` wordt automatisch verhoogd voor elke instantie van het lijstelement en heeft de waarde 2, 3 enzovoort. U kunt ook aangepaste tekst in het veld toevoegen om de lijststijl op te maken. Als u bijvoorbeeld wilt dat alle lijststijlen op het eerste niveau een achtervoegsel &quot;`)`&quot;, moet u dit veld voor de lijststijl op het eerste niveau instellen als &quot;`<x>)`&quot;.

   * **Teken invoegen**: Als u een speciaal teken wilt toevoegen in de nummeropmaak, klikt u op Teken invoegen (<img src="./assets/insert-chars.png" width="25">). Selecteer het gewenste teken dat u in de stijlindeling wilt toevoegen en klik op Invoegen. Er zijn verschillende typen speciale tekens die u kunt kiezen in de vervolgkeuzelijst Categorie selecteren.

   * **Niveau invoegen**: U kunt het aantal van om het even welke voorafgaande niveaus in uw aantalformaat omvatten. Als u bijvoorbeeld de getalnotatie van het 5e niveau wilt opnemen in de getalnotatie van het 6e niveau, kiest u 5 in de vervolgkeuzelijst Niveau invoegen. Let op: in de vervolgkeuzelijst Niveau invoegen worden alleen de nummers van de voorafgaande niveaus weergegeven en niet het volgende niveau. Als u bijvoorbeeld op niveau 3 werkt, worden in de lijst Niveau invoegen alleen niveaus 1 en 2 weergegeven.

      <img src="./assets/list-insert-level.png" width="400">

      U kunt ook de nummeropmaak wijzigen en zo nodig de lijstwaarden weergeven. Als u bijvoorbeeld een geneste nummeringsstijl gebruikt voor niveau 3, kunt u deze opmaken als &quot;`<2>.<x>))`&quot;. Dit toont lijstnummer 2, gevolgd door een punt, gevolgd door lijstnummer 3 en vervolgens twee haakjes, zoals `2.3))`.

   * **Inspringen**: Als u de lijst wilt laten inspringen, moet u de waarde Inspringen instellen. Wijzigingen in de inspringing kunnen worden gecontroleerd in het deelvenster Voorvertoning en aangepast.

      >[!NOTE]
      U kunt de waarde invoeren in px (pixels), pt (punten), rem, em, % (percentage) of in (inches) eenheden.

   * **Breedte voorvoegsel**: Dit is het gebied dat door het Formaat van het Aantal wordt bezet. Deze wordt automatisch ingesteld op een grootte die gemakkelijk geschikt is voor de geselecteerde indeling. Als u de grootte wilt vergroten, kunt u de standaardwaarde vervangen.

      Wanneer u deze waarde handmatig instelt, wijzigt u de andere eigenschappen die van invloed zijn op de breedte. Wijzig bijvoorbeeld de tekengrootte, de opmaak met voor- of achtervoegsel en de verschillende lettertype-eigenschappen om de optimale grootte te bereiken.

   * **Tussenruimte**: Geef de horizontale afstand tussen de nummeropmaak van de lijst en de inhoud op. De verticale spatiëring bepaalt de tussenruimte tussen de twee lijstitems.

      De volgende schermafbeelding toont de aangepaste geordende lijst voor elk niveau:

      <img src="./assets/list-number-format-final.png" width="500">


## Werken met tabelstijl

Met de stijlpagina&#39;s kunt u ontwerpen *n* aantal tabelstijlen. Met behulp van de tabelstijlen kunt u ontwerpen hoe de volledige tabel, een bepaalde rij of kolom. Met controle bij cel-vlakke het stileren, kunt u zeer presenteerbare lijststijlen tot stand brengen.

In het volgende voorbeeld ziet u hoe u een tabelstijl en de verschillende opties voor tabelopmaak kunt maken die u kunt aanpassen:

1. Open de vereiste stijlpagina voor bewerking.

   >[!NOTE]
   Zie *Een vooraf gedefinieerde of nieuwe stijl aanpassen* voor het openen van een opmaakmodel voor aanpassen of bewerken.

1. In de **Stijlen** lijst, klik met de rechtermuisknop op de **Tabelstijl** en kiest u **Nieuwe stijl**.

1. In de *Stijl toevoegen* het dialoogvenster **Tag** name as `table` en betreden `double-border` in de **Klasse** naamveld.

1. Klikken **Gereed**.

   Een nieuwe tabelstijl met de naam `table.double-border` wordt gemaakt en toegevoegd onder de lijst Tabelstijlen.

1. Selecteren `table.double-border` van de **Tabelstijlen** en stel de volgende eigenschappen in:

   * **Opmaak toepassen op**: U kunt de opmaak van de stijl toepassen op de hele tabel, op oneven/even rijen of kolommen of op de eerste/laatste rij of kolom.

      >[!NOTE]
      De volgende instellingen zijn beschikbaar onder de **Algemeen** delen wanneer **Opmaak toepassen op** is ingesteld op **Hele tabel**.

   * **Tekstomloop**: Selecteer hoe u tekst om de tabel heen wilt laten lopen. Dit is handig wanneer de tabel zich in een ander element op blokniveau bevindt en de tabel samen met andere inhoud in het blokelement moet worden gerenderd. De omloopopties zijn *left* of *right* uitgelijnd, of *none*.

   * **Rand samenvouwen**: Selecteer de vormgeving van de tabelrand. Als u samenvouwen selecteert, wordt er slechts één randlijn tussen de tabelcellen getekend. Voor afzonderlijke stijlen is de rand echter zichtbaar rond elke cel met extra opvulling.

      <img src="./assets/table-style-collapse-separate.png" width="500">

   * **Randafstand**: Deze instelling is alleen beschikbaar als Rand samenvouwen is ingesteld op Afzonderlijk. Met deze instelling kunt u de verticale en horizontale afstand tussen de celranden opgeven.

      <img src="./assets/table-border-spacing.png" width="500">

      >[!NOTE]
      De volgende instellingen zijn beschikbaar onder de **Cel** delen wanneer **Opmaak toepassen op** is ingesteld op **Hele tabel**.

   * **Opvulling**: Geef de opvulling tussen tabelcellen op. U kunt verschillende opvullingswaarden opgeven voor de boven-, onder-, linker- en rechterzijde.

   * **Verticale uitlijning**: Geef de verticale uitlijning voor celinhoud op. Beschikbare opties zijn: Boven, Midden en Onder.

   * **Randzijde, Stijl, Kleur, Breedte, Straal:** Geef de eigenschappen voor de rand op. U kunt ervoor kiezen om alleen randen te hebben aan bepaalde zijden, zoals Links of Rechts. De randstijl geeft een overzicht van de beschikbare randstijlen, zoals Effen, Onderbroken, Dubbele lijn en nog veel meer. Geef de randkleur op met het kleurenpalet. U kunt de randbreedte opgeven in px, pt, rem, em, % en in eenheden. De straal bepaalt de kromme om cirkelhoeken te maken.

   De andere eigenschappen onder Lettertype, Rand, Lay-out, Paginering, en Achtergrond worden verklaard onder andere voorbeelden in dit onderwerp. Afhankelijk van uw selectie in het dialoogvenster **Opmaak toepassen op** eigenschap, kunt u deze waarden toepassen op de gehele tabel of op geselecteerde rijen of kolommen.

   Hieronder ziet u een voorbeeld van een voorbeeldtabel met verschillende rijen die op een andere manier zijn opgemaakt:

   <img src="./assets/table-final-design.png" width="500">

## Werken met andere stijlen

Als u met gestructureerde (DITA) inhoud werkt, dan zult u merken dat bijna alle elementen DITA een stijlafbeelding in het standaardstijlblad hebben. Bijvoorbeeld een `<shortdesc>` de stijl van het element is gedefinieerd onder **Andere stijl** > **.shortdesc** stijldefinitie. U kunt al deze stijlen eenvoudig aanpassen en ze worden automatisch toegepast in de PDF-uitvoer die wordt gegenereerd uit uw gestructureerde inhoud. Dit betekent dat u, in tegenstelling tot andere aangepaste stijlen, geen `outputclass` op de inhoud voor deze stijlen.

Als u een stijldefinitie voor om het even welk element wilt tot stand brengen dat niet door gebrek beschikbaar is of u een douaneelement hebt, dan kunt u het gemakkelijk tot stand brengen in het stijlblad. Het enige punt dat u moet overwegen, is het maken van de stijl met dezelfde naam als de naam van het gestructureerde element.

In het volgende voorbeeld wordt de titel van een nieuw venster gemaakt (`wintitle`) stijl:

1. Open de vereiste stijlpagina voor bewerking.

   >[!NOTE]
   Zie *Een vooraf gedefinieerde of nieuwe stijl aanpassen* voor het openen van een opmaakmodel voor aanpassen of bewerken.

1. In de **Stijlen** lijst, uitvouwen **Overige stijlen**.

1. Klik met de rechtermuisknop op de knop **Andere stijl** en kiest u **Nieuwe stijl**.

1. In de *Stijl toevoegen* het dialoogvenster **Tag** name as *blank* en betreden `wintitle` in de **Klasse** naamveld.

   Als `wintitle` is een herkende DITA-elementnaam, de stijldefinitie ervan wordt automatisch toegewezen aan de `<wintitle>` -element in uw bron.

1. Klikken **Gereed**.

   Een nieuwe stijl met de naam `.wintitle` wordt gemaakt en toegevoegd onder de **Overige stijlen** lijst.

1. Selecteer .wintitle in het menu **Overige stijlen** en stel de gewenste eigenschappen in.

In de volgende schermafbeelding wordt de stijl van de venstertitel weergegeven die wordt toegepast op de tekst &quot;Primair besturingselement&quot;.

<img src="./assets/other-style-wintitle.png" width="500">