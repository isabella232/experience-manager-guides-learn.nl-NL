---
title: Native PDF-publicatiefunctie | Componenten van een PDF-sjabloon
description: Leer de verschillende componenten van een PDF sjabloon en hoe u deze kunt aanpassen en configureren.
hide: true
hidefromtoc: true
source-git-commit: 698469293e41558753ff6aada92f050f45be867a
workflow-type: tm+mt
source-wordcount: '2208'
ht-degree: 0%

---

# Componenten van een PDF-sjabloon

Een PDF-sjabloon bestaat uit vier componenten: Pagina-indelingen, stijlbladen, bronnen en instellingen. U kunt een sjabloon maken door deze afzonderlijke componenten aan te passen en de sjabloon aan een uitvoervoorinstelling te koppelen tijdens het genereren van een PDF-uitvoer. In de volgende secties worden deze componenten en hun aanpassingsproces uitgebreid besproken.


## Paginalay-outs maken en aanpassen

Met de instellingen in de component Pagina-indelingen kunt u de structuur van een pagina ontwerpen door de koptekst, voettekst en het inhoudsgebied op een pagina te definiëren. Met de WYSIWYG-paginaopmaakeditor kunt u een paginalay-out maken voor verschillende secties in een PDF, zoals de voorpagina&#39;s en achteromslag, het hoofdstuk, de inhoudsopgave, de index, de lege pagina, de lijst met afbeeldingen (LOF), de lijst met tabellen (LOT), de woordenlijst of een lay-out maken voor een aangepaste pagina. In de het malplaatjemontages van de PDF, kunt u een paginalay-out met verschillende secties binnen een PDF toewijzen, die dan worden gebruikt om de output van de PDF te produceren.

### Een nieuwe pagina-indeling maken

> **Opmerking**: Er zijn voorbeeldpaginalay-outs die uit de doos worden verzonden. U kunt deze aanpassen of nieuwe paginalay-outs maken.

1. Ga in de webeditor naar de **Uitvoer** tab.
1. Vouw de linkerzijbalk uit en klik op **Sjablonen**.
1. Open de sjabloon waarmee u wilt werken.
   > **Opmerking**: U kunt een sjabloon openen door te dubbelklikken op de naam of op het pictogram > naast de naam.
1. Voer een van de volgende handelingen uit om een nieuwe pagina-indeling te maken:
   * Overslaan **Pagina-indelingen** en klik op de knop (*Opties* pictogram) **...** en kiest u **Nieuwe paginalay-out**.
   * In de **Sjablonen** klikt u op de knop **+** pictogram naast **Sjablonen** en kiest u **Pagina-indeling** in het contextmenu.

      Hiermee wordt het dialoogvenster Lay-out toevoegen geopend.

      <img src="assets/add-layout-2.png" alt="Dialoogvenster Lay-out toevoegen" width="250">
1. Geef een naam op voor de nieuwe pagina-indeling.
   > **Opmerking:** Gebruik geen speciale tekens wanneer u een paginalay-out een naam geeft. Een spatie in de naam wordt vervangen door een onderstrepingsteken &quot;_&quot;.
1. Klikken **Gereed**.

   De nieuwe indeling wordt gemaakt en toegevoegd onder Pagina-indelingen.

### Een pagina-indeling aanpassen

1. In de **Sjablonen** van de sjabloon die u wilt bewerken, dubbelklikt u op **Pagina-indelingen** of klik op **>** pictogram voor **Pagina-indelingen**.

   Hiermee wordt de lijst met paginalay-outs in de sjabloon weergegeven.
1. Voer een van de volgende handelingen uit om een pagina-indeling aan te passen:
   * Dubbelklik op een willekeurige pagina-indeling.
   * Houd de muisaanwijzer boven een willekeurige paginalay-out en klik op de knop (*Opties* pictogram) **...** en selecteert u **Bewerken** in het contextmenu.

   Hiermee opent u de pagina-indeling-editor voor aanpassing.
1. Als u de gewenste wijzigingen hebt aangebracht, klikt u op *Alles opslaan* (of `Crl+S`).

   Ga voor meer informatie over het definiëren van afzonderlijke lay-outelementen, zoals kop- en voettekst, paginanummer, titel en meer naar *Werken met pagina-indelingselementen*.

## Stylesheets gebruiken om PDF aan te passen

Met de instellingen in de component Stylesheets kunt u de paginalay-outcomponenten en DITA-inhoud opmaken met de WYSIWYG-editor of rechtstreeks met het CSS-bestand werken. U kunt uw eigen stijlen maken of de standaardstijleigenschappen aanpassen. De redacteur WYSIWYG geeft u de toegang tot de meeste eigenschappen die u uw paginalay-out of inhoud DITA zou moeten opmaken. Voor geavanceerde aanpassingen kunt u rechtstreeks in de bronweergave werken.

