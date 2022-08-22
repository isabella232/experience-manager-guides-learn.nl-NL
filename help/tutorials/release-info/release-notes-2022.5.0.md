---
title: Opmerkingen bij de release | Adobe Experience Manager-hulplijnen as a Cloud Service, release mei 2022
description: Kan Adobe Experience Manager-hulplijnen in mei vrijgeven as a Cloud Service
exl-id: 7928a300-5ec9-492c-b9be-02b6f87638c6
source-git-commit: 0f5c1cabdbda9fa2606f67faedbf9a38ca1ec0aa
workflow-type: tm+mt
source-wordcount: '1874'
ht-degree: 4%

---

# Kan Adobe Experience Manager-hulplijnen in mei vrijgeven as a Cloud Service

## Upgrade naar de release van mei

Upgrade uw huidige as a Cloud Service Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*) door de volgende stappen uit te voeren:
1. Controle uit de Cloud Services Gespitcode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2022.5.144.
3. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om naar de release van mei van AEM as a Cloud Service hulplijnen te upgraden.

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM in de release van mei 2022 as a Cloud Service hulplijnen.

### FrameMaker en het Publiceren FrameMaker Server

| FMPS | FrameMaker |
| --- | --- |
| Niet compatibel | 2020-update 4 en hoger |
|  |  |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac |
| --- | --- | --- |
| 2022,5,0 | 2.6.9. | 2.6.9. |
|  |  |  |


## Nieuwe en verbeterde functies

AEM de as a Cloud Service Gidsen verstrekt vele verhogingen en nieuwe eigenschappen in de versie van Mei:

### Verbeterde webeditor

* **Kaarten maken op basis van aangepaste sjablonen**

Nu krijgt u de krachtige eigenschap om aangepaste kaartmalplaatjes tot stand te brengen. U kunt hen gebruiken om kaarten DITA samen met de onderwerpmalplaatjes en kaartmalplaatjes tot stand te brengen die in het kaartmalplaatje van verwijzingen worden voorzien.

![dita-sjablonen](assets/dita-templates.png)

U kunt naar andere kaartmalplaatjes en onderwerpmalplaatjes van het aangepaste kaartmalplaatje ook verwijzen. De genoemde kaartmalplaatjes kunnen naar diverse kaartmalplaatjes, onderwerpmalplaatjes, onderwerpen, kaarten, beelden, video&#39;s, en andere activa verwijzen.

![bewerkingssjablonen maken](assets/create-dita-template.png)

Het aangepaste kaartsjabloon kan u zeer gemakkelijk helpen de kaartsjablonen en de volledige doorverwezen omslagstructuur te herhalen. Deze aangepaste sjablonen zijn vooral handig voor het maken en opnieuw maken van meerdere kaarten met recursieve structuren en verwijzingen.

* De **Trefwoord invoegen** deze functie is verbeterd. U kunt nu gemakkelijker een trefwoord vinden dat moet worden ingevoegd omdat de trefwoorden in alfabetische volgorde worden weergegeven. U kunt ook naar trefwoorden zoeken door een zoektekenreeks in het vak Zoeken te typen.

![trefwoord invoegen](assets/insert-keyword.png)

* In de weergavebestanden voor opslagplaatsen worden nu batches geladen. Er worden 75 bestanden tegelijk geladen. Het laden van deze batch is efficiënt en u hebt sneller toegang tot de bestanden dan het laden van alle bestanden in een map.

![meer bestanden laden](assets/load-more-files.png)

* U kunt SVG-afbeeldingen renderen die ingesloten gegevens of koppelingen bevatten in alle schermen van XML-editors, inclusief maar niet beperkt tot de voorvertoning en de weergave Auteur.

* De standaard XSD/DTD kan worden bijgewerkt naar de nieuwste versie

### Verbeterd vertaalproces

* **De capaciteit om een scoping vertaalproject tot stand te brengen**
Als u slechts het werkingsgebied voor een te vertalen project moet creëren, kunt u selecteren 
**Een nieuw vertaal-project met bereik maken**. Hierdoor worden de kopieën niet voor vertaling verzonden en blijft de oorspronkelijke vertaalstatus van de bestanden behouden.

