---
title: Versiebeheer
description: Meer informatie over het werken met versiebeheer
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1662'
ht-degree: 0%

---

# Versiebeheer {#id181GB000XY4}

Versioning is een belangrijk aspect van elk contentbeheersysteem. Hiermee kunt u een momentopname van uw digitale middel op een bepaald tijdstip maken. Met een versie van een digitaal middel kunt u de vereiste versie van het middel herstellen en bijwerken. Doorgaans kunt u voor het maken van een versie van een element het vereiste element uitchecken en inchecken.

Als beheerder kunt u regels afdwingen die gebruikers beperken om een bestand te bewerken zonder het uit te checken. Op dezelfde manier kunt u ervoor zorgen dat alle uitgecheckte bestanden worden ingecheckt om gegevensverlies te voorkomen.

In een omgeving voor meerdere toepassingen is het ook belangrijk ervoor te zorgen dat gebruikers geen bestanden van het systeem verwijderen. Deze vereiste is belangrijker voor bestanden die door andere gebruikers zijn uitgecheckt. U kunt toestaan of voorkomen dat gebruikers bestanden overschrijven die door andere gebruikers zijn uitgecheckt. Als u wilt voorkomen dat uitgecheckte bestanden per ongeluk door gebruikers worden verwijderd uit het systeem, biedt AEM hulplijnen een configuratie die u kunt gebruiken. Naast uitgecheckte bestanden kunt u ook het verwijderen van bestanden besturen die verwijzingen bevatten of waarnaar wordt verwezen vanuit andere bestanden. Bovendien kunt u ook een nieuwe versie voor het geüploade bestand maken.

## Nieuwe versie maken voor geüploade bestand

>[!NOTE]
>
> Deze configuratie is alleen van toepassing tijdens het uploaden van bestanden.

Voer de volgende stappen uit om een nieuwe versie van het geüploade bestand te maken:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. Selecteer de **Nieuwe versie maken voor geüpload bestand** -optie.

   Deze optie is standaard uitgeschakeld.

   Als de optie is geselecteerd, wordt er een nieuw versiebeheermechanisme toegepast dat het standaarduploadgedrag overschrijft dat voor elke volgende upload wordt gebruikt. Hierdoor wordt de inhoud van het geüploade bestand als een nieuwe versie opgeslagen. Als deze optie is uitgeschakeld, gebruikt AEM hulplijnen het AEM standaardmechanisme voor versiebeheer.

1. Klikken **Opslaan**.


>[!NOTE]
>
> U kunt bestanden in batches van 70 of minder uploaden als u de eigenschap inschakelt **Nieuwe versie maken voor geüpload bestand** \(create.ver.new.content\) en de opdracht **UI Middelen** uploadmiddelen in bulk.

## Instellingen configureren om het bewerken van uitgecheckte bestanden toe te staan

De redacteur van het Web van de Gidsen van de AEM staat u toe om onderwerpen te creëren en bij te werken DITA. U kunt de Redacteur van het Web vormen om het uitgeven van slechts die documenten toe te staan die uit de bewaarplaats zijn gecontroleerd. Dit zorgt ervoor dat geen andere schrijver per ongeluk een onderwerp overschrijft dat voor het uitgeven door een andere schrijver wordt geopend. Zodra een onderwerp voor het uitgeven wordt geopend, kan een auteur het dossier op het tijdstip van het sluiten van het dossier inchecken.

Een andere belangrijke regel is ervoor te zorgen dat de dossiers die zijn gecontroleerd terug in het systeem worden gecontroleerd. Zo voorkomt u dat gebruikers per ongeluk de bestanden sluiten zonder ze weer in te checken.

Voer de volgende stappen uit om deze functies in te schakelen:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundel.

1. Selecteer de **Bewerken uitschakelen zonder afhandeling** -optie.

   ![](assets/xml-editor-config.png){width="650" align="left"}

   Met deze optie zien gebruikers de optie Bewerken pas op de werkbalk nadat ze een bestand hebben uitgecheckt.

1. Selecteer de **Inchecken bij sluiten vragen** als u een waarschuwingsbericht wilt weergeven wanneer een uitgecheckt bestand wordt gesloten zonder het op te slaan of terug te checken in de opslagplaats.

1. Klikken **Opslaan**.


>[!NOTE]
>
> Ongeacht of u deze functie in- of uitschakelt, zijn de opties voor het uitchecken en inchecken van bestanden altijd beschikbaar in een voorvertoning van een onderwerp.

## Uitgecheckt bestand tijdens uploaden overschrijven

>[!NOTE]
>
> Deze configuratie is alleen van toepassing wanneer u bestanden maakt via de interface Middelen en niet wanneer u bestanden uploadt met het WebDAV-hulpprogramma.

Voer de volgende stappen uit om gebruikers toe te staan het uploadbestand te overschrijven dat door hen of een andere gebruiker is uitgecheckt:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. Selecteer de **Uitgecheckt bestand tijdens uploaden overschrijven** -optie.

   Deze optie is standaard ingeschakeld. Als deze optie is geselecteerd, kunnen gebruikers uitgecheckte bestanden overschrijven. Als de optie niet is geselecteerd, kan het bestand niet worden overschreven als het door de gebruiker of een andere gebruiker is uitgecheckt.

1. Klikken **Opslaan**.


## Verwijderen van uitgecheckte bestanden voorkomen

Voer de volgende stappen uit om te voorkomen dat gebruikers per ongeluk bestanden verwijderen die door hen of een andere gebruiker zijn uitgecheckt:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundel.

1. Selecteer de **Verwijderen van uitgecheckte inhoud voorkomen** -optie.

   Deze optie is standaard ingeschakeld. Als deze optie is geselecteerd, kunnen gebruikers uitgecheckte bestanden niet verwijderen.

1. Klikken **Opslaan**.


Ter ondersteuning van deze functie, een nieuwe index-eigenschap `drivelock` wordt toegevoegd in `oak:index`:

`/oak:index/damAssetLucene/indexRules/dam:Asset/properties/drivelock`

![](assets/index-property-oak-index-drivelock.png){width="800" align="left"}

Controleer, naast de nieuwe eigenschap index, of de volgende eigenschappen zijn ingesteld op `/oak:index/damAssetLucene`:

- `jcr:primaryType`=`"oak:QueryIndexDefinition"`
- `async`=`"async"`
- `compatVersion`=`"{Long}2"`
- `evaluatePathRestrictions`=`"{Boolean}true"`
- `reindex`=`"{Boolean}false"`
- `reindexCount`=`"{Long}3"` *\(Dit is het aantal keren dat opnieuw indexeren wordt uitgevoerd, wordt het vervangen door de installatie van ons pakket\)*
- `type`=`"lucene"`

>[!NOTE]
>
> U kunt de waarde wijzigen van `reindex` tot `"{Boolean}true"`. Hierdoor worden sneller zoekresultaten mogelijk voor de uitgecheckte bestanden in een hiërarchie met mappen.

## Verwijderen van bestanden waarnaar wordt verwezen voorkomen

Als beheerder kunt u bepalen wie bestanden uit de AEM kan verwijderen. Als een bestand verwijzingen bevat of door een ander bestand wordt genoemd, kunt u met name bepalen wie dergelijke bestanden kan verwijderen.

Met deze configuratie kunt u toestaan of weigeren dat alle gebruikers bestanden verwijderen of alleen een bepaalde gebruikersgroep bestanden laten verwijderen. Als het verwijderen van een bestand is toegestaan, wordt het volgende proces uitgevoerd:

- Als u een map verwijdert, die alle bestanden bevat waarnaar wordt verwezen en waarnaar wordt verwezen, worden alle bestanden verwijderd. Het proces verwijdert eerst alle bestanden die geen verwijzingen bevatten, gevolgd door de bestanden die verwijzingen bevatten of waarnaar wordt verwezen.

- Als u een map verwijdert en naar een bestand in de map wordt verwezen door een bestand buiten die map, wordt u gevraagd de verwijzing te verwijderen voordat u het bestand verwijdert.


Voer de volgende stappen uit om te bepalen wie een bestand met verwijzingen kan verwijderen of waarnaar door andere bestanden wordt verwezen:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. Zoek de **Blok verwijderen voor middelen waarnaar wordt verwezen** -optie.

1. Afhankelijk van wie u toegang voor verwijdering wilt geven, geeft u een van de volgende constanten op:

   - allow\_unsafe\_delete\_for\_all: geef alle gebruikers toestemming om bestanden te verwijderen. In dit geval kunt u dergelijke bestanden ook met kracht verwijderen als het bestand\(en\) verwijzingen bevat of door andere bestanden wordt genoemd. Voordat u het bestand verwijdert, verschijnt er een bericht met de referenties waarin u wordt gevraagd of u de verwijderbewerking wilt annuleren, de verwijzingen wilt verwijderen en vervolgens het bestand wilt verwijderen. U kunt ook het bestand of de bestanden zonder geweld verwijderen zonder de referenties te verwijderen.

     ![](assets/allow_unsafe_delete-force-delete.PNG){width="550" align="left"}

   - allow\_unsafe\_delete\_for\_delete\_assets\_group: Beheerder of gebruiker die tot de *delete-assets* groep mag bestanden verwijderen. Als een andere gebruiker bestanden met verwijzingen probeert te verwijderen, is het hem niet toegestaan deze bestanden te verwijderen totdat alle referenties zijn verwijderd. De volgende schermafbeelding wordt weergegeven wanneer een gebruiker die geen machtigingen heeft, bestanden probeert te verwijderen.

     ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG){width="550" align="left"}

   - block\_unsafe\_delete\_for\_all: Sta alle gebruikers \(inclusief beheerders\) niet toe bestanden te verwijderen totdat de verwijzingen naar en van het bestand\(en\) zijn verwijderd.

1. Klikken **Opslaan**.


## Oudere versies van DITA-bestanden wissen

Wanneer u inhoud bijwerkt en nieuwe versies maakt, blijven de vorige versies van DITA-bestanden behouden in de opslagplaats. Veel versies worden mogelijk gemaakt voor uw DITA-bestanden over een bepaalde periode en kunnen samen een grote hoeveelheid ruimte innemen in uw opslagplaats. AEM Met hulplijnen kunt u de oudere versies configureren die uit de opslagplaats moeten worden verwijderd.

U hebt toegang tot dit hulpprogramma via de opgegeven URL als u beheerdersrechten hebt:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

De versie van een DITA-bestand die aan een van de opgegeven criteria voldoet, blijft behouden en wordt niet gewist:

- Is de eerste versie van een bestand
- Is opgenomen in een basislijn
- Is inbegrepen in om het even welke vertaling of revisiewerkschema
- Er is een label op toegepast
- Voldoet aan de gedefinieerde leeftijd of het gedefinieerde aantal versiecriteria

Voer de volgende stappen uit om de oudere versies leeg te maken:

1. Voer de volgende gegevens in over de bestanden die u wilt leegmaken:

   ![](assets/preview-purge-report.png){width="350" align="left"}

1. 
   - **Aantal versies dat moet worden behouden vanaf de nieuwste versie**: Voer het aantal versies in dat behouden moet blijven en niet moet worden gewist. Als we bijvoorbeeld 5 invoeren, blijven de laatste 5 versies behouden en worden de versies vóór die versies gekwalificeerd om te worden gewist als aan andere zuiveringsvoorwaarden wordt voldaan.
- **Versies behouden die zijn gemaakt binnen tijdspan \(in dagen\)**: Voer de maximumleeftijd van een versie in dagen in. De versies ouder dan het opgegeven aantal dagen zijn gekwalificeerd om te worden gewist als aan andere zuiveringsvoorwaarden wordt voldaan. Als we bijvoorbeeld 100 invoeren, kunnen alle versies die vóór 100 dagen zijn gemaakt, worden gewist als aan andere zuiveringsvoorwaarden wordt voldaan.
- **Pad**: Selecteer het pad van het bestand of de map waarvan u de bestanden wilt wissen.

  >[!NOTE]
  >
  > U kunt alleen DITA-bestanden leegmaken.

1. Klikken **Voorvertoning rapport voor wissen**.

   >[!NOTE]
   >
   > Er kan slechts één zuiveringstaak tegelijk zijn. U kunt geen andere versiezuivering in werking stellen als één bezig is.

   Het rapport voor het verwijderen van de versie wordt gegenereerd.

1. Rapport voor het opschonen van versies downloaden en de bestanden en versies controleren die worden gewist.
1. U kunt ervoor kiezen **Wissen annuleren** of **Opschonen starten**.

   ![](assets/download-purge-report.png){width="350" align="left"}

   De status van leegmaken wordt weergegeven.

   Klikken **Rapport voor opschonen van versie downloaden** om de gezuiverde versies weer te geven. Dit rapport bevat de opschonende status voor alle versies, samen met de redenen waarom een bepaalde versie is behouden of waarom deze is gewist.


>[!NOTE]
>
> Het rapport wordt gedownload op de volgende locatie: /var/dxml/versionpurge
