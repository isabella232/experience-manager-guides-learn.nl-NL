---
title: Native PDF | Productie van PDF
description: Leer hoe u het publiceren van eigen PDF kunt gebruiken, een voorinstelling voor PDF-uitvoer kunt maken en genereren, tijdelijke bestanden kunt downloaden nadat u de uitvoer van eigen PDF hebt gegenereerd en taalvariabelen in AEM hulplijnen kunt gebruiken.
exl-id: ec3d59b7-1dda-4fd1-848e-21d8a36ff5e4
source-git-commit: 1305c960df98553edbd1fb65c8f6e8da7c232087
workflow-type: tm+mt
source-wordcount: '3327'
ht-degree: 0%

---

# PDF-uitvoer publiceren

Met AEM Gidsen, kunt u PDF van individuele onderwerpen of een volledig kaartdossier produceren. U kunt de inhoud publiceren in een PDF-indeling met een van de volgende drie methoden:

* **DITA-OT**

Gebruik deze methode om een uitvoer van PDF voor een kaart van het kaartdashboard te produceren. U kunt publicatie-eigenschappen instellen voordat u de PDF genereert door een uitvoervoorinstelling te maken voor de kaart die is geopend in het kaartdashboard. Als u een uitvoervoorinstelling wilt maken of bewerken, *Uitvoervoorinstellingen* in de [as a Cloud Service gebruikershandleiding voor AEM](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Voor meer informatie bij het produceren van een PDF die de methode DITA-OT gebruikt, zie [PDF genereren met DITA-OT](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-pdf.html).

* **FrameMaker Publishing Server (FMPS)**

Met deze methode kunt u een PDF-uitvoer genereren op basis van niet alleen de DITA-inhoud, maar ook FrameMaker-documenten (.book en .fm) die beschikbaar zijn in uw AEM opslagplaats. De PDF kan worden gemaakt door een uitvoervoorinstelling te configureren en te publiceren met behulp van FrameMaker Publishing Server (FMPS). U kunt het uiterlijk van uw uitvoer voor PDF en andere indelingen ontwerpen en configureren en deze opslaan in een instellingsbestand (.sts). Dit instellingsbestand wordt vervolgens door FMPS gebruikt om uitvoer te genereren voor een DITA-kaart of .book-bestand. Als u een uitvoervoorinstelling wilt maken of bewerken, raadpleegt u de  *Uitvoervoorinstellingen* in de [as a Cloud Service gebruikershandleiding voor AEM](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

Zie voor meer informatie over het configureren van FMPS [Uitvoer genereren op basis van FrameMaker-documenten](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Ffm-output-generatation.html).

* **Native PDF-publicatie**

Gebruik deze methode om een PDF-uitvoer met veel functies te genereren op basis van W3C CSS3- en CSS-paginanormen. Met de publicatie Native PDF kunt u sjablonen gebruiken om de lay-out en opmaak voor uw inhoud in te stellen en verschillende instellingen toepassen om uw PDF te verfijnen. Daarnaast kunt u uw eigen sjablonen wijzigen en maken met de sjablooneditor.

Voor meer informatie over het publiceren van Native PDF raadpleegt u [Native PDF-publicaties gebruiken](#native-pdf-publishing).


## De publicatie Native PDF gebruiken {#native-pdf-publishing}

Bij het ontwerpen van inhoud wordt het van essentieel belang dat de inhoud is geoptimaliseerd voor weergave, bewerking en afdrukken. Met standaarden zoals W3C CSS3 voor inhoudsopmaak en CSS-normen voor gepagineerde media voor eigenschappen van paginadefinities, zoals grootte, marges, afdrukstand, pagina-einden, kop- en voetteksten en paginanummering, kunt u de weergave en lay-out voor uw PDF-document instellen, zodat deze consistent en bruikbaar zijn. De publicatiefunctie Native PDF gebruikt deze standaarden om een PDF te genereren.

Met de native publicatie van PDF kunt u vooraf gedefinieerde sjablonen gebruiken om consistentie in de indeling en structuur van de inhoud te garanderen, stijlpagina&#39;s toepassen om de vormgeving van de uitvoer te wijzigen, PDF te optimaliseren, drukkermarkeringen in te stellen, ondersteuning voor schermlezers mogelijk te maken, PDF-conformiteit in te stellen, lettertypen in te sluiten en nog veel meer.

Het genereren van een PDF met behulp van Native PDF-publicaties heeft twee aspecten:

* Gebruik sjablonen om opmaak toe te passen op inhoud, paginalay-outs en verschillende instellingen in te stellen om de PDF te perfectioneren. Auteurs kunnen de voorbeeldsjablonen gebruiken of wijzigen of aangepaste sjablonen maken en geavanceerde configuratieopties instellen die door uitgevers en ontwikkelaars worden gebruikt.

* Maak of configureer een voorinstelling voor PDF-uitvoer om de PDF-instellingen te bepalen. Nadat u een voorinstelling voor PDF-uitvoer hebt gemaakt, kunt u de PDF genereren.

Zie voor meer informatie [Een PDF-uitvoer genereren](#generate-pdf-output).

## Een voorinstelling voor PDF-uitvoer maken {#create-output-preset}

De eerste stap bij het genereren van een PDF-uitvoer bestaat uit het maken van een voorinstelling voor PDF-uitvoer. Dit is een verzameling publicatie-eigenschappen die aan een kaart zijn toegewezen. U kunt een uitvoervoorinstelling maken voor elke kaart die is geopend in het deelvenster Kaartweergave, of een bestaande voorinstelling configureren om snel een PDF voor dezelfde kaart te genereren.

Vanuit de voorinstelling voor PDF-uitvoer kunt u een sjabloon selecteren, voorwaarden toepassen, beperkingen instellen om te bepalen hoe een gebruiker met de PDF werkt, geavanceerde instellingen configureren, zoals compressie, conformiteit en meer.

Een voorinstelling voor PDF-uitvoer maken of configureren:

1. Klik op het tabblad Uitvoer op **Voorinstellingen** in de linkerzijbalk.
Het deelvenster Voorinstelling wordt geopend. <br>
<img src="assets/preset-panel.png" alt="deelvenster met voorinstellingen" width="600">

1. In de uitvoer **Voorinstellingen** voert u een van de volgende handelingen uit:
   * Dubbelklik op een vooraf gedefinieerde PDF-uitvoervoorinstelling om deze weer te geven.
   * Klik op het pictogram + **Voorinstellingen** om een nieuwe uitvoervoorinstelling toe te voegen van **Type: PDF**

1. Instellingen configureren van een bestaande PDF-voorinstelling:
   * Klik op de knop  **Opties** ![opties](assets/options.svg) pictogram naast de gewenste uitvoervoorinstelling en selecteer **Bewerken**.
U kunt de volgende instellingen gebruiken in het dialoogvenster **Algemeen**, **Metagegevens**, **Layout**, **Beveiliging**, en **Geavanceerd** tabs voor het configureren van een PDF-uitvoervoorinstelling:

**Algemeen**

Gebruik deze optie om basisuitvoerinstellingen op te geven, zoals een uitvoerpad, een bestandsnaam voor PDF en meer.

| Instelling | Beschrijving |
| --- | --- |
| **Uitvoerpad** | Het pad binnen de AEM opslagplaats waar de PDF-uitvoer wordt opgeslagen. Zorg ervoor dat het uitvoerpad zich niet in de projectmap bevindt. Als deze optie leeg wordt gelaten, wordt de uitvoer gegenereerd op de standaarduitvoerlocatie voor de DITA-kaart.<br>U kunt ook de volgende variabelen buiten het vak gebruiken om het uitvoerpad te definiëren. U kunt een enkele of een combinatie van variabelen gebruiken om deze optie te definiëren. <br> `${map_filename}`: Hiermee gebruikt u de naam van de DITA-toewijzingsbestanden om het doelpad te maken. <br> `${map_title}`: Hiermee gebruikt u de titel van de DITA-kaart om het doelpad te maken. <br>`${preset_name}`: Hiermee wordt de naam van de uitvoervoorinstelling gebruikt om het doelpad te maken. <br> `${language_code}`: Hiermee wordt de taalcode gebruikt waar het kaartbestand zich bevindt om het doelpad te maken. <br> `${map_parentpath}`: gebruikt het volledige pad van het kaartbestand om het doelpad te maken.  <br>`${path_after_langfolder}`: gebruikt het pad van het kaartbestand na de taalmap om het doelpad te maken. |
| **PDF-bestand** | Geef een bestandsnaam op om de PDF op te slaan. Standaard wordt in de bestandsnaam PDF de naam van de DITA-kaart en de naam van de voorinstelling toegevoegd. ditamap is bijvoorbeeld &#39;TestMap&#39; en de naam van de voorinstelling is &#39;preset1&#39;. De standaardnaam van de pdf is &#39;TestMap_preset1.pdf&#39;. <br>U kunt ook de volgende variabelen gebruiken om het PDF-bestand te definiëren. U kunt een enkele of een combinatie van variabelen gebruiken om deze optie te definiëren. <br>`${map_filename}`<br>`${map_title}`<br>`${preset_name}` <br> `${language_code}`. |
| **Voorwaarden toepassen met** | Voor geconditionaliseerde inhoud kiest u uit de onderstaande opties om op basis van deze voorwaarden een PDF-uitvoer te genereren: <br><ul> <li> **Geen toegepast** Selecteer deze optie als u geen voorwaarde wilt toepassen op de kaart en broninhoud. <br><li> **Ditaval File** Selecteer een DITAVAL-bestand om geconditioneerde inhoud te genereren. Klik op Voorinstelling voorwaarde om dit te selecteren en zoek het bestand. <br> <li> **Voorinstelling voorwaarde** Selecteer een voorinstelling voor een voorwaarde in het keuzemenu om een voorwaarde toe te passen tijdens het publiceren van de uitvoer. Deze optie is zichtbaar als u een voorwaarde voor het DITA kaartdossier hebt toegevoegd. De voorwaardelijke instellingen zijn beschikbaar op het tabblad Voorinstellingen voorwaarde van de DITA-kaartconsole. Zie voor meer informatie over voorinstellingen voor voorwaarden [Voorinstellingen voor voorwaarden gebruiken](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-condition-presets.html). <br> </ul> |
| **Basislijn gebruiken** | Als u een basislijn voor de geselecteerde kaart hebt gecreeerd DITA, selecteer deze optie om de versie te specificeren die u wilt publiceren. Zie [Werken met basislijn](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Fgenerate-output-use-baseline-for-publishing.html) voor meer informatie . |
| **PDF maken met wijzigingsbalk tussen gepubliceerde versies** | Gebruik de volgende opties om een PDF te maken die de verschillen in inhoud tussen twee versies weergeeft met wijzigingsbalken:   <br><ul><li> **Basislijn van de vorige versie** Kies de basislijnversie die u met de huidige versie of een andere basislijn wilt vergelijken. Er wordt een wijzigingsbalk weergegeven in de PDF om de gewijzigde inhoud aan te geven. Een wijzigingsbalk is een verticale lijn die nieuwe of herziene inhoud visueel identificeert. De wijzigingsbalk verschijnt links van de inhoud die is ingevoegd, gewijzigd of verwijderd. <br> **Opmerking**: Als u **Basislijn gebruiken** en kies een basislijn om te publiceren, zal de vergelijking tussen de twee geselecteerde basislijnversies worden gedaan. Als u bijvoorbeeld basislijnversie 1.3 kiest onder **Basislijn gebruiken** en versie 1.1 onder **Basislijn van de vorige versie**, zal de vergelijking tussen basislijnversie 1.1 en basislijnversie 1.3 worden gedaan. <br><li> **Toegevoegde tekst tonen** Selecteer deze optie om de ingevoegde tekst in groene kleur en onderstreept weer te geven. Deze optie is standaard ingeschakeld. <br> <li> **Verwijderde tekst tonen** Selecteer deze optie om de verwijderde tekst rood weer te geven en doorhalen. Deze optie is standaard ingeschakeld. <br>**Opmerking** U kunt de opmaak van de wijzigingsbalk, ingevoegde inhoud of verwijderde inhoud ook aanpassen met de stijlpagina.<br></ul> |
| **Workflow na generatie** | Selecteer deze optie om een vervolgkeuzelijst weer te geven met alle workflows die in AEM zijn geconfigureerd. U kunt de workflow selecteren die u wilt uitvoeren nadat de workflow voor het genereren van PDF is voltooid. |

**Metagegevens**

Metagegevens zijn de beschrijving of definitie van de inhoud. Metagegevens helpen bij inhoudsbeheer en helpen bij het zoeken naar bestanden op internet.

Gebruik het tabblad Metagegevens om de metagegevensvelden in te stellen, zoals de naam van de auteur, de documenttitel, trefwoorden, copyrightinformatie en andere gegevensvelden voor de uitvoer van de PDF. U kunt ook aangepaste metagegevens toevoegen voor uw PDF-uitvoer.

Deze metagegevens worden toegewezen aan de metagegevens op het tabblad Beschrijving in de documenteigenschappen van de uitvoer-PDF.

**Opmerking**: Deze metagegevens overschrijven de metagegevens die op boekniveau zijn gedefinieerd.

<img src="assets/pdf-metadata.png" alt="tabblad Metagegevens" width="600">

Uit de uitvoervoorinstellingen **PDF selecteren** > **Metagegevens** als u opties voor metagegevens wilt toevoegen en aanpassen.
* **XMP bestand opgeven**

  Metagegevensvelden kunnen rechtstreeks worden gevuld door te importeren [XMP](https://www.adobe.com/products/xmp.html) (Extensible Metadata Platform)-bestand. U kunt hier een voorbeeld XMP bestand downloaden.

[Downloaden](assets/SampleXMP.xmp)

  U kunt ook een XMP bestand genereren met Adobe Acrobat.
   1. Klikken **Bestand** > **Eigenschappen** in Acrobat.
   1. Onder **Beschrijving**, klikt u op **Aanvullende metagegevens**.
   1. Selecteer in het linkerdeelvenster de optie **Geavanceerd**.
   1. Klikken op **Opslaan**.

  XMP bestand wordt opgeslagen op het apparaat.

* **Geef metagegevensnamen en -waarden op**

   1. Voeg naam toe door uit de drop-down te selecteren of een douanemetagegevens toe door direct op het naamgebied te typen.
   1. Voer de waarde voor de metagegevens in en klik op het pictogram &#39;+&#39;.
De metagegevens worden toegevoegd aan de lijst met metagegevens voor de PDF.

U kunt ook variabelen gebruiken om de waarden van metagegevens te definiëren.  U kunt de metagegevens die voor de DITA-kaart of het bladwijzerbestand zijn gedefinieerd, als variabelen gebruiken. De metagegevens vindt u onder de `/jcr:content/metadata` knooppunt van de DITA-kaart of het bladwijzerbestand.
Wanneer u een variabele gebruikt, wordt de waarde ervan gekozen uit de eigenschappen van metagegevens.

Als u een variabele wilt gebruiken, moet u deze definiëren in het dialoogvenster `${<variable>}` gebruiken.

Een van de metagegevenseigenschappen die bijvoorbeeld zijn gedefinieerd in de map /`jcr:content/metadata` node is
`dc:title`. U kunt `${dc:title}`en wordt de titelwaarde gebruikt in de uiteindelijke uitvoer.

U kunt een enkele of een combinatie van variabelen gebruiken om de metagegevens te definiëren. Bijvoorbeeld, `${dc:title} ${dc:docstate}`. U kunt ook de combinatie van een variabele en een tekenreeks gebruiken.  Bijvoorbeeld, `View ${dc:title} in ${dc:language}`.

Taalvariabelen gebruiken om de gelokaliseerde waarde van eigenschappen van metagegevens te definiëren. Afhankelijk van de gekozen taal wordt de gelokaliseerde waarde automatisch gekozen in de uitvoer van de PDF. U kunt bijvoorbeeld &quot;Auteur&quot; afdrukken als de metagegevenswaarde in het Engels en &quot;Autorin&quot; in het Duits.

Indeling: `${lng:<variable name>}`. Bijvoorbeeld: `${lng:author-label}` waar `author-label` is een taalvariabele.

Overslaan <img src="./assets/info-details.svg" alt= "info icon" width="25"> in de buurt van de optie voor meer informatie over de optie.


**Layout**

Hiermee kunt u paginalay-outs instellen en paginaweergaveopties opgeven voor PDF-uitvoer, zoals Paginaweergave en Zoomniveaus instellen.

| Instelling | Beschrijving |
| --- | --- |
| **PDF-sjabloon** | PDF-sjablonen bieden een duidelijke structuur voor het definiëren van paginalay-outs, het opmaken van inhoud en het toepassen van verschillende instellingen op de PDF-uitvoer. Selecteer een sjabloon in de vervolgkeuzelijst PDF-sjabloon om uw voorkeursjabloon te kiezen. <br> U kunt ook **Door sjabloon bladeren** <img src="./assets/browse-templates-icon.svg"  alt= "bladersjablonen, pictogram" width="25">  om een sjabloon te kiezen. In de **PDF-sjabloon selecteren** kunt u ook een voorvertoning van de miniatuur weergeven en de titel en beschrijving van de geselecteerde sjabloon bekijken. |
| **Paginaweergave** | Gebruik de paginaweergave voor de paginaweergave waarin wordt getoond hoe de PDF wordt weergegeven wanneer deze wordt geopend. Selecteer een optie in het keuzemenu Paginaweergave om een voorkeursweergave te kiezen. <br><ul><li> **Standaard**  Hiermee wordt de standaardinstelling van de PDF-viewer op de computer van de gebruiker weergegeven.  <br> <li> **Weergave één pagina** Hiermee geeft u één pagina tegelijk weer.   <br> <li> **Bladeren op één pagina** Hiermee geeft u één pagina weer in een doorlopende verticale kolom.  <br> <li> **Weergave van twee pagina&#39;s** Hiermee geeft u de spread van twee pagina&#39;s naast elkaar weer. .<br> <li> **Bladeren op twee pagina&#39;s** Hiermee geeft u de spread van twee pagina&#39;s naast elkaar weer terwijl u doorlopend schuift. </ul> |
| **Zoomen** | Selecteer deze optie om het formaat te wijzigen van de paginaweergave waarin wordt getoond hoe de PDF wordt weergegeven wanneer deze wordt geopend.  <br><ul><li> **Standaard** Wordt weergegeven volgens de standaardinstelling van de PDF-viewer op de computer van de gebruiker    <br> <li> **100%** Hiermee geeft u de pagina op ware grootte weer.     <br> <li> **Pagina passend maken** Hiermee past u de breedte en hoogte van de pagina aan in het documentvenster. .<br> <li> **Paginabreedte passend maken** Hiermee zorgt u dat de breedte van de pagina de breedte van het documentvenster vult.  <br> <li> **Paginahoogte passend maken** Hiermee stelt u de hoogte van de pagina in op de hoogte van het documentvenster. </ul> |

**Beveiliging**

Protect uw PDF door beperkingen toe te voegen om het bestand te openen en te lezen. Gebruik de onderstaande opties om ongeoorloofde toegang te voorkomen.

| Instelling | Beschrijving |
| --- | --- |
| **Wachtwoord instellen om het document te openen** | Selecteer deze optie om een beveiligd wachtwoord toe te voegen om uw PDF-bestand weer te geven. Geef een wachtwoord op in het dialoogvenster **Gebruikerswachtwoord** veld. Gebruikers kunnen de PDF alleen openen door het wachtwoord in te voeren dat in dit veld is opgegeven. |
| **Documentbeperkingen instellen** | Selecteer deze optie om de interactie tussen gebruikers en uw PDF te beperken. Geef een wachtwoord op in het dialoogvenster **Wachtwoord eigenaar** -veld voor de onderstaande beperkingsinstellingen.  <br><ul><li> **Afdrukken** Selecteer deze optie als de gebruiker de PDF mag afdrukken. <br> <li> **Afdrukken van conceptkwaliteit** Schakel deze optie in om de gebruiker toe te staan de PDF in een lagere resolutie af te drukken.  <br> <li> **Inhoud kopiëren** Selecteer deze optie om toe te staan dat een gebruiker inhoud uit de PDF kopieert.   <br> <li> **Annotaties** Selecteer deze optie om een gebruiker toe te staan een opmerking of opmerking toe te voegen in de PDF.  <br> <li> **Inhoudswijzigingen** Schakel deze optie in als u wilt dat een gebruiker de inhoud van de PDF kan wijzigen.  <br> <li> **Inhoud kopiëren voor toegankelijkheid** Schakel deze optie in om schermlezers de mogelijkheid te bieden inhoud te lezen en te navigeren in PDF.  <br>  **Documentverzameling** Selecteer deze optie om gebruikers toe te staan pagina&#39;s in te voegen in de PDF.  <br> **Opmerking**: De gebruikers moeten het wachtwoord van de eigenaar invoeren om beperkingen te kunnen wijzigen via Bestand > Eigenschappen in Adobe Acrobat. |

**Geavanceerd**

Gebruik de volgende opties om geavanceerde instellingen op te geven voor het samenvoegen van PDF, compressie gebruiken, compatibiliteitsnorm selecteren en meer.

| Instelling | Beschrijving |
| --- | --- |
| **Toegankelijke (gelabelde) PDF maken** | Selecteer deze optie als u een PDF met tags wilt genereren. Met een gecodeerde PDF kunnen schermlezers gemakkelijker inhoud, hyperlinks, bladwijzers enzovoort lezen en door de inhoud navigeren. Als een tabel bijvoorbeeld is gecodeerd, weet de schermlezer dat deze de tabel leest en niet alleen regels en tekst. |
| **PDF in de inhoudsopgave samenvoegen** | Selecteer deze optie om bestaande PDF in uw output samen te voegen door hen aan uw kaart DITA als middeldossier toe te voegen. De PDF worden ingevoegd op de locatie die op de kaart wordt weergegeven en de pagina&#39;s worden dienovereenkomstig verhoogd. |
| **Gebruikte lettertypen insluiten** | Selecteer deze optie als u lettertypen gebruikt die mogelijk niet op de computer van de eindgebruiker zijn geïnstalleerd. Als deze optie is ingeschakeld, worden de gebruikte lettertypen ingesloten in de PDF, zodat de gebruiker de PDF kan zien zoals deze is bedoeld, zelfs als de lettertypen niet op zijn computer zijn geïnstalleerd. <br> **Opmerking**: Een lettertype kan alleen worden ingesloten als het een instelling van de leverancier van het lettertype bevat die insluiten van het lettertype toestaat. Zorg ervoor dat u de vereiste instelling of licentie hebt voordat u een lettertype insluit. |
| **Automatische woordafbreking gebruiken** | Als automatische woordafbreking is ingeschakeld, worden woorden aan het einde van regels op grammaticaal correcte plaatsen afgebroken met een afbreekstreepje. |
| **JavaScript inschakelen** | Schakel deze optie in als u een JavaScript-code hebt waarmee u de inhoud dynamisch wilt transformeren voordat u een PDF genereert. |
| **Multimediabestanden insluiten** | Selecteer deze optie als u alle audio, video en interactieve inhoud van de PDF wilt opnemen. |
| **Volledige compressie gebruiken om de PDF te optimaliseren** | Selecteer deze optie als u een grote PDF wilt comprimeren of verkleinen. Houd er rekening mee dat het comprimeren van de PDF de bestandskwaliteit kan verminderen. |
| **Afbeeldingscompressie gebruiken om de PDF te optimaliseren** | Selecteer deze optie als u de gebruikte afbeeldingen in uw PDF wilt comprimeren of verkleinen. Houd er rekening mee dat het comprimeren van een afbeelding de afbeeldingskwaliteit kan verminderen. |
| **Aangepaste resolutie gebruiken (pixels per inch)** | Dit is de resolutie van de paginaweergave bij pixels per inch. Voer in het veld een voorkeurswaarde in die wordt weergegeven wanneer deze optie wordt geselecteerd. De standaardwaarde is 96 pixels per inch. Stel een hogere waarde in om meer inhoud in een inch te passen en andersom als u een lagere waarde instelt. |
| **Watermerk tonen** | Selecteer deze optie als u een watermerk in de uitvoer wilt plaatsen. U kunt een nieuwe tekstreeks in het tekstvak invoeren met de tekenbehuizing zoals u wilt. <br><br>Gebruik statische tekst of taalvariabelen om de gelokaliseerde versie van het watermerk te publiceren.  Afhankelijk van de gekozen taal wordt de gelokaliseerde waarde automatisch gekozen in de uitvoer van de PDF. U kunt bijvoorbeeld &quot;Publisher&quot; afdrukken als een watermerk in het Engels en &quot;Auteure&quot; in het Frans.  <br> Indeling: `${lng:<variable name>}`. Bijvoorbeeld: `$ {lng:publisher-label}` waar `publisher-label` is een taalvariabele. <br> Overslaan <img src="./assets/info-details.svg" alt= "info icon" width="25"> in de buurt van de optie voor meer informatie over de optie. |
| **MathML-vergelijkingen inschakelen** | Selecteer deze optie om MathML-vergelijkingen in uw inhoud te renderen. De vergelijkingen worden anders standaard genegeerd. |
| **Tijdelijke bestanden downloaden** | Selecteer deze optie als u de tussentijdse HTML-bestanden wilt downloaden die tijdens het genereren van de native PDF-uitvoer zijn gemaakt. U kunt de tijdelijke bestanden later downloaden nadat u de uitvoer hebt gegenereerd. |
| **PDF-conformiteit** | Dit is de standaard waarmee u de PDF wilt opslaan om ervoor te zorgen dat deze compatibel is. Selecteer een optie in het vervolgkeuzemenu om een keuze te maken in de lijst met beschikbare PDF-standaarden. Zie voor meer informatie over de ondersteunde standaarden [PDF-standaarden](https://helpx.adobe.com/acrobat/using/pdf-conversion-settings.html#about_pdf_x_pdf_e_and_pdf_a_standards). |
| **Bestandseigenschappen** | Selecteer de eigenschappen die u als metagegevens wilt verwerken. In het vervolgkeuzemenu worden zowel de aangepaste als de standaardeigenschappen weergegeven. Deze eigenschappen worden ingesteld op de pagina Eigenschappen van de DITA-kaart of het bladwijzerbestand. Zodra reeks, worden deze eigenschappen ook gekopieerd in de onderwerpen binnen de kaart. De geselecteerde eigenschappen van metagegevens worden doorgegeven aan de uitvoer die wordt gegenereerd met Native-PDF. |

## Een PDF-uitvoer genereren {#generate-pdf-output}

Als u de uitvoervoorinstelling hebt geconfigureerd, kunt u uitvoer genereren vanuit het deelvenster Voorinstellingen met de opdracht **Voorinstelling genereren** gebruiken.

1. Onder de **Auteur** selecteert u de **Bewaarplaats** Weergeven.\
   Hiermee wordt het deelvenster Opslagplaats geopend.

1. Open het DITA-kaartbestand in het deelvenster Opslagplaats **Kaartweergave**.

1. In de **Uitvoer** tabblad, klikt u op **Voorinstellingen** om het deelvenster Voorinstelling weer te geven.
Als u een uitvoervoorinstelling wilt maken of configureren, raadpleegt u [Een voorinstelling voor PDF-uitvoer maken](#create-output-preset).
1. Als u uw instellingen wilt opslaan, klikt u op de knop **Alles opslaan** ![alles opslaan](assets/SaveFloppy_icon.svg) in de linkerbovenhoek van de standaardwerkbalk in de uitvoerweergave.
1. Klik op de knop **Voorinstelling genereren** ![voorinstelling genereren](assets/generate-output.svg) op de bovenste balk.
In het deelvenster Voorinstellingen uitvoer kunt u een voortgangsbalk weergeven naast de geselecteerde uitvoervoorinstelling.
1. Als de uitvoergeneratie is voltooid, klikt u op  **Uitvoer weergeven** ![uitvoer weergeven](assets/view-output.svg) op de bovenste balk om de uitvoer weer te geven.\
   A **Succes** wordt in de rechterbenedenhoek van het scherm weergegeven.
Als de uitvoer niet is gelukt, wordt het onderstaande foutbericht weergegeven.
<img src="assets/error-log.png" alt="foutenlogboek" width="250">

Als u het foutenlogboek wilt weergeven, klikt u op **Afwijzen**, plaatst u de cursor boven het geselecteerde tabblad met voorinstellingen en klikt u op ![opties](assets/options.svg) **Opties** > **Logboek weergeven**.

### Tijdelijke bestanden downloaden nadat de uitvoer van de native PDF is gegenereerd

Als u **Tijdelijke bestanden downloaden** in de Geavanceerde instellingen kunt u ook de tussentijdse HTML-bestanden downloaden die zijn gemaakt tijdens het genereren van de eigen PDF-uitvoer. Nadat u de uitvoer hebt gegenereerd, kunt u de tijdelijke bestanden downloaden met de opdracht **Tijdelijke bestanden downloaden** ![tijdelijke bestanden downloaden](assets/native-pdf-download-temporary-files-icon.svg)op de bovenste balk. Met deze functie kunt u uw tijdelijke stijlen en lay-outs voor HTML weergeven en kunt u uw CSS-stijlen naar wens corrigeren of wijzigen.


>[!NOTE]
>
> De **Tijdelijke bestanden downloaden**  ![tijdelijke bestanden downloaden](assets/native-pdf-download-temporary-files-icon.svg) wordt alleen weergegeven als u de laatste PDF-uitvoer hebt gegenereerd met de voorinstelling waarin u de optie hebt geselecteerd in het dialoogvenster **Geavanceerd** tab.



### Taalvariabelen gebruiken

AEM de Gidsen verleent ook de steun voor taalvariabelen. Selecteren **Taalvariabelen** <img src="./assets/language-variables.svg" width="25">  in het linkerpaneel om een gelokaliseerde versie van de uit-van-de-doos etiketten zoals Nota, Voorzichtigheid, en Waarschuwing of statische tekst in de output van PDF te bepalen. Zie voor meer informatie [Ondersteuning voor taalvariabelen](../native-pdf/native-pdf-language-variables.md).

