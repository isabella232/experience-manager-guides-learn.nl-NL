---
title: Opmerkingen bij de release | Adobe Experience Manager Guides as a Cloud Service, release april 2023
description: Laatste release van Adobe Experience Manager-hulplijnen as a Cloud Service
source-git-commit: 77b118655ad8e37e00b0371497e4a2578ddd276e
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 1%

---

# Release van Adobe Experience Manager Guides as a Cloud Service in april

## Upgrade naar de nieuwste versie

Upgrade uw huidige as a Cloud Service Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*) door de volgende stappen uit te voeren:

1. Controle uit de Cloud Services Gespitscode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2023.4.249.
3. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om naar de nieuwste versie van AEM as a Cloud Service hulplijnen te upgraden.

## Stappen om de bestaande inhoud te indexeren (Alleen als u een versie hebt die ouder is dan de release van AEM hulplijnen in september as a Cloud Service)

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe tekst zoeken en vervangen op kaartniveau te gebruiken:

* Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optioneel: U kunt specifieke paden van de kaarten doorgeven om ze te indexeren. Standaard worden alle kaarten geïndexeerd || Voorbeeld: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Bijvoorbeeld: http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Als de taak is voltooid, reageert het bovenstaande verzoek van de GET met succes en vermeldt u of kaarten zijn mislukt. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM in de release van april 2023 van hulplijnen.

### FrameMaker en het Publiceren FrameMaker Server

| Hulplijnen AEM als Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.04.0 | Niet compatibel | 2022 of hoger |
|  |  |  |


### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.04.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 |
|  |  |  |  |


## Nieuwe en verbeterde functies

AEM de as a Cloud Service Gidsen verstrekt verhogingen en nieuwe eigenschappen in de recentste versie:

### Geavanceerde ondersteuning voor metagegevens in PDF-publicaties

AEM Hulplijnen bieden nu geavanceerde ondersteuning voor de metagegevens die zijn toegewezen aan de metagegevens in de uitvoer van de PDF. De opties voor metagegevens bevatten informatie over het document en de inhoud ervan, zoals de naam van de auteur, de documenttitel, trefwoorden, copyrightinformatie en andere gegevensvelden.

<img src="assets/pdf-metadata.png" alt=" native PDF-metagegevens">

U kunt een XMP importeren en AEM hulplijnen kunnen de gegevens uit het bestand kiezen. U kunt ook de namen en waarden van metagegevens opgeven met het vervolgkeuzemenu. U kunt ook aangepaste metagegevens toevoegen door deze rechtstreeks in het naamveld te typen.


### Verbeterd deelvenster Omtrekweergave

AEM hulplijnen biedt een verbeterd deelvenster Omtrekweergave waarin u de hiërarchische weergave kunt zien van de elementen die in het document worden gebruikt.

<img src="assets/select-element-content-outline-view_cs.png" alt=" native PDF-metagegevens">

De omtrekweergave biedt de volgende verbeteringen:

* Het vervolgkeuzemenu Weergaveopties wordt boven in het deelvenster Omtrekweergave weergegeven. Als een element een id, kenmerk en tekst heeft, kunt u deze selecteren in het vervolgkeuzemenu en ze samen met het element weergeven. De attributen die in het paneel van de Mening van het Overzicht kunnen worden getoond worden bepaald door de montages van de Attributen van de Vertoning die door uw beheerder binnen zijn gevormd **Editor-instellingen**.

* Met de zoekfunctie kunt u naar een element zoeken op basis van de naam, id, tekst of kenmerkwaarde.


### Op microservices gebaseerde publicaties voor AEM hulplijnen as a Cloud Service

AEM de as a Cloud Service Gidsen verstrekt de eigenschap om grote het publiceren werkbelastingen met microdienst-gebaseerde het publiceren in werking te stellen en hefboomwerking het industrie-toonaangevende de serverplatform van Adobe I/O Runtime.

Nu in de versie van April kunt u veelvoudige het publiceren verzoeken tezelfdertijd in werking stellen en bulkoutput van PDF zeer efficiënt produceren gebruikend de op microdienst-gebaseerde Inheemse PDF het publiceren.
Zie voor meer informatie [Nieuwe op microservice gebaseerde publicatie configureren voor as a Cloud Service AEM hulplijnen](../knowledge-base/publishing/configure-microservices.md).


## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

* Native PDF | Het publiceren van inhoud die een outputklasse met steunen () heeft leidt tot een het publiceren bevriezing. (11596)
* Probleem doet zich voor bij het verplaatsen (slepen en neerzetten) in plaats van een bestaand lijstitem met Wijzigingen bijhouden ingeschakeld. (11570)
* Probleem doet zich voor bij het verplaatsen (slepen en neerzetten) als een nieuw lijstitem met Wijzigingen bijhouden ingeschakeld. (11569)
* Lijstitems inspringen of uitspringen werken niet zoals u had verwacht bij Wijzigingen bijhouden ingeschakeld. (11568)
* Als u inhoud toevoegt op een regel met Wijzigingen bijhouden ingeschakeld en vervolgens Wijzigingen bijhouden uitschakelt, wordt de inhoud niet daadwerkelijk uitgeschakeld. (11567)
* Moeilijk om een list-item te slepen en neer te zetten, wordt tekst verplaatst in plaats van het list-item. (11566)
* Voltooide revisie wordt niet geopend in de modus Alleen-lezen. (11387)
* Het probleem doet zich voor in AEM zoekopdracht op de site (werkt niet meer dan 2-3 knooppunten op het niveau). (11352)
* Bij het ontwerpen in het element dat groen (Wijzigingen bijhouden) wordt weergegeven, wordt de nieuwe inhoud weergegeven als een wijziging in de track, ook al is de trackwijziging uitgeschakeld. (7021)

### Bekend probleem met tijdelijke oplossing

Adobe heeft het volgende bekende probleem voor AEM Guides as a Cloud Service april 2023 geïdentificeerd.

* Native PDF | De oude metagegevens worden pas gevuld wanneer de voorinstelling voor uitvoer expliciet wordt geopend.