### Een nieuw stijlblad maken

Terwijl CSS-bestanden worden geleverd voor inhoud en lay-out, kunt u een nieuwe stijlpagina maken om meerdere aanpassingen toe te passen op een specifiek stijltype dat vervolgens kan worden toegepast op een doelcomponent. Standaard worden CSS-voorbeeldbestanden gebundeld in het product. Deze CSS-bestanden zijn bedoeld om u te helpen bij het ordenen van uw opmaakgegevens over inhoud en lay-outs. U kunt deze stijlen samenvoegen in één CSS-bestand of in meerdere bestanden.

Wanneer u een nieuwe pagina-indeling maakt, worden standaard de `layout.css` wordt opgenomen in de nieuwe pagina-indeling. Als u wilt dat de paginalay-out stijlen uit een ander CSS-bestand bevat, kunt u het gewenste CSS-bestand gewoon slepen en neerzetten in het inhoudsbewerkingsgebied van de nieuwe paginalay-out. Als u wilt controleren of het CSS-bestand is ingesloten in de paginalay-out, schakelt u over naar de bronweergave en vindt u een koppeling naar het CSS-bestand in het dialoogvenster `<head>` element.


Voer de volgende stappen uit om een stijlpagina te maken:
1. In de **Sjablonen** voert u een van de volgende handelingen uit:
   * Houd de aanwijzer boven de **stijlbladen** en klik op de knop (*Opties* pictogram) **...** en kiest u **Nieuw stijlblad**.
   * Klik op de knop **+** pictogram naast **Sjablonen** en kiest u **Stijlblad** in het contextmenu.

   Hiermee wordt het dialoogvenster Stijlpagina toevoegen geopend.

   <img src="assets/add-stylesheet.png" alt="Stijlpagina toevoegen" width="250">
1. Geef een naam op voor de nieuwe stijlpagina.
1. Klikken **Gereed**.

   Er wordt een nieuwe stijlpagina gemaakt en toegevoegd onder de sectie Stijlvoorbladen.

### Een nieuwe stijl maken

Standaard bevatten de CSS-bestanden stijlen voor kop, alinea, teken, hyperlink, afbeelding, tabel, div, pagina en andere stijlen. U kunt de standaardopmaak overschrijven of een nieuwe stijl maken.

Gewoonlijk maakt u een nieuwe stijl wanneer u een aangepaste stijl voor een DITA-element wilt koppelen. Aangepaste stijlen werken alleen als u de klassenaam van de stijl koppelt aan het kenmerk outputclass van het DITA-element.


Voer de volgende stappen uit om een nieuwe stijl te maken:
1. Klik met de rechtermuisknop op een stijl en kies Nieuwe stijl in het contextmenu.

   Hiermee opent u het dialoogvenster Stijl toevoegen.

   <img src="assets/add-style.png" alt="Nieuwe stijl toevoegen" width="300"/>
1. In de **Tag** , kiest u een label waarvoor u een nieuwe stijl wilt maken.
1. Geef een **Klasse** naam.

   Deze klassenaam moet in de broninhoud worden gekoppeld aan het kenmerk outputclass van de tag.
1. Selecteer een **Pseudo-klasse** voor verbeterde opmaak van het element.
1. Klikken **Gereed**.

   Er wordt een nieuwe stijl gemaakt en toegevoegd onder de basisstijl.

### Een vooraf gedefinieerde of nieuwe stijl aanpassen

Nadat u een nieuw CSS-bestand met standaardstijlen hebt gemaakt of stijlen in een bestaand CSS-bestand wilt aanpassen, kunt u hiervoor de stijleneditor gebruiken.

Voer de volgende stappen uit om een stijl aan te passen:
1. Dubbelklikken op **stijlbladen** of klik op **>** pictogram voor **stijlbladen**.

   Hiermee worden de standaard (Inhoud en Lay-out) en aangepaste CSS-bestanden weergegeven.
1. Open een stijlpagina om te bewerken.

   Voer een van de volgende handelingen uit om stijlpagina te openen voor bewerken:
   * Dubbelklik op de naam van het stijlblad.
   * Houd de muisaanwijzer boven de naam van het stijlblad en klik op het pictogram (Opties)... en kiest u Bewerken.

   Hiermee wordt het stijlblad geopend voor bewerking en wordt de lijst met stijlen weergegeven in het deelvenster Stijlen.

   <img src="assets/customize-style.png" alt="Stijl aanpassen" width="450">

1. Als u een stijl wilt aanpassen, dubbelklikt u op een stijl of klikt u op het pictogram > vóór een stijl om de stijl weer te geven en aan te passen met de Stijleditor.

## Werken met bronnen

