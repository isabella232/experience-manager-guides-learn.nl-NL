---
title: Niet-UUID-inhoud met versies omzetten in UUID-inhoud
description: Leer hoe u niet-UUID-inhoud migreert met versies.
source-git-commit: 33cdc1b14db0d123c01bbc719c2833ce0df4c9d9
workflow-type: tm+mt
source-wordcount: '1272'
ht-degree: 0%

---




# Niet-UUID-inhoud migreren met versies

Voer de volgende stappen uit om uw niet-UUID-inhoud met versies te migreren naar UUID-inhoud.

## Compatibiliteitsmatrix

| Huidige versie van AEM (niet-UUID) | Vereiste versie voor migratie naar UUID | Ondersteund upgradepad |
|---|---|---|
| 3.8.5 | 4.0 niet-UUID | 4.1 (UUID) installeren en de migratie uitvoeren |
| 4.0, 4.0.x, 4.1 of 4.1.x | Hetzelfde als huidige niet-UUID | 4.1 (UUID) installeren en de migratie uitvoeren |
| 4.2 of hoger | NA | Nog niet ondersteund |

## Vereiste pakketten

1. **Versieverwijdering**: `com.adobe.guides.version-purge-1.0.11.zip` (optioneel)
1. **Pre-migratie**: `com.adobe.guides.pre-uuid-migration-1.0.7.zip`
1. **Migratie**: `com.adobe.guides.uuid-upgrade-1.0.17`
1. **Na migratie**: `com.adobe.guides.post-uuid-migration-1.0.2.zip`


## Pre-migratie

1. (Optioneel) Voer versiebeheer uit op de inhoud om overbodige versies te verwijderen en het migratieproces te versnellen. Installeer het pakket om versiebeheer uit te voeren op versie 4.1 (NIET ondersteund op 4.0) `com.adobe.guides.version-purge-1.0.11.zip`en ga naar de gebruikersinterface met deze URL `http://<server-name> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`.

   >[!NOTE]
   >
   >Dit hulpprogramma verwijdert geen versies die in basislijnen of revisies worden gebruikt of heeft labels.
1. Het pre-migratiepakket installeren (`com.adobe.guides.pre-uuid-migration-1.0.7.zip`).

1. Voer de volgende onderstaande query uit om een rapport te krijgen met een geschatte tijd (ETA) van hoe lang de migratie zal duren en het rapporteert als er bestanden zijn met inhoudsproblemen die niet zouden migreren.

>[!NOTE]
>
>U hebt beheerdersmachtigingen nodig om de migratie uit te voeren.


| URL van eindpunt | Type aanvraag | Query-parameter | Verwachte resultaten |
|---|---|---|---|
| `/bin/guides/pre_uuid_upgrade` <br> <br>**Bijvoorbeeld**: http://localhost:4502/bin/guides/pre_uuid_upgrade?root=/content/dam | GET | **basis**: hoofdmap<br> **Waarde**: `/content/dam` voor de gehele gegevensopslagruimte. | Er wordt een pre-migratierapport (.csv) gemaakt met daarin het aantal bestanden, de totale versies en de fouten. <br><br> **Voorbeelduitvoer**:<br>Hoofdmap: /content/dam <br>Totaal aantal bestanden: 2697 <br>Totaal aantal versies: 10380 <br>Aantal bestanden met fouten: 28 <br>Een gedetailleerd rapport is beschikbaar via AEM CRX op `/content/uuid-pgrade/UuidMigrationReport_1688400131039.csv` |

Deze stap zou kunnen ontbreken als er vele DITA dossiers in het systeem zijn. Om dit te richten, verhoog de grens van het aantal dossiers die in de vraag door de waarde te verhogen van *Leeslimiet geheugen (queryLimitReads)* in Apache Jackrabbit Query Engine Settings Service vanaf 100000 een getal dat groter is dan het totale aantal DITA-elementen in het systeem.

## Migratie

### Stap 1: Configuratie bijwerken

1. Zorg ervoor dat de beschikbare vrije ruimte ten minste tien keer zo groot is als AEM (crx-quickstart-map) tijdens de migratie. Wanneer u de migratie hebt voltooid, kunt u het grootste deel van de schijfruimte vrijmaken door een compactie uit te voeren (raadpleeg [Revisie opschonen](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Inschakelen *Launchers voor naverwerking inschakelen* in `com.adobe.fmdita.config.ConfigManager` en *Version Postprocessing inschakelen* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Installeer de UUID-versie van de ondersteunde versie op de niet-UUID-versie. Als u bijvoorbeeld een 4.0-build zonder UUID of een 4.1-build zonder UUID gebruikt, moet u UUID-versie 4.1 installeren.

1. Installeer het nieuwe pakket voor uuid-migratie (`com.adobe.guides.uuid-upgrade-1.0.17`).

1. De volgende workflows uitschakelen en eventuele andere workflows uitschakelen die worden uitgevoerd `/content/dam` draagraketten gebruiken in `http://localhost:4502/libs/cq/workflow/content/console.html`.

   * Workflow voor DAM-update-middelen
   * DAM-workflow Metagegevens terugschrijven

1. Uitschakelen *Launchers voor naverwerking inschakelen* in `com.adobe.fmdita.config.ConfigManager` en uitschakelen *Version Postprocessing inschakelen* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`.

1. De eigenschap Validatie inschakelen uitschakelen (`validation.enabled`) in Day CQ Tagging Service.

1. Zorg ervoor dat `uuid.regex` eigenschapmap is ingesteld in `com.adobe.fmdita.config.ConfigManager`. Als deze leeg is, stelt u de standaardwaarde in - `^GUID-(?<id>.*)`.
1. Een afzonderlijk logger toevoegen voor `com.adobe.fmdita.uuid.upgrade.UuidUpgrade` De browserreactie is ook beschikbaar op `/content/uuid-upgrade/logs`.

### Stap 2: Voer het script uit en valideer

Voer de opgegeven query uit op een map met kleinere gegevens voordat deze wordt uitgevoerd `/content/dam`.

>[!TIP]
>
>U kunt controleren of alle bestanden in de map correct zijn bijgewerkt en of alle functies alleen voor die map werken.

| URL van eindpunt | Type aanvraag | Query-parameter | Verwachte resultaten |
|---|---|---|---|
| `/bin/guides/uuid_upgrade`<br><br> **Bijvoorbeeld**: `http://localhost:4502/bin/guides/uuid_upgrade?root=/content/dam/test` | GET | **basis**: hoofdmap <br>**Waarde**: /content/dam voor de gehele opslagplaats.<br><br>**ignoreImageVersions**<br> **Waarde**: true/false (hiermee wordt de verwerking van afbeeldingsversies genegeerd). De standaardwaarde is false) | Migratierapport met lijst met bestanden die met succes zijn gemigreerd, waarvan de upgrade is mislukt, waarvoor fouten zijn opgetreden en de totale benodigde tijd is verstreken. <br><br> **Voorbeelduitvoer**: <br> [INFO] Lijst met bestanden is mislukt:0 <br>[INFO] Nee. van bestanden is bijgewerkt: 2241 <br>[INFO] Nee. van bestanden bijgewerkt met fouten: 28 <br>[INFO] Nee. van bestanden kon niet worden bijgewerkt: 0 <br> [INFO] Totale duur: 0:37:03,131 |

>[!NOTE]
>
> De migratie van de inhoud kan op een omslagniveau of volledig worden in werking gesteld `/content/dam` of in dezelfde map (migratie opnieuw uitvoeren).

Daarnaast is het belangrijk om ervoor te zorgen dat de migratie van inhoud ook wordt uitgevoerd voor alle media-elementen, zoals afbeeldingen en afbeeldingen die u in de DITA-inhoud hebt gebruikt.

#### Basislijnmigratie

Voer de query uit op de map die u al hebt gemigreerd om de basislijnen ervan te migreren.

| URL van eindpunt | Type aanvraag | Query-parameter | Verwachte resultaten |
|---|---|---|---|
| `/bin/guides/baseline_uuid_upgrade`<br><br> **Bijvoorbeeld**: ` http://localhost:4502/bin/guides/baseline_uuid_upgrade?root=/content/dam/test` | GET | **basis**: hoofdmap <br> **Waarde**: /content/dam voor de gehele opslagplaats. <br><br> **ignoreImageVersions**<br> **Waarde**: true/false <br>(Hiermee wordt de verwerking van afbeeldingsversies genegeerd. De standaardwaarde is false) <br><br> **doReviews** <br> **Waarde**: true/false <br> (Als revisies moeten worden bijgewerkt of niet. De standaardwaarde is false.) Migratierapport met lijst met bestanden die met succes zijn gemigreerd, waarvan de upgrade is mislukt, waarvoor fouten zijn opgetreden en de totale benodigde tijd is verstreken. <br> <br> **Voorbeelduitvoer**:<br>[INFO] Lijst met bestanden is mislukt <br> [INFO] Nee. van bestanden bijgewerkt naar 2241<br> [INFO] Nee. van bestanden bijgewerkt met fouten 28<br>[INFO] Nee. van bestanden is niet bijgewerkt op 0<br>[INFO] Totale duur: 0:37:03,131 |


### Stap 3: Herstel de configuratie

Nadat de server is gemigreerd, kunt u naverwerking, codering en de volgende workflows (inclusief alle andere workflows die aanvankelijk tijdens de migratie zijn uitgeschakeld) inschakelen om te blijven werken op de server.

* Workflow voor DAM-update-middelen
* DAM-metagegevensworkflow

>[!NOTE]
>
>Als sommige bestanden niet worden verwerkt of vóór de migratie zijn beschadigd, worden ze vóór de migratie beschadigd en blijven ze zelfs na de migratie beschadigd.

## Migratievalidatie

1. Installeer het post uuid migratiepakket (`com.adobe.guides.post-uuid-migration-1.0.2.zip`).

1. Voer de volgende query uit om te controleren of er geen fouten zijn opgetreden tijdens de migratie die ertoe hebben geleid dat koppelingen zijn verbroken. Met dit script wordt aangegeven of er koppelingen zijn die nog niet zijn verbroken, maar die nu om welke reden dan ook zijn verbroken.

   | URL van eindpunt | Type aanvraag | Query-parameter | Verwachte resultaten |
   |---|---|---|---|
   | `/bin/guides/get_broken_links` <br> <br> **Bijvoorbeeld**:<br>`http://localhost:4502/bin/guides/get_broken_links` | GET | NA | Migratierapport met het totale aantal bestanden dat UUID&#39;s en hun respectievelijke bestandspaden heeft verbroken. <br> <br> **Voorbeelduitvoer**:<br>[DEBUG] Controleren of al deze GUIDs in de inhoud wordt gebruikt.<br>[DEBUG] Totaal aantal bestanden met mogelijk verbroken UUID&#39;s: 0 <br>[DEBUG] Paden met mogelijk gebroken UUID&#39;s:0 |

1. Wanneer de migratie is voltooid, kan het grootste deel van de schijfruimte worden teruggewonnen door compactie uit te voeren (verwijs naar `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).

## Migratie van Delta-inhoud

1. Als u de delta-inhoud van de actieve server (niet-UUID) naar de huidige uuid-server wilt migreren, installeert u het script voor de migratie op de niet-UUID-server.

1. Voer de volgende query uit op de gehele gegevensset (of submap) om alle bestanden te identificeren en te exporteren die na de opgegeven tijdstempel zijn gewijzigd: de tijdstempel gebruikt de ISO8601-indeling voor datums en tijden ( YYYY-MM-DDTHH):mm:ss.SSSZ) en staat ook gedeeltelijke vertegenwoordiging, zoals JJJ-MM-DD toe.

   | URL van eindpunt | Type aanvraag | Query-parameter | Verwachte resultaten |
   |---|---|---|---|
   | `/bin/guides/data_export`<br><br>**Bijvoorbeeld**: <br> `http://localhost:4502/bin/guides/data_export?timestamp=2023-07-11&root=/content/dam` | GET | **tijdstempel** <br> **Waarde**: YYYY-MM-DD<br><br> **basis**: hoofdmap <br> **Waarde**: `/content/dam` voor de gehele gegevensopslagruimte. | Een ZIP-bestand met delta-inhoud wordt gemaakt op /var/dxml/exporting. <br> <br>**Monster**: data export_1689761491218.zip (bestand wordt gemaakt) |

1. Download het zip-bestand dat door het script is geëxporteerd. De laatste regel van de reactie moet het pad van het gegenereerde ZIP-bestand aangeven (opgeslagen in /var/dxml/exporting in het systeem).

1. Upload het ZIP-bestand naar de uuid-server op het gewenste pad in de interface Middelen.

1. Controleer of het pakket na de migratie op de uuid-server is geïnstalleerd.

1. Voer de volgende query uit om de delta-inhoud uit het geüploade ZIP-bestand in het systeem te importeren. De query moet het pad van het geüploade ZIP-bestand bevatten om de gegevens correct te kunnen identificeren en verwerken.

   | URL van eindpunt | Type aanvraag | Query-parameter | Verwachte resultaten |
   |---|---|---|---|
   | `/bin/guides/data_import`<br> **Bijvoorbeeld**:`http://localhost:4502/bin/guides/data_import?path=/content/dam/dataexport_1689344927551.zip&createVersion=true` | POST | **pad**<br> **Waarde**: `/content/dam/filename.zip`(Locatie geüpload bestand) **createVersion** <br> **Waarde**: true/false<br>(De standaardwaarde van createVersion is false). | Het bestand wordt geüpload naar het gewenste inhoudspad.<br><br>**Monster**: `dataexport_1689761491218.zip`<br><br> (Het bestand dat in de vorige stap is geëxporteerd, wordt geüpload naar het gewenste pad in `/content/dam`). |

1. Het script maakt een nieuw bestand als het niet bestaat of overschrijft het bestaande bestand als het is gewijzigd.

>[!NOTE]
>
> De versiegeschiedenis en andere wijzigingen die op de server zijn aangebracht (zoals workflows en revisies) moeten handmatig worden bijgewerkt.
