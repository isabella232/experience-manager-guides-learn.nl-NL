---
title: Niet-DITA-inhoud migreren
description: Leer hoe u niet-DITA-inhoud kunt migreren
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '2761'
ht-degree: 0%

---

# Niet-DITA-inhoud migreren {#id181AH0R02HT}

Deze sectie begeleidt u door het migratieproces om niet-DITA documenten in formaat te migreren DITA. AEM de Gidsen verstrekt migratie uit de volgende bronnen:

- [Microsoft Word](#id1949B040Z5Z)

- [Documenten InDesigns](#id195AD0B0K5Z)

- [XHTML](#id1949B04L0Y4)

- [Niet-gestructureerde FrameMaker](#id1949B050VUI)

- [Alle andere gestructureerde documenten](#id1949B0590YK)


## Microsoft Word-documenten migreren {#id1949B040Z5Z}

Met AEM hulplijnen kunt u bestaande Word-documenten migreren \(`.docx`\) in DITA onderwerptypedocumenten. U moet de locatie van de invoer- en uitvoermap en andere parameters opgeven en het document wordt geconverteerd naar DITA-document. Afhankelijk van de inhoud, zou u een.dita dossier en een.ditamap- dossier kunnen hebben.

Als u een Word-document wilt converteren, moet het document een goede structuur hebben. Uw document moet bijvoorbeeld een titel hebben, gevolgd door Kop 1, Kop 2 enzovoort. Elk van de rubrieken zou wat inhoud in het moeten hebben. Als uw document niet goed gestructureerd is, werkt het proces mogelijk niet naar behoren.

AEM hulplijnen gebruiken standaard de [Transformatieframework Word-naar-DITA \(Word2DITA\)](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/word2dita-intro.html). Deze transformatie is afhankelijk van de [stijl-aan-markering, afbeelding](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) configuratiebestand. Als u de Word2DITA-transformatie met succes wilt kunnen gebruiken, moet u de volgende richtlijnen in overweging nemen voor het voorbereiden van uw Word-document voor conversie:

>[!NOTE]
>
> Als u wijzigingen aanbrengt in het standaardconfiguratiebestand voor de toewijzing van stijl naar label, moet u de richtlijnen bijwerken en gebruiken die bevestigen bij uw bijgewerkte stijltoewijzing.

- Zorg ervoor dat het document begint met een titel. Deze titel wordt toegewezen aan de titel van de DITA-kaart. Daarnaast moet de titel worden gevolgd door gewone inhoud.

- Na de titel moet er rubriek 1, rubriek 2 enzovoort zijn. Elke kop moet inhoud bevatten. De rubrieken worden omgezet in nieuwe Concept typeonderwerpen. De hiërarchie van de gegenereerde onderwerpen is afhankelijk van de niveaus van Kop in het document. Kop 1 komt bijvoorbeeld voor Kop 2 en Kop 2 komt voor Inhoud Kop 3.

- Het document moet ten minste één koptekstinhoud hebben.

- Zorg ervoor dat u geen gegroepeerde afbeeldingen hebt. Als u afbeeldingen in uw document hebt gegroepeerd, degroepeert u deze allemaal.

- Alle kop- en voetteksten verwijderen.

- Inline stijlen zoals vet, cursief en onderstrepen worden omgezet in `b`, `i`, en `u` elementen.

- Alle geordende en ongeordende lijsten worden omgezet in `ol` en `ul` elementen. Dit geldt ook voor geneste lijsten, lijsten binnen tabellen, notities of voetnoten.

- Alle hyperlinks worden geconverteerd naar `xref`.

- De bestandsnaam van de omgezette bestanden is gebaseerd op de koptekst gevolgd door een bestandsnummer. Het bestandsnummer is een opeenvolgend nummer op basis van de positie van de koptekst in het document. Als een koptekst bijvoorbeeld &#39;Voorbeeldkop&#39; is en de tekst een tiende kop in het document heeft, is de resulterende bestandsnaam voor dit onderwerp vergelijkbaar met Sample\_Heading\_10.dita.


Voer de volgende stappen uit om uw bestaande documenten van Word in DITA onderwerptype document om te zetten:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het standaardconfiguratiebestand dat beschikbaar is op de volgende locatie:

   `/libs/fmdita/config/w2d_io.xml`

1. Maak een overlayknooppunt van het dialoogvenster `config` in de `apps` knooppunt.

1. Navigeer naar het configuratiebestand dat beschikbaar is in het dialoogvenster `apps` knooppunt:

   `/apps/fmdita/config/w2d_io.xml`

   De `w2d_io.xml` bestand bevat de volgende configureerbare parameters:

   - In de `inputDir` -element, geeft u de locatie op van de invoermap waarin uw Word-brondocumenten beschikbaar zijn. Als uw Word-documenten bijvoorbeeld zijn opgeslagen in een map met de naam `wordtodita` in `projects` en geef vervolgens de locatie op als: `/content/dam/projects/wordtodita/`

   - In de`outputDir` -element, geeft u de locatie van de uitvoermap op of behoudt u de standaarduitvoerlocatie om het omgezette DITA-document op te slaan. Als de opgegeven uitvoermap niet bestaat op DAM, maakt de conversieworkflow de uitvoermap.

   - Voor de `createRev` element, specificeer of een nieuwe versie van het omgezette onderwerp DITA \ (`true`of niet \(`false`\).

   - In de `s2tMap` -element, geeft u de locatie op van het kaartbestand dat toewijzingen voor Word-documentstijlen aan DITA-elementen bevat. De standaardtoewijzing wordt opgeslagen in het bestand dat zich bevindt op:

     ```XML
     /libs/fmdita/word2dita/word-builtin-styles-style2tagmap.xml
     ```

     >[!NOTE]
     >
     > Voor meer informatie over de structuur van `word-builtin-styles-style2tagmap.xml` en hoe u het kunt aanpassen, zie [Toewijzing stijl aan label](http://www.dita4publishers.org/docs/repo/org.dita4publishers.word2dita/word2dita/style-to-tag-map-overview.html) in *DITA voor gebruikershandleiding voor uitgevers*.

   - In het element props2Propagate, specificeer de eigenschappen die tot de kaart moeten worden overgegaan DITA. Deze eigenschap is vereist voor het doorgeven van de standaardmetagegevens, zoals dc:title,dc:subject,dam:trefwoorden,dam:categorie van documentmetagegevens naar geconverteerde DITA-elementen.

1. Sla de `w2d_io.xml` bestand.

1. Na het vormen van de vereiste parameters in `w2d_io.xml` bestand, meldt u zich aan bij AEM en opent u de interface Middelen.

1. Ga naar de locatie van de invoermap \()`wordtodita`\).

1. Upload de Word-brondocumenten naar deze map. Voor informatie over het uploaden van inhoud naar DAM raadpleegt u [Bestaande DITA-inhoud uploaden](migrate-content-upload-existing-dita-content.md#).


Met de `config` `/config` , kunt u een of meerdere configuraties definiëren voor conversie. De omzettingswerkstroom wordt uitgevoerd en de definitieve output in de vorm van een onderwerp DITA wordt bewaard in de plaats die in wordt gespecificeerd `outputDir` element.

## Adobe InDesign-documenten migreren {#id195AD0B0K5Z}

Met AEM hulplijnen kunt u documenten van InDesigns converteren. Net als FrameMaker kunt u met InDesign ook ongestructureerde en gestructureerde documenten maken. De ongestructureerde documenten gebruiken de alinea- en tekenstijlen om inhoud op te maken. In het gestructureerde document worden elementen en de bijbehorende kenmerken gebruikt.

Voor het conversieproces moeten de opmaak van de alinea- en tekenstijl worden toegewezen aan relevante DITA-elementen. Op dezelfde manier zal in het geval van gestructureerde documenten het toewijzingsdossier één-aan-één afbeelding van de elementen en de attributen van het InDesign met elementen DITA en attributen bevatten.

Het conversieproces omvat de volgende acties op de achtergrond:

- De *Taal voor opmaakcodes voor InDesigns* Het bestand \(IDML\) wordt uitgepakt in een werkmap.
- Het bestand designmap.xml wordt gelezen om de afzonderlijke artikelen van het InDesign te zoeken.
- Alle artikelen worden samengevoegd tot één XML-instantie, &#39;lege&#39; artikelen worden genegeerd.
- Alle ingesloten afbeeldingen worden geëxporteerd.
- Pre-conversie van standaardstructuren zoals tabellen en afbeeldingen naar DITA-indeling.
- Stijl- of structuurtoewijzing aan de uiteindelijke uitvoer op basis van het toewijzingsbestand.
- Creatie en bevestiging van individuele onderwerpen DITA en DITA kaartdossiers.
- Verwijderen van tijdelijke bestanden.

In grote lijnen is het voor het conversieproces nodig [Bestanden van InDesigns voorbereiden voor conversie](appendix.md#id195DBF0045Z) en [Het toewijzingsbestand voorbereiden voor InDesign naar DITA-migratie](appendix.md#id194AF0003HT) dan moet u de bepaalde procedure volgen om het omzettingsproces in werking te stellen.

Voer de volgende stappen uit om uw bestaande documenten van het InDesign in DITA onderwerptype document om te zetten:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het standaardconfiguratiebestand dat beschikbaar is op de volgende locatie:

   `/libs/fmdita/config/idml2dita_io.xml`

1. Maak een overlayknooppunt van het dialoogvenster `config` in de `apps` knooppunt.

1. Navigeer naar het configuratiebestand dat beschikbaar is in het dialoogvenster `apps` knooppunt:

   `/apps/fmdita/config/idml2dita_io.xml`

   Vorm de volgende parameters in `idml2dita_io.xml` bestand:

   - In de `inputDir` -element, geeft u de locatie op van de invoermap waarin de brondocumenten van het InDesign beschikbaar zijn. Als uw documenten van het InDesign bijvoorbeeld zijn opgeslagen in een map met de naam `indesigntodita` in `projects` en geef vervolgens de locatie op als: `/content/dam/idmlfiles/indesigntodita/`

   - In de`outputDir` -element, geeft u de locatie van de uitvoermap op of behoudt u de standaarduitvoerlocatie om het omgezette DITA-document op te slaan. Als de opgegeven uitvoermap niet bestaat op DAM, maakt de conversieworkflow de uitvoermap.

   - In de `mapStyle` -element, geeft u de locatie op van het kaartbestand dat toewijzingen bevat voor documentstijlen van InDesigns naar DITA-elementen. De standaardtoewijzing wordt opgeslagen in het bestand dat zich bevindt op:

     ```XML
     /stmap.adobeidml.xml
     ```

     >[!NOTE]
     >
     > Voor meer informatie over de structuur van `stmap.adobeidml.xml` en hoe u het kunt aanpassen, raadpleegt u de [Het toewijzingsbestand voorbereiden voor InDesign naar DITA-migratie](appendix.md#id194AF0003HT) sectie in *Bijlage*.

1. Sla de `idml2dita_io.xml` bestand.

1. Na het vormen van de vereiste parameters in `idml2dita_io.xml` bestand, meldt u zich aan bij AEM en opent u de interface Middelen.

1. Ga naar de locatie van de invoermap \()`indesigntodita`\).

1. Upload de documenten van het bronInDesign in deze omslag. Voor informatie over het uploaden van inhoud naar DAM raadpleegt u [Bestaande DITA-inhoud uploaden](migrate-content-upload-existing-dita-content.md#).


## XHTML-documenten migreren {#id1949B04L0Y4}

Met AEM hulplijnen kunt u uw bestaande XHTML-documenten converteren naar DITA-onderwerpdocumenten. U moet de locatie van de invoer- en uitvoermap en andere parameters opgeven en de documenten worden geconverteerd naar DITA-indeling. Er zijn twee methoden waarmee u gestructureerde HTML-documenten kunt omzetten:

- Alle documenten uploaden naar de invoermap, of
- Maak een ZIP van alle documenten samen met de mediabestanden en upload deze naar de invoermap. Deze aanpak wordt over het algemeen gebruikt voor een set HTML-bestanden die aan elkaar zijn gekoppeld en er is een inhoudsopgave \(index.html\). Het bestand index.html bevat koppelingen naar alle HTML-bestanden in de set.

Of u nu alle bestanden afzonderlijk uploadt of in een ZIP-bestand gebundeld, het conversieproces zorgt voor een een-op-een-toewijzing tussen de HTML-bestanden en de resulterende DITA-bestanden. Dit betekent in wezen dat er een .dita dossier voor elk .html dossier in de inputomslag wordt gecreeerd.

Voor het uploaden van uw documenten in een ZIP-bestand moet u rekening houden met de volgende punten:

- Alle onderwerpen waarnaar wordt verwezen, moeten in het ZIP-bestand worden geplaatst.

- Alle mediabestanden waarnaar wordt verwezen, moeten worden doorverwezen in de onderwerpbestanden met behulp van de relatieve koppeling.

- Maak een bestand index.html en voeg koppelingen toe naar de onderwerpen die u wilt toevoegen aan de inhoudsopgave. Dit bestand index.html wordt gebruikt om het DITA-kaartbestand te maken. In het bestand index.html kunt u ook geneste onderwerpen maken die worden vermeld in het volgende codevoorbeeld:

  ```XML
  <?xml version="1.0" encoding="UTF-8"?>
  <html
  xmlns="http://www.w3.org/1999/xhtml">
      <head>
          <title>Sample Index File</title>
      </head>
      <body>
          <h1>Sample Index</h1>
          <div class="content">
              <ul class="book">
                  <li class="topicref">
                      <a href="Topic1.html">Topic 1</a>
                      <ul class="book">
                          <li class="topicref">
                              <a href="Topic1-1.html">Topic 1.1</a>
                          </li>
                          <li class="topicref">
                              <a href="Topic1-2.html">Topic 1.2</a>
                          </li>
                      </ul>
                  </li>
                  <li class="topicref">
                      <a href="Topic2.html">Topic 2</a>
                  </li>
              </ul>
          </div>
      </body>
  </html>
  ```

  Let erop dat elke `ul` -tag moet de `class` kenmerk ingesteld op `book`. Op dezelfde manier elke `li` tag `class` moet worden ingesteld op `topicref`.

- Als u inline stijlen gebruikt, zet u de inline stijlen om in op CSS gebaseerde stijlklassen in uw XHTML-bestand. Vervolgens gebruikt u stijlkenmerktoewijzing om deze op klassen gebaseerde stijlen te converteren naar DITA `outputclass` in het geconverteerde DITA-bestand.

  Tijdens het genereren van de HTML- of AEM Site-uitvoer uit deze DITA-bestanden `outputclass` U kunt stijlklassen toepassen op gegenereerde HTML of AEM Site, zodat deze overeenkomen met de HTML-inhoud van uw bron.


Naast de overwegingen voor het maken van het ZIP-bestand moet uw XHTML-document ook goed gestructureerd zijn. Uw document moet bijvoorbeeld een *Titel*, gevolgd door *Kop 1*, *Kop 2*, enzovoort. Elk van de rubrieken zou wat inhoud in het moeten hebben. Als uw document niet goed gestructureerd is, werkt het migratieproces mogelijk niet naar behoren.

Voer de volgende stappen uit om uw bestaande XHTML-document om te zetten in DITA-onderwerp:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het standaardconfiguratiebestand dat beschikbaar is op de volgende locatie:

   `/libs/fmdita/config/h2d_io.xml`

1. Maak een overlayknooppunt van het dialoogvenster `config` in de `apps` knooppunt.

1. Navigeer naar het configuratiebestand dat beschikbaar is in het dialoogvenster `apps` knooppunt:

   `/apps/fmdita/config/h2d_io.xml`

   De `h2d_io.xml` bestand bevat de volgende configureerbare parameters:

   - In de `inputDir` -element, geeft u de locatie op van de invoermap waarin uw XHTML-brondocumenten beschikbaar zijn. Als uw XHTML-documenten bijvoorbeeld zijn opgeslagen in een map met de naam `xhtmltodita` in `projects` en geef vervolgens de locatie op als: `/content/dam/projects/xhtmltodita/`

   - In de`outputDir` -element, geeft u de locatie van de uitvoermap op of behoudt u de standaarduitvoerlocatie. Als de opgegeven uitvoermap niet bestaat op DAM, maakt de conversieworkflow de uitvoermap.

   - Voor de `createRev` element, specificeer of een nieuwe versie van het omgezette onderwerp DITA \ (`true`of niet \(`false`\).

1. Sla de `h2d_io.xml` bestand.

1. Na het vormen van de vereiste parameters in `h2d_io.xml` bestand, meldt u zich aan bij AEM en opent u de interface Middelen.

1. *\(Optioneel\)* U kunt ook de verwante sectie Koppelingen toevoegen aan de omgezette documenten. Voer de volgende stappen uit om deze functie in te schakelen:

   >[!NOTE]
   >
   > Standaard wordt de sectie Verwante koppelingen niet gemaakt in de omgezette documenten.

   1. Navigeer naar het bestand h2d.xsl op de volgende locatie:

      /libs/fmdita/html2dita/

   2. Zoek naar de volgende parameter:

      `<xsl:param name="generate-related-links" select="false()"/>`

   3. Stel de waarde van de bovenstaande parameter in op `true()`.
   4. Sla het bestand op en sluit het.
1. Ga naar de locatie van de invoermap \()`xhtmltodita`\).

1. Upload de bron-XHTML-documenten naar deze map. Voor informatie over het uploaden van inhoud naar DAM raadpleegt u [Bestaande DITA-inhoud uploaden](migrate-content-upload-existing-dita-content.md#).


Met de `<config> </config>` , kunt u een of meerdere configuraties definiëren voor conversie. De omzettingswerkstroom wordt uitgevoerd en de definitieve output in de vorm van een onderwerp DITA wordt bewaard in de plaats die in wordt gespecificeerd `outputDir` element.

## Niet-gestructureerde FrameMakers migreren {#id1949B050VUI}

Met AEM hulplijnen kunt u uw bestaande ongestructureerde FrameMaker \() omzetten`.fm` en `.book`\) documenten in DITA-documenten. De eerste stap bestaat uit het maken van stijltoewijzingen met behulp van FrameMaker en het opslaan van deze instellingen in een .sts-bestand. Als u vervolgens aangepaste DITA gebruikt, kunt u uw aangepaste elementen toewijzen aan de indelingen voor de FrameMaker van de bron in het dialoogvenster `ditaElems.xml` bestand. Als u bijvoorbeeld een aangepast element hebt gemaakt met de naam `impnote` als u alle belangrijke notities wilt verwerken, kunt u dit aangepaste element definiëren in het dialoogvenster `ditaElems.xml` bestand. Wanneer dit aangepaste element is gedefinieerd, wordt AEM hulplijnen geen fout weergegeven bij het omzetten van een FrameMaker met `impnote` element.

Ook, als u sommige extra attributen met uw douane of geldig element wilt specificeren DITA, kunt u die in het style2attrMap.xml- dossier bepalen. U kunt bijvoorbeeld de opdracht `type` kenmerk met de waarde van `important` die samen met de `impnote` element. Deze aanvullende informatie kan worden opgegeven in het bestand style2attrMap.xml.

Naast het specificeren van

Ga als volgt te werk om uw bestaande ongestructureerde documenten van de FrameMaker om te zetten in DITA-indeling:

1. Maak stijltoewijzingen in FrameMaker en sla deze instellingen op in een .sts-bestand.

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Als u aangepaste DITA-elementen hebt, definieert u deze in het dialoogvenster `ditaElems.xml` bestand beschikbaar op de volgende locatie:

   `/libs/fmdita/config/ditaElems.xml`

1. Maak een overlayknooppunt van het dialoogvenster `config` in de `apps` knooppunt.

1. Navigeer naar het configuratiebestand dat beschikbaar is in het dialoogvenster `apps` knooppunt:

   `/apps/fmdita/config/ditaElems.xml`

   De `ditaElems.xml` bestand bevat één configureerbare parameter:

   - In de `elem` , geeft u de naam op van het aangepaste element dat u wilt gebruiken in uw omgezette DITA-documenten. Dit element wordt doorgegeven, net als in de gegenereerde DITA-documenten.

1. Als u aanvullende kenmerken wilt opgeven, definieert u deze in het dialoogvenster `style2attrMap.xml` bestand beschikbaar op de volgende locatie:

   `/libs/fmdita/config/style2attrMap.xml`

1. Maak een overlayknooppunt van het dialoogvenster `config` in de `apps` knooppunt.

1. Navigeer naar het configuratiebestand dat beschikbaar is in het dialoogvenster `apps` knooppunt:

   `/apps/fmdita/config/style2attrMap.xml`

   De `style2attrMap.xml` bestand bevat de volgende configureerbare parameters:

   - In de `fmStyle` geeft u de bronindeling op die wordt gebruikt in het FrameMaker-document dat u wilt toewijzen.

   - In de`ditaAttr` -element, geeft u het DITA-kenmerk op dat u wilt toewijzen met de bronindeling.

   - In de `ditaVal` -element, geeft u de waarde voor het toegewezen kenmerk op. Als u geen waarde hebt, kunt u dit item leeg laten.

1. Sla de `style2attrMap.xml` bestand.

1. Na het vormen van de vereiste parameters in `style2attrMap.xml` bestand, meldt u zich aan bij AEM en opent u de interface Middelen.

1. Navigeer naar en klik op het document van de FrameMaker dat u wilt omzetten.

   De DITA kaartconsole verschijnt tonend de lijst van Output stelt beschikbaar om output te produceren.

1. Selecteer DITA-uitvoerindeling en configureer de vereiste parameters.

   >[!NOTE]
   >
   > U moet het instellingenbestand \(.sts\) gebruiken dat u in de FrameMaker hebt gemaakt. Geef ook de naam van de instellingen en het bestemmingspad op.

1. Klik op de knop **Genereren** om het productieproces voor de uitvoer te starten.


Met de `<attrMap> </attrMap>` , kunt u een of meerdere configuraties definiëren voor conversie. Afhankelijk van de inhoud, zou u een.dita- dossier en een.ditamap- dossier als omgezette dossiers kunnen hebben.

## Andere gestructureerde documenten migreren {#id1949B0590YK}

Met AEM hulplijnen kunt u uw bestaande gestructureerde documenten converteren naar geldige DITA-documenten. U moet de locatie van de invoer- en uitvoermap, de locatie van het transformatiebestand, de extensie opgeven waarmee de uiteindelijke uitvoer wordt opgeslagen en of een nieuwe versie van het document is vereist of niet.

Voer de volgende stappen uit om uw bestaande gestructureerde documenten om te zetten in DITA-indeling:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het standaardconfiguratiebestand dat beschikbaar is op de volgende locatie:

   `/libs/fmdita/config/XSLConfig.xml`

1. Maak een overlayknooppunt van het dialoogvenster `config` in de `apps` knooppunt.

1. Navigeer naar het configuratiebestand dat beschikbaar is in het dialoogvenster `apps` knooppunt:

   `/apps/fmdita/config/XSLConfig.xml`

   De `XSLConfig.xml` bestand bevat de volgende configureerbare parameters:

   - In de `inputDir` -element, geeft u de locatie op van de invoermap waarin de gestructureerde brondocumenten beschikbaar zijn. Als uw gestructureerde documenten bijvoorbeeld zijn opgeslagen in een map met de naam `xsltodita` in `projects` en geef vervolgens de locatie op als: `/content/dam/projects/xsltodita/`

   - In de`outputDir` -element, geeft u de locatie van de uitvoermap op of behoudt u de standaarduitvoerlocatie. Als de opgegeven uitvoermap niet bestaat op DAM, maakt de conversieworkflow de uitvoermap.

   - In de `xslFolder` -element, geeft u de locatie op van de map waarin de XSL-transformatiebestanden zijn opgeslagen.

   - In de ``xslPath`` -element, geeft u de locatie op van het primaire XSL-bestand waarmee het conversieproces wordt gestart.

   - In de ``outputExt`` -element, geeft u de bestandsextensies op van het uiteindelijke uitvoerbestand dat met de transformatiestream is gemaakt.

   - Voor de `createRev` element, specificeer of een nieuwe versie van het omgezette onderwerp DITA \ (`true`of niet \(`false`\).

1. Sla de `XSLConfig.xml` bestand.

1. Na het vormen van de vereiste parameters in `XSLConfig.xml` bestand, meldt u zich aan bij AEM en opent u de interface Middelen.

1. Ga naar de locatie van de invoermap \()`xsltodita`\).

1. Upload de gestructureerde brondocumenten naar deze map. Voor informatie over het uploaden van inhoud naar DAM raadpleegt u [Bestaande DITA-inhoud uploaden](migrate-content-upload-existing-dita-content.md#).


Met de `<config> </config>` , kunt u een of meerdere configuraties definiëren voor conversie. De omzettingswerkstroom wordt uitgevoerd en de definitieve output in de vorm van een onderwerp DITA wordt bewaard in de plaats die in wordt gespecificeerd `outputDir` element.

**Bovenliggend onderwerp:**[ Bestaande inhoud migreren](migrate-content.md)
