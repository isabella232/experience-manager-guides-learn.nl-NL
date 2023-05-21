---
title: Opmerkingen bij de release | Adobe Experience Manager-hulplijnen as a Cloud Service, release maart 2023
description: Release Adobe Experience Manager Guides as a Cloud Service in maart
exl-id: b3fe7cc8-1654-467a-ab18-6e6912855ecc
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 1%

---

# Release Adobe Experience Manager Guides as a Cloud Service in maart

## Upgrade naar de release van maart

Upgrade uw huidige as a Cloud Service Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*) door de volgende stappen uit te voeren:
1. Controle uit de Cloud Services Gespitscode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2023.3.242.
3. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om de release van AEM hulplijnen in maart te upgraden.

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


## Nieuwe en verbeterde functies

AEM as a Cloud Service hulplijnen bieden verbeteringen en nieuwe functies in de release van maart 2023:

### Video- of audiobestanden openen en afspelen in de webeditor

AEM Hulplijnen bieden nu de functie om de audio- of videobestanden te openen en af te spelen in de webeditor. U kunt het volume of de weergave van de video wijzigen. In het snelmenu hebt u ook de opties om **Downloaden**, wijzigen **Afspeelsnelheid**, of weergave **Beeld-in-beeld**.

<img src="assets/video-web-editor.png" alt="video afspelen" width="600">


## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

* Het proces van de PDF van de download werkt niet geschikt in de Redacteur van het Web. (11496)
* JSON-uitvoer | Metagegevens met kenmerk eigenschap als `"value in spaces and double quotes"` leidt tot een publicatiefout. (11438)
* Het invoegen van audio- en video-multimediabestanden mislukt in de YouTube-indeling onder de **Multimedia invoegen** pictogram. (11320)
* Validatiefout treedt op wanneer een kaart wordt gemaakt met behulp van de sjabloon met een speciaal titelelement. (11212)
* Native PDF | voetnoot in de tabelkoptekst leidt tot vette en gecentreerde tekst in de bijbehorende voettekst op de pagina in de PDF-uitvoer. (10610)
>[!NOTE]
>
>Om op de Inheemse verandering van de PDF te wijzen, schrap de omslag van de PDF die bij /content/dam/dita-templates wordt gevestigd en dan aan de recentste bouwstijl te bevorderen. (10610)

### Bekend probleem met tijdelijke oplossing

Adobe heeft het volgende bekende probleem voor AEM Guides as a Cloud Service maart 2023 geïdentificeerd.

* Gebruikers kunnen geen versie van een gedupliceerd element opslaan of maken.

**Workaround**: Voordat u wijzigingen aanbrengt in het dubbele element, moet u dit opnieuw verwerken via de interface Elementen.
