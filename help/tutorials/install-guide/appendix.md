---
title: Aanhangsel
description: Leer hoe u InDesign-bestanden voorbereidt voor conversie
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '2861'
ht-degree: 0%

---

# Aanhangsel {#id195AD0L60Y4}

## InDesign-bestanden voorbereiden voor conversie {#id195DBF0045Z}

InDesign biedt auteurs een uitgebreide reeks functies voor het maken van aantrekkelijke en complexe documenten. Dit betekent vaak dat de verschillende delen van een document visueel op de pagina worden geplaatst, maar zonder dat wordt geprobeerd om stroom tussen die tekstkaders tot stand te brengen. Wanneer &#39;*leesvolgorde*&#39; van de tekstkaders is niet gedefinieerd, bevat het IDML-bestand artikelen die geen betekenisvolle volgorde volgen. Het eindresultaat zal één of meerdere onderwerpen DITA met paragrafen, lijsten en grafiek in een willekeurige orde zijn.

Terwijl het mogelijk is om de inhoud DITA in een zinnige orde in een redacteur uit te geven DITA, is het veel gemakkelijker om het dossier van de InDesign te bevestigen alvorens het IDML- dossier te creëren. Dit kan worden gedaan zonder de blik van het brondocument te veranderen. Het heeft ook het voordeel dat het brondocument toegankelijk wordt gemaakt door de leesvolgorde correct te definiëren.

***Tekstkaders verbinden***

InDesign gebruikt de term *&#39;threading&#39;* voor het koppelen van een frame naar een ander frame. Zie voor meer informatie over het verbinden van tekstkaders *[Tekst met verbindingen](https://helpx.adobe.com/in/indesign/using/threading-text.html)* onderwerp in de documentatie van InDesign.

***Overlappende frames***

Sommige InDesign-documenten gebruiken niet-verbonden overlappende frames voor de layout. Het kan erg moeilijk zijn om deze inhoud samen te voegen in de hoofdthread. De beste optie kan zijn om het resultaat in het milieu uit te geven DITA.

***InDesign-verhalen***

Elke verbonden stroom van inhoud in een document van de InDesign wordt genoemd &quot;*verhaal*&quot;. Voor de beste resultaten is het raadzaam het aantal artikelen beperkt te houden. Er zijn echter delen van uw document die niet nodig zijn in de DITA-uitvoer. Pagina-voetteksten zijn bijvoorbeeld zelden nodig, maar kunnen in het midden van een onderwerp verschijnen als ze niet zorgvuldig worden verwerkt.

De eenvoudigste manier om tekst uit te sluiten die niet in het document is vereist, is om deze een speciale code te geven *Alinealabel* die alleen voor de ongewenste inhoud wordt gebruikt. In plaats van een *\[Basisalinea\]* voor de voettekst, maakt u een speciale *Voettekst* tag. Vervolgens stelt u in het MapStyle-bestand gewoon het *Voettekst* alinea&#39;s die als volgt moeten worden verwijderd:

```XML
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Toewijzen aan DITA-documenttypen***

Het is van essentieel belang dat uw brondocument ten minste één alineastijl of -element heeft die het begin van een onderwerp kan markeren. Documenten worden veel gebruikt *Kop1* als de naam van de titels op hoofdniveau in het document. U kunt dan een afbeelding van die stijl aan een specifiek DITA documenttype tot stand brengen. Als uw document goed is georganiseerd en u kunt *Kop1* is constant door, dan zult u goede resultaten krijgen.

***Meerdere DITA-doctypen***

Als sommige van de *Kop1* alinea&#39;s moeten worden omgezet in verschillende DITA-documenttypen en vervolgens de alineastijl in InDesign dupliceren. Geef deze stijlen een herkenbare naam, zoals *Heading1\_genTask* of *Kop1\_problemen oplossen* in voorkomend geval. Stel vervolgens het mapStyle-bestand in zoals hieronder wordt weergegeven:

```XML
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Gestructureerde InDesign documenten***

InDesign heeft een losse relatie met XML. Hoewel een document een XML DTD kan bevatten en het hoofdartikel geldig kan zijn tegen die DTD, is het ook mogelijk om hybride documenten te maken waar sommige inhoud XML is, maar geen DTD is inbegrepen. Dit zijn de ongewenste gevallen van een geslaagde conversie naar DITA. Als een document XML-onderdelen bevat, probeert u de uitvoer op te slaan in XML en controleert u of de resultaten acceptabel zijn. Als dat niet het geval is, bevat de DITA-inhoud ook ongeldige inhoud of kan deze volledig mislukken.

