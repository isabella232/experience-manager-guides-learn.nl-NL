---
title: Site AEM
description: Meer informatie over het AEM van de site
source-git-commit: 23d6c87b525f0763990166e46f4bd4ac2d6e7cd5
workflow-type: tm+mt
source-wordcount: '2545'
ht-degree: 0%

---


# Site AEM {#id205BE3008SW}

De volgende opties zijn beschikbaar voor de AEM Site-uitvoer:

U kunt de AEM sitevoorinstelling op twee manieren maken:

**Vanuit de webeditor:** Open in het deelvenster Opslagplaats het DITA-toewijzingsbestand in Kaartweergave en selecteer vervolgens op het tabblad Uitvoer het pictogram + om een uitvoervoorinstelling te maken. Selecteer vervolgens AEM Site in het keuzemenu Type in het dialoogvenster Voorinstelling toevoegen. In de webeditor zijn de configuraties georganiseerd onder de tabbladen Algemeen en Geavanceerd:

**Algemeen**

De **Algemeen** bevat de volgende configuraties:

- Sitenaam
- Uitvoerpad
- Bestaande uitvoerpagina&#39;s
- Orphan-sitepagina&#39;s verwijderen
- Voorwaarden toepassen met \(als de voorwaarden voor een kaart zijn gedefinieerd\)
- Basislijn gebruiken \(als een basislijn is gemaakt voor een kaart\)
- Workflow na generatie

**Geavanceerd**

Het tabblad Geavanceerd bevat de volgende configuraties:

- Tijdelijke DITA-OT-bestanden opschonen
- Afzonderlijke PDF genereren voor elk onderwerp
- Eigenschappen Kaart als standaard gebruiken

