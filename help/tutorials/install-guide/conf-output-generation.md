---
title: Instellingen voor uitvoergeneratie configureren
description: Leer hoe u instellingen voor uitvoergeneratie configureert
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '5762'
ht-degree: 0%

---

# Instellingen voor uitvoergeneratie configureren {#id181AI0B0E30}

AEM Hulplijnen worden geleverd met veel configuratieopties waarmee u het productieproces voor uitvoer kunt aanpassen. Dit onderwerp behandelt alle configuraties en aanpassingen die u aan opstelling uw proces van de outputgeneratie zouden helpen.

## Het tabblad Basislijn op het dashboard voor de DITA-kaart configureren {#id223MD0D0YRM}

U kunt het tabblad Basislijn dat beschikbaar is op het dashboard voor de kaart configureren en verbergen.

De **Tabblad Basislijn verbergen** optie wordt niet toegelaten door gebrek en u moet dit van configMgr toelaten. Voer de volgende stappen uit om de optie door gebrek in de Redacteur van het Web toe te laten:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. Selecteer de **Tabblad Basislijn verbergen** -optie.

1. Klikken **Opslaan**.

   >[!NOTE]
   >
   > Deze configuratie is standaard uitgeschakeld en het tabblad Basislijn is beschikbaar op het kaartdashboard.


## FrameMaker Publishing Server configureren {#id1678G0Z0TN6}

U kunt FrameMaker Publishing Server \(FMPS\) gebruiken om uitvoer voor uw DITA-inhoud te genereren. Als u FMPS configureert, kunt u uitvoer genereren in meerdere indelingen die worden ondersteund door FMPS.

>[!NOTE]
>
> Als u uitvoer wilt genereren met FMPS, moet u de FMPS-server hebben ingesteld. Zie de gebruikershandleiding voor de FrameMaker Publishing Server voor installatie- en configuratiegegevens.

Als u AEM hulplijnen wilt configureren voor het gebruik van FMPS, moet u de volgende eigenschappen van de `com.adobe.fmdita.config.ConfigManager` in de webconsole.

>[!NOTE]
>
> http://&lt;server name=&quot;&quot;>:&lt;port>/system/console/configMgr URL om de Console van het Web te openen.

