---
title: Opmerkingen bij de release | Upgrade-instructies en opgeloste problemen in Adobe Experience Manager-hulplijnen, release november 2023
description: Leer over de insectenmoeilijke situaties en hoe te aan de versie van November 2023 van as a Cloud Service Gidsen van Adobe Experience Manager te bevorderen
exl-id: 80839890-075f-4187-a167-444c73215496
source-git-commit: e8a912b0f8bc690fceade0b54bb36057a727ab33
workflow-type: tm+mt
source-wordcount: '1640'
ht-degree: 2%

---

# Release van Adobe Experience Manager Guides in november 2023 as a Cloud Service

In deze releaseopmerking worden de instructies voor de upgrade, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie november 2023 van de as a Cloud Service Adobe Experience Manager-hulplijnen (later genoemd als *Experience Manager-hulplijnen as a Cloud Service*).

Voor meer informatie over de nieuwe eigenschappen en de verhogingen, mening [Nieuwe functies in de release van november 2023 met as a Cloud Service hulplijnen voor Experience Managers](whats-new-2023.11.0.md).

## Upgrade naar release november 2023

Voer de volgende stappen uit om de huidige as a Cloud Service installatie van de hulplijnen voor Experience Managers bij te werken:

1. Controle uit de code van Git van Cloud Servicen en schakelaar aan de tak die in de pijpleiding van Cloud Servicen wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van uw Cloud Servicen Git-code naar 2023.11.0.406.
3. Leg de veranderingen vast en stel de pijpleiding van Cloud Servicen in werking om aan de as a Cloud Service versie van de Gidsen van de Experience Manager van november 2023 te bevorderen.

## Stappen om de trigger van een script via een servlet in te schakelen

(Alleen als u een versie hebt die ouder is dan de versie van juni 2023 van de hulplijnen voor Experience Managers as a Cloud Service)

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

In de vorige reactie van JSON was de sleutel `lockNodePath` bevat het pad naar het knooppunt dat in de opslagplaats is gemaakt en dat naar de ingediende taak verwijst. Het wordt automatisch verwijderd als de taak is voltooid. U kunt dan naar dit knooppunt verwijzen voor de status van de taak.

Wacht tot deze taak is voltooid voordat u verdergaat met de volgende stappen.

>[!NOTE]
>
> Controleer of het knooppunt nog aanwezig is en wat de status van de taak is.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Stappen om de bestaande inhoud te posten om het verbroken koppelingsrapport te gebruiken

(Alleen als u een versie hebt die ouder is dan de versie van juni 2023 van de hulplijnen voor Experience Managers as a Cloud Service)

Voer de volgende stappen uit voor de nabewerking van de bestaande inhoud en het gebruik van het nieuwe verbroken koppelingsrapport:

1. (Optioneel) Als het systeem meer dan 100.000 DITA-bestanden bevat, werkt u de `queryLimitReads` en `queryLimitInMemory` krachtens `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` naar een hogere waarde (een waarde die groter is dan het aantal aanwezige elementen, bijvoorbeeld 200.000) en vervolgens opnieuw te implementeren.

   - Gebruik de instructies in de *Configuratieoverschrijvingen* in Installeer en configureer as a Cloud Service Adobe Experience Manager-hulplijnen om het configuratiebestand te maken.
   - In het configuratiedossier, verstrek de volgende (bezit) details om het `queryLimitReads` en `queryLimitInMemory` optie:

     | PID | Eigenschappensleutel | Waarde van eigenschap |
     |---|---|---|
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Waarde: 200000 Standaardwaarde: 100000 |
     | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitInMemory | Waarde: 200000 Standaardwaarde: 100000 |

1. Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>//bin/guides/reports/upgrade`.

1. De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Zodra de baan wordt voltooid, antwoordt het vorige verzoek van de GET met succes. Als de taak om een of andere reden mislukt, kan de fout worden gezien in serverlogboeken.

1. Terugkeren naar de standaardwaarde of vorige bestaande waarde van `queryLimitReads` als u dit in stap 1 hebt gewijzigd.

## Stappen om de bestaande inhoud te indexeren om de nieuwe zoek- en vervangings- en onderwerpenlijst onder het tabblad Rapporten te gebruiken:

(Alleen als u een versie hebt die ouder is dan de versie van juni 2023 van de hulplijnen voor Experience Managers as a Cloud Service)

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe vondst en vervangt tekst op kaartniveau en onderwerpenlijst onder het rapportlusje te gebruiken:

1. Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>/bin/guides/map-find/indexing`. (Optioneel) U kunt specifieke paden van de kaarten doorgeven om deze te indexeren. Standaard worden alle kaarten geïndexeerd || Bijvoorbeeld: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. U kunt ook een hoofdmap doorgeven om de DITA-kaarten van een specifieke map (en de bijbehorende submappen) te indexeren. Bijvoorbeeld, `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Wanneer zowel de parameter paths als de hoofdparameter worden doorgegeven, wordt alleen de parameter paths gebruikt.

1. De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`)


1. Zodra de baan wordt voltooid, antwoordt het vorige verzoek van de GET met succes en vermeld als om het even welke kaarten ontbrak. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

## Stappen om de `'fmdita rewriter'` conflict

Hulplijnen voor Experience Manager hebben een [**aangepaste herschrijffunctie voor verkoop**](../cs-install-guide/conf-output-generation.md#custom-rewriter) module voor het afhandelen van de koppelingen die worden gegenereerd in het geval van cross-maps (koppelingen tussen de onderwerpen van twee verschillende kaarten).

Als u een andere aangepaste schrijver voor de spelling in uw codebase hebt, gebruikt u een `'order'` waarde groter dan 50, aangezien de Experience Manager Gidsen herschrijver gebruikt `'order'` 50  Als u dit wilt overschrijven, hebt u een waarde > 50 nodig. Voor meer informatie, bekijkt u [Output Rewriting Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Tijdens deze upgrade, sinds de `'order'` waarde is gewijzigd van 1000 in 50, moet u de bestaande aangepaste rewriter, indien aanwezig, samenvoegen met `'fmdita-rewriter'`.


## Compatibiliteitsmatrix

Deze sectie maakt een lijst van de verenigbaarheidsmatrijs voor de softwaretoepassingen die door de Experience ManagerGidsen worden gesteund as a Cloud Service versie van November 2023.

### FrameMaker en FrameMaker Publishing Server

| Hulplijnen voor hulplijnen Experience Managers als een cloudrelease | FMPS | FrameMaker |
| --- | --- | --- |
| 2023.11.0 | Niet compatibel | 2022 of hoger |
| | | |


### Zuurstofaansluiting

| Hulplijnen Experience Managers als cloudrelease | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023.11.0 | 3.2-uuid 5 | 3.2-uuid 5 | 2.3 | 2.3 |
|  |  |  |  |


### Versie van basissjabloon

| Naam van componentenpakket | Versie van componenten | Sjabloonversie |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:



### Authoring

- Ruimte na conref `<ph>` het element verdwijnt bij het bewaren van het onderwerp. (13642)
- Toepassingsfout treedt op wanneer u probeert DITA-bestanden op te slaan voordat de naverwerking is voltooid. (13571)
- Als de titel van een onderwerp een slash bevat `/`Op het tabblad in de editor worden alleen de volgende letters weergegeven. (13455)
- De voorvertoning van de afbeelding verdwijnt niet nadat de voorvertoning in de Editor is weergegeven. (13454)
- Het sleutelwoord van het Tussenvoegsel pop-up verschijnt niet wanneer het gebruiken van wortel kaart-bepaalde sleutels in andere onderwerpen. (12950)
- Pictogrammen sluiten is niet zichtbaar wanneer een voorvertoning wordt weergegeven van zeer grote afbeeldingen in het deelvenster Versiehistorie. (12867)
- Kan de tijdzone van niet wijzigen **Versie gemaakt op** kolom voor de basislijnen. (12711)
- De **Versiehistorie** in de interface Middelen een onjuist tijdstempel voor de **Huidig** veld. (12624)
- Als u een DITA-bestand maakt op basis van een sjabloon met een bestandsnaam die begint met numerieke tekens, treedt er een naamruimtefout op. (12188)
- In de webeditor **Belangrijke verwijzingen** wordt geopend wanneer het venster wordt ingevoegd `varname` -tag. (10940)
- Zip-bestanden worden niet herkend in de webeditor en u kunt ze niet slepen en neerzetten. (12709)
- De inhoud waarop bepaalde kenmerken zijn toegepast, wordt niet gemarkeerd in de modus Auteur of Voorvertoning. (11063)
- Wanneer u een onderwerp sluit nadat u het hebt bewerkt, wordt u omgeleid naar de AEM startpagina in plaats van terug te keren naar de mappenweergave. (13306)
- De verwerking van bestanden die naar de cloudservices zijn gekopieerd en geplakt, verloopt traag. (12457)
- De rootmap-instelling blijft bestaan in de webeditor, zelfs als de gebruiker deze niet expliciet heeft ingesteld in de gebruikersvoorkeuren. (11551)


### Publiceren

- Publiceren als functie voor inhoudsfragmenten werkt niet voor bestanden die in zoekresultaten worden vermeld. (14090)
- In Native PDF-publicaties vereist de achtergrondkleur die u in de sjabloonlay-out selecteert, dat de pagina opnieuw wordt geladen wanneer u terugkeert naar `None`. (13621)
- Probleem bij het vastleggen van datastore voor een grote DITA-kaart met &#39;scope peer&#39;-koppelingen in AEM publicatie van de site. (13530)
- In het publiceren van de Eigen PDF, wordt de toegankelijkheid gecompromitteerd aangezien de beelden in kopbal en footer alt geen tekst tonen. (12829)
- Het dupliceren van de paginalay-out in de native PDF werkt niet zonder automatische toevoeging. (12534)
- Wanneer u de PDF-uitvoer genereert met Native PDF-publicatie, wordt de bestandsnaam na een punt afgekapt. (13620)
- Onjuist pictogram en knopinfo worden weergegeven voor  **Inhoud bewerken** in de werkbalk Pagina-indelingen van de sjablonen die worden gebruikt in de publicatie Native PDF. (13492)
- Aangepaste metagegevens zijn niet beschikbaar in de uiteindelijke uitvoer. (12116)
- fmdita rewriter veroorzaakt een conflict met de rewriter-config van de gebruiker en leidt tot de weergave van lange URL&#39;s in plaats van de koppelingen. (12076)
- In de voorinstelling AEM site kunt u **Afzonderlijke PDF genereren voor elk onderwerp** is niet functioneel. (11555)
- Native PDF-publicaties bieden geen ondersteuning voor het omzetten van CMYK-kleurruimten. (10754)
- Dynamische basislijnaanroepen gebruiken de naam in plaats van de titel, wat resulteert in een fout van de DITA-kaart-API exporteren. (14268)

### Beheer

- De verwijzing van de inhoud wordt gebroken op kopiëren-kleeft de DITA- dossiers die zelfverwijzingsverbindingen zonder GUID hebben. (13540)
- In de Redacteur van het Web, toont de basislijn de titel voor de vorige versie in plaats van de geselecteerde versie van het DITA- dossier. (13444)
- De **Rapporten** het lusje in de Redacteur UI van het Web er niet in slaagt om de onderwerpenlijst voor oude kaarten te tonen DITA die vóór de verbetering van Juli 2023 van as a Cloud Service Gidsen van de Experience Manager worden gecreeerd. (11852)
- Voorinstellingen voor voorwaarden voor grote DITA-kaarten worden niet gemaakt. (10936)
- Er wordt een koppeling met een zelfverwijzing weergegeven onder de lijst Verbroken koppelingen in Rapporten. (13539)

### Controleren

- De zij aan zij overzichtspanelen van vorige en de huidige versies in de Redacteur van het Web zijn niet correct in de as a Cloud Service versie van de Gidsen van de Experience Manager van oktober 2023. (14156)
- Aanpassing e-mailsjabloon voor **Controleren** workflow werkt niet met het bedekken van knooppunten. (13954)
- De **Sluiten** op de pagina Reviseren in de hulplijnen voor Experience Managers gaan de gebruikers naar de AEM Homepage. (13535)
- Verbroken tekens worden weergegeven tijdens het maken van de fragmenten in de Koreaanse taal. (13489)
- Op Koreaanse bijlagen kan niet worden geklikt in het scherm Experience Manager Guides Review. (13436)
- De kaarthandleiding wordt afgesneden in het overzichts- en samenwerkingsscherm, zonder optie om de volledige titel te bekijken. (13012)

### Vertaling

- Automatisch goedkeuren werkt soms niet, en de uitzonderingen komen voor als een onjuiste waarde wordt geplaatst **Vertaalstatus**. (13607)
- De basislijn die u exporteert vanaf het dashboard Vertalen mislukt en wordt niet geopend in de doeltaal. (12993)

## Bekend probleem

Adobe heeft het volgende bekende probleem voor de release van november 2023 geïdentificeerd.

- Selectieve onderwerpregeneratie voor AEM output van de Plaats ontbreekt.