***Tabelopmaak***

De conversie van InDesign table formatting regels aan het gelijkwaardige lijst formatteren in DITA is een complex proces. Dit komt door de rijke opmaakkenmerken die beschikbaar zijn in de bronbestanden in vergelijking met de basisopties in het tabelmodel Oasis \(CALS\) dat wordt gebruikt in DITA. Verticale en horizontale tekstuitlijning is beschikbaar en geeft vergelijkbare resultaten, hoewel uitgevulde tekst altijd wordt uitgevuld volgens de tekstrichting, terwijl InDesign Links uitvullen en Rechts uitvullen toestaat.

InDesign van kolom- en rijscheidingen zijn veel beter geschikt dan de basisopties van de tabel Oasis. InDesign biedt vier celranden: randtype \(effen of patroondikte\), randdikte, randkleur, randtint, randtussenkleur en randtussenruimtetint. Deze moeten allemaal worden toegewezen aan de randen rechts en onder aan elke cel \(entry-element\), waarbij de enige opties 0 of 1 zijn: de rand verbergen of de rand tonen.

De grens in InDesign kan op de volgende niveaus worden toegepast:

- Tabelstijlen
- Celstijlen
- Lokale overschrijvingen op elke cel

Bij het conversieproces van InDesign naar DITA wordt de grensregeling als volgt toegepast:

- Tabelstijlen worden toegewezen aan de `colspec/@colsep` kenmerk voor verticale regels. Horizontale regels worden toegewezen aan de `row/@rowsep` kenmerk. In beide gevallen wordt het kenmerk niet gemaakt als de rand niet is gedefinieerd.
- Celstijlen worden toegewezen aan de `entry/@colsep` en `entry/@rowsep` kenmerken. Deze waarden zullen om het even welke van de Stijl van de Lijst afgeleide grensheerser met voeten treden.
- Bij lokale overschrijvingen wordt de opmaak rechtstreeks op de cel toegepast en worden de tabelstijlen en celstijlen genegeerd.

***Wisselende patronen***

Met Tabelstijlen voor InDesign kunt u kolom- en cellijnen afwisselend weergeven. Hoewel deze functie wordt ondersteund voor conversie, zijn de resultaten alleen duidelijk wanneer een patroongroep de regel \(1\) weergeeft en de andere patroongroep de toewijzingen \(0\) verbergt.

## Het toewijzingsbestand voorbereiden voor InDesign naar DITA-migratie {#id194AF0003HT}

Voor de juiste DITA-conversie is een toewijzingsbestand vereist dat overeenkomt met de inhoud van het brondocument. Voor ongestructureerde InDesign-documenten betekent dit dat alle beschikbare alineastijlen en tekenstijlen moeten worden toegewezen. Voor documenten van XML gestructureerde InDesign moeten alle elementen in zijn bijbehorende DTD in kaart worden gebracht.

De toewijzingsbestanden voor ongestructureerde en gestructureerde InDesign-documenten zijn verschillend. Dit is toe te schrijven aan de complexere verwerkingsvereisten voor het omzetten van ongestructureerde broninhoud in DITA.

Hieronder volgt een voorbeeld van het toewijzingsbestand:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

Het toewijzingsbestand is een XML-bestand met een eenvoudige structuur waarin alle bronalineastijlen en tekenstijlcodes worden vermeld. De bestandsinhoud wordt hieronder uitgelegd:

**Stijltoewijzing**

In de `styleMap` -element, kunt u twee optionele kenmerken opgeven - `@map_date` en `@map_version` voor het opnemen van de versie van het toewijzingsbestand.

**Documenttype**

De `doctypes` Het element maakt een lijst van de gesteunde kaart DITA en onderwerpafbeeldingen.

**Alinealijnen voor documenttype toewijzen**

De `mapDoctypeParaRule` element is verplicht. De attributen van dit element moeten niet worden uitgegeven omdat het de wortelelement van bronXML altijd aan de wortel van de kaart DITA in kaart wordt gebracht `map` element.

**Alinealijn voor documenttype**

