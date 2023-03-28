---
title: Opmerkingen bij de release | Adobe Experience Manager Guides as a Cloud Service, release februari 2023
description: Release van Adobe Experience Manager Guides as a Cloud Service in februari
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
source-git-commit: ee520ab86ea41df7556a1f40d7bfc5e3617b34ae
workflow-type: tm+mt
source-wordcount: '2178'
ht-degree: 1%

---

# Release van Adobe Experience Manager Guides as a Cloud Service in februari

## Upgrade naar de release van februari

Upgrade uw huidige as a Cloud Service Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*) door de volgende stappen uit te voeren:
1. Controle uit de Cloud Services Gespitscode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2023.2.235.
3. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om de release van AEM hulplijnen in februari te upgraden.

## Stappen om de bestaande inhoud te indexeren (Alleen als u een versie hebt die ouder is dan de release van AEM hulplijnen in september as a Cloud Service)

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe tekst zoeken en vervangen op kaartniveau te gebruiken:

* Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optioneel: U kunt specifieke paden van de kaarten doorgeven om ze te indexeren. Standaard worden alle kaarten geïndexeerd || Voorbeeld: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Bijvoorbeeld: http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Als de taak is voltooid, reageert het bovenstaande verzoek van de GET met succes en vermeldt u of kaarten zijn mislukt. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM hulplijnen, as a Cloud Service in februari 2023.

### FrameMaker en het Publiceren FrameMaker Server

| Hulplijnen AEM als Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.02.0 | Niet compatibel | 2022 of hoger |
|  |  |  |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.02.0 | 2,8-uuid-8 | 2,8-uuid-8 | 2.3 | 2.3 |
|  |  |  |  |


## Nieuwe en verbeterde functies

AEM as a Cloud Service hulplijnen bieden verbeteringen en nieuwe functies in de release van februari:

### Rapporten genereren vanuit de webeditor

AEM de Gidsen komen met een eigenschap in de Redacteur van het Web die u toelaat om de algemene volledigheid van uw technische documenten te controleren en rapporten voor hen te produceren.
U kunt de onderwerpenlijst bekijken, de meta-gegevens beheren en multimedia zien die in alle verwijzingen voor de huidige kaart van wordt gebruikt
**Rapporten** in de webeditor.

**De weergave Lijst met onderwerpen genereren**

U kunt de Lijst van het Onderwerp produceren die gedetailleerde informatie over uw onderwerpen, zoals het verwijzingstype, documentstaat, en auteur verstrekt. U kunt CSV ook produceren om de huidige momentopname van de onderwerpen in de kaart te downloaden DITA.

**Metagegevens beheren en documentstatus wijzigen**

U kunt markeringen op een individueel onderwerp toepassen of de bulketiketterende eigenschap gebruiken om veelvoudige markeringen op veelvoudige onderwerpen, een kaart DITA, of een sub-kaart toe te passen. U kunt de documentstatus van alle geselecteerde onderwerpen ook wijzigen in de volgende mogelijke algemene documentstatus.

<img src="assets/web-editor-metadata-panel.png" alt="metagegevens beheren" width="600">

**Het multimediapport genereren**

U kunt het multimediapport genereren dat gedetailleerde informatie bevat over de multimedia die wordt gebruikt in uw verwijzingen in de huidige kaart. U hebt de flexibiliteit om de dossiers van verschillende media te filtreren en te sorteren die in het rapport worden vermeld.
U kunt CSV ook produceren om de huidige momentopname van multimedia te downloaden die in de kaart DITA wordt gebruikt.

<img src="assets/web-editor-reports-multimedia.png" alt="multimediapport" width="600">

### Nieuwe UX voor de revisiefunctionaliteit

AEM gidsen verstrekt nu een betere UX die u helpt de onderwerpen herzien die voor overzicht worden gedeeld. In de meest recente ervaring zijn de volgende verbeteringen beschikbaar voor de revisiefunctionaliteit:

* Vernieuwde gebruikersinterface
* Het paneel van voorwaarden dat u toestaat om de inhoud volgens de beschikbare voorwaarden in het onderwerp te benadrukken
* Elke opmerking in het opmerkingenvenster is gekoppeld aan de corresponderende tekst in het huidige onderwerp. Hiermee kunt u de tekst met opmerkingen herkennen.
* De opmerkingen worden weergegeven in de volgorde van de tekst met opmerkingen in het document.
* De naam van de revisietaak wordt weergegeven in de revisiewerkstroom.
* Selecteer de routekaart voor de overzichtstaak die wordt gebruikt om alle belangrijkste verwijzingen en verklarende woordenlijsttermijnen op te lossen die in de overzichtsinhoud worden gebruikt.
* Contextuele werkbalk waarmee u tekst snel kunt markeren of doorhalen
* Menu Opties voor het bewerken of verwijderen van uw eigen opmerkingen
* Voor verouderde commentaren, hebt u toegang tot zij-aan-zij mening die u helpt de vorige versie van het onderwerp met huidige overzichtsversie vergelijken.
* Wanneer u de filters gebruikt, worden de opmerkingen in het rechtervenster gefilterd op basis van de selectie en wordt het aantal opmerkingen in het linkervenster dienovereenkomstig bijgewerkt.


   <img alt="controletaak" src="assets/comment-pop-up-panel.png" width="600">



### Verbeterde vertaling

Nu hebt u gebruikersvriendelijkere verhogingen in het Dashboard van de Vertaling die u helpen uw documenten van de Redacteur van het Web gemakkelijk vertalen.

**Geef het versielabel door aan de doelversie**

Met AEM hulplijnen kunt u het label van het bronbestand aan het doelbestand doorgeven. Zo kunt u gemakkelijk de bronversie van het vertaalde bestand identificeren.

<img alt="vertaallabels" src="assets/translation-pass-source-label.png" width="600">

Als er bijvoorbeeld bronbestanden zijn waarop het versielabel Release 1.0 is toegepast, kunt u ook het bronlabel (Release 1.0) aan het vertaalde bestand doorgeven.

**Synchronisatie forceren voor niet-synchrone elementen**

Als u wijzigingen aanbrengt in sommige elementen, worden deze door AEM hulplijnen als Uit-synchroon gemarkeerd. U kunt de gewijzigde elementen opnieuw vertalen of de status Niet-gesynchroniseerd negeren. Als u bijvoorbeeld enkele kleine wijzigingen hebt aangebracht waarvoor geen vertaling nodig is, kunt u de status van de wijzigingen markeren als Bij synchroniseren.

<img src="assets/translation-version-diff.png" alt="vertaalbord" width="600">

**Vertaalprojecten in uitvoering voor een onderwerp of kaart weergeven**

Sommige verwijzingen op het vertaaldashboard zijn mogelijk in uitvoering. Nu AEM Gidsen verstrekt een eigenschap om u te helpen de lijst van alle Lopende vertaalprojecten (samen met de doeltaal) bekijken die de geselecteerde verwijzing bevatten.


### Produceer output in diverse formaten van de Redacteur van het Web

Nu kunt u de output voor uw onderwerpen of kaart DITA van de Redacteur van het Web gemakkelijk produceren. U kunt verschillende uitvoervoorinstellingen configureren, zoals AEM Site, PDF, HTML5, JSON (een indeling voor uitvoer zonder kop) en aangepaste uitvoer. U kunt deze vervolgens gebruiken om de respectievelijke uitvoerbestanden te genereren.

U kunt attributen in uw onderwerpen bepalen DITA en dan de voorwaarde gebruiken vooraf ingesteld om een voorwaarde toe te passen terwijl het publiceren van de output. U kunt de het publiceren eigenschap van de Basislijn ook gebruiken om een specifieke versie van uw kaart DITA of onderwerp selectief te publiceren.


### Tekst zoeken en vervangen op kaartniveau

Met AEM hulplijnen kunt u zoeken naar bestanden in een kaart die specifieke tekst bevatten. De gezochte tekst wordt benadrukt in de dossiers. Nu kunt u ook het gezochte woord of de gezochte uitdrukking door een ander woord of een uitdrukking binnen alle dossiers vervangen. U kunt **Alles vervangen** rechts boven in de lijst om alle instanties van de zoekterm in alle bestanden te vervangen.

<img src="assets/map-find-replace.png" alt="map zoeken vervangen" width="600">

