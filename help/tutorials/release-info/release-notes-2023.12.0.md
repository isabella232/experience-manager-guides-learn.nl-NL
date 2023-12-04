---
title: Opmerkingen bij de release | Upgrade-instructies en vaste problemen in Adobe Experience Manager-hulplijnen, release december 2023
description: Leer over de insectenmoeilijke situaties en hoe te aan de versie van December 2023 as a Cloud Service van de Gidsen van Adobe Experience Manager te bevorderen.
source-git-commit: b4bbed1de8fc2d8ef81332445a5c96161be508d4
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 0%

---

# Release van Adobe Experience Manager Guides in december 2023 as a Cloud Service

In deze releaseopmerking worden de instructies voor het bijwerken, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie december 2023 van de as a Cloud Service Adobe Experience Manager-hulplijnen (later aangeduid als *Experience Manager-hulplijnen as a Cloud Service*).

Voor meer informatie over de nieuwe eigenschappen en de verhogingen, mening [Nieuwe functies in de release van december 2023 Experience Manager Guides as a Cloud Service](whats-new-2023.12.0.md).

## Upgrade naar release december 2023

Voer de volgende stappen uit om de huidige as a Cloud Service installatie van de hulplijnen voor Experience Managers bij te werken:

1. Controle uit de code van Git van Cloud Servicen en schakelaar aan de tak die in de pijpleiding van Cloud Servicen wordt gevormd die aan het milieu beantwoordt dat u wilt bevorderen.
2. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van uw Cloud Servicen Git-code naar 2023.12.0.16.
3. Leg de wijzigingen vast en voer de pijplijn met Cloud Servicen uit om naar de release van december 2023 van as a Cloud Service hulplijnen voor Experience Manager te upgraden.

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

In de vorige reactie van JSON was de sleutel `lockNodePath` bevat het pad naar het knooppunt dat in de opslagplaats is gemaakt en dat naar de ingediende taak verwijst. Het wordt automatisch verwijderd als de taak is voltooid en u kunt naar dit knooppunt verwijzen voor de status van de taak.

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

1. Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server>//bin/guides/reports/upgrade`.

1. De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(Bijvoorbeeld: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Zodra de baan wordt voltooid, antwoordt het vorige verzoek van de GET met succes. Als de taak om een of andere reden mislukt, kan de fout worden gezien in serverlogboeken.

1. Terugkeren naar de standaardwaarde of vorige bestaande waarde van `queryLimitReads` als u dit in stap 1 hebt gewijzigd.

## Stappen om de bestaande inhoud te indexeren om de nieuwe zoek- en vervangings- en onderwerpenlijst onder het tabblad Rapporten te gebruiken:

(Alleen als u een versie hebt die ouder is dan de versie van juni 2023 van de hulplijnen voor Experience Managers as a Cloud Service)

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe vondst en vervangt tekst op kaartniveau en onderwerpenlijst onder het rapportlusje te gebruiken:

1. Voer een verzoek van de POST op de server uit (met correcte authentificatie) - `http://<server:port>/bin/guides/map-find/indexing`. (Optioneel: u kunt specifieke paden van de kaarten doorgeven om deze te indexeren. Standaard worden alle kaarten geïndexeerd|| Bijvoorbeeld: `https://<Server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>`)

1. U kunt ook een hoofdmap doorgeven om de DITA-kaarten van een specifieke map (en de bijbehorende submappen) te indexeren. Bijvoorbeeld: `http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test`. Wanneer zowel de parameter paths als de hoofdparameter worden doorgegeven, wordt alleen de parameter paths gebruikt.

1. De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)


1. Zodra de baan wordt voltooid, antwoordt het vorige verzoek van de GET met succes en vermeld als om het even welke kaarten ontbrak. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

## Stappen om de `'fmdita rewriter'` conflict

Hulplijnen voor Experience Manager hebben een [**aangepaste herschrijffunctie voor verkoop**](../cs-install-guide/conf-output-generation.md#custom-rewriter) module voor het afhandelen van de koppelingen die worden gegenereerd in het geval van cross-maps (koppelingen tussen de onderwerpen van twee verschillende kaarten).

Als u een andere aangepaste schrijver voor de spelling in uw codebase hebt, gebruikt u een `'order'` waarde groter dan 50, aangezien de Experience Manager Gidsen herschrijver gebruikt `'order'` 50  Als u dit wilt overschrijven, hebt u een waarde > 50 nodig. Voor meer informatie, bekijkt u [Output Rewriting Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

Tijdens deze upgrade, sinds de `'order'` waarde is gewijzigd van 1000 in 50, moet u de bestaande aangepaste rewriter, indien aanwezig, samenvoegen met `'fmdita-rewriter'`.


## Compatibiliteitsmatrix

Deze sectie maakt een lijst van de verenigbaarheidsmatrijs voor de softwaretoepassingen die door de Experience ManagerGidsen worden gesteund as a Cloud Service versie van december 2023.

### FrameMaker en FrameMaker Publishing Server

| Hulplijnen Experience Managers als cloudrelease | FMPS | FrameMaker |
| --- | --- | --- |
| 2023 12,0 | Niet compatibel | 2022 of hoger |
| | | |


### Zuurstofaansluiting

| Hulplijnen Experience Managers als cloudrelease | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2023 12,0 | 3.3-uuid.5 | 3.3-uuid.5 | 2,3 | 2,3 |
|  |  |  |  |


### Versie van basissjabloon

| Naam van componentenpakket | Versie van componenten | Sjabloonversie |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:



### Authoring

- De **Titel** in het tabblad Webeditor wordt afgekapt na een punt (.) teken. 14372
- Foutberichten voor dubbele kaartnamen in de interface Elementen worden niet bijgewerkt. 14320
- Er treedt een fout op in de logica voor het maken van versies tijdens het slepen en neerzetten van elementen. 14291
- Herbruikbare inhoud slaat de element-id&#39;s over. 14213
- Het instellingsbesturingselement voor verbergen **Taalvariabelen** paneel onder **Uitvoer** ontbreekt. (14194)
- De Redacteur van het Web werpt toepassingsfouten wanneer het toevoegen van een nieuwe verwijzing of een onderwerp gebruikend een gespecialiseerd schema in de mening van de Lay-out. (14094)
- Een ankerkoppeling naar `<dlentry>` of `<dt>` -element kan de koppelingstekst niet weergeven. 13543
- De **Favorieten** verzameling in de webeditor kan niet worden geladen. 13495
- Bij het maken van een unieke id met spaties worden niet-klikbare koppelingen weergegeven. (13447)
- In de **Layout** weergave voor een bladmap, gebruiken **Naar rechts** om een geselecteerd hoofdstuk te maken werkt een subelement niet. 12567
- Het voorvertoningsvenster van de XML-editor wordt afgebroken in Google Chrome- en Microsoft Edge-browsers. 10755
- In de webeditor is het niet mogelijk een element binnen de mogelijke bovenliggende elementen te plaatsen. 8791

### Publiceren

- Fmdita-componenten hebben een hardcoded pad van `delegator.jsp`te voorkomen, de bedekking van AEM Sites-componenten te voorkomen. (13993)
- De getagde weergave van de PDF-reactor in Native PDF-publicatie-uitvoer werkt niet zoals u had verwacht. (13622)
- AEM het publiceren van de Plaats ontmoet een kwestie wanneer het begaan aan aan de datastore voor grote kaarten met werkingsgebied peer verbindingen. 13531
- Kan een site niet activeren met het dashboard voor publicatie van Experience Manager Guides Bulk. 13439
- De lokalisatie van de elementlabels werkt niet goed in de AEM Sites-uitvoer. (12144)
- Ontbreekt **ditaval** in uitvoervoorinstellingen op het niveau van het mapprofiel die zijn gemaakt via de gebruikersinterface van de webeditor. (1903)

### Beheer

- AEM cloudomgevingen hebben een MongoWrite-uitzondering vanwege grote knooppunten. 13509

### Vertaling

- De **Accepteren/afwijzen** De knoppen worden abusievelijk weergegeven voor automatisch goedgekeurde menselijke vertaling. (14318)
- Problemen met internationalisatie (i18n) treden op tijdens de transformatie van DITA-bestanden die niet in het Engels staan, naar AEM pagina&#39;s. 14286
- De vertaalde inhoud synchroniseert niet van tijdelijke vertaalprojecten, en de redacteurs vertaaltovenaar van DITA XML toont verkeerd **In uitvoering** status voor goedgekeurde banen. (9938)

### Toegankelijkheid

- Kan niet door de gebruikersinterface van het auteurcanvas navigeren, aangezien de nadruk gevangen in de onderwerpredacteur wordt. 13517

## Bekend probleem

Adobe heeft voor de release van december 2023 het volgende bekende probleem geïdentificeerd:
- &quot;Ongeldige DTD-fout opvragen&quot; treedt soms op bij de upgrade naar de release van december 2023.
