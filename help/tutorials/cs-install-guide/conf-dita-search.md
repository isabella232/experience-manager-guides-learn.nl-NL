---
title: Zoeken naar gebruikersinterface van AEM Assets configureren
description: Leer hoe u zoekopdrachten voor de gebruikersinterface van AEM Assets kunt configureren
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1580'
ht-degree: 0%

---

# Zoeken naar gebruikersinterface van AEM Assets configureren {#id192SC800MY4}

AEM herkent standaard geen DITA-inhoud, waardoor het geen mechanisme biedt om DITA-inhoud in de opslagplaats te doorzoeken. Er is ook geen OOTB-mogelijkheid om inhoud te zoeken op basis van hun UUID. Met AEM hulplijnen kunt u de zoekfunctie voor DITA-inhoud en de zoekmogelijkheden op basis van UUID toevoegen aan de AEM opslagplaats.

Het vormen van DITA inhoudsonderzoek impliceert de volgende taken:

1. [DITA Element-zoekcomponent toevoegen aan interface Middelen](#id192SF0F50HS)
1. [Op UUID gebaseerde zoekcomponent toevoegen aan interface voor elementen](#id2034F04K05Z)
1. [Rechten aan gebruikers opgeven](#id192SF0G0RUI)
1. [Aangepaste elementen of kenmerken toevoegen in zoekopdracht](#id192SF0G10YK)
1. [Metagegevens uit bestaande inhoud extraheren](#id192SF0GA0HT)

Naast het toevoegen van onderzoeksvermogen, kunt u de omslagen ook vormen die niet in het onderzoek zouden moeten worden omvat. Zie voor meer informatie [Tijdelijke bestanden uitsluiten van zoekresultaten](#id197AHI0035Z).

## DITA Element-zoekcomponent toevoegen aan interface Middelen {#id192SF0F50HS}

Ga als volgt te werk om een zoekcomponent voor DITA-inhoud toe te voegen in de gebruikersinterface van AEM Assets:

1. Meld u als beheerder aan bij Adobe Experience Manager.

1. Klik op de knop **Adobe Experience Manager** koppeling bovenaan en kies **Gereedschappen**.

1. Selecteren **Algemeen** in de lijst met gereedschappen en klik op de knop **Zoeken in Forms** tegel.

1. In de **Zoeken in Forms** Selecteer de **Middelen Admin Search Rail**.

1. Klikken **Bewerken**.
1. In de **Predicate selecteren** schuiven naar het einde van de lijst.

1. Slepen en neerzetten **DITA Element Predicate** op de vereiste locatie in het zoekformulier.

   ![](assets/drag-search-predicate.png)

1. Klikken **Gereed** om uw wijzigingen op te slaan.

   Wanneer u tot de optie van Filters in Elementen UI toegang hebt, zult u de het onderzoek het filtreren optie van het Element DITA krijgen.

   ![](assets/search-filter-asset-console.png)


## Op UUID gebaseerde zoekcomponent toevoegen aan interface voor elementen {#id2034F04K05Z}

Voer het volgende uit om op UUID-Gebaseerde onderzoekscomponent in AEM Assets UI toe te voegen:

1. Meld u als beheerder aan bij Adobe Experience Manager.

1. Klik op de knop **Adobe Experience Manager** koppeling bovenaan en kies **Gereedschappen**.

1. Selecteren **Algemeen** in de lijst met gereedschappen en klik op de knop **Zoeken in Forms** tegel.

1. In de **Zoeken in Forms** Selecteer de **Middelen Admin Search Rail**.

1. Klikken **Bewerken**.
1. In de **Predicate selecteren** tab, kiest u **Eigenschappenvoorspelling** en sleep het naar de gewenste locatie in het zoekformulier.

1. In de **Instellingen** tabblad, geeft u de volgende gegevens op voor het toegevoegde **Eigenschappenvoorspelling** component:

   - **Veldlabel**: UUID
   - **Eigenschapnaam**: jcr:content/fmUuid
1. Klikken **Gereed** om uw wijzigingen op te slaan.

   Als u de optie Filters opent in de interface Elementen, wordt de zoekfilteroptie op basis van UIS weergegeven.


## Rechten aan gebruikers opgeven {#id192SF0G0RUI}

Auteurs en uitgevers moeten expliciete machtigingen krijgen om toegang te krijgen tot de zoekmogelijkheden via de interface Middelen. Als u deze toestemmingen niet verleent, dan zullen uw gebruikers niet inhoud kunnen zoeken DITA die op hun element/attributenwaarden of UUID wordt gebaseerd.

Voer de volgende stappen uit om toegang tot de eigenschap van het Onderzoek te verlenen DITA:

1. Open de pagina met gebruikers- en groepsmachtigingen.

1. Zoek naar de gebruikersgroep of een individuele gebruiker aan wie u toegang wilt verlenen. Als u bijvoorbeeld toegang wilt geven tot alle gebruikers in de groep Auteurs, voert u de auteurs in het dialoogvenster **Filterquery** veld en druk op **Enter**.

   ![](assets/authors-group-permission.png)

1. Selecteer de **auteurs** groep.

1. Selecteer in het rechterdeelvenster de optie **Machtigingen** tab.

1. Navigeer naar de volgende maplocatie:

   /conf/global/settings/dam/search

1. Geef de **Lezen** toestemming voor de zoekmap.

   ![](assets/read-permission-authors.png)

1. Klikken **Opslaan**.


De geselecteerde gebruiker of gebruikersgroep heeft nu toegang tot de zoekfunctie voor DITA-inhoud in de interface Middelen.

## Aangepaste elementen of kenmerken toevoegen in zoekopdracht {#id192SF0G10YK}

De DITA-zoekopdracht werkt alleen als de DITA-inhoud vooraf is verwerkt. Deze preprocessing stap haalt selectieve inhoud uit individuele kaarten DITA en onderwerpen zodat het voor sneller het zoeken kan worden geïndexeerd. Intern wordt dit proces aangeroepen *Serienummering*. Serienummering van DITA-bestanden vindt plaats tijdens het uploaden van inhoud of kan ook op aanvraag worden uitgevoerd. Het gebruikt een configuratiedossier om te bepalen hoeveel inhoud van elk DITA- dossier zou moeten worden geïndexeerd. De standaardlocatie van het serialisatiebestand is:

/libs/fmdita/config/serializationconfig.xml

De standaardonderzoeksconfiguratie staat u toe om naar alle elementen en attributen binnen DITA te zoeken `prolog` element. Als u op basis van andere elementen of attributen wilt zoeken, dan moet u het dossier van de onderzoeksrangschikking vormen.

>[!NOTE]
>
> Als u met de standaardonderzoeksconfiguratie binnen wilt gaan `prolog` , kunt u dit proces overslaan.

Dit bestand bevat twee hoofdsecties: een kenmerkset en een regelset. Hieronder ziet u een fragment van de sectie voor regelsets:

```
<ruleset filetypes="xml dita"><!-- Element rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]//*[not(*)]" text="yes" attributeset="all-attrs" /><!-- Attribute rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]///@[local-name() != 'class']" /></ruleset>
```

In het gedeelte Regelset kunt u het volgende opgeven:

- Regels om de elementen te extraheren

- Regels voor het uitnemen van kenmerken


Een regel bestaat uit het volgende:

xpath : Dit is de XPath-query die de elementen of kenmerken van DITA-bestanden ophaalt. De standaardconfiguratie voor de elementregel wint allen terug `prolog` elementen. En, wint de standaardconfiguratie voor de attributenregel alle attributen van terug `prolog` elementen. U kunt een vraag van XPath specificeren om de elementen of de attributen in series te vervaardigen die u wilt zoeken.

    De XPath-query bevat de klassenaam van het documenttype. De klasse ` topic/topic ` wordt gebruikt voor onderwerptype DITA documenten. Als u een regel wilt maken voor andere DITA-documenten, moet u de volgende klassenamen gebruiken:
    
    |Documenttype|Klassenaam|
    |—|—|
    |Onderwerp|- onderwerp/onderwerp|
    |Taak|- onderwerp/onderwerp/taak|
    |Concept|- onderwerp/onderwerp/concept|
    |Referentie|- onderwerp/onderwerp/referentie|
    |Kaart|- kaart/kaart|

text : Als u naar de tekst binnen het opgegeven element wilt zoeken, geeft u de waarde ja op. Als u geen waarde opgeeft, worden alleen de kenmerken in het element geserialiseerd. De kenmerken waarnaar u wilt zoeken, moeten worden opgegeven in de sectie voor kenmerksets.

Kenmerken: geef de id op van de kenmerkset die u aan deze regel wilt koppelen. De waarde alle-attrs is een speciaal geval om erop te wijzen dat alle attributen voor deze regel in series moeten worden vervaardigd.

Een kenmerkset bevat een lijst met kenmerken die u wilt zoeken binnen DITA-inhoud. De kenmerkenreeks bevat het volgende:

id: Een unieke id voor de kenmerkset. Deze id wordt opgegeven in de parameter attributeset van een regelset.

kenmerk: een lijst met kenmerken die u wilt doorzoeken. Voor elk kenmerk moet u een afzonderlijk item maken in het dialoogvenster `attribute` element.

Voer de volgende stappen uit om aangepaste DITA-elementen of -kenmerken toe te voegen in het bestand met zoekserienummering:

1. Gebruik Package Manager om het bestand /libs/fmdita/config/serializationconfig.xml te downloaden.

1. Maak een overlayknooppunt van het dialoogvenster `config` in de `apps` knooppunt.

1. Navigeer naar het configuratiebestand dat beschikbaar is in het dialoogvenster `apps` knooppunt:

   `/apps/fmdita/config/serializationconfig.xml`

1. Voeg de vereiste element- of kenmerkregelsets toe.

1. Leg de wijzigingen vast en voer de Cloud Manager \(CI/CD\)-pijplijn uit om configuratiewijzigingen te implementeren.


De nieuwe rangschikkingsinformatie wordt opgeslagen en geactiveerd voor onderzoek. U moet de metagegevens echter extraheren uit uw bestaande DITA-inhoud om deze beschikbaar te maken voor zoekopdrachten.

## Metagegevens uit bestaande inhoud extraheren {#id192SF0GA0HT}

Als u een wijziging hebt aangebracht in het standaardbestand voor zoekserienummering, moet u de optie DITA-metagegevens extraheren inschakelen in het dialoogvenster *com.adobe.fmdita.config.ConfigManager* gebruiken en vervolgens de workflow uitvoeren om metagegevens op te halen. Hiermee haalt u de vereiste metagegevens uit de bestaande DITA-bestanden en wordt hetzelfde vervolgens beschikbaar gesteld voor zoekopdrachten.

Als u nieuwe bestanden maakt of een bestand bewerkt nadat u het serialisatiebestand hebt bijgewerkt, worden de metagegevens automatisch uit dergelijke bestanden geëxtraheerd. Het uitpakken van metagegevens is alleen vereist voor bestanden die al in de AEM opslagplaats bestaan.

Het uitpakken van meta-gegevens uit bestaande DITA- dossiers impliceert twee taken:

1. De optie voor het extraheren van metagegevens inschakelen in configMgr
1. De workflow voor het uitnemen van metagegevens uitvoeren

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\) gegevens op om de optie voor het uitnemen van metagegevens te configureren:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `dita.serialization` | Boolean \(true/false\).<br> **Standaardwaarde**: `false` |

Voer de volgende stappen uit om de workflow voor het uitnemen van metagegevens uit te voeren:

1. Meld u als beheerder aan bij Adobe Experience Manager.

1. Klik op de knop **Adobe Experience Manager** koppeling bovenaan en kies **Gereedschappen**.

1. Selecteren **Hulplijnen** in de lijst met gereedschappen en klik op de knop **DITA-metagegevensextractie** tegel.

1. Als u metagegevens uit één bestand en de bijbehorende afhankelijkheden wilt extraheren, klikt u op de knop **Een bestand selecteren** en naar een bestand bladeren.

1. Als u metagegevens wilt extraheren uit meerdere bestanden in een map, klikt u op de knop **Map selecteren\(s\)** , bladert u naar de gewenste map en selecteert u deze. Klik op de knop **Toevoegen** om de map toe te voegen aan de lijst met serialisatietaken.

   >[!NOTE]
   >
   > U kunt meerdere mappen selecteren en toevoegen aan een serialisatietaak.

1. Klikken **Start**.

1. Klik op **OK**.


## Tijdelijke bestanden uitsluiten van zoekresultaten {#id197AHI0035Z}

Standaard wordt de zoekopdracht uitgevoerd op de gehele opslagplaats van AEM. Er kunnen locaties zijn die u wilt uitsluiten van de zoekopdracht. Wanneer u bijvoorbeeld de workflow voor het vertalen van inhoud start, blijven de niet-goedgekeurde bestanden op een tijdelijke maplocatie staan. Wanneer u de zoekopdracht uitvoert, worden ook bestanden van deze tijdelijke locatie geretourneerd in de zoekresultaten.

Als u wilt voorkomen dat AEM hulplijnen de locatie van de tijdelijke vertaalmap doorzoeken, moet u een tijdelijke maplocatie toevoegen aan de lijst met uitsluitingen.

Voer de volgende stappen uit om de tijdelijke vertaalmap uit te sluiten van de zoekopdracht:

>[!NOTE]
>
> Met deze procedure kunt u elke andere maplocatie aan de lijst met uitsluitingen toevoegen. Zie voor meer informatie over het werken met indexen [Inhoud zoeken en indexeren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html).

1. Voeg de volgende eigenschap toe aan de aangepaste damAssetLucene-index:

   | Eigenschapnaam | Type | Waarde |
   |-------------|----|-----|
   | excludePaths | Tekenreeks\[\] | Voeg de volgende waarde toe aan deze eigenschap:<br> `/content/dam/projects/translation\_output` |

1. Navigeer naar het lucene knooppunt dat beschikbaar is op de volgende locatie:

   /oak:index/lucene

1. Voeg de volgende eigenschap toe aan het knooppunt lucene:

   | Eigenschapnaam | Type | Waarde |
   |-------------|----|-----|
   | excludePaths | Tekenreeks\[\] | Voeg de volgende waarden toe aan deze eigenschap:<br> `/content/dam/projects/translation\_output` |