Dit is een container voor alle elementen die worden gebruikt om een sjabloon te ontwerpen. U kunt de map beschouwen als een map die elementen bevat zoals achtergrondafbeeldingen, aangepaste lettertypen, logo&#39;s en meer. Telkens wanneer u middelen in uw malplaatje toevoegt, wordt het geupload of controleert in de activaomslag. Vervolgens kunt u deze elementen gebruiken om uw PDF-sjablonen aan te passen of te ontwerpen.

Voer de volgende stappen uit om een elementbestand toe te voegen aan de map Resources:
1. Houd de cursor boven het tabblad Bronnen en klik op het pictogram Opties... en kiest u Importeren.

   Hiermee wordt het dialoogvenster Elementen uploaden geopend.

   <img src="assets/resources-import-assets.png" alt="Elementen uploaden" width="300">

   Het pad waar het elementbestand wordt geüpload, wordt weergegeven in het dialoogvenster **Map voor middelen selecteren** veld.
   > **Opmerking:** U kunt het pad voor het uploaden van elementen niet wijzigen. Standaard worden alle elementen opgeslagen onder de `/content/dam/dita-templates/pdf/<PDF-template-name>` map.

1. Klikken **Bestanden kiezen** om het elementbestand op uw lokale computer te zoeken
1. Klikken **Uploaden**.
Het geselecteerde bestand wordt geïmporteerd en vermeld in de map Bronnen.

## Geavanceerde PDF-instellingen

Met de sectie Instellingen kunt u de geavanceerde instellingen voor de paginalay-out van PDF configureren, PDF vanaf een oneven of even pagina, indelingen voor de kruisverwijzingen en het inschakelen van drukkermarkeringen in de uiteindelijke PDF die met de sjabloon wordt gegenereerd.

Om te vormen, klik **Instellingen** in de **Sjablonen** voor het weergeven van de volgende opties:

**Algemeen**

Stel de basisconfiguratie-instellingen in voor het starten van een hoofdstuk van een oneven of even pagina, de inhoudsopgavestructuur en definieer de opmaak van de leaderregel voor de inhoudsopgave-items. U kunt de volgende instelling definiëren:

* **Hoofdstuk altijd beginnen vanaf**: Hiermee kunt u definiëren hoe elk hoofdstuk in de uiteindelijke PDF wordt gepubliceerd. U kunt kiezen uit een **Nieuwe pagina**, **Oneven pagina**, of **Even pagina** opties. Als u ervoor kiest om een nieuw hoofdstuk te beginnen vanaf een oneven pagina, wordt een lege pagina ingevoegd na een hoofdstuk dat op een oneven pagina eindigt. Als uw hoofdstuk bijvoorbeeld eindigt op pagina 15, wordt een lege pagina 16 ingevoegd tijdens het publicatieproces<sup>th</sup> pagina zodat het nieuwe hoofdstuk kan beginnen vanaf de 17<sup>th</sup> pagina.

* **Begin elk onderwerp van een nieuwe pagina**: Als u elk onderwerp in uw hoofdstuk van een nieuwe pagina wilt beginnen, dan uitgezocht **Begin elk onderwerp van een nieuwe pagina** optie. Schakel deze optie uit als u uw onderwerpen wilt voortzetten zonder tussenruimten op de pagina.

* **Structuur van inhoudsopgave**: Hiermee kunt u de hiërarchie van de inhoudsopgave aanpassen. Hiervoor worden de volgende aanvullende instellingen gebruikt:

   * **Koppen tot niveau gebruiken**: Hiermee kunt u het aantal kopniveaus aanpassen dat in de inhoudsopgavestructuur van de PDF moet worden weergegeven.
   * **Geen paginanummer tonen voor eerste niveau in inhoudsopgave**: Selecteer deze optie om de corresponderende paginanummers te verbergen voor alle hoofdstukken die geneste of onderliggende onderwerpen bevatten. Bekijk het volgende voorbeeld waarin een uitvoer wordt gemaakt zonder deze optie te selecteren.

   <img src="assets/page-number-in-toc.png" alt="Elementen uploaden" width="250">

   In het bovenstaande voorbeeld zijn Geavanceerde instellingen voor PDF, Bijlage en Juridisch het eerste niveau van onderwerpkoppen of hoofdstuktitels. Aan al deze koppen wordt een paginanummer toegewezen.

   Nu, als u deze optie selecteert en de output produceert, dan zult u volgende TOC krijgen:
   <img src="assets/page-number-missing-in-toc.png" alt="Elementen uploaden" width="250">

   Hier kunt u opmerken dat het eerste hoofdstuk Geavanceerde PDF-instellingen geen paginanummer krijgt, aangezien het geneste of onderliggende onderwerpen heeft. Terwijl een paginanummer indien toegewezen aan Bijlage en Juridisch omdat zij standalone onderwerpen zonder enig kindonderwerp zijn.