### Bestanden verwijderen en dupliceren uit het deelvenster Verplaats

U kunt nu gemakkelijk een duplicaat of een kopie van een bestand maken op basis van de **Opties** menu van het geselecteerde bestand in het paneel van de gegevensopslagruimte. Standaard wordt het bestand gemaakt met een achtervoegsel (zoals `filename_1.extension`).

<img src="assets/options-menu-repo-view-file-level.png" alt="menu met bestandsopties " width="500">


### Andere verbeteringen in de webeditor

* In AEM hulplijnen kunt u bepaalde veelvoorkomende bewerkingen voor afbeeldingen en mediabestanden uitvoeren met behulp van het contextmenu. Nu kunt u ook de geselecteerde afbeelding of media vinden in de opslagplaats of de voorvertoning van het bestand bekijken in de interface Middelen.

* De naam van het huidige mapprofiel wordt weergegeven als een label voor het pictogram Gebruikersvoorkeuren op de hoofdwerkbalk. Zo kunt u het mapprofiel identificeren waaraan u werkt.

* Wanneer u een kaart opent in de kaartweergave, wordt de titel van de huidige kaart weergegeven in het midden van de hoofdwerkbalk. Dit is handig om de gebruikers te laten weten welke kaart momenteel is geopend.


### Titel weergeven in plaats van UUID in de Zuurstofbewerker

Met AEM hulplijnen kunt u nu kiezen **Titel gebruiken in Editor en kaartbeheer** in Instellingen. Als u deze optie selecteert, wordt de titel van het bestand weergegeven op het tabblad van het bestand wanneer het wordt geopend in de Editor of DITA Maps Manager. Als u deze optie niet selecteert, wordt de UUID van het bestand weergegeven op het tabblad van het bestand.

### Op microservices gebaseerde publicaties voor AEM hulplijnen as a Cloud Service

Met de nieuwe publicatiemicroservice kunt u grote publicatiewerkbelastingen tegelijk uitvoeren op AEM as a Cloud Service hulplijnen en het toonaangevende Adobe I/O Runtime-serverplatform benutten.

Voor elke publicatieaanvraag AEM as a Cloud Service hulplijnen wordt een aparte container uitgevoerd die horizontaal wordt geschaald volgens de wensen van de gebruiker. Hierdoor kunt u meerdere publicatieverzoeken uitvoeren en de prestaties verbeteren.

Zie voor meer informatie [Nieuwe op microservice gebaseerde publicatie configureren voor as a Cloud Service AEM hulplijnen](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/publishing/configure-microservices.md).

### Native PDF | Een aangepaste bladwijzer toevoegen in PDF-uitvoer

Nu kunt u voor eenvoudige navigatie een aangepaste bladwijzer toevoegen aan een bepaalde inhoud in de uiteindelijke PDF-uitvoer. Dit zou aan TOC worden toegevoegd die van de onderwerp of sectietitels in uw kaart DITA wordt gecreeerd.

### Native PDF | Aangepaste stijl toepassen op inhoudsopgave-items en onderwerpinhoud

AEM de Gidsen verstrekt de eigenschap om douanemateriaal op de ingangen van TOC of een bepaald onderwerp in de output van PDF toe te passen. U kunt bijvoorbeeld de kleur wijzigen van de tekst in de inhoudsopgave en de titel van het onderwerp. U kunt stijlen ook toepassen op de volledige inhoud binnen het onderwerp.


### Native PDF | De paginamarkering opmaken in de voetnootcomponent

Nu kunt u de paginamarkering opmaken in de voetnoten. U kunt bijvoorbeeld vierkante haakjes toevoegen of de kleur ervan wijzigen. Met deze stijlen kunnen gebruikers gemakkelijk de paginamarkeringen in het document herkennen.

### Native PDF | De bar van de verandering om op veranderde onderwerpen in Inhoudsopgave te wijzen

Met AEM hulplijnen kunt u nu snel de gewijzigde onderwerpen in de inhoudsopgave van de PDF-uitvoer identificeren.  Het toont een veranderingsbar op de linkerzijde van de veranderde onderwerpen in TOC. U kunt op het onderwerp in TOC klikken en de gedetailleerde veranderingen bekijken.

