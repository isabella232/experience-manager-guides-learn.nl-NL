---
title: Opmerkingen bij de release | Adobe Experience Manager Guides as a Cloud Service, release september 2022
description: Laatste release van Adobe Experience Manager-hulplijnen as a Cloud Service
source-git-commit: 748a37298849b3fbf6079c19de3cb052dee3a464
workflow-type: tm+mt
source-wordcount: '1284'
ht-degree: 3%

---

# Laatste release van Adobe Experience Manager-hulplijnen as a Cloud Service

## Upgrade naar de nieuwste versie

Upgrade uw huidige as a Cloud Service Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*) door de volgende stappen uit te voeren:
1. Controle uit de Cloud Services Gespitcode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2022.9.178.
3. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om naar de nieuwste versie van AEM as a Cloud Service hulplijnen te upgraden.

## Stappen om de bestaande inhoud te indexeren

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe tekst zoeken en vervangen op kaartniveau te gebruiken:
* Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>/bin/guides/map-find/indexin`.
(Optioneel: U kunt specifieke paden van de kaarten doorgeven om ze te indexeren. Standaard worden alle kaarten geïndexeerd || Voorbeeld:   `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)
* De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Bijvoorbeeld: `http://<_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)`
* Als de taak is voltooid, reageert het bovenstaande verzoek van de GET met succes en vermeldt u of kaarten zijn mislukt. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.


## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM release van september 2022 van hulplijnen.

### FrameMaker en het Publiceren FrameMaker Server

| FMPS | FrameMaker |
| --- | --- |
| Niet compatibel | 2020-update 4 en hoger |
|  |  |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022,9,0 | 2.7.13. | 2.7.13. | 2.3 | 2,3 |
|  |  |  |  |


## Nieuwe en verbeterde functies

AEM de as a Cloud Service Gidsen verstrekt vele verhogingen en nieuwe eigenschappen in de recentste versie:


### Een dynamische basislijn maken op basis van labels

AEM hulplijnen biedt u nu de functie om dynamische basislijnen te maken op basis van labels. Als u een basislijn genereert, een basislijn downloadt of een vertaalproject maakt met een basislijn, worden de bestanden dynamisch gekozen op basis van de bijgewerkte labels. Deze functie is handig omdat u de basislijn niet hoeft te wijzigen wanneer u de labels bijwerkt.
U kunt de momentopname van de basislijn als CSV ook uitvoeren.

![Basislijnen maken](assets/dynamic-baseline.png)

### Tekst zoeken en vervangen op kaartniveau

U kunt nu zoeken naar bestanden in een kaart die specifieke tekst bevatten. De gezochte tekst wordt benadrukt in de dossiers. U kunt het gezochte woord of de gezochte uitdrukking met een ander woord of een uitdrukking binnen de dossiers ook vervangen.
Selecteer **Vervangen** pictogram om het huidige exemplaar en het **Alles in bestand vervangen** om alle instanties in het geselecteerde bestand te vervangen.

![Zoeken in vervangen op kaart](assets/map-find-replace.png)

Standaard zijn de opties **Bestand uitchecken vóór vervangen** en **Nieuwe versie maken na vervangen** zijn geselecteerd, wordt een bestand uitgecheckt voordat u de tekst vervangt en wordt een nieuwe versie gemaakt nadat de tekst is vervangen.

### Het versieverschil voor uit-synchronisatiebestanden van het vertaaldashboard weergeven

U kunt er nu voor kiezen om de **Niet gesynchroniseerd** bestanden die zijn gebaseerd op de wijzigingen die zijn aangebracht tussen de twee versies van een onderwerp.\
![Vertaaldashboard](assets/translation-version-diff.png)
Vanuit het vertaaldashboard kunt u eenvoudig zien wat de verschillen zijn tussen de laatste vertaalde versie en de huidige versie van het geselecteerde bestand.

![dialoogvenster voor versieverschil](assets/version-diff.png)

Gebaseerd op de verschillen, kunt u beslissen of u een onderwerp wilt vertalen of niet.

### Gebruikersinterface met metagegevens beschikbaar voor PDF-voorinstellingen

U kunt de metagegevens instellen vanuit de uitvoervoorinstelling van een DITA-kaart. U kunt de metagegevens Titel, Auteur, Onderwerp en Trefwoorden instellen. Deze metagegevens worden toegewezen aan de metagegevens in de bestandseigenschappen van de uitvoer PDF.
Deze metagegevens overschrijven de metagegevens die op boekniveau zijn gedefinieerd. U kunt de metagegevens specifiek definiëren in elke uitvoervoorinstelling en deze doorgeven aan de PDF van de uitvoer.

![Metagegevens in voorinstelling](assets/preset-metadata.png)


## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

