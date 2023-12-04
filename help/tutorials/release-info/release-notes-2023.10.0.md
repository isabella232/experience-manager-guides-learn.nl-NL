---
title: Opmerkingen bij de release | Upgrade-instructies en opgeloste problemen in Adobe Experience Manager-hulplijnen, release oktober 2023
description: Meer informatie over de opgeloste problemen en hoe u een upgrade uitvoert naar de as a Cloud Service release van Adobe Experience Manager Guides van oktober 2023
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 0%

---

# Release van Adobe Experience Manager Guides in oktober 2023 as a Cloud Service

In deze releaseopmerking worden de instructies voor het bijwerken, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie oktober 2023 van de Adobe Experience Manager-hulplijnen (later genoemd als *Hulplijnen AEM as a Cloud Service*).

Zie voor meer informatie over de nieuwe functies en verbeteringen [Nieuwe functies in de release van oktober 2023 van AEM hulplijnen as a Cloud Service](whats-new-2023.10.0.md).

## Upgrade naar oktober 2023

Voer de volgende stappen uit om de huidige installatie van de AEM hulplijnen te upgraden:

1. Controle uit de code van Git van Cloud Servicen en schakelaar aan de tak die in de pijpleiding van Cloud Servicen wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van uw Cloud Servicen: hiermee wordt de Git-code ingesteld op 2023.10.0.373.
3. Leg de wijzigingen vast en voer de pijplijn Cloud Servicen uit om te upgraden naar de release van oktober 2023 van AEM as a Cloud Service hulplijnen.

## Stappen om de trigger van een script via een servlet in te schakelen

(Alleen als u een versie hebt die ouder is dan de versie van juni 2023 van AEM hulplijnen as a Cloud Service)

Nadat u de installatie hebt voltooid, kunt u ervoor kiezen om de trigger te HIT om de vertaaltaak te starten:

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Reactie:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

In de vorige reactie van JSON was de sleutel `lockNodePath` bevat het pad naar het knooppunt dat in de opslagplaats is gemaakt en dat naar de ingediende taak verwijst. Het wordt automatisch verwijderd als de taak is voltooid. Tot dan kunt u naar dit knooppunt verwijzen voor de huidige status van de taak.

Wacht tot deze taak is voltooid voordat u verdergaat met de volgende stappen.

>[!NOTE]
>
> Controleer of het knooppunt nog aanwezig is en wat de status van de taak is.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Stappen om de bestaande inhoud te posten om het verbroken koppelingsrapport te gebruiken

(Alleen als u een versie hebt die ouder is dan de versie van juni 2023 van AEM hulplijnen as a Cloud Service)

Voer de volgende stappen uit voor de nabewerking van de bestaande inhoud en het gebruik van het nieuwe verbroken koppelingsrapport:

1. (Optioneel) Als het systeem meer dan 100.000 DITA-bestanden bevat, werkt u de `queryLimitReads` krachtens `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` naar een hogere waarde (een waarde die groter is dan het aantal aanwezige elementen, bijvoorbeeld 200.000) en vervolgens opnieuw te implementeren.

   - Gebruik de instructies in de *Configuratieoverschrijvingen* in Installeer en configureer as a Cloud Service Adobe Experience Manager-hulplijnen om het configuratiebestand te maken.
   - In het configuratiedossier, verstrek de volgende (bezit) details om de queryLimitReads optie te vormen:

     | PID | Eigenschappensleutel | Waarde van eigenschap |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Waarde: 200000 Standaardwaarde: 100000 |

1. Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>//bin/guides/reports/upgrade`.

1. De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Zodra de baan wordt voltooid, antwoordt het vorige verzoek van de GET met succes. Als de taak om een of andere reden mislukt, kan de fout worden gezien in serverlogboeken.

1. Terugkeren naar de standaardwaarde of vorige bestaande waarde van `queryLimitReads` als u dit in stap 1 hebt gewijzigd.

## Stappen om de bestaande inhoud te indexeren om de nieuwe zoek- en vervangings- en onderwerpenlijst onder het tabblad Rapporten te gebruiken:

(Alleen als u een versie hebt die ouder is dan de versie van juni 2023 van AEM hulplijnen as a Cloud Service)

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe vondst en vervangt tekst op kaartniveau en onderwerpenlijst onder het rapportlusje te gebruiken:

1. Een verzoek van een POST uitvoeren op de server \(met correcte verificatie\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optioneel: u kunt specifieke paden van de kaarten doorgeven om deze te indexeren. Standaard worden alle kaarten geïndexeerd \|\| Bijvoorbeeld: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. U kunt ook een hoofdmap doorgeven om de DITA-kaarten van een specifieke map (en de bijbehorende submappen) te indexeren. Bijvoorbeeld: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Wanneer zowel de parameter paths als de hoofdparameter worden doorgegeven, wordt alleen de parameter paths gebruikt.

1. De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Zodra de baan wordt voltooid, antwoordt het vorige verzoek van de GET met succes en vermeld als om het even welke kaarten ontbrak. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

## Compatibiliteitsmatrix

Deze sectie bevat een overzicht van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM in de release van oktober 2023 as a Cloud Service hulplijnen.

### FrameMaker en FrameMaker Publishing Server

| Hulplijnen AEM als Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023 10,0 | Niet compatibel | 2022 of hoger |
| | | |


### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023 10,0 | 3.2-uuid 5 | 3.2-uuid 5 | 2,3 | 2,3 |
|  |  |  |  |


### Versie van basissjabloon

| Naam van componentenpakket | Versie van componenten | Sjabloonversie |
|---|---|---|
| Inhoudspakket voor componenten van hulplijnen AEM voor Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

### Authoring

- De uren van de middag worden niet geplaatst in **Datum** voor de vaststelling van basislijnen. 12712
- Kan de JSON-code niet plakken in het dialoogvenster `<codeblock>` -element van de webeditor. 12326
- Niet-opgeslagen versiewijzigingen en de indicatoren daarvoor worden niet weergegeven voor grote bestanden. (11784)
- Tijdens het bewerken in de Koreaanse taal verandert het eerste teken in de standaardwaarde. 10049


### Publiceren

- Native PDF | De volgorde van de onderwerpen is niet vast wanneer de PDF-uitvoer wordt gegenereerd. 13157
- Native PDF| Geen standaardstijltag beschikbaar voor `<p>`element. (12559)
- Native PDF | Inline stijlen die worden toegepast op het inhoudsgebied, worden niet toegepast op de onderwerpen voor- en achtermaterie. 13510
- De `DeliveryTarget` attribuut wordt niet verspreid bij het produceren van de output van de Plaats van de AEM.  13132
- De **Publiceren** De workflow blijft vastzitten tijdens het genereren van AEM Site-uitvoer voor inhoud met bepaalde fouten. 12000

### Beheer

- Versiehistorie wordt niet weergegeven, zelfs niet als de `dc:format` eigenschap is niet aanwezig voor een element. 10463


### Controleren

- In de revisie over een onderwerp worden onjuiste opmerkingen weergegeven. 13453



### Vertaling

- De basislijn die uit de **Vertaling** Het dashboard mislukt en wordt niet geopend in de doeltaal. (13466)

- Er worden nieuwe vertaalprojecten gemaakt in plaats van nieuwe banen toe te voegen aan de geselecteerde bestaande vertaalprojecten.  10214

## Bekend probleem

Adobe heeft de volgende bekende kwestie voor de release van oktober 2023 geïdentificeerd.

- Opnieuw publiceren van inhoudsfragment mislukt.