<img src="assets/change-marker-toc.png" alt="Markeerteken in inhoudsopgave wijzigen " width="500">

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

### Authoring

* Wijzigingen in de webeditor veroorzaken problemen met `<dl>` en `<dlentry>`. (11024)
* Sommige kenmerken worden niet behandeld als voorwaardelijk en veroorzaken problemen. (10895)
* Drie niveaus of meer genest `<indexterm>` niet genest zijn in native PDF-export. (10799)
* De inhoud verdwijnt in de hoofdtekst van een taak bij het schakelen van Auteur naar Bronweergave. (10735)
* Opmerkingen voor revisies worden verkeerd geplaatst in een revisietaak. (10625)
* **Ongedaan maken** of **Opnieuw** werkt niet correct bij sommige bestanden. (10373)
* Aangepaste metagegevens blijven niet behouden bij kopiëren en plakken. (10367)
* Met de optie Ongedaan maken in de XML-editor gaat de gebruiker naar de bovenkant van de pagina. (10091)
* Node-eigenschappen worden verwijderd nadat een element is gekopieerd en geplakt. (10053)
* mimeType is hardcoded voor het creëren en bijwerken van activa DITA. (8979)
* De naam van de maker van de versie in Versiehistorie is &quot;fmdita-servicegebruiker&quot; voor de bestanden die via de interface Elementen zijn geüpload. (8910)
* Inhoudsfragmenten kunnen niet worden gekopieerd en geplakt wanneer AEM hulplijnen op de cloud zijn geïnstalleerd. (11315)
* Browser (de Redacteur van het Web) bevriest bij het laden van inhoud met douaneschema. (11211)

### Beheer

* Het kopiëren van een DITA-kaart-element (van de Asset UI) veroorzaakt onjuiste basislijnen in het gekopieerde element. (11218)
* Er wordt geen waarschuwingsbericht weergegeven bij het uploaden van een bestand dat groter is dan de limiet die is toegestaan in AEM (standaard 2 GB). (10817)
* Web Editor-basislijn | Het gedrag van de kolom Laatste is verschillend in het nieuwe basislijndashboard binnen de Redacteur van het Web. (10808)
* Vertaling | De vertaaltaak wordt niet gestart vanwege ongeldige /libs/fmdita/i18n/ja.json. (10543)
* Vertaling | Er is een fout opgetreden in een bereikvertaalproject dat is gemaakt op het vertaaldashboard (Menselijke vertaling). (10526)
* Vertaling | Nabewerking wordt geblokkeerd voor de gehele taalmap waarvan de middelen aanwezig zijn in een actief vertaalproject. (10332)
* Er worden meerdere pop-ups weergegeven voor elk element als de versie wordt gewijzigd en opgeslagen in de basislijneditor. (10399)
* Sessieklek treedt op bij `com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver(QueryBuilderImpl.java:210)`. (10279)

### Publiceren

* De regeneratie van het onderwerp werkt niet voor sommige scenario&#39;s. (10635)
* De luisteraar van de uitgever toont niet de gevraagde gegevens in info- logboeken, en het bevat ook sommige junk logboeken.( 10567)
* Native PDF | Bij het maken van een uitvoervoorinstelling met de optie Toevoegen aan mapprofiel mislukt het genereren van de PDF met een Null-aanwijzeruitzondering. (10950)
* Native PDF | Problemen treden op bij het roteren van de tabelkop. (10555)
* Native PDF | Genest `<indexterm>` niet genest zijn in native PDF-export. (10521)
* Native PDF | Geneste topicref in aanhangsels worden allemaal omgezet in h1 in de tijdelijke HTML. (10454)
* Het publiceren van de basislijn ontbreekt voor PDF die gebruikend het Publiceren FrameMaker Server 2020 wordt geproduceerd. (10551)
* Native PDF | Toevoegen `xref` naar een afbeelding wordt de afbeelding niet op de gegenereerde PDF weergegeven. (11346)
* Native PDF | Met de tag Afbeelding wordt het kenmerk display-inline toegevoegd aan alle afbeeldingen. (10653)
* Native PDF | Conceptopmerkingen worden standaard verborgen in de gegenereerde uitvoer. (10560)
* Native PDF | navtitle is niet geëerd voor topichead. (10509)