* Webeditor | Bij het bewegen van elementen binnen een onderwerp, toegewezen IDs op elementen worden beschreven door auto-toegewezen IDs. (7895)
* Wijzigingen bijhouden | De inhoud gaat verloren wanneer een nieuw element wordt ingegaan gebruikend de Enter sleutel. (10246)
* Submap die naar de hoofdkaart in dita-malplaatjes wordt verwezen wordt niet gecreeerd. (10231)
* XML-editor | Kopiëren en plakken werkt niet in de modus Schrijver. (10309)
* Meerdere versielabels die u hebt geselecteerd, worden niet uitgeschakeld. (9561)
* Automatische navigatie naar het pad in het dialoogvenster Bladeren van de site werkt niet zoals bladeren door bestanden. (9920)
* Het deelvenster Omtrek geeft geen inhoud weer wanneer u overschakelt van **Auteur** tot **Bron** in. (10319)
* Conref in een nieuw gecreeerd onderwerp gebruikend een inhoud in het onderwerpmalplaatje werkt niet. De gekopieerde hash-id wordt niet bijgewerkt in de inhoudskopie. (9890)
* Web-editor | Er bestaat geen lader tijdens het maken van een kaart op basis van de kaartsjabloon. (9891)
* Nieuwe kaarteditor | Toegevoegde vette of cursieve tekst in de kaartitel wordt niet behouden als we van **Auteur** aan de **Layout** weergeven. (10218)
* Nieuwe kaarteditor | Voorwaarden die worden toegepast op een verwijzing kunnen niet worden verwijderd uit de layoutweergave. (10213)
* Nieuwe kaarteditor | Het toepassen van voorwaardenverwijzingen werkt in de layoutweergave niet zoals in de weergave Auteur. (10198)
* Nieuwe kaarteditor | Naar links verplaatsen in het contextmenu verwijdert de verwijzing als deze niet naar links kan worden verplaatst. (10219)
* Nieuwe kaarteditor |Het pictogram wordt onjuist weergegeven voor de verwijzingen in een kaart die is gemaakt met de layoutweergave. (10197)
* Deelvenster Opslagplaats | Klik met de rechtermuisknop in het deelvenster Opslagplaats om een toepassingsfout te maken. (10123)
* Zoeken en vervangen | Donkere modus is niet leesbaar voor zoekresultaten in de webeditor. (9978)
* Vertaling | Metagegevens en codes worden niet aan de vertaalde kopieën doorgegeven. (4696)
* Bij kopiëren en plakken (ctrl+c/ctrl+v) treedt een fout op in de auteurmodus. (10304)
* PDF-sjabloon | Als u achtergrondafbeeldingen toevoegt aan een paginalay-out, wordt het afbeeldingspad absoluut weergegeven en worden de afbeeldingen niet weergegeven in de uitvoer PDF. (10297)
* Native PDF | De titel van het hoofdstuk en de koptekst van het hoofdstuk werken niet in PDF-publicaties. (9947)
* Native PDF | `xref` voor een concept wordt niet correct opgelost voor een specifiek onderwerp DITA. (10229)
* Native PDF | Bijschrifttekst voor een tabel kan niet worden weergegeven in de gegenereerde PDF-uitvoer. (9827)
* Native PDF | Verwijzingen in bijlagen worden niet als bijlagen weergegeven in PDF-uitvoer. (10182)
* Native PDF | Het kenmerk Frame voor een tabel wordt niet doorgegeven aan de tijdelijke HTML (als klasse). (10353)
* Native PDF | temp-bestanden voegen de klassen colsep en rowsep toe aan td en de HTML, zelfs als de waarde 0 is in de bron-DITA. (10352)
* Native PDF | Metagegevens voor criteria die in paginalay-out zijn toegevoegd, worden niet nageleefd. (10377)
* Native PDF | Het genereren van PDF mislukt voor specifieke inhoud. (9927)
* Native PDF | Inhoud via conkeyref wordt niet weergegeven in de PDF-uitvoer. (9836)
* Native PDF | Belangrijke referenties voor Keydefs met afbeeldingen of externe koppelingen zijn niet opgelost. (10063)
* In de weergave Auteur voor een kaart wordt geen plaatsaanduidingstekst weergegeven voor tabellen en figuurlijsten. (10330)
* Wanneer we een nieuwe basislijn maken, wordt het reeds geselecteerde basislijnfilter niet toegepast. (9954)
* Videobestand ontbreekt vanaf de basislijn als de naam van de bovenliggende map een spatieteken heeft. (10031)
* Bij het maken van de basislijn wordt de laatste versie niet gekozen als de tijdzone van de gebruiker afwijkt van de tijdzone van de server. (10190)
* Met de sneltoets Control + F wordt de zoekmodus van de browser in de middelenconsole niet geopend nadat u AEM hulplijnen 4.1 op AEM 6.5.12 hebt geïnstalleerd. (10189)


## Bekende problemen

Adobe heeft de volgende bekende problemen voor AEM release van september 2022 in kaart gebracht.


* Dynamische basislijn is niet geïntegreerd met publicatie op basis van kennis.

* Vertaling | Het pictogram Versieverschil wordt weergegeven voor de broninhoud vanwege wijzigingen in de doelinhoud.