* **Leader-indeling**: Gebruik de vervolgkeuzelijst om Stippellijnen, Effen lijnen of Lijnvullijnen voor spaties te selecteren om kopniveaus aan de corresponderende paginanummers te koppelen.
Voor het toepassen van de inhoudsopgavestructuur en de vormkopniveaus raadpleegt u *Inhoudsopgave definiëren*.

   > **Opmerking**: Als u een CSS-ontwikkelaar bent, kunt u de leaderindeling ook rechtstreeks in het CSS-bestand definiëren.
* **Vervolgmarkering tabel gebruiken**: Selecteer deze optie als u markeertekens wilt definiëren voor lange tabellen die zich over meerdere pagina&#39;s uitstrekken. Voor meer informatie bij het gebruiken van de tellers van de lijstvoortzetting, zie de de plaatsingstellers van de Lijst van het Gebruik.

**Pagina-indelingen**

Met de instellingen voor Pagina-indelingen hebt u volledige controle over het opgeven van de paginalay-out die moet worden gebruikt voor een bepaalde sectie van het document. Als u bijvoorbeeld een indeling voor de inhoudsopgave wilt selecteren, klikt u op het vervolgkeuzemenu onder het veld Inhoudsopgave en selecteert u de indeling die u hebt ontworpen om de inhoudsopgave te genereren.

Als u geen lay-out voor een bepaalde sectie in uw document hebt gemaakt, kunt u eenvoudig een lay-out kiezen die als standaardlay-out voor dergelijke secties of onderwerpen dient. De standaardpaginalay-out wordt dan toegepast voor alle dergelijke secties die geen specifieke paginalay-out hebben.

Als u een omslag en een achterpagina wilt, dan moet u een paginalay-out hebben die in de montages wordt gecreeerd en wordt toegepast. Anders bevat uw PDF niet de omslag- en achterpagina&#39;s.


Voor meer informatie over paginalay-outs raadpleegt u *Pagina-indeling instellen*.

**Afdrukken**

Configureer de afdrukproductie-instellingen om drukkermarkeringen toe te wijzen, selecteer kleurmodellen en geef eigenschappen op die betrekking hebben op het afdrukken van de PDF-uitvoer.

* **Drukkermarkeringen**: Wanneer u een document voorbereidt voor afdrukproductie, worden drukkermarkeringen aan de paginaranden toegevoegd om de uitlijning, bijsnijding en kleurselectie tijdens het afdrukken te verbeteren. Door een drukkermarkering te selecteren, wordt de paginagrens uitgebreid om de markering aan te passen, die tijdens het afdrukken wordt bijgesneden. U kunt de volgende drukkermarkeringen weergeven in de PDF-uitvoer:
   * **Snijtekens**: Selecteer de optie om een markering op elke hoek van het bijsnijdgebied te plaatsen om aan te geven waar het papier na het afdrukken moet worden bijgesneden.
   * **Aflooptekens**: Selecteer deze optie om een markering op elke hoek van het afloopvak te plaatsen om het snijgebied voor de uitgebreide afbeelding aan te geven.
   * **Registratietekens**: Selecteer deze optie om een markering buiten het snijgebied te plaatsen voor het uitlijnen van de verschillende scheidingen in een kleurendocument.
   * **Kleurenbalken**: Selecteer deze optie om een kleurenstrip buiten het bijsnijdgebied toe te voegen om de kleurconsistentie te behouden en de inktdichtheid bij het afdrukken aan te passen.

   De afmetingen van de geselecteerde drukkermarkeringen instellen met de **Lijnbreedte**, **Lijnkleur**, en **Breedte van afloopvak** opties.

* **Grootte van mediavak**: Dit is het algemene paginaformaat, inclusief het uitgebreide gebied dat wordt ingenomen door drukkermarkeringen. Gebruik de vervolgkeuzelijst om het paginaformaat te selecteren voor de PDF-uitvoer of om uw eigen aangepaste grootte te maken.

* **Kleurruimte**: U kunt kiezen uit de kleurruimten RGB of CMYK om het PDF-document af te drukken. Kies RGB om de gegenereerde PDF digitaal en CMYK weer te geven voor fysiek afdrukken. De kleuren die in het document zijn gedefinieerd, worden omgezet in de gekozen kleurruimte.
   > **Opmerking**: Een ICC-kleurprofiel is vereist voor het maken van PDF/A-kleuren als u CMYK-kleurruimte gebruikt.

   Voor meer informatie over het toepassen van deze afdrukinstellingen raadpleegt u *Afdrukvoorkeuren*.

**Kruisverwijzingen**

Met het tabblad Kruisverwijzing definieert u hoe de kruisverwijzingen worden gepubliceerd in de PDF. U kunt de kruisverwijzingen opmaken voor onderwerptitel, tabellen, figuren en meer. Zie voor meer informatie *Kruisverwijzingen opmaken*.