De `doctypeParaRule` element is verplicht. Dit geeft het omzettingsproces een manier om het begin van een nieuw onderwerp te identificeren. Normaal gesproken worden de `@style` kenmerk wordt op zichzelf gebruikt met de `@local` kenmerk ingesteld op 0. Als er echter altijd lokale opmaakoverschrijvingen op de gekozen stijl staan, moet u een regel toevoegen voor elke stijl plus de lokale overschrijvingen. Dit is eenvoudig te herkennen in het gegenereerde toewijzingsbestand waar dit of een vergelijkbaar bestand kan worden gevonden:

```XML
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

In het bovenstaande voorbeeld zijn er twee `paraRule` elementen voor `@style` = &quot;Kop1&quot;. Eenvoudig, creeer een gelijkwaardig `doctypeParaRule` elementen met de `@mapToDoctype` naar wens ingestelde kenmerk.

De kenmerken die worden gebruikt in de `doctypeParaRule` worden hieronder uitgelegd:

- `@style`: De naam van een stijl in het InDesign-brondocument.
- `@local`: Zie [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: De naam van een DITA onderwerptype van een opgesomde lijst van alle geldig `doctypes`.

**Regels voor het verpakken van elementen**

De elementomsluitende regels bepalen de manieren om elementen in het binnenkomende document om te zetten in een vooraf gedefinieerd element volgens een reeks kenmerkwaarden.

***`wrap`element***

Dit is een optioneel element. De `wrap` het element maakt een lijst van de elementen die zullen worden verpakt of worden bewogen. Wrapping wordt doorgaans gebruikt wanneer een reeks elementen een gemeenschappelijk bovenliggend element moet krijgen. Bijvoorbeeld meerdere `li` elementen die in een `ol` element. Daarnaast `wrap` kan worden gebruikt voor het verplaatsen van elementen, zoals titels voor figuren en tabellen.

De kenmerken die worden gebruikt in de `wrap` worden hieronder uitgelegd:

- `@element`: Een plusteken na een elementnaam geeft aan dat alle aangrenzende elementen met dezelfde naam worden opgenomen in het element dat wordt genoemd in het dialoogvenster `@wrapper`kenmerk.
- `@wrapper`: The name of the wrapping element.
- `@context`: Verstrekt een manier om verder te verfijnen hoe een bepaald element verpakt is. In het volgende voorbeeld wordt een manier getoond om een reeks `li` elementen in een geordende lijst `ol` of een ongeordende lijst `ul` volgens de `@context` waarde \(de context wordt gedefinieerd op het tabblad `paraRule` element\):

   ```XML
   <wrap elements="li+" context="number" wrapper="ol">
      <attributeRules createID="true"/>
   </wrap>
   <wrap elements="li+" context="bullet" wrapper="ul">
      <attributeRules createID="true"/>
   </wrap>
   ```


In het volgende voorbeeld wordt getoond hoe u een `fig` element van een `title` en `image` element:

- `@elements`: De elementen die worden vermeld en van elkaar worden gescheiden door een komma, worden opgenomen in het element dat wordt genoemd in het dialoogvenster `@wrapper` kenmerk. Omdat het gebruikelijk is om figuurtitels onder de afbeelding op te nemen, wordt de titel `title` element onmiddellijk na de `image`.

   De volgende omloopregel:

   ```XML
   <wrap elements="title, image" context="FigTitle" wrapper="fig">
      <attributeRules createID="true"/>
   </wrap>
   ```

   Hiermee wordt de volgende tussenliggende XML geconverteerd:

   ```XML
   <image href="Links/myImage.png" scale="59">
      <title>IDML2DITA workflow</title>
   ```

   In de volgende geldige DITA figuurstructuur:

   ```XML
   <fig id="id397504">
      <title>IDML2DITA workflow</title>
      <image href="Links/myImage.png" scale="59">
   </fig>
   ```

- `@wrapper`: The name of the wrapping element.
- `@context`: Biedt een manier om verder te verfijnen hoe een bepaald element omlopen is \(de context is gedefinieerd op het tabblad `paraRule` element\).

In het volgende voorbeeld wordt getoond hoe u een `title` in een `table`:

- `@elements`: De `title` element dat vlak voor of onmiddellijk na een `table` wordt opgenomen in het element dat in het dialoogvenster `@wrapper` kenmerk. Een voorspelling in XPath-stijl kan de positie van het titelelement identificeren als `[before]` of `[after]`.

   Voorbeeld: De volgende omloopregel:

   ```XML
   <wrap elements="title[before]" context="TableTitle" wrapper="table">
      <attributeRules createID="true"/>
   </wrap>
   ```

   Hiermee wordt de volgende tussenliggende XML geconverteerd:

   ```XML
   <title>IDML2DITA workflow</title>
   <table id="id289742" outputclass="BasicTable">
      <tgroup cols="2">
         <colspec colname="0" colwidth="0.7*">
            <colspec colname="1" colwidth="0.3*">
   ```

   In deze geldige DITA-figuurstructuur:

   ```XML
   <table id="id289742" outputclass="BasicTable">
      <title>IDML2DITA workflow</title>
      <tgroup cols="2">
         <colspec colname="0" colwidth="0.7*">
            <colspec colname="1" colwidth="0.3*">
   ```

- `@wrapper`: The name of the wrapping element.

- `@context`: Biedt een manier om verder te verfijnen hoe een bepaald element omlopen is \(de context is gedefinieerd op het tabblad `paraRule` element\).


**Regels voor alineastijlen**

De `<paragraphStyleRule>` de elementen worden hieronder beschreven :

***`paraRule`element***

De `paraRule` element is verplicht. Hiermee geeft u de toewijzingsregels voor alle alineastijlen op. In een InDesign-document bevindt alle tekst zich in de substructuur van Alineastijlen, zelfs alinea&#39;s zonder stijl krijgen een naam `[No paragraph style]`. De vierkante haakjes geven een ingebouwde stijlnaam InDesign aan.

>[!NOTE]
>
> De vierkante haakjes geven een ingebouwde InDesign-stijlnaam aan.

De kenmerken die worden gebruikt in de `paraRule` worden hieronder uitgelegd:

- `@style`: De naam van een stijl in het InDesign-brondocument.
- `@local`: Zie [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: De naam van een DITA-doelelement.

- `@context`: Dit kenmerk wordt gebruikt om een koppeling te maken naar een specifieke **wrap** regel wanneer meer dan één omslagkeuze beschikbaar is. Voorbeeld: de `li` element kan worden verpakt in een van beide `ol`of een `ul` element. Als u de verschillende lijsttypen wilt identificeren, kunt u een specifieke stijlnaam of de `@local` kenmerk dat het volgende kan weergeven:
   - `local="p[-|-|-|-|-|b|-|-]"` Waar &#39;`b`&#39; in veld 6 verwijst naar een lijstitem met opsommingstekens. In dit geval instellen `@context` aan &#39;`bullet`&quot;.
   - `local="p[-|-|-|-|-|n|-|-]"` Waar &#39;`n`&#39; in veld 6 verwijst naar een genummerd lijstitem. In dit geval instellen `@context` aan &#39;`number`&quot;.

- `@commentOut`: Dit attribuut laat de verpakking van het doelelement in de commentaren van XML toe zodat de informatie niet verloren wordt maar manueel door de gebruiker kan worden behandeld. Dit is nuttig als de broninhoud niet kan worden gedwongen om aan de DITA-structuurregels te voldoen.

- `@refactor`: Dit optionele kenmerk heeft twee waarden:

- `unwrap`: Het overeenkomende element wordt verwijderd terwijl de inhoud behouden blijft.

- `drop`: Het overeenkomende element en de inhoud ervan worden verwijderd.


**Regels voor tekenstijl**

De `charRule` de elementen worden hieronder beschreven :

>[!NOTE]
>
> Er wordt geen toewijzing gemaakt voor de ingebouwde tekenstijl `[No character style]` wanneer `local="0"`, omdat deze tijdens de voorbehandeling worden verwijderd.

***`charRule`element***

Dit is een optioneel element.

Dit zijn de toewijzingsregels voor alle tekenstijlen. In een InDesign-document is alle tekst opgenomen in onderliggende elementen van tekenstijlen.

De kenmerken die worden gebruikt in de `charRule` worden hieronder uitgelegd:

- `@style`: De naam van een stijl in het InDesign-brondocument.
- `@local`: Zie [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: De naam van een DITA-doelelement.
- `@refactor`: Dit optionele kenmerk heeft twee waarden:
   - `unwrap`: Het overeenkomende element wordt verwijderd terwijl de inhoud behouden blijft.

   - `drop`: Het overeenkomende element en de inhoud ervan worden verwijderd.


**Kenmerkregels**

Dit element kan een onderliggend element zijn van de volgende elementcontexten:

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

Het doel van kenmerkregels is het beheren van de kenmerken voor de overeenkomende elementen.

Afhankelijk van de context zijn de volgende kenmerken beschikbaar in het dialoogvenster `attributeRules` element:

- `@createID`: Hiermee genereert u een unieke id voor de overeenkomende elementen. Toegestane waarden `true` of `false`. Beschikbaar in alle contexten.
- `@copyAll`: Hiermee kopieert u alle kenmerken van de XML-broninhoud alleen voor gestructureerde bronbestanden. Toegestane waarden zijn `true` of `false`. Beschikbaar voor contexten `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` en `elementRule`.


De kenmerken die worden gebruikt in de `attributeRules` worden hieronder uitgelegd:

>[!NOTE]
>
> Dit element kan meerdere onderliggende elementen bevatten.

- `addNew`: Hiermee voegt u een nieuw kenmerk toe aan het overeenkomende element. Beschikbaar voor alle contexten. Het heeft twee attributen:
   - `@name`: Moet een geldige XML-naam zijn, bij voorkeur geldig voor de DITA-context.
   - `@value`: Dit kan letterlijke tekst of een eenvoudige XPath-expressie zijn.
- `copyAtt`: Hiermee kopieert u één kenmerk naar het doel en wijzigt u de naam van het kenmerk in het proces. De waarde wordt niet gewijzigd. Beschikbaar voor contexten `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` en `elementRule`. Wanneer dit element aanwezig is, wordt `@copyAllAtts` waarde wordt geacht `false`. Het heeft twee attributen:
   - `@name`: Dit moet de naam zijn van een kenmerk dat aanwezig is op het bron-XML-element.
   - `@mapTo`: Moet een geldige XML-naam zijn, bij voorkeur geldig voor de DITA-context.

**Lokale opmaakcodes**

In elk InDesign-document is het mogelijk dat alineastijlen en tekenstijlen honderden verschillende opmaakoverschrijvingen hebben. De meeste van deze eigenschappen bieden geen nuttige rol in het conversieproces. We hebben echter een kernset opmaakfuncties geïdentificeerd die wel van invloed zijn op de semantiek van het document en die het conversieproces moeten beïnvloeden.

De `@local` kenmerken worden weergegeven als een speciale indeling met scheidingstekens, waarbij acht velden worden opgegeven en een voorvoegsel wordt weergegeven waarmee het type opmaakoverschrijving wordt aangegeven. De velden met opmaakcodes worden hieronder weergegeven:

- Voorvoegsel **p** voor para-stijl lokale overschrijving of **c** voor tekenstijl lokale overschrijving.
- **Lettertypestijl** Dit is de familienaam en eigenschappen zoals &quot;***Vet, versmald en cursief***&quot;.
- **Fontgrootte** in punten.
- **Tekenpositie** voor superscript of subscript.
- **Onder** voor onderstrepingsteken.
- **Strike** voor doorhaling.
- **Lijstcode** om lijsttype als bulleted of Genummerd te identificeren - niet altijd gebruikt door InDesign.
- **Opsommingscode** Hiermee geeft u alle gedefinieerde opsommingstekens in het document weer.
- **Nummercode** Hiermee worden alle gedefinieerde nummeringsstijlen in het document weergegeven.

Wanneer u deze functie zorgvuldig gebruikt, kan verloren lokale opmaak de kwaliteit van een overdracht van gestileerde inhoud naar DITA verbeteren. Dit voorbeeld kan worden omgezet in cursieve, 16-pt tekst in een lijst met opsommingstekens: `p[Italic|16|-|-|-|b|-|-]`.

**Structuurtoewijzing**

Het structuurtoewijzingsbestand lijkt op het stijltoewijzingsbestand met een eenvoudige structuur die alle bronelementen en relevante kenmerktypen opsomt. Twee kenmerken, `@map_date` en `@map_version` worden verstrekt voor het registreren van de versie van het te gebruiken toewijzingsbestand.

**Documenttype**

De `doctypes` Het element maakt een lijst van de gesteunde kaart DITA en onderwerpafbeeldingen.

**Elementregels voor documenttype toewijzen**

De `mapDoctypeElemRule` element is verplicht. De attributen van dit element moeten niet worden uitgegeven omdat het de wortelelement van bronXML altijd aan de wortel van de kaart DITA in kaart wordt gebracht `map` element.

**Regels voor het verpakken van elementen**

**`elementRules`element** Hier worden alle elementen weergegeven.

**`elementRule`element** De `elementRule` element is verplicht. Dit zijn de toewijzingsregels voor alle bronelementen. Een InDesign-document bevat wel ongestructureerde stijlelementen, maar deze worden genegeerd voor gestructureerde inhoud, tenzij de syntaxis &quot;***hybride modus***&#39;-verwerking is ingeschakeld.

De kenmerken die worden gebruikt in de `elementRule` worden hieronder uitgelegd:

- `@elementName`: De naam van een element in het InDesign-brondocument.

- `@local`: Zie [\#id194CG0V005Z](#id194CG0V005Z). \(Alleen handig voor hybride documenten\).

- `@mapTo`: De naam van een DITA-doelelement.

- `@refactor`: Dit optionele kenmerk heeft twee waarden:

   - `unwrap`: Het overeenkomende element wordt verwijderd terwijl de inhoud behouden blijft.

   - `drop`: Het overeenkomende element en de inhoud ervan worden verwijderd.

- `@context`: Dit kenmerk wordt gebruikt om een koppeling te maken naar een specifieke omloopregel wanneer er meer dan één keuze voor de omloop beschikbaar is. Voorbeeld: de `li` element kan worden verpakt in een van beide `ol`of een `ul` element.

- `@commentOut`: Dit attribuut laat de verpakking van het doelelement in de commentaren van XML toe zodat de informatie niet verloren wordt maar manueel door de gebruiker kan worden behandeld. Dit is nuttig als de broninhoud niet kan worden gedwongen om aan de DITA-structuurregels te voldoen.


## Problemen AEM hulplijnen oplossen

Nadat u AEM hulplijnen hebt geïnstalleerd en geconfigureerd, kunt u de problemen oplossen.

## Referenties valideren

U kunt de opgegeven scripts uitvoeren om de referenties te valideren. Deze scripts kunnen u helpen de verbroken verwijzingen te identificeren en deze vervolgens te repareren of te herstellen.

- `/bin/fmdita/validatebtree?operation=validate` - rapporten om het even welke gebroken inhoudsverwijzingen maar verhelpt hen niet.
- `/bin/fmdita/validatebtree?operation=patch`- geeft een overzicht van de verbroken inhoudsverwijzingen en patches of corrigeert deze.

**Script valideren**

Voer de volgende stappen uit om de verwijzingen te controleren, gebruikend het validate manuscript beschikbaar in het productpakket:

1. Script voor validatie uitvoeren \[`/bin/fmdita/validatebtree?operation=validate`\] om te controleren of er nieuwe verbroken verwijzingen zijn.
1. Als het validate manuscript om het even welke fouten meldt, kunt u het herstellen gebruikend het flardmanuscript.
1. Registreer de hieronder gegeven details en deel hen indien nodig met uw team van het klantensucces:
1. 
   - Wordt afgedrukt door script voor validatie
- Pakket met &quot;`/content/fmdita/references`&quot;
- Eventuele andere vereiste details, afhankelijk van het gerapporteerde scenario

**Patchscript**

Voer de volgende stappen uit om verbroken verwijzingen te repareren met behulp van het patchscript dat beschikbaar is in het productpakket:

1. Het patchscript uitvoeren `[/bin/fmdita/validatebtree?operation=patch]` om de verbroken verwijzingen te herstellen. De uitvoering van het script neemt een paar minuten in beslag en drukt de logbestanden af terwijl deze worden uitgevoerd. Wanneer de uitvoering is voltooid, wordt de afdruk &quot;`Done`&quot; aan het einde.

   **Opmerking:* Het wordt aanbevolen de logbestanden te kopiëren en op te slaan ter referentie.

1. Nadat het patchscript is uitgevoerd, kunt u de volgende controles uitvoeren:
1. 
   - Een nieuw knooppunt controleren &quot;`references_backup_<timestamp>"` is gemaakt op `/content/fmdita`
- Controleer of de referenties zijn gecorrigeerd

**Aanmelder**

U kunt ook een afzonderlijk logger maken voor de uitvoering van dit script, zoals beschreven in de volgende details:

- Een logger toevoegen aan de klasse &quot;`adobe.fmdita.common.BTreeReferenceValidator`&quot;
- Instellen op `DEBUG`

In het gemaakte logbestand wordt alle informatie opgenomen die betrekking heeft op de uitvoering van het script. Deze informatie is handig voor het geval de sessietime-outs van de browser worden uitgeschakeld en wordt het script geactiveerd vanuit de browser.

