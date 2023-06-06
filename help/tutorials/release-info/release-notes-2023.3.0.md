---
title: Opmerkingen bij de release | Adobe Experience Manager-hulplijnen as a Cloud Service, release maart 2023
description: Release Adobe Experience Manager Guides as a Cloud Service in maart
source-git-commit: 99ca14a816630f5f0ec1dc72ba77994ffa71dff6
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---


# Release van Adobe Experience Manager Guides, maart 2023 as a Cloud Service

In deze releaseopmerking worden de instructies voor het bijwerken, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie maart 2023 van de Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*).

Voor meer informatie over de nieuwe functies en verbeteringen raadpleegt u [Nieuwe functies in maart 2023, release van AEM hulplijnen as a Cloud Service](whats-new-2023.3.0.md).

## Upgrade naar release maart 2023

Voer de volgende stappen uit om de huidige installatie van de AEM hulplijnen te upgraden:
1. Controle uit de Cloud Services Gespitscode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2023.3.242.
3. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om naar de release van maart 2023 van AEM as a Cloud Service hulplijnen te upgraden.

## Stappen om de bestaande inhoud te indexeren (Alleen als u een versie hebt die ouder is dan de release van AEM hulplijnen in september as a Cloud Service)

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe tekst zoeken en vervangen op kaartniveau te gebruiken:

* Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>/bin/guides/map-find/indexing`.
(Optioneel: U kunt specifieke paden van de kaarten doorgeven om ze te indexeren. Standaard worden alle kaarten geïndexeerd || Voorbeeld: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

* De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`
(Bijvoorbeeld: http://&lt;
_localhost:8080_>/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678)

* Als de taak is voltooid, reageert het bovenstaande verzoek van de GET met succes en vermeldt u of kaarten zijn mislukt. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM in de release van maart 2023 as a Cloud Service hulplijnen.

### FrameMaker en het Publiceren FrameMaker Server

| Hulplijnen AEM als Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.03.0 | Niet compatibel | 2022 of hoger |
|  |  |  |


### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.03.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 |
|  |  |  |  |