![vertaal project](assets/scoping-translation-project.png)

* Als u de vertaling voor één of meerdere onderwerpen in een vertaalbaan verwerpt, herstelt de Bezig vertaalstatus van alle verworpen onderwerpen aan hun originele status.

* De **Talen** de taalomslagen samen met hun taalcodes toont. Bijvoorbeeld Frans (fr) en Duits (de).

* De vertaalfunctie ondersteunt nu ook de taalcode die zowel het land als de taal omvat. Bijvoorbeeld, `fr-fr`, `en-us`.

![vertaaltaal](assets/translation-languages.png)

* Bij het laden van een kaart DITA die buiten de taalomslag is, wordt geen uitzondering geregistreerd bij het achtereind.

Voor meer informatie over vertaling raadpleegt u *Documenten vertalen vanuit de webeditor* in Adobe Experience Manager-hulplijnen as a Cloud Service gebruiken.


### Verbeterde publicatie

* U hebt ook toegang tot de **Dashboard publiceren** van het lusje van Output terwijl u output van het kaartdashboard produceert. Een lijst met alle actieve publicatietaken is beschikbaar op het dashboard Publiceren.

![uitgangen in een wachtrij](assets/queued-output.png)

* Via het kaartdashboard kunt u meerdere DITAVAL-bestanden selecteren om geconditioneerde inhoud te genereren. U kunt de bestandsvolgorde behouden door bestanden toe te voegen of te verwijderen. U kunt de muisaanwijzer ook boven de bestandsnaam plaatsen om het pad te zien in de AEM opslagplaats waar het bestand is opgeslagen.

* **Verouderde functie**
AEM as a Cloud Service steunt niet meer de generatie van DITA outputformaat voor documenten FrameMaker. Deze optie DITA is ook verwijderd uit de uitvoervoorinstellingen van het kaartdashboard.

### Verbeterde publicatie op basis van artikelen

De Redacteur van XML verstrekt de capaciteit om meer dan één productcategorie aan een artikel in kaart te brengen terwijl het publiceren aan een profiel Salesforce.

### Andere functieverbeteringen

* De modus Voorbeeld biedt ook ondersteuning voor `deliveryTarget` voorwaardelijk verwerkingskenmerk in DITA. Het is beschikbaar als optie in de drop-down filter samen met **publiek**, **platform**, **product**, props, **andere props**.
* Er is een optie beschikbaar waarmee de AEM server in Oxygen en het lokale systeem met kracht kan worden gesynchroniseerd.

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

