---
title: Opmerkingen bij de release | Adobe Experience Manager Guides as a Cloud Service, release februari 2023
description: Release van Adobe Experience Manager Guides as a Cloud Service in februari
exl-id: c639b136-11ed-4a8b-a595-4bb5da879747
source-git-commit: 99ca14a816630f5f0ec1dc72ba77994ffa71dff6
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 4%

---

# Release van Adobe Experience Manager Guides, februari 2023 as a Cloud Service

In deze releaseopmerking worden de instructies voor het bijwerken, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie februari 2023 van de Adobe Experience Manager-hulplijnen (later genoemd als *Hulplijnen AEM as a Cloud Service*).

Voor meer informatie over de nieuwe functies en verbeteringen raadpleegt u [Nieuwe functies in februari 2023, release van AEM hulplijnen as a Cloud Service](whats-new-2023.2.0.md).

## Upgrade naar de release van februari 2023

Voer de volgende stappen uit om de huidige installatie van de AEM hulplijnen te upgraden:
1. Controle uit de Cloud Services Gespitscode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2023.2.235.
3. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om naar de release van februari 2023 van AEM as a Cloud Service hulplijnen te upgraden.

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
