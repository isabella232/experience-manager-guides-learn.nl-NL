---
title: Opmerkingen bij de release | Upgrade-instructies en opgeloste problemen in Adobe Experience Manager-hulplijnen, release van juni 2023
description: Meer informatie over de opgeloste problemen en hoe u een upgrade uitvoert naar de as a Cloud Service release van Adobe Experience Manager Guides in juni 2023
exl-id: ea0ff27a-9c3a-49d7-b94a-d1b9d9e85dcf
source-git-commit: 4359d857f3662ae29a55420c0fafc4a244258389
workflow-type: tm+mt
source-wordcount: '1143'
ht-degree: 2%

---

# Release van Adobe Experience Manager Guides in juni 2023 as a Cloud Service

In deze releaseopmerking worden de instructies voor het bijwerken, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie juni 2023 van de Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*).

Zie voor meer informatie over de nieuwe functies en verbeteringen [Nieuwe functies in juni 2023: AEM hulplijnen as a Cloud Service](whats-new-2023.6.0.md).

## Upgrade naar juni 2023

Voer de volgende stappen uit om de huidige installatie van de AEM hulplijnen te upgraden:

1. Controle uit de Cloud Services Gespitscode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2023.6.297.
3. Leg de wijzigingen vast en voer de pijpleiding Cloud Services uit om te upgraden naar de release van juni 2023 van AEM as a Cloud Service hulplijnen.

## Stappen om de trigger van een script via een servlet in te schakelen

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

(Alleen als u een versie hebt die ouder is dan juni 2023, release van AEM hulplijnen as a Cloud Service)

Voer de volgende stappen uit voor de naverwerking van de bestaande inhoud en het gebruik van het nieuwe verbroken koppelingsrapport:

1. (Optioneel) Als het systeem meer dan 100.000 dita-bestanden bevat, werkt u de `queryLimitReads` krachtens `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` naar een hogere waarde (een waarde die groter is dan het aantal aanwezige elementen, bijvoorbeeld 200.000) en vervolgens opnieuw te implementeren.

   - Gebruik de instructies die worden gegeven in *Configuratieoverschrijvingen* in Installeer en configureer as a Cloud Service Adobe Experience Manager-hulplijnen om het configuratiebestand te maken.
   - In het configuratiedossier, verstrek de volgende (bezit) details om de queryLimitReads optie te vormen:

     | PID | Eigenschappensleutel | Waarde van eigenschap |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Waarde: 200000 Standaardwaarde: 100000 |

1. Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>//bin/guides/reports/upgrade`.

1. De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Wanneer de taak is voltooid, reageert de vorige GET-aanvraag met succes. Als de taak om een of andere reden mislukt, kan de fout worden gezien in de serverlogboeken.

1. Terugkeren naar de standaardwaarde of vorige bestaande waarde van `queryLimitReads` als u dit in stap 1 hebt gewijzigd.

## Stappen om de bestaande inhoud te indexeren om de nieuwe zoek- en vervangings- en onderwerpenlijst onder het tabblad Rapporten te gebruiken:

(Alleen als u een versie hebt die ouder is dan september 2022 en als u AEM hulplijnen hebt as a Cloud Service)

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe vondst en vervangt tekst op kaartniveau en onderwerpenlijst onder het rapportlusje te gebruiken:

1. Een verzoek van een POST uitvoeren op de server \(met correcte verificatie\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optioneel: u kunt specifieke paden van de kaarten doorgeven om deze te indexeren. Standaard worden alle kaarten geïndexeerd \|\| Bijvoorbeeld: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. U kunt ook een hoofdmap doorgeven om de DITA-kaarten van een specifieke map (en de bijbehorende submappen) te indexeren. Bijvoorbeeld, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Wanneer zowel de parameter paths als de hoofdparameter worden doorgegeven, wordt alleen de parameter paths gebruikt.

1. De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1. Wanneer de taak is voltooid, reageert het vorige verzoek van de GET met succes en wordt vermeld of kaarten zijn mislukt. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM in de release van juni 2023 as a Cloud Service hulplijnen.

### FrameMaker en FrameMaker Publishing Server

| Hulplijnen AEM als Cloud Release | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | Niet compatibel | 2022 of hoger |
| | | |


### Zuurstofaansluiting

| Hulplijnen AEM als Cloud Release | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.06.0 | 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 |
|  |  |  |  |


## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

### Authoring

- Navtitle wordt verwijderd uit content33 bij het schakelen van de layoutweergave naar de auteur- of bronweergave. (12174)
- Soms treedt een toepassingsfout op bij het klikken op een DITA-kaart. (11842)
- Webeditor | Vaste spatie wordt toegevoegd in de Redacteur van XML terwijl het uitgeven van een onderwerp. (11786)
- Elementinterface | In de lijstweergave kunnen de overbelaste beschikbare kolommen niet worden samengevoegd. (11528)
- Keyref wordt niet opgelost in de kaartweergave. (11490)
- Het bovenste menu wordt niet weergegeven wanneer u door de XML-editor navigeert. (10868)
- `conref` in tag ph | Het weergegeven dialoogvenster Bladeren is onjuist. (9481)
- Lokale koppelingen naar andere elementen worden niet opgelost in de webeditor. (8790)
- De functie Matches() werkt niet in de functie schema. (11224)


### Beheer

- Het lusje van rapporten in de Redacteur UI van het Web toont niet de onderwerpenlijst van oude kaarten DITA die vóór 4.2 verbetering worden gecreeerd. (11708)

- De functionaliteit van de knop Bestanden uploaden in het interface-einde voor middelen in versie 4.2. (11633)

### Publiceren

- Publiceren naar AEM site mislukt bij het lezen van tijdelijke bestanden uit pod die mogelijk zijn vernieuwd of opnieuw zijn gestart. (12113)
- Native PDF | Het publiceren van inhoud die een outputklasse met steunen () heeft leidt tot een het publiceren bevriezing. (11936)
- JSON-uitvoer | Metagegevens met kenmerk eigenschap als `"value in spaces and double quotes"` leidt tot een publicatiefout. (11933)
- Webeditor | Uitvoerpad en sjabloon kunnen niet worden geselecteerd in de AEM Voorinstelling. (11530)
- Native PDF | Aangepaste kenmerken worden niet doorgegeven aan tijdelijke HTML- of PDF-engine. (DXML-12005)
- Native PDF | Java OutOfMemoryError treedt op bij het publiceren van grote inhoud. (11789)
- JSON-uitvoer | De `fmUuid` eigenschap op het JCr:content-knooppunt van JSON verschilt van de &quot;id&quot; in de JSON. (11564)
- JSON-uitvoer | Als de kaart en het onderwerp met dezelfde bestandsnaam aanwezig zijn, wordt JSON voor de kaart verwijderd. (11524)
- Native PDF | Xref drukt de inhoud van href onderwerptitel in plaats van het etiket Xref. (11322)
- Native PDF | De sjablooninstellingen voor PDF kunnen niet worden opgeslagen. (10751)
- Native PDF | De tekst breidt zich voorbij de kolombreedte uit bij het opnemen van meerdere voorkeuren. (10876)
- Native PDF | `<note>``</note>` element genereert geen extra bereiktitel van het type. (10549)
- Native PDF | De metagegevens voor de taal kunnen niet in de gegenereerde PDF worden ingesteld om te voldoen aan WCAG 2.0. (12296)



### Vertaling

- Na de cloudrelease van februari (2302) wordt alle vertaalinhoud weergegeven als Niet-gesynchroniseerd of Ontbrekend exemplaar. (11834)

### Controleren

- Nieuwe revisie-interface | De voorwaarden benadrukken, en tonen verberg werk anders dan hoe zij in de Redacteur van het Web werken. (11628)