* In het revisievenster van de webeditor kan de gebruiker niet reageren op de revisieopmerkingen. (9667)
* De toepassing wordt leeg wanneer u op een lege map klikt nadat u deze hebt vernieuwd via het menu Opties. (9639)
* Er wordt een nieuwe versie gemaakt wanneer we **Opslaan en sluiten** het ingecheckte bestand. (9638)
* Knop Sluiten wordt niet weergegeven wanneer **Opslaan als nieuwe versie** selectievakje is ingeschakeld. (9637)
* De juiste PDF wordt niet gepubliceerd als deze eerst via een aparte PDF voor elk hoofdstuk wordt gepubliceerd en vervolgens via één PDF-bestand (het selectievakje Afzonderlijke PDF-bestanden maken is uitgeschakeld). (9632)
* Het kaartdashboard veroorzaakt een probleem met metagegevens voor gebruikers die geen beheerder zijn. (9620)
* Zodra een basislijn wordt gecreeerd, wordt de status geplaatst aan ontbroken op UI (krijgt statusvraag ontbreekt) als de server meer dan 10000 dossiers heeft. (9608)
* Het opslaan van grote gegevens in eigenschappen resulteert in een publicatiefout omdat de gesplitste publicatieworkflow mislukt. (9586)
* De staat Voorwaardelijke kenmerkenfilters blijft niet behouden wanneer wordt geschakeld tussen de modus Voorbeeld naar bron en nogmaals de modus Voorbeeld. (9553)
* De naam van de bladwijzer wordt leeg weergegeven in de weergave Opslagplaats voor het geval er geen naam wordt gegeven via het dialoogvenster `mainbooktitle` tag. (9538)
* HTTP 400-fout treedt op tijdens het openen van een bestand dat is geüpload met Oxygen. (9535)
* De voorinstellingen van een eerder geopende kaart blijven op het tabblad Uitvoer zichtbaar wanneer een kaart wordt geopend zonder dat voorinstellingen zijn gedefinieerd. (9523)
* De zoekfunctionaliteit voor tags en kenmerken werkt niet in het deelvenster Overzicht. (9506)
* Nieuw gemaakte verzameling is pas zichtbaar nadat de browser is vernieuwd. (9505)
* Voorwaardelijke labels voor kenmerken (niet de waarden) worden weergegeven in de bronmodus wanneer u alle voorwaarden toevoegt via de optie Alle profielen toevoegen. (9501)
* Bestanden worden automatisch uitgecheckt wanneer u terugkeert naar een versie. (9482)
* Onjuiste tijdstempelverschillen worden weergegeven in de interface Middelen bij het terugkeren van een bestandsversie. (9480)
* De veelvoudige punten van onderzoeksresultaten worden toegevoegd terwijl het opnemen van punten in topicref element van kaart DITA. (9474)
* Als de instelling **Nieuwe versie maken voor geüpload bestand** is, wordt een nieuwe versie gecreeerd bij het terugkeren en het bewaren op om het even welk bevroren knoop. (9473)
* De tekst van de vertoning van Zeer belangrijke Verwijzing en de Belangrijkste Verwijzing van de Inhoud wordt niet gehandhaafd bij het veranderen van verbindingsURL, als de vertoningstekst niet terwijl het bepalen van zeer belangrijke verwijzing wordt toegevoegd. (9458)
* In Versiegeschiedenis worden het versienummer en het label niet weergegeven voor de huidige versie. (9446)
* De Editor bevriest wanneer bepaalde inhoudsbestanden worden geopend in de editor. (9443)
* Als u in het deelvenster Opslagplaats zoekt en in het dialoogvenster Bladeren op onderwerp bladert, wordt het scherm geblokkeerd wanneer de inhoud groot is. (9432)
* Metagegevens die aan AEM site-uitvoer worden doorgegeven, voldoen niet aan de basislijn van de inhoud. (9416)
* Zuurstof controleert een onjuiste versie van een onderwerp nadat een versie in AEM terugkeert. (9411)
* Uitgeschakelde basislijn schakelt bewerking uit op het tabblad Voorinstelling van het kaartdashboard. (9403)
* Fout wordt altijd geregistreerd op de verwezenlijking van nieuwe inhoud. (9388)
* Nieuw gemaakte DITA-elementen worden altijd uitgecheckt door een andere gebruiker. (9387)
* Naam van element wijzigen werkt niet correct tijdens het omzetten van topicref in glossref. (9380)
* Versielabel wordt niet weergegeven als vervolgkeuzelijst in **Opslaan als nieuwe versie** . (9379)
* De voorwaarden worden niet toegepast op omschakeling tussen verschillende versies van **Diff tonen** vervolgkeuzelijst. (9366)
* Er doen zich meerdere problemen voor bij het gebruik van voorvertoningsfilters. (9365)
* Kan niet-DITA- en DITAVAL-elementen niet invoegen in topicref. (9363)
* De goedgekeurde vertaling integreert niet aan de doeltaal wanneer de doeltaalcode vijf karakters zoals bevat `fr_ca`. (9357)
* Kan bestanden niet zoeken met **Bestanden zoeken in map** van de **Meer opties** en reageert de toepassing niet meer. (9337)
* Het dialoogvenster Bladeren loopt vast als er een groot aantal toetsen aanwezig is. (9332)
* DITAVAL-bestanden werken niet tijdens het publiceren op basis van artikelen. (9330)
* De volgorde van voetnoten is onjuist in de uitvoer AEM Site. (9327)
* De zoekopdracht wordt niet automatisch uitgevoerd wanneer het geselecteerde pad wordt gewijzigd. (9323)
* Wanneer de vertaling is voltooid, wordt een extra versie gemaakt voor het vertaalde element. (9310)
* Kan de gebruikers van de beheerder in het mappenprofiel niet verwijderen. (9306)
* Hoofdmap die wordt bijgewerkt via Content Key Reference, wordt pas ingesteld wanneer de pagina is vernieuwd. (9302)
* Webverificatie werkt niet in oxygen. (9296)
* Webkoppelingen met gecodeerde tekens werken niet correct. (9227)
* Het bestand wordt niet uitgecheckt wanneer het wordt geopend in zuurstof. (9217)
* Uitgecheckte bestanden vernieuwen werkt niet aan registratie met webverificatie in Oxygen. (9179)
* De tabbladen Vertaling en Basislijn zijn enige tijd zichtbaar op het dashboard van Kaart. (9146)
* Er treden problemen op bij het opnieuw laden van het mapprofiel. (9103)
* Als u de pagina-indeling-editor verwijdert, wordt deze niet gesloten vanuit het middelste deelvenster van de weergave Auteur. (9087)
* De fout van de bevestiging komt in de Redacteur van het Web bij het verwijderen van een beeld voor en dan bewaart de nieuwe versie van het document. (8985)
* Kan niet alle `glossrefs` in het deelvenster Verklarende woordenlijst (specifiek voor inhoud). (886)
* `xref` zonder tekst wordt niet weergegeven in op artikelen gebaseerde publicatie-uitvoer. (8764)
* Verwijzingen naar bewegende afbeeldingen of multimediabestanden met een spatie in de bestandsnamen. (8624)
* Verwijzingseinde bij kiezen `Select All` en verplaatst u de multimediabestanden of DITA-inhoud naar een andere map. (8622)
* Uitvoertaken met de status &quot;Wachten&quot; of &quot;Uitvoeren&quot; worden niet opgeschoond in het publicatiedashboard.  (8569)
* De functie Uitvoer leegmaken mislukt als er een groot aantal knooppunten in de uitvoergeschiedenis aanwezig zijn. (8568)
* Met DITA toevoegen op pakket voorkomt u dat elementen door DAM worden gedupliceerd. (8417)
* De knop Revisietaak maken is ingeschakeld voor niet-DITA-bestanden. (8401)
* Het dialoogvenster Referenties invoegen wordt geopend wanneer u subjectref aan een kaart toevoegt met behulp van de gebruikersinterface. (8212)
* Onverwachte ruimte gevonden in elke lege ruimte `entry` element wanneer kenmerk outputklasse wordt toegevoegd aan `tgroup` element. (7532)
* Het deelvenster Opslagplaats geeft de pictogrammen voor het in- of uitchecken van bestanden niet weer zodra de handeling is voltooid. (5817)
* Het vergrendelingspictogram wordt weergegeven in de dataweergave, zelfs als het bestand is ingecheckt in de editor.  (5756)
* Sites ontbreken in AEM voorinstellingen onder het tabblad Uitvoer. (9567)
* XML-editor hangt vast bij het bewerken van sommige DITA-bestanden. (9537)
* Als u een zoekopdracht uitvoert in de XML-editor, wordt de pagina vastgezet. (9452)
* Kaart downloaden met basislijn werkt niet als de inhoud naar een andere map wordt verplaatst. (9331)
* Herladen mislukt in zuurstof wanneer het bestand of de bestanden al in AEM op dezelfde locatie aanwezig zijn. (9328)
* De positie van markering is onjuist in de weergave Naast elkaar. (9305)
* Nadat een document van Oxygen naar AEM is ingecheckt, wordt Japanse inhoud in het document vervangen door vraagtekens (????). (9276)
* Uploaden van bestanden van Oxygen naar AEM mislukt. (9157)
* E-mailmelding wordt niet verzonden wanneer een revisietaak opnieuw wordt toegewezen in het Postvak IN. (8376)

## Bekende problemen

De lege pagina wordt periodiek weergegeven bij het openen van de editor.