| Eigenschap | Beschrijving |
|--------|-----------|
| Aanmeldingsdomein FrameMaker Publishing Server | Geef de domeinnaam of de naam van de werkgroep op waarop de FrameMaker Publishing Server wordt gehost. Geef op basis van de FMPS-versie de domeinnaam op als:-   **FMPS 2020**: IP-adres als 192.168.1.101 <br>- **FMPS 2019 en eerder**: IP-adres of domeinnaam |
| FrameMaker Publishing Server-URL | Geef de URL van de FrameMaker Publishing Server op. Geef op basis van de FMPS-versie de FMPS-URL op als:<br>- **FMPS 2020**: `http://<fmps_ip>:<port>` \(http://192.168.1.101:7000\) <br> - **FMPS 2019 en eerder**: `http://<fmps_ip>:<port>/fmserver/v1/` |
| FMPS-versie | Geef het versienummer van de FrameMaker Publishing Server op. Geef de versiegegevens op basis van de FMPS-versie als volgt op: <br>- **FMPS 2020**: 2020 <br> - **FMPS 2019 en eerder**: 2019 of 2017 |
| Gebruikersnaam en wachtwoord voor FrameMaker Publishing Server | Geef de gebruikersnaam en het wachtwoord op voor toegang tot de FrameMaker Publishing Server. |
| FMPS-timeout | \(*Optioneel*\) Geef de tijd op \(in seconden\) waarop AEM hulplijnen wachten op een reactie van de FrameMaker Publishing Server. Als er geen reactie is ontvangen binnen de opgegeven tijd, wordt de publicatietaak beëindigd door AEM hulplijnen en wordt de taak gemarkeerd als mislukt. <br> Standaardwaarde: 300 seconden \(5 minuten\) |
| Externe AEM URL | *\(Optioneel\)* De AEM URL waar de FrameMaker Publishing Server de gegenereerde uitvoerbestanden plaatst. Bijvoorbeeld: `http://<server-name>:<port>/`. |
| Gebruikersnaam en wachtwoord AEM Admin | *\(Optioneel\)* De gebruikersnaam en het wachtwoord voor een beheerder van uw AEM. Dit zal door FrameMaker Publishing Server worden gebruikt om met AEM te communiceren. |
| Time-out voor FMPS-taakuitvoering | Deze instelling is alleen van toepassing voor FMPS 2020. Geef de tijd op \(in seconden\) waarna FMPS stopt met wachten tot dit proces wordt uitgevoerd. |

## Overvloeien publiceren binnen een bestaande AEM site configureren {#id1691I0V0MGR}

Als u een AEM site hebt die DITA-inhoud bevat, kunt u de AEM Site-uitvoer zo configureren dat DITA-inhoud wordt gepubliceerd naar een vooraf gedefinieerde locatie binnen uw site. In de volgende schermafbeelding van een AEM sitepagina worden bijvoorbeeld de `ditacontent` knooppunt is gereserveerd voor opslag van DITA-inhoud:

![](assets/publish-in-aem-site.png){width="300" align="left"}

De resterende knooppunten op de pagina worden rechtstreeks vanuit de AEM Site-editor gemaakt. Als u de publicatie-instelling configureert voor het publiceren van DITA-inhoud op een vooraf gedefinieerde locatie, weet u zeker dat geen van de bestaande niet-DITA-inhoud wordt gewijzigd door het publicatieproces AEM hulplijnen.

U moet de volgende configuraties op uw bestaande plaats uitvoeren om het publiceren van inhoud DITA aan een vooraf bepaalde knoop toe te staan:

- De sjablooneigenschappen van uw site configureren

- Knooppunten op uw site toevoegen om DITA-inhoud te publiceren


Voer de volgende stappen uit om de sjablooneigenschappen van uw bestaande site te configureren:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het sjabloonconfiguratieknooppunt van uw site. AEM hulplijnen slaat bijvoorbeeld de standaardsjabloonconfiguraties op in het volgende knooppunt:

   `/libs/fmdita/config/templates/default`

   >[!NOTE]
   >
   > Breng geen aanpassingen aan in de standaardconfiguratiebestanden in het dialoogvenster `libs` knooppunt. U moet een bedekking maken van de `libs` knooppunt in de `apps` de vereiste bestanden in de `apps` alleen knooppunt.

1. Voeg de volgende eigenschappen toe:

   | Eigenschapnaam | Type | Waarde |
   |-------------|----|-----|
   | `topicContentNode` | String | Geef de knooppuntnaam op waar u de DITA-inhoud wilt publiceren. Het standaardknooppunt waar AEM hulplijnen DITA-inhoud publiceren, is bijvoorbeeld: <br>`jcr:content/contentnode` |
   | `topicHeadNode` | String | Geef de knooppuntnaam op waarin u de metagegevens van uw DITA-inhoud wilt opslaan. Het standaardknooppunt waarin AEM hulplijnen metagegevens opslaan, is bijvoorbeeld: <br>`jcr:content/headnode` |


De volgende schermafbeelding toont de eigenschappen die zijn toegevoegd in het standaardsjabloonknooppunt van AEM hulplijnen:

![](assets/add-content-node.png){width="800" align="left"}

De volgende keer dat u DITA-inhoud publiceert met behulp van de sjabloonconfiguraties van uw site, wordt de inhoud gepubliceerd in de knooppunten die zijn opgegeven in het dialoogvenster `topicContentNode` en `topicHeadNode` eigenschappen.

Voor bestaande sites moet u echter handmatig de opdracht `topicContentNode` en `topicHeadNode` knooppunten.

Voer de volgende stappen uit om de vereiste knooppunten aan uw bestaande site toe te voegen:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Zoeken `jcr:content` in uw sitenode.

1. Toevoegen `topicContentNode` en `topicHeadNode` knooppunten met dezelfde naam die u hebt opgegeven in de sjabloonconfiguraties van de site.


## Uitvoer van AEM site aanpassen {#id166TG0B30WR}

AEM hulplijnen ondersteunen het maken van uitvoerbestanden in de volgende indelingen:

- Site AEM

- PDF

- HTML 5
- EPUB
- Aangepaste uitvoer via DITA-OT

Voor de AEM Site-uitvoer kunt u verschillende ontwerpsjablonen met verschillende uitvoertaken toewijzen. Deze ontwerpsjablonen kunnen de DITA-inhoud in verschillende lay-outs renderen. U kunt bijvoorbeeld verschillende ontwerpsjablonen opgeven voor een intern en extern publiek.

U kunt ook aangepaste DITA Open Toolkit \(DITA-OT\)-plug-ins met AEM hulplijnen gebruiken. U kunt deze aangepaste DITA-OT-plug-ins uploaden om PDF-uitvoer op een specifieke manier te genereren.

>[!TIP]
>
> Zie de *AEM publiceren* in de handleiding voor aanbevolen procedures[appendix.md\#](appendix.md#) voor aanbevolen procedures bij het maken van AEM Site-uitvoer.

### Ontwerpsjabloon aanpassen voor het genereren van uitvoer {#customize_xml-add-on}

AEM de Gidsen gebruikt een reeks vooraf bepaalde ontwerpmalplaatjes om AEM output van de Plaats te produceren. U kunt de het ontwerpmalplaatjes van de Gidsen van de AEM aanpassen om de output te produceren die met uw collectieve branding in overeenstemming is. Een ontwerpsjabloon is een verzameling van verschillende stijlen \(CSS\), scripts \(zowel server- als client-side\), bronnen \(afbeeldingen, logo&#39;s en andere elementen\) en JCR-knooppunten die al deze bronnen aan elkaar koppelen. Een ontwerpsjabloon kan zo eenvoudig zijn als één serverscript met slechts een paar JCR-knooppunten of een complexe combinatie van stijlen, bronnen en JCR-knooppunten. De malplaatjes van het ontwerp worden gebruikt door AEM het publiceren subsysteem van Gidsen terwijl het produceren AEM de output van de Plaats en zij controleren de structuur, de blik en het gevoel van de geproduceerde output.

Er is geen beperking ten aanzien van waar de middelen van het ontwerpmalplaatje op de server zouden moeten worden gevestigd, maar zij zijn gewoonlijk logisch georganiseerd volgens hun functie. In de standaardsjabloon zijn bijvoorbeeld alle JavaScript- en CSS-bestanden opgeslagen onder `/etc/designs/fmdita/clientlibs/siteoutput/default` map. Waar deze bestanden zich bevinden, worden ze aan elkaar gekoppeld door een verzameling JCR-knooppunten. Samen vormen deze JCR-knooppunten en de bestanden de hele ontwerpsjabloon.

Het standaardontwerpmalplaatje dat met AEMGidsen wordt verscheept staat u toe om het landen, het onderwerp, en de componenten van de onderzoekspagina aan te passen. U kunt een kopie maken van het standaardontwerp en de bijbehorende verwijzingssjablonen en verschillende componenten opgeven om de gewenste uitvoer te genereren.

Voer de volgende stappen uit om uw eigen ontwerpmalplaatje te specificeren voor AEM de outputproductie van de Plaats te gebruiken:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het standaardontwerpsjabloonknooppunt. De locatie van het standaardontwerpsjabloonknooppunt is:

   `/libs/fmdita/config/templates/`

   ![](assets/templates-node.png){width="300" align="left"}

   >[!NOTE]
   >
   > Maak een kopie van de standaardontwerpsjablonen vanuit het dialoogvenster `libs` aan de `apps` en brengt wijzigingen aan in de `apps` map. U moet ook wijzigingen aanbrengen in de sjablonen waarnaar wordt verwezen vanuit het standaardsjabloonknooppunt. De sjablonen waarnaar wordt verwezen, worden onder `/libs/fmdita/templates/default/cqtemplates` knooppunt. Maak een kopie van de sjablonen waarnaar wordt verwezen in het dialoogvenster `apps` map voordat u wijzigingen aanbrengt.

1. Klik op de knop *default* in de *sjablonen* knooppunt om toegang te krijgen tot zijn eigenschappen.

   De sjablooneigenschappen van AEM hulplijnen worden in de volgende tabel beschreven.

   | Eigenschap | Beschrijving |
   |--------|-----------|
   | `landingPageTemplate`, `searchPageTemplate`, `topicPageTemplate`, `shadowPageTemplate` | Geef de `cq:Template` knooppunt voor deze overeenkomende pagina&#39;s \(landen, zoeken en onderwerp\). Standaard worden de `cq:Template` knooppunt voor deze pagina&#39;s vindt u in `/libs/fmdita/templates/default/cqtemplates` knooppunt. Dit knooppunt definieert de structuur en eigenschappen van de bestemmings-, zoek- en onderwerppagina&#39;s. <br>De `shadowPageTemplate` wordt gebruikt om de inhoud te optimaliseren. U moet de waarde van deze eigenschap instellen op: <br> `fmdita/templates/default/cqtemplates/shadowpage` <br> **Opmerking** U moet een waarde opgeven voor het dialoogvenster `topicPageTemplate`. De `landingPageTemplate` en `searchPageTemplate` zijn optionele eigenschappen. Geef deze eigenschappen niet op als u niet wilt dat de zoek- en bestemmingspagina&#39;s worden gegenereerd. |
   | `title` | Een beschrijvende naam van de ontwerpsjabloon. |
   | `topicContentNode` | De plaats van de knoop die de inhoud DITA in een onderwerppagina zal bevatten. Het pad is relatief ten opzichte van de onderwerppagina. |
   | `topicHeadNode` | De locatie van het knooppunt dat de hoofdwaarden \(of metagegevens\) bevat die zijn afgeleid van de DITA-inhoud. Pad is relatief ten opzichte van onderwerppagina. |
   | `tocNode` | De locatie van het knooppunt dat de inhoudsopgave zal bevatten. Het pad is relatief ten opzichte van de bestemmingspagina of het bestemmingspad. |
   | `basePathProp` | De eigenschapnaam voor het opslaan van het pad van de hoofdmap van de gepubliceerde site. |
   | `indexPathProp` | De eigenschapsnaam voor het opslaan van het pad van de bestemmings-/indexpagina van de gepubliceerde site. |
   | `pdfPathProp` | De bezitsnaam voor het opslaan van de weg van onderwerpPDF, als de generatie van onderwerpPDF wordt toegelaten. |
   | `pdfTypeProp` | De bezitsnaam voor het opslaan van het type van de generatie van PDF. Momenteel bevat deze eigenschap altijd &quot;Onderwerp&quot;. |
   | `searchPathProp` | De eigenschapsnaam voor het opslaan van het pad van de zoekpagina als de sjabloon een zoekpagina bevat. |
   | `siteTitleProp` | De eigenschapsnaam voor het opslaan van de titel van de site die wordt gepubliceerd. Deze titel is meestal dezelfde als de titel van de kaart die wordt gepubliceerd. |
   | `sourcePathProp` | De bezitsnaam voor het opslaan van de weg van het bronDITA onderwerp voor de huidige pagina. |
   | `tocPathProp` | De eigenschapnaam voor het opslaan van het pad van de inhoudsopgave-hoofdmap voor de gepubliceerde site. |


>[!NOTE]
>
> Nadat u een aangepaste ontwerpsjabloonnode hebt gemaakt, moet u de optie Ontwerpen in de voorinstellingen voor AEM site-uitvoer bijwerken om de aangepaste ontwerpsjabloonnode te kunnen gebruiken.

Zie voor meer informatie [Uw eerste Adobe Experience Manager 6.3-website maken](https://helpx.adobe.com/experience-manager/using/first_aem63_website.html) en [De basisbeginselen](https://helpx.adobe.com/experience-manager/6-3/sites/developing/using/the-basics.html) van het ontwikkelen van uw eigen website op AEM.

### Documenttitel gebruiken om AEM site-uitvoer te genereren

Bij het genereren van AEM site-uitvoer speelt de manier waarop URL&#39;s worden gegenereerd een belangrijke rol bij de ontdekkbaarheid van uw inhoud. Als u op UUID gebaseerde bestandsnamen gebruikt, is het genereren van URL&#39;s op basis van UUID van uw bestanden niet zoekvriendelijk. Als Beheerder of Uitgever, hebt u de controle over hoe u URLs voor uw uitvoer van de Plaats van de AEM wilt produceren. AEM Hulplijnen geeft u een configuratie waarmee u de URL&#39;s van AEM Site-uitvoer kunt genereren met de titel van het bestand in plaats van de op UUID gebaseerde bestandsnamen. Voor op UUID gebaseerde bestandssystemen is deze optie standaard ingeschakeld. Dit betekende dat wanneer u AEM Site-uitvoer voor op UUID gebaseerde bestandssystemen genereert, de bestandstitels worden gebruikt om de URL&#39;s te genereren en niet de UUID&#39;s van de bestanden.

Bij het genereren van AEM site-uitvoer speelt de manier waarop URL&#39;s worden gegenereerd een belangrijke rol bij de ontdekkbaarheid van uw inhoud. Bij niet-UUID-bestandssystemen wordt de AEM Site-uitvoer gegenereerd met de bestandsnamen en niet met de titels van het bestand. Als Beheerder of Uitgever, hebt u de controle over hoe u URLs voor uw uitvoer van de Plaats van de AEM wilt produceren. AEM Hulplijnen geeft u een configuratie waarmee u de URL&#39;s van AEM Site-uitvoer kunt genereren met de titel van het bestand in plaats van met de bestandsnamen. Deze optie is standaard uitgeschakeld. Dit betekende dat wanneer u AEM Site-uitvoer genereert, de bestandsnamen worden gebruikt om de URL&#39;s te genereren en niet de titel van het bestand. U kunt ervoor kiezen de URL&#39;s te genereren op basis van de bestandstitels door deze optie in te schakelen.

>[!NOTE]
>
> U kunt regels verder configureren om alleen een set tekens toe te staan in de URL&#39;s van een AEM Site-uitvoer. Zie voor meer informatie [Vorm filename het ontsmetten regels voor het creëren van onderwerpen en het publiceren AEM de output van de Plaats](#id2164D0KD0XA).

Voer de volgende stappen uit om het genereren van URL&#39;s in AEM Site-uitvoer te configureren:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. Selecteer de **Titel gebruiken voor AEM paginanamen van sites** -optie.

   >[!NOTE]
   >
   > Als u uitvoer wilt genereren met de bestandsnamen, schakelt u deze optie uit.

1. Klikken **Opslaan**.


### Vorm filename het ontsmetten regels voor het creëren van onderwerpen en het publiceren AEM de output van de Plaats {#id2164D0KD0XA}

Als beheerder kunt u een lijst definiëren met geldige speciale tekens die zijn toegestaan in bestandsnamen. Deze tekens vormen uiteindelijk de URL van een AEM Site-uitvoer. In eerdere versies mochten gebruikers bestandsnamen definiëren die speciale tekens bevatten, zoals `@`, `$`, `>`en meer. Deze speciale tekens resulteerden in gecodeerde URL bij het genereren van AEM sitepagina&#39;s.

Vanaf de release 3.8 zijn configuraties toegevoegd om een lijst met speciale tekens te definiëren die zijn toegestaan in de bestandsnamen. Standaard bevat de geldige bestandsnaamconfiguratie &quot;`a-z A-Z 0-9 - _`&quot;. Dit houdt in dat u tijdens het maken van een bestand elk speciaal teken in de titel van het bestand kunt hebben, maar dat het intern wordt vervangen door een afbreekstreepje \(`-`\) in de bestandsnaam. U kunt bijvoorbeeld de bestandstitel Introduction 1 of Introduction@1 hebben. De overeenkomstige bestandsnaam die voor beide gevallen wordt gegenereerd, is Introduction-1.

Wanneer u een lijst met geldige tekens definieert, moet u niet vergeten dat deze tekens &quot;`*/:[\]|#%{}?&<>"/+`&quot; en `a space` zal altijd worden vervangen door een afbreekstreepje \(`-`\).

>[!NOTE]
>
> Als u de geldige lijst met speciale tekens niet configureert, kan het maken van bestanden onverwachte resultaten opleveren.

Voer de volgende stappen uit om de geldige speciale tekens in bestandsnamen en AEM Site-uitvoer te configureren:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop *com.adobe.fmdita.common.SanitizeNodeNameImpl* bundel.

1. In de **Tekenset voor publiceren naar AEM Sites niet toegestaan** eigenschap, zorg ervoor dat de eigenschap is ingesteld op ```'<>`@$```. U kunt meer speciale tekens aan deze lijst toevoegen, maar deze moeten de vereiste speciale tekens bevatten.

   >[!NOTE]
   >
   > U kunt ook andere eigenschappen configureren, zoals **Kleine letters gebruiken** in bestandsnamen, **Scheidingsteken** ongeldige tekens te verwerken, en **Maximum aantal tekens** toegestaan in de bestandsnamen.

1. Klikken **Opslaan**.

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. In de **Regex voor geldige tekens** eigenschap, zorg ervoor dat de eigenschap is ingesteld op `[-a-zA-Z0-9_]`. U kunt meer tekens aan deze lijst toevoegen, maar de lijst moet deze basistekens hebben en de lijst moet beginnen met een afbreekstreepje \(`-`\).

   >[!NOTE]
   >
   > Deze eigenschap definieert de lijst met geldige tekens die wordt gebruikt om een nieuw bestand te maken.

1. Klikken **Opslaan**.


### Samenvoegen van AEM siteknooppuntstructuur configureren

Wanneer u AEM output van de Plaats produceert, wordt een knoop voor elk element in de onderwerpen intern gecreeerd. Voor een kaart DITA met duizenden onderwerpen, kan deze knoopstructuur te diep worden. Dit type van diep genestelde knoopstructuur kan prestatieskwesties voor grotere plaatsen hebben. De volgende momentopname toont diep genestelde knoopstructuur voor een output van de Plaats van de AEM:

![](assets/deep-nested-aem-site-node-structure.png){width="300" align="left"}

In de bovenstaande momentopname, merk op dat er een knoop voor elke wordt gecreeerd `p` element en zijn verdere sub-elementen en een gelijkaardige structuur wordt gecreeerd voor elk ander element dat in het onderwerp wordt gebruikt.

AEM de Gidsen staat u toe om te vormen hoe de de knoopstructuur van de output van de Plaats intern wordt gecreeerd. U kunt de nodestructuur bij gespecificeerde elementen afvlakken, zo betekent het dat u een element kunt bepalen dat als belangrijkste element zal worden beschouwd en alle sub-elementen binnen het zullen met het belangrijkste element worden samengevoegd. Als u bijvoorbeeld besluit de `p` element, dan elk element dat in het `p` element wordt samengevoegd met het hoofdelement `p` element. Er wordt geen aparte notitie gemaakt voor subelementen binnen de `p` element. In de volgende momentopname wordt de nodestructuur afgevlakt bij `p` element:

![](assets/flattened-aem-site-node-structure.png){width="300" align="left"}

Voer de volgende stappen uit om de structuur van AEM siteknooppunt af te vlakken:

1. Geef het element op waarop u de nodestructuur wilt afvlakken.

   1. Bedekking van de `libs` knooppunt in de `apps` en open het bestand elementmapping.xml.

   1. Voeg de `<flatten>true</flatten>` eigenschap in de definitie van het element waarbij u de nodestructuur wilt afvlakken. Als u bijvoorbeeld de nodestructuur in het deelvenster `p` -element, voegt u vervolgens het afgevlakte kenmerk toe aan de definitie van `p` element zoals hieronder getoond:

      ```XML
      <ditaelement>
          <name>p</name>
          <class>- topic/p</class>
          <componentpath>fmdita/components/dita/wrapper</componentpath>
          <type>COMPOSITE</type>
          <target>para</target>
          <flatten>true</flatten>
          <wrapelement>div</wrapelement>
      </ditaelement>
      ```

      >[!NOTE]
      >
      > Door gebrek, is het afgevlakte knoopbezit gevormd bij `p` element.

1. Schakel de configuratie voor het afvlakken van siteknooppunten in configMgr in.

   1. Open de Adobe Experience Manager Web Console Configuration-pagina.

      De standaard-URL voor toegang tot de configuratiepagina is:

      ```http
      http://<server name>:<port>/system/console/configMgr
      ```

   1. Zoeken naar en klikken op de knop *com.adobe.dxml.flattening.FlatteningConfigurationService* bundel.

   1. Selecteer de **Eigenschap flattening.enabled** -optie.

   1. Klikken **Opslaan**.


>[!IMPORTANT]
>
> Als u om het even welke verandering in het elementmapping.xml- dossier hebt aangebracht, zorg ervoor dat u configMgr opent en om het even welke bundel voor veranderingen opslaat om in werking te treden.

Wanneer u nu de AEM Site-uitvoer genereert, worden de knooppunten in de `p` element wordt afgevlakt en opgeslagen binnen het `p` element zelf. U kunt de nieuwe afvlakkingseigenschappen voor de `p` -element in CRXDE.

![](assets/flatten-aem-site-note-props-crxde.png){width="650" align="left"}

**Afvlakking van de structuur van AEM sitenotitie voorkomen**

Net als wanneer u het knooppunt opgeeft dat moet worden samengevoegd in AEM Site-uitvoer, kunt u ook een element opgeven dat u wilt uitsluiten van deze configuratie. Als u bijvoorbeeld knooppunten wilt afvlakken bij `body` -element, maar u wilt geen `table` element binnen `body` om af te vlakken, kunt u de eigenschap exclude toevoegen binnen de `table` definitie element.

Als u de opdracht `table` -element van afvlakking toevoegen aan de volgende eigenschap `table` definitie element:

`<preventancestorflattening>true|false</preventancestorflattening>`

### De versie voor verwijderde pagina&#39;s configureren in AEM Site-uitvoer

Wanneer u AEM Site-uitvoer genereert met **Verwijderen en** Maken ****Als deze optie is geselecteerd bij de instelling Bestaande uitvoerpagina&#39;s, wordt een versie gemaakt voor de pagina\(s\) die wordt verwijderd. U kunt het systeem vormen om de verwezenlijking van een versie vóór schrapping tegen te houden.

Voer de volgende stappen uit om te stoppen met het maken van een versie voor de pagina\(s\) die wordt verwijderd:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop *com.adobe.fmdita.config.ConfigManager* bundel.

1. Selecteren **Geen versie maken voor verwijderde pagina&#39;s** -optie.

   >[!NOTE]
   >
   > Als deze optie is geselecteerd, kunnen gebruikers elke pagina\(s\) rechtstreeks verwijderen zonder daarvoor een versie te maken. Als de optie niet is geselecteerd, wordt een versie gemaakt voordat de pagina\(s\) worden verwijderd.

1. Klikken **Opslaan**.

## Metagegevens gebruiken bij het publiceren van uitvoer via DITA-OT {#id191LF0U0TY4}

Met AEM hulplijnen kunt u aangepaste metagegevens doorgeven terwijl u uitvoer publiceert met DITA-OT. Als beheerder en uitgever zou u de volgende taken moeten uitvoeren om douanemetagegevens in de gepubliceerde output te vormen en te gebruiken:

- Als beheerder, voeg de vereiste meta-gegevens in het systeem toe zodat het op de pagina van Eigenschappen van de kaart DITA ter beschikking wordt gesteld.

- Als beheerder, voeg de douanemetagegevens in de meta-gegevenslijst toe zodat het in de DITA kaartconsole verschijnt.

- Als Uitgever, vorm en voeg de douanemetagegevens met de kaart DITA toe en produceer de vereiste output.


Voer de volgende stappen uit om de vereiste metagegevens in het systeem toe te voegen:

1. Meld u als beheerder aan bij Adobe Experience Manager.

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.

1. Selecteren **Activa** in de lijst met gereedschappen.

1. Klik op de knop **Metagegevensschema&#39;s** tegel.

   De pagina Metadata Schema Forms wordt weergegeven.

1. Selecteer de **default** in de lijst.

   >[!NOTE]
   >
   > De eigenschappen die op de pagina Eigenschappen voor een DITA-kaart worden weergegeven, zijn afkomstig uit dit formulier.

1. Klikken **Bewerken**.

1. Voeg de aangepaste metagegevens toe die u in de gepubliceerde uitvoer wilt gebruiken. We voegen bijvoorbeeld metagegevens voor het publiek toe door de volgende stappen uit te voeren:

   1. Van de **Formulier maken** lijst met componenten, slepen en neerzetten **Tekst met één regel** op het formulier.

   1. Selecteer het nieuwe veld om het dialoogvenster **Instellingen** van het veld.

   1. In de **Veldlabel**, voert u de naam van de metagegevens in: Publiek.

   1. In de **Toewijzen aan eigenschap** instellen, specificeren./jcr:content/metadata/&lt;name of=&quot;&quot; the=&quot;&quot; metadata=&quot;&quot;>. We zullen het bijvoorbeeld instellen op ./jcr:content/metadata/publiek.

   Voeg met deze stappen alle vereiste metagegevensparameters toe.

1. Klikken **Opslaan**.


De nieuwe parameter verschijnt nu op de pagina van Eigenschappen voor alle kaarten DITA.

![](assets/properties-page-custom-metadata.PNG){width="650" align="left"}

Vervolgens moet u de aangepaste metagegevens beschikbaar stellen in de DITA-kaartconsole. Voer de volgende stappen uit om de aangepaste metagegevens beschikbaar te maken op het dashboard voor de DITA-kaart:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Open het bestand metadataList dat beschikbaar is op de volgende locatie:

   /libs/fmdita/config/metadataList

   >[!NOTE]
   >
   > Het bestand metadataList bevat een lijst met eigenschappen die worden weergegeven in het dialoogvenster **Eigenschappen** vervolgkeuzelijst van een DITA-kaart in het kaartdashboard. Standaard worden in dit bestand vier eigenschappen vermeld: docstate, dc:language, dc:description en dc:title.

1. Voeg de aangepaste metagegevens toe die u hebt toegevoegd aan de pagina Forms van het metagegevensschema. Voeg voor ons voorbeeld publieksparameter toe aan het einde van de standaardlijst.

1. Klikken **Alles opslaan**.


De aangepaste metagegevens worden nu weergegeven in de DITA-kaartconsole **Eigenschappen** vervolgkeuzelijst.

Ten slotte moet u als uitgever de aangepaste metagegevens opnemen in de gepubliceerde uitvoer. Voer de volgende stappen uit om de aangepaste metagegevens te verwerken tijdens het genereren van de uitvoer:

1. Navigeer in de interface Elementen naar de DITA-kaart die u wilt publiceren.

1. Selecteer het DITA-kaartbestand en open de eigenschappenpagina.

1. Geef op de pagina Eigenschappen de waarde voor de aangepaste metagegevens op. In ons voorbeeld hebben we een waarde van External opgegeven voor de publieksparameter.

   ![](assets/properties-page-custom-metadata-value.png){width="650" align="left"}

1. Klikken **Opslaan en sluiten**.

1. Klik op het DITA kaartdossier om de DITA kaartconsole te openen.

1. In de **Voorinstellingen uitvoer** selecteert u de uitvoervoorinstelling die u wilt gebruiken om de uitvoer te genereren.

1. Klikken **Bewerken**.

1. Van de **Eigenschappen** selecteert u de eigenschappen die u wilt doorgeven aan het publicatieproces.

   ![](assets/props-in-publish-output.PNG){width="650" align="left"}


De geselecteerde eigenschappen/metagegevens worden doorgegeven aan het publicatieproces en beschikbaar gesteld in de uiteindelijke uitvoer.

## DITA-elementtoewijzing aanpassen met AEM componenten {#id1679J600HEL}

DITA-elementen in AEM hulplijnen worden toegewezen aan de corresponderende AEM. AEM Hulplijnen gebruiken deze toewijzing in workflows, zoals publiceren en reviseren, om het DITA-element om te zetten in een corresponderende AEM. De toewijzing wordt gedefinieerd in het dialoogvenster `elementmapping.xml` bestand, dat kan worden geopend vanuit de modus CRXDE Lite. Open de volgende URL in de modus CRXDE Lite:

`/libs/fmdita/config/elementmapping.xml`

>[!NOTE]
>
> Breng geen aanpassingen aan in de standaardconfiguratiebestanden in het dialoogvenster ``libs`` knooppunt. U moet een bedekking maken van de ``libs`` knooppunt in de ``apps`` de vereiste bestanden in de ``apps`` alleen knooppunt.

U kunt de vooraf bepaalde elementen gebruiken DITA, of u kunt elementen DITA aan uw douane AEM componenten in kaart brengen. Als u uw aangepaste AEM wilt gebruiken, moet u de structuur van de component `elementmapping.xml` bestand.

### elementmapping.xml-structuur

Een overzicht op hoog niveau van de `elementmapping.xml` de structuur wordt hieronder toegelicht :

1. Elk element DITA wordt eerst gezocht naar een overeenkomstige componentenafbeelding die op de elementnaam wordt gebaseerd. Bijvoorbeeld:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   In het bovenstaande voorbeeld worden alle `substeps` DITA-elementen worden gerenderd met de `dita/components/ditaolist` component.

1. Als een element DITA geen gelijke vindt die op de naam wordt gebaseerd, dan een gelijke op de basis van `class` is voltooid. Bijvoorbeeld:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   Als er in het bovenstaande voorbeeld geen toewijzing is gedefinieerd voor de `task` element, dan de `task` element is toegewezen aan de bovenstaande component omdat `task` wordt overgeërfd van de `topic` component.

1. Wanneer een element een overeenkomstige componentenafbeelding heeft, dan wordt de verdere verwerking van zijn kindelementen bepaald door `type`. Bijvoorbeeld:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` heeft de volgende waarden:

   - SAMENGESTELD: element naar component *toewijzing gaat verder voor onderliggende elementen* ook.

   - STANDALONE: onderliggende elementen van het huidige element zijn *niet verder toegewezen*.

   In het bovenstaande voorbeeld, als `<title>` element heeft onderliggende elementen, deze worden niet toegewezen aan een andere component. De component voor `<title>` element is verantwoordelijk voor het renderen van alle onderliggende elementen in het `<title>` element.

1. Als er meerdere componenten zijn toegewezen aan één DITA-element, wordt de beste overeenkomst voor het element geselecteerd. Om de beste overeenkomende component te selecteren, worden het domein en de structurele specialisatie van elementen DITA overwogen.

   Als er elementen DITA met domeinspecialisatie zijn en een component voor domeinspecialisatie in kaart wordt gebracht, dan wordt die component hoge prioriteit gegeven.

   Op dezelfde manier als er elementen DITA met structurele specialisatie zijn en een component voor structurele specialisatie in kaart wordt gebracht, dan wordt die component hoge prioriteit gegeven.

1. U kunt `<attributemap>` in elementtoewijzing om kenmerkwaarden toe te wijzen aan de overeenkomstige knoopeigenschappen.

1. `textprop` kan worden gebruikt voor het serialiseren van de tekstinhoud van een element DITA aan een knoopbezit. Bovendien kan de klasse meerdere keren worden gebruikt in een elementtag om de tekstinhoud op meerdere locaties in de gepubliceerde hiërarchie te serialiseren. U kunt ook de locatie en naam van de eigenschap target aanpassen. Bijvoorbeeld:

   ```XML
   <ditaelement> 
       <name>title</name> 
       <class>- topic/title</class> 
       <componentpath>foundation/components/title</componentpath> 
       <type>STANDALONE</type> 
       <target>para</target> 
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   In de bovenstaande elementtoewijzing wordt opgegeven dat de tekstinhoud van `<title>` element will be saved as value of a property named `jcr:title` op het uitvoerknooppunt.

1. `xmlprop` kan voor het in series vervaardigen van volledige XML voor een bepaald element aan een knoopbezit worden gebruikt. De component kan deze knoopeigenschap vervolgens lezen en aangepaste rendering uitvoeren. Bijvoorbeeld:

   ```XML
   <ditaelement> 
       <name>svg-container</name> 
       <class>+ topic/foreign svg-d/svg-container</class> 
       <componentpath>fmdita/components/dita/svg</componentpath> 
       <type>STANDALONE</type> 
       <target>para</target> 
       <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   De bovenstaande elemententoewijzing specificeert dat de volledige prijsverhoging van XML voor element `<svg-container>` wordt opgeslagen als waarde van een eigenschap met de naam `data` op het uitvoerknooppunt.

1. Er is een speciale kenmerktoewijzing om wegresolutie in het proces van de outputgeneratie te behandelen. Bijvoorbeeld:

   ```XML
   <attributemap> 
       <attribute from="href" to="fileReference" ispath="true" rel="source" /> 
       <attribute from="height" to="height" /> 
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Voor het bovenstaande `attributemap`de `href` attribuut in uw element DITA zal aan een knoopbezit genoemd worden in kaart gebracht `fileReference`. Nu sinds `ispath` is ingesteld op `true`wordt dit pad door het productieproces van de uitvoer omgezet en vervolgens ingesteld in `fileReference` node, eigenschap.

   Hoe deze resolutie verloopt, wordt bepaald op basis van de waarde van de `rel` kenmerk in kenmerktoewijzing.

   - Indien `rel=source`, dan de waarde van `href` wordt opgelost met betrekking tot het DITA-bronbestand dat momenteel wordt verwerkt. De waarde van `href` wordt omgezet en geplaatst in de waarde van `fileReference` eigenschap.

   - Indien `rel=target`, dan de waarde van `href` wordt opgelost ten opzichte van de hoofdpublicatielocatie. De waarde van `href` wordt omgezet en geplaatst in de waarde van `fileReference` eigenschap.

   Als u geen voorbewerking of resolutie op wegattributen wilt gebeuren, dan te hoeven u niet te specificeren `ispath` kenmerk. De waarde wordt ongewijzigd gekopieerd en de component kan de vereiste resolutie uitvoeren.


### DITA-elementschema

Hier volgt een voorbeeld van het DITA-elementenschema in `elementmapping.xml` bestand:

```XML
<ditaelement>         
    <name>element_name</name>     
    <class>element_class</class>     
    <componentpath>fmdita/components/dita/component_name</componentpath>     
    <type>COMPOSITE|STANDALONE</type>      
    <attributeprop>propname_a</attributeprop>       
    <textprop>propname_t</textprop>     
    <xmlprop>propname_x</xmlprop>      
    <xpath>xpath expression string</xpath>      
    <target>head|para</target>      
    <wrapelement>div</wrapelement>      
    <wrapclass>class_name</wrapclass>      
    <attributemap>           
    <attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />     
    </attributemap>     
    <skip>true|false</skip> 
</ditaelement>
```

De volgende lijst beschrijft de elementen in het DITA elementenschema:

| Element | Beschrijving |
|-------|-----------|
| `<ditaelement>` | The top-level node for each mapping element. |
| `<class>` | Het klassenkenmerk van het doel-DITA-element waarvoor u de component schrijft. <br>Bijvoorbeeld, is de klassenattributen voor het onderwerp DITA: <br>`topic/topic` |
| `<componentpath>` | Het CRXDE-pad van de toegewezen AEM. |
| `<type>` | Mogelijke waarden: <br>- **SAMENSTELLING**: Verwerk onderliggende elementen ook <br>- **STANDALONE**: slaat de verwerking van onderliggende elementen over |
| `<attributeprop>` | Gebruikt voor afbeelding in series vervaardigde attributen DITA en waarden aan AEM knopen als bezit. Als u bijvoorbeeld `<note type="Caution">` element en de component die voor dit element is toegewezen, heeft `<attributeprop>attr_t</ attributeprop>`, dan wordt de attributen en de waarde van de knoop in series vervaardigd aan `attr_t` eigenschap of the corresponding AEM node \( `attr_t->type="caution"`\). |
| `<textprop>propname_t</textprop>` | Sla de `getTextContent()` uitvoer naar eigenschap gedefinieerd door `propname_t.` **Opmerking:**  Dit is een geoptimaliseerde eigenschap. |
| `<xmlprop>propname_x </xmlprop>` | Met serienummering gecodeerde XML van dit knooppunt opslaan naar een eigenschap gedefinieerd door `propname_x.` **Opmerking:** Dit is een geoptimaliseerde eigenschap. |
| `<xpath>` | Als het element van XPath in de elementenafbeelding wordt verstrekt, dan samen met elementnaam en klasse zou de voorwaarde van XPath ook voor de componentenafbeelding moeten worden voldaan om te worden gebruikt. |
| `<target>` | Plaats voor het element DITA in de crx bewaarplaats op gespecificeerde plaats. <br>Mogelijke waarden:<br>- **kop**: Onder het head-knooppunt <br>- **text**: Onder het alineaknooppunt |
| `<wrapelement>` | Het HTML-element waarin de inhoud moet worden verpakt. |
| `<wrapclass>` | De elementwaarde voor de eigenschap `wrapclass.` |
| `<attributemap>` | Containerknooppunt met een of meer `<attribute>` knooppunten. |
| `<attribute from="attrname" to="propname" ispath="true|false" rel="source|target" />` | Wijst de attributen DITA aan AEM eigenschappen toe:<br>- **`from`**: DITA-kenmerknaam<br>- **`to`**: naam AEM componenteigenschap <br>- **`ispath`**: Als het kenmerk een padwaarde \(bijvoorbeeld: *image*\)<br>- **`rel`**: Als het pad de bron of het doel is <br>**Opmerking:** Indien `attrname` begint met `%`, dan kaart `attrname minus '%'` om &#39; `propname`&quot;. |

**Aanvullende opmerkingen**

- Als u van plan bent om de standaardelementenafbeelding met voeten te treden, adviseert men dat u niet de veranderingen in het gebrek aanbrengt `elementmapping.xml` bestand. Maak een nieuw XML-toewijzingsbestand en plaats het bestand op een andere locatie, bij voorkeur in de aangepaste map voor apps die u maakt.

- In de `elementmapping.xml` Er zijn veel toewijzingsitems die verwijzen naar de component fmdita/components/dita/wrapper. Wrapper is een generische component die relatief eenvoudige constructies DITA gebruikend eigenschappen op hun plaatsknoop teruggeeft om relevante HTML te produceren. Het gebruikt de `wrapelement` eigenschap om omsluitende tags te genereren en de onderliggende rendering te delegeren aan de corresponderende componenten. Dit is handig wanneer u alleen een containercomponent wilt. In plaats van een nieuwe component te maken die een specifieke containertag weergeeft als `div` of `p`, kunt u de component Wrapper gebruiken met de component `wrapelement` en `wrapclass` eigenschappen om hetzelfde effect te bereiken.

- Het wordt niet aanbevolen grote hoeveelheden tekst op te slaan in JCR-eigenschappen van String. De geoptimaliseerde berekening van het eigenschapstype bij het genereren van de uitvoer zorgt ervoor dat grote tekstinhoud niet wordt opgeslagen als tekenreekstype. In plaats daarvan, wanneer de inhoud groter dan een bepaalde drempel moet worden bewaard, wordt het type van het bezit veranderd in binair. Door gebrek, wordt deze drempel gevormd aan 512 bytes, maar kan in de Manager van de Configuratie \ (*com.adobe.fmdita.config.ConfigManager*\) door de **Opslaan als binaire drempelwaarde** instellen.

- Als u van plan bent om sommige \(en niet alle \) van de elementtoewijzingen met voeten te treden, moet u niet het volledige herhalen `elementmapping.xml` bestand. U moet een nieuw XML-toewijzingsbestand maken en alleen de elementen definiëren die u overschrijft.

- Nadat u het XML-bestand op de aangepaste locatie hebt gemaakt, werkt u de `Override Element Mapping` in het dialoogvenster `com.adobe.fmdita.config.ConfigManager` bundel.


## DITA-kaartconsole aanpassen {#id188HC08M0CZ}

AEM de Gidsen geeft u de flexibiliteit om de mogelijkheden van de DITA kaartconsole uit te breiden. Bijvoorbeeld, als u een reeks rapporten hebt die van wat in AEM Gidsen beschikbaar zijn verschillend zijn, kunt u dergelijke rapporten aan de kaartconsole toevoegen. Als u de kaartconsole wilt aanpassen, moet u een AEM Client Library \(of ClientLib\) maken die de code bevat om de vereiste functionaliteit uit te voeren.

>[!NOTE]
>
> Directe aanpassing aan pagina-onderdelen wordt niet aanbevolen, omdat deze wordt overschreven door nieuwe versies van het product.

AEM hulplijnen biedt de `apps.fmdita.dashboard-extn` categorie voor het aanpassen van de kaartconsole. Wanneer de kaartconsole wordt geladen, wordt de functionaliteit onder de `apps.fmdita.dashboard-extn` rubriek wordt uitgevoerd en geladen.

>[!NOTE]
>
> Ga voor meer informatie over het maken van AEM clientbibliotheek naar [Client-Side bibliotheken gebruiken](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/clientlibs.html).

## Afbeeldingsuitvoering afhandelen tijdens het genereren van de uitvoer {#id177BF0G0VY4}

AEM wordt geleverd met een set standaardworkflows en mediapandgrepen om elementen te verwerken. In AEM zijn er vooraf gedefinieerde workflows voor het verwerken van elementen voor de meest gangbare MIME-typen. Doorgaans worden voor elke afbeelding die u uploadt, AEM meerdere uitvoeringen van hetzelfde resultaat gemaakt in binaire indeling. Deze vertoningen kunnen van verschillende grootte, met een verschillende resolutie, met een toegevoegd watermerk, of één of andere andere veranderde eigenschap zijn. Voor meer informatie over hoe AEM activa behandelt, zie [Middelen verwerken met behulp van mediafuncties en workflows](https://helpx.adobe.com/experience-manager/6-5/assets/using/media-handlers.html) in AEM documentatie.

Met AEM hulplijnen kunt u configureren welke afbeeldingsuitvoering moet worden gebruikt wanneer uitvoer voor uw documenten wordt gegenereerd. U kunt bijvoorbeeld kiezen uit een van de standaardafbeeldingsuitvoeringen of een uitvoering maken en hetzelfde gebruiken om uw documenten te publiceren. Afbeeldingsrenditie-toewijzing voor het publiceren van uw documenten is opgeslagen in het dialoogvenster `/libs/fmdita/config/ **renditionmap.xml**` bestand. Een fragment van `renditionmap.xml` bestand is als volgt:

>[!NOTE]
>
> U wordt aangeraden een kopie van het dialoogvenster `renditionmap.xml` in het `apps` voor alle aanpassingen.

```XML
<renditionmap>
   <mapelement>
      <mimetype>image/png</mimetype>
      <rendition output="AEMSITE">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="PDF">original</rendition>
      <rendition output="HTML5">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="EPUB">cq5dam.web.1280.1280.jpeg</rendition>
      <rendition output="CUSTOM">cq5dam.web.1280.1280.jpeg</rendition>
   </mapelement>
...
</renditionmap>
```

De `mimetype` -element geeft het MIME-type van de bestandsindeling aan. De `rendition output` element geeft het type uitvoerindeling en de naam van uitvoering aan \(bijvoorbeeld `cq5dam.web.1280.1280.jpeg`\) die moet worden gebruikt voor het publiceren van de opgegeven uitvoer. U kunt de afbeeldingsuitvoeringen opgeven die moeten worden gebruikt voor alle ondersteunde uitvoerindelingen: AEMSITE, PDF, HTML5, EPUB en CUSTOM.

Als de opgegeven vertoning niet aanwezig is, zoekt AEM publicatieproces voor hulplijnen eerst naar de webuitvoering van de opgegeven afbeelding. Als zelfs de webuitvoering niet wordt gevonden, wordt de oorspronkelijke uitvoering van de afbeelding gebruikt.

>[!NOTE]
>
> Deze afbeeldingsuitvoeringen bepalen alleen de uitvoergeneratie. De webuitvoering van een afbeelding wordt gebruikt wanneer u een document opent voor voorvertoning of revisie.

## Automatische herstelperiode voor uitvoergeschiedenis configureren {#id19AAI070V8Q}

Wanneer u een uitvoer genereert, wordt de uitvoer samen met de uitvoerlogboeken gemaakt. Voor grote DITA-kaarten nemen deze logboeken veel ruimte in uw opslagplaats in beslag. De logbestanden worden standaard opgeslagen op de volgende locatie in de opslagplaats:

/var/dxml/metadata/outputHistory/

Over een periode, kon de collectieve grootte van alle logboekdossiers in GBs lopen. AEM Met hulplijnen kunt u een tijdsperiode configureren om deze logbestanden in de opslagplaats te bewaren. Na de opgegeven tijdsperiode worden de logbestanden samen met de productiegeschiedenis van de uitvoer verwijderd uit de opslagplaats.

>[!NOTE]
>
> De geschiedenis van de outputgeneratie is de logboekingang in de Gegenereerde lijst van Output op het lusje van Output.

Het configureren van de functie voor het opschonen van historie heeft invloed op de uitvoergeneratie voor alle DITA-kaarten in de opslagplaats. Op het lusje van Output van een kaart DITA, wordt de geschiedenis gezuiverd na het gespecificeerde aantal dagen en op de tijd die in het plaatsen wordt gespecificeerd.

>[!NOTE]
>
> Het verwijderen van de logbestanden en de productiegeschiedenis van de uitvoer heeft geen invloed op de gegenereerde uitvoer.

Voer de volgende stappen uit om een dag en tijd in te stellen voor het wissen van de uitvoergeschiedenis en logboeken:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. In de **Positie-herstelperiode uitvoergeschiedenis** eigenschap, geeft u het aantal dagen op waarna de uitvoergeschiedenis en de uitvoerlogbestanden worden gewist. De standaardwaarde is 5 dagen. Als u deze functie wilt uitschakelen, stelt u deze eigenschap in op 0.

1. In de **Opstarttijd uitvoergeschiedenis** eigenschap, geeft u de tijd op waarop het zuiveringsproces wordt gestart. De standaardwaarde is 0:00 \(of 12:00 middernacht\). Op dit moment wordt het leegmaken uitgevoerd op uitvoerbestanden die zijn gegenereerd vóór het aantal dagen dat is opgegeven in het dialoogvenster **Positie-herstelperiode uitvoergeschiedenis** eigenschap.

   >[!NOTE]
   >
   > Standaard wordt de functie voor leegmaken elke middernacht uitgevoerd op uitvoerbestanden ouder dan 5 dagen.

1. Klikken **Opslaan**.


## De onlangs gegenereerde limieten in de lijst met uitvoerbestanden wijzigen {#id1679JH0H0O2}

U kunt het maximumaantal geproduceerde output veranderen die in het lusje van Output voor een kaart DITA wordt getoond. Standaard wordt een lijst met de laatste 25 gegenereerde uitvoerbestanden weergegeven. Als u het aantal uitvoerbestanden wilt wijzigen dat in de lijst wordt weergegeven, werkt u de **Limiet uitvoerlijst** in het dialoogvenster `com.adobe.fmdita.config.ConfigManager` bundel.

>[!TIP]
>
> Zie de *Uitvoerhistorie* in de handleiding voor aanbevolen procedures[appendix.md\#](appendix.md#) voor beste praktijken rond het werken met outputgeschiedenis.

## Optimalisatie van uitvoerprestaties {#id176LB050VUI}

AEM de Gidsen staat u toe om de grootte van de de generatieprocessen van de outputproductie te vormen die het aantal processen controleert van de outputgeneratie die gelijktijdig lopen. Standaard is de grootte van de procespool ingesteld op het aantal verwerkingskernen dat beschikbaar is in uw systeem plus één. U kunt deze waarde wijzigen in 1 als u opeenvolgende publicaties wilt. In dit geval wordt de eerste publicatietaak uitgevoerd en wordt de volgende publicatietaak opgeslagen in de publicatiereeks.

Als u de grootte van de verwerkingspool van de uitvoergeneratie wilt wijzigen, werkt u de **Grootte generatiepool** in het dialoogvenster `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` bundel.