Zie voor meer informatie [AEM](#id231KIM004X1).

**Van het kaartdashboard**

Als u uitvoervoorinstellingen voor AEM site wilt openen, klikt u op een DITA-toewijzingsbestand in de interface Middelen, klikt u op Uitvoervoorinstellingen en klikt u vervolgens op de uitvoeroptie AEM Site.Klik in het dashboard voor de kaart op **Bewerken** bovenaan om de verschillende configuraties bij te werken, en klik dan **Opslaan**.

>[!TIP]
>
> Zie de *AEM publiceren* in de handleiding met aanbevolen procedures voor aanbevolen procedures bij het maken van AEM site-uitvoer.

## AEM {#id_aem_site_config}

De volgende opties zijn beschikbaar voor de AEM Site-uitvoer:

| Site-opties AEM | Beschrijving |
| --- | --- |
| Uitvoertype | Het type uitvoer dat u wilt genereren. Kies de optie Site AEM om responsieve AEM Site-uitvoer te genereren. |
| Naam instellen | Geef een beschrijvende naam voor de AEM site-instellingen die u maakt. U kunt bijvoorbeeld *Uitvoer van interne klanten* of *eindgebruikeruitvoer*. |
| Sitenaam | Een sitenaam waar de uitvoer wordt opgeslagen in uw AEM opslagplaats.<br><br>Er wordt een knooppunt in de AEM gemaakt met de hier opgegeven naam. Als u de Sitenaam niet opgeeft, wordt het siteknooppunt gemaakt met de naam van het DITA-toewijzingsbestand.<br><br>De sitenaam die u hier opgeeft, wordt ook gebruikt als titel op het browsertabblad.<br><br>U kunt ook variabelen gebruiken bij het instellen van de sitenaam. Voor meer informatie over het gebruik van variabelen raadpleegt u [Variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam](generate-output-use-variables.md#id18BUG70K05Z). |
| Ontwerp | Selecteer het ontwerpmalplaatje dat u wilt gebruiken om de output te produceren.<br><br>Neem contact op met de publicatiebeheerder voor meer informatie over het gebruik van aangepaste ontwerpsjablonen om uitvoer te genereren. |
| Doelpad | Het pad in de AEM opslagplaats waar de uitvoer wordt opgeslagen. Bij het genereren van de uiteindelijke uitvoer worden de sitenaam en het bestemmingspad gecombineerd. Als u bijvoorbeeld de sitenaam opgeeft als `user-guide` en het bestemmingspad als `/content/output/aem-guides`wordt de einduitvoer gegenereerd onder de `/content/output/aem-guides/user-guide` knooppunt.<br><br>U kunt ook variabelen gebruiken bij het instellen van het bestemmingspad. Voor meer informatie over het gebruik van variabelen raadpleegt u [Variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam](generate-output-use-variables.md#id18BUG70K05Z). |
| Voorwaarden toepassen met | Selecteer een van de volgende opties:<br><br>**Geen toegepast**: Selecteer deze optie als u geen voorwaarde wilt toepassen op de gepubliceerde uitvoer.<br>**DITAVal-bestand**: Selecteer DITAVal-bestand(en) om geconditioneerde inhoud te genereren. U kunt meerdere DITAVal-bestanden selecteren via het dialoogvenster Bladeren of door een bestandspad te typen. Gebruik het kruispictogram bij de bestandsnaam om het te verwijderen. DITAVal-bestanden worden in de opgegeven volgorde geëvalueerd, zodat de voorwaarden die in het eerste bestand zijn opgegeven voorrang hebben op de voorwaarden die in latere bestanden worden vermeld. U kunt de bestandsvolgorde behouden door bestanden toe te voegen of te verwijderen. Als het DITAVal-bestand naar een andere locatie wordt verplaatst of wordt verwijderd, wordt het niet automatisch verwijderd van het kaartdashboard. U moet de locatie bijwerken als bestanden worden verplaatst of verwijderd. U kunt de muisaanwijzer boven de bestandsnaam plaatsen om het pad te zien in de AEM opslagplaats waar het bestand is opgeslagen. U kunt alleen DITAVal-bestanden selecteren en er wordt een fout weergegeven als u een ander bestandstype selecteert.<br>**Voorinstelling voorwaarde**: Selecteer een voorinstelling voor een voorwaarde in het keuzemenu om een voorwaarde toe te passen tijdens het publiceren van de uitvoer. Deze optie is zichtbaar als u een voorwaarde voor het DITA kaartdossier hebt toegevoegd. De voorwaardelijke instellingen zijn beschikbaar op het tabblad Voorinstellingen voorwaarde van de DITA-kaartconsole. Zie voor meer informatie over voorinstellingen voor voorwaarden [Voorinstellingen voor voorwaarden gebruiken](generate-output-use-condition-presets.md#id1825FL004PN). |
| Bestaande uitvoerpagina&#39;s | Selecteer **Inhoud overschrijven** om de inhoud van de bestaande pagina&#39;s te overschrijven. Met deze optie overschrijft u alleen de inhoud onder de inhoud en de kopknooppunten van de pagina. Met deze optie schakelt u het gezamenlijk publiceren van inhoud in. Als u deze optie selecteert, kunt u het verwijderen van weespagina&#39;s uit de gepubliceerde uitvoer selecteren. Dit is ook het *default* optie voor het maken van de AEM Site-uitvoer.<br><br>Selecteer **Verwijderen en maken** gebruiken om bestaande pagina&#39;s tijdens het publiceren te verwijderen. Met deze optie verwijdert u het paginaknooppunt samen met de inhoud ervan en alle onderliggende pagina&#39;s eronder. Gebruik deze optie als u de ontwerpsjabloon van de uitvoervoorinstelling hebt gewijzigd of als u extra pagina&#39;s wilt verwijderen die zich al in het doel bevinden. |
| Orphan-sitepagina&#39;s verwijderen | Het selecteren van **Inhoud overschrijven** in de **Bestaande uitvoerpagina&#39;s** deze optie wordt weergegeven. Als u deze optie selecteert, worden alle wezen pagina&#39;s verwijderd uit de gepubliceerde AEM Site. Deze functie kan alleen worden uitgevoerd als u de volledige DITA-kaart publiceert en niet de incrementele publicatie gebruikt.<br><br>Stel dat u een DITA-kaart hebt gepubliceerd, die de onderwerpen a.dita, b.dita en c.dita bevat. Alvorens de kaart opnieuw te publiceren, verwijderde u b.dita onderwerp van de kaart. Nu, als u deze optie hebt geselecteerd, dan wordt alle inhoud met betrekking tot b.dita verwijderd uit de output van de AEMPlaats en slechts a.dita en c.dita worden gepubliceerd.<br><br>Deze functie verwijdert geen gepubliceerde onderliggende kaart. Bijvoorbeeld, als uw ouderkaart een kindkaart bevat, en u de volledige kindkaart verwijdert, dan wordt de inhoud van de kindkaart niet geschrapt van de gepubliceerde output. Nochtans, als u om het even welk onderwerp uit een kindkaart verwijdert en opnieuw publiceert, dan wordt de inhoud van het verwijderde onderwerp geschrapt van de plaatsuitvoer.<br><br>Als er inhoud waarnaar wordt verwezen is en die inhoud wordt verwijderd voordat de inhoud opnieuw wordt gepubliceerd, worden de gegevens van de inhoud waarnaar wordt verwezen niet verwijderd.<br><br>**Opmerking**: Informatie over verwijderde weespagina&#39;s wordt ook vastgelegd in de logbestanden voor het genereren van uitvoer. Voor meer informatie over de toegang tot van de logboekdossiers, zie [Logbestand weergeven en controleren](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). |
| Tijdelijke DITA-OT-bestanden opschonen | Selecteer deze optie als u de tijdelijke bestanden die door DITA-OT worden gegenereerd, wilt opschonen. De plaats waar DITA-OT tijdelijke dossiers opslaat kan in het logboek van de outputgeneratie worden gevonden.<br><br>Als er fouten optreden bij het genereren van uitvoer via DITA-OT, kunt u deze optie uitschakelen om de tijdelijke bestanden te behouden. Vervolgens kunt u deze bestanden gebruiken om fouten met uitvoergeneratie op te lossen. |
| Afzonderlijke PDF genereren voor elk onderwerp | Indien geselecteerd, wordt een PDF ook gecreeerd voor elk onderwerp in de kaart DITA. Als u deze optie kiest, wordt een nieuwe optie PDF-pad splitsen weergegeven.<br><br>In het Splitste gebied van de Weg van de PDF, specificeer de weg om de PDF op te slaan die voor elk onderwerp worden geproduceerd.<br><br>**Opmerking**: AEM de Gidsen gebruikt stop-in DITA-OT genoemd pdfx om PDF voor elk onderwerp te produceren. Deze plug-in is gebundeld met het DITA-OT-pakket dat buiten de box wordt geleverd. U kunt deze plug-in naar wens aanpassen om PDF te genereren. Als u een aangepaste insteekmodule DITA-OT gebruikt, moet u de insteekmodule pdfx integreren voor het genereren van PDF op onderwerpniveau. |
| Workflow na generatie uitvoeren | Wanneer u deze optie kiest, wordt een nieuwe vervolgkeuzelijst Werkstroom na generatie weergegeven met alle werkstromen die in AEM zijn geconfigureerd. U moet een werkstroom selecteren die u wilt uitvoeren nadat de werkstroom van de outputgeneratie is voltooid. |
| Basislijn gebruiken | Als u een basislijn voor de geselecteerde kaart hebt gecreeerd DITA, selecteer deze optie om de versie te specificeren die u wilt publiceren.<br><br>**Belangrijk**: Wanneer u incrementele uitvoer voor de AEM Site genereert, wordt de uitvoer gemaakt met de huidige versie van de bestanden en niet met de gekoppelde basislijn.<br><br>Zie [Werken met basislijn](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) voor meer details. |
| Eigenschappen | Selecteer de eigenschappen die u als metagegevens wilt verwerken. Deze eigenschappen worden ingesteld op de pagina Eigenschappen van de DITA-kaart of het bladwijzerbestand. De eigenschappen die u in de vervolgkeuzelijst selecteert, worden onder het veld Eigenschappen weergegeven en uit de vervolgkeuzelijst verwijderd.<br><br>**Opmerking**: De eigenschappen van de metagegevens zijn hoofdlettergevoelig.<br><br>*Als u een basislijn hebt geselecteerd, zijn de waarden voor de eigenschappen gebaseerd op de versie van de geselecteerde basislijn.<br>* Als u geen basislijn hebt geselecteerd, zijn de waarden voor de eigenschappen gebaseerd op de meest recente versie.<br><br>U kunt de metagegevens ook doorgeven aan de uitvoer met DITA-OT-publicatie. Zie voor meer informatie [Geef de metagegevens door aan de uitvoer met DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Opmerking**: Als u geen definitie hebt gegeven van `cq:tags` in de optie Eigenschappen, dan de waarden voor `cq:tags` worden gekozen uit de huidige werkkopie, zelfs als u een basislijn hebt geselecteerd voor publicatie. |
| Kaarteigenschappen gebruiken als deze ontbreken bij onderwerp | Als deze optie is geselecteerd, worden de eigenschappen die voor het kaartbestand zijn gedefinieerd, ook gekopieerd naar de onderwerpen waar deze eigenschappen niet zijn gedefinieerd. Houd rekening met de volgende punten wanneer u deze optie gebruikt:<br><br>*Alleen eigenschappen String, Date of Long (enkelvoudig en geavanceerd) kunnen worden doorgegeven aan de AEM sitepagina&#39;s.<br>* De metagegevenswaarden voor een eigenschap van het type String ondersteunen geen speciale tekens (zoals `@, #, " "`).<br>* Deze optie dient te worden gebruikt in combinatie met de `Properties` optie. |

## Aanvullende notitie op AEM site

### Op artikel gebaseerde uitvoer genereren vanuit de webeditor

U kunt de output van de Plaats van de AEM voor één of meerdere onderwerpen, of de volledige kaart DITA van de Redacteur van het Web produceren. U moet uitvoervoorinstellingen maken voor uw DITA-kaart en vervolgens kunt u de AEM Site-uitvoer voor uw kaart eenvoudig genereren. Als u een paar onderwerpen in uw kaart hebt bijgewerkt, kunt u de output van de AEMPlaats slechts voor die onderwerpen van de Redacteur van het Web ook produceren. Zie voor meer informatie [Publiceren op basis van artikelen vanuit de webeditor](web-editor-article-publishing.md#id218CK0U019I).

### Output die onderwerpen van andere kaarten verbinden

Het is een zeer gemeenschappelijk scenario om een grote reeks documentatie te hebben die zich over veelvoudige omslagen en kaarten DITA uitgespreid. Het wordt bijzonder ingewikkeld om inhoud te publiceren die van diverse plaatsen verbonden is. Standaard alle koppelingen `<xref>` worden gemaakt met de `local` `@scope`. Het publiceren van dergelijke onderwerpen impliceert geen uitdaging, aangezien het directe verbinding aan het onderwerp gebruikt. Als het onderwerp buiten de huidige kaart DITA is, toont de verbinding niet de verbonden inhoud.

Een andere manier om inhoud te koppelen, is het maken van een koppeling met de `peer` `@scope`. Voor dergelijke inhoud, wordt de verbinding opgelost in runtime door de gevormde context voor het verbonden onderwerp van de het publiceren van de kaart DITA context te kiezen. In de volgende schermafbeelding ziet u het deelvenster Eigenschappen voor een koppeling met de `peer` `@scope`:

![](images/peer-link-scope-link.png){width="800" align="left"}

Om het publiceren van complexe kaarten en onderwerpen te vereenvoudigen die met andere onderwerpen in andere kaarten verbinden, staat AEM Gidsen u toe om de het publiceren context voor elke vooraf ingestelde output te plaatsen.

De het publiceren context staat u toe om te specificeren welk onderwerp moet worden gebruikt waarvan kaart voor het publiceren van een specifieke output. Laten we dit begrijpen met behulp van een voorbeeld — laten we zeggen dat je vier mappen hebt: monster a, monster b, monster c en monster d. Elke map bevat een DITA-kaart — DITA-kaart A, DITA-kaart B, DITA-kaart C en DITA-kaart D. Cross-map het verbinden zal gebeuren wanneer een onderwerp in DITA kaartA verbindingen met een onderwerp in kaart DITA B, C, of D brengt. In het volgende schermafbeelding bevat een onderwerp met voorbeeldconcepten koppelingen \(of verwijzingen\) naar bestanden die deel uitmaken van andere DITA-kaarten.

![](images/sample-concept-link-to-other.png){width="450" align="left"}

Wanneer u nu de publicatie-instellingen voor AEM site configureert voor het kaartbestand dat dit onderwerp bevat, kunt u selecteren welke publicatiecontext voor de gekoppelde inhoud wordt gebruikt tijdens het publiceren. Een publicatiecontext is een combinatie van een DITA-kaart en de bijbehorende uitvoervoorinstelling. De uitvoervoorinstelling bevat op zijn beurt een specifieke versie van de inhoud en voorwaardelijke voorinstellingen. Deze volledige combinatie van de DITA-kaart, de uitvoervoorinstelling, de versie \(bestanden\) en de voorwaarden definiëren de publicatiecontext voor een gekoppelde kaart.

Voer de volgende stappen uit om de publicatiecontext voor cross-linked bestanden op te geven:

1. Open de **Voorinstellingen uitvoer** tabblad van de DITA-kaart die u wilt publiceren.

1. Selecteer **Site AEM** uitvoervoorinstelling.

   U krijgt de AEM vooraf instelt Montages en Publish lusjes van de Context.

   ![](images/aem-site-publish-settings.png){width="800" align="left"}

1. Open de **Context publiceren** tab.

   U wordt getoond een lijst van afhankelijke onderwerpen. Dit zijn de onderwerpen die van één of ander onderwerp in de huidige kaart verbonden zijn, maar zij zijn beschikbaar in sommige andere kaarten DITA.

   >[!NOTE]
   >
   > Op het tabblad Publicatie worden onderwerpen weergegeven die zijn gekoppeld met het tabblad `peer` `@scope` alleen. Voor koppelingen met `local` `@scope`hoeft u de publicatiecontext niet op te geven.

   Standaard zijn voor alle gekoppelde onderwerpen de meest recente uitvoervoorinstelling en -toewijzing geselecteerd.

   ![](images/default-publish-context.png){width="800" align="left"}

1. Als u de standaardselectie van de DITA-kaart en -voorinstelling wilt wijzigen, klikt u op **Bewerken** \(in de hoofdwerkbalk\).

1. Als u de laatst gepubliceerde uitvoer van elk afhankelijk bestand op de kaart wilt gebruiken, selecteert u **Laatst gegenereerde publicatiecontext gebruiken voor alle afhankelijke onderwerpen**.

1. In de **Bovenliggende kaart** Selecteer in de vervolgkeuzelijst het kaartbestand met de uitvoer van de huidige kaart die u wilt koppelen.

   Bij het selecteren van een kaartdossier, wordt UUID van de kaart getoond in de Ouderlijke kolom van UUID van de Kaart. De uitvoervoorinstellingen die aan de geselecteerde kaart zijn gekoppeld, worden vermeld in de lijst Voorinstellingen bovenliggende kaart.

1. In de **Voorinstelling bovenliggende kaart** Selecteer de uitvoervoorinstelling waarmee u de uitvoer van de huidige kaart wilt koppelen.

1. Selecteer de vereiste kaart en zijn output vooraf ingesteld voor alle afhankelijke onderwerpen en klik **Gereed**.

   De context voor de afhankelijke onderwerpen is nu ingesteld. U kunt de uitvoer voor de huidige kaart genereren. Voor meer informatie over het produceren van output, zie [Produceer output voor een kaart DITA van de kaartconsole](generate-output-for-a-dita-map.md#).

### Overvloeien van publicaties

AEM hulplijnen ondersteunen het publiceren van DITA-inhoud binnen uw bestaande AEM. Als u bijvoorbeeld een bestaande site hebt, kunt u met de AEM Site-uitvoer alleen de DITA-inhoud op die site publiceren. In dit proces wordt de bestaande niet-DITA-inhoud niet gewijzigd door het publicatieproces. Neem contact op met de publicatiebeheerder voor meer informatie over het instellen van uw site om alleen DITA-inhoud te publiceren.

### Publiceren `conref`

Als u `conref` in uw inhoud, dan wordt het gepubliceerd als normale of ingebedde inhoud samen met de inhoud in het bron \ (of verwijzend \) onderwerp. De `conref` inhoud wordt samen met de hoofdinhoud gerenderd en er wordt geen aparte sitepagina voor dezelfde inhoud gemaakt. Wanneer u naar de inhoud zoekt die in `conref`en vervolgens alleen het hoofdonderwerp of de pagina met het `conref` inhoud wordt weergegeven in de zoekresultaten.

>[!NOTE]
>
>Als u afzonderlijke pagina&#39;s voor de `conref` met AEM versie 3.5 of lager van de hulplijnen, wordt aangeraden deze pagina&#39;s te verwijderen of opnieuw te verwijderen met behulp van de [Orphan-sitepagina&#39;s verwijderen](#delete-orphan-page-aem-site) optie.


### Zoeken in een tekenreeks binnen de inhoud

U kunt zoeken naar een tekenreeks in de uitvoer AEM Site. Standaard kunt u alleen in de titels naar de tekenreeks zoeken. Als u naar de tekenreeks in de inhoud of de hoofdtekst van de AEM site-uitvoer wilt zoeken, neemt u contact op met de systeembeheerder om de eigenschap flattening.enabled in te schakelen.


<img src="images/aem-output-search.png" alt="Zoeken AEM Site-uitvoer" width="800">

Zie voor meer informatie *Samenvoegen van AEM siteknooppuntstructuur configureren* in de handleiding voor het installeren en configureren van Adobe Experience Manager-hulplijnen.

**Bovenliggend onderwerp:**[ Uitvoervoorinstellingen](generate-output-understand-presets.md)