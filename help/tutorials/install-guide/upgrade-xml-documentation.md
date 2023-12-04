---
title: Adobe Experience Manager-hulplijnen upgraden
description: Meer informatie over het upgraden van Adobe Experience Manager-hulplijnen
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '4470'
ht-degree: 0%

---

# Adobe Experience Manager-hulplijnen upgraden {#id224MBE0M0XA}

>[!NOTE]
>
> Volg de upgrade-instructies voor de versie met licentie van uw product.

U kunt uw huidige versie van de Gidsen van de Experience Manager aan versie 4.3.1 bevorderen

- Als u versie 4.3.0, 4.2 of 4.2.1 gebruikt, kunt u rechtstreeks upgraden naar versie 4.3.1.
- Als u versie 4.1 of 4.1.x gebruikt, moet u een upgrade naar versie 4.3.0, 4.2 of 4.2.x uitvoeren voordat u een upgrade naar versie 4.3.1 uitvoert.
- Als u versie 4.0 gebruikt, moet u een upgrade naar versie 4.2 uitvoeren voordat u een upgrade naar versie 4.3.1 uitvoert.
- Als u versie 3.8.5 gebruikt, moet u een upgrade naar versie 4.0 uitvoeren voordat u een upgrade naar versie 4.2 uitvoert.
- Als u een versie hebt die ouder is dan 3.8.5, raadpleegt u de sectie Upgradehulplijnen voor Experience Managers in de productspecifieke installatiehandleiding.


>[!NOTE]
>
> U moet AEM de dienstpak installeren alvorens de versie van de Gidsen van de Experience Manager te bevorderen.

Raadpleeg de volgende procedures voor meer informatie:

- [Upgrade van 3.8.5 naar versie 4.0](#id2256DK003E1)
- [Upgrade naar versie 4.2](#id22A3F500SXA)
- [Upgrade naar versie 4.2.1](#upgrade-version-4-2-1)
- [Upgrade naar versie 4.3.0](#upgrade-version-4-3)
- [Upgrade naar versie 4.3.1](#upgrade-version-4-3-1)


>[!IMPORTANT]
>
> Voordat u begint met een upgrade, moet u een volledige back-up van het systeem maken om gegevensverlies te voorkomen.

## Upgrade van versie 3.8.5 naar versie 4.0 {#id2256DK003E1}

Als u versie 3.8.5 van de Gidsen van de Experience Manager gebruikt, dan kunt u aan versie 4.0 van de Gidsen van de Experience Manager bevorderen. Met de verbeteringseigenschap, moet u niet de vorige versie van de Gidsen van de Experience Manager verwijderen.

Voordat u het proces uitvoert, moet u bepaalde taken uitvoeren. De volgende subsecties zullen u door de eerste vereisten, rapportgeneratie, en migratieproces lopen. Nadat u versie 4.0 van de Hulplijnen van de Experience Manager hebt geïnstalleerd, kunt u ook diverse configuraties aanpassen, volgens de klantenmontages.

>[!NOTE]
>
> Dit upgradeproces is alleen van toepassing van versie 3.8.5 tot versie 4.0. Raadpleeg voor het upgradeproces van versie 3.4 of hoger naar versie 3.8.5 de *Hulplijnen Experience Manager bijwerken* in de productspecifieke installatiehandleiding beschikbaar in het gedeelte [Help-archiveringspagina](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

****Vereisten****

Voordat u het upgradeproces voor de hulplijnen van de Experience Manager start, moet u controleren of:

1. De revisieopmerkingen zijn geïmporteerd in onderwerpen die zijn geopend voor revisie.
1. Alle actieve revisies zijn gesloten.
1. Alle vertaaltaken zijn afgesloten.
1. Verwijder alle hotfixes voor hulplijnen voor Experience Managers die boven op de vorige versie \(hoofdversie of patchrelease\) van de hulplijnen voor Experience Managers zijn geïnstalleerd.

**Voordat u versie 4.0 installeert**

Voer de volgende stappen uit voordat u versie 4.0 installeert:

1. Zorg ervoor dat de hulplijnen voor Experience Managers op dit punt zijn ingeschakeld in versie 3.8.5.
1. Download het pakket met het upgradescript. U kunt dit doen door te zoeken naar &quot;XML Documentation-oplossing 4.0 Upgrade Package&quot; op [Distributieportaal voor software voor Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) dat een ZIP-bestand downloadt.
1. Upload dit pakket naar AEM via Package Manager en installeer dit pakket.
1. Nadat het upgradepakket is geïnstalleerd, voert u de onderstaande scripts in dezelfde volgorde uit en volgt u de gegeven instructies:

**CompatibiliteitsAPI voor upgrades controleren**

Deze API is ontworpen om de huidige systeemstatus te beoordelen en te rapporteren of de upgrade mogelijk is of niet. Als u dit script wilt uitvoeren, activeert u het onderstaande eindpunt:

| Eindpunt | /bin/dxml/upgrade/3xto4x/report |
| --- | --- |
| Type aanvraag | **GET** U kunt een webbrowser gebruiken waarin u als beheerder bent aangemeld bij de AEM. |
| Verwachte reactie | - Als alle vereiste knooppunten kunnen worden verplaatst, wordt een controle geslaagd weergegeven. <br>- Als er een knooppunt aanwezig is op de doellocatie, wordt er een relevante fout gegenereerd. Maak de opslagplaats \(verwijder knoop /var/dxml\) schoon en installeer het verbeteringspakket opnieuw en breng dan dit eindpunt opnieuw teweeg. <br>**Opmerking:** Dit is geen algemene fout omdat de doellocatie niet eerder wordt gebruikt door 3.x-hulplijnen voor Experience Managers. <br> - Als dit script niet slaagt, ga dan niet verder en rapporteer aan uw team van de klantensucces. |

**API voor migratie van systeemgegevens**

Deze API is ontworpen om systeemgegevens te migreren zoals vermeld in het **Migratietoewijzing** sectie.

1. Voer dit script niet uit als de API voor compatibiliteit van upgrades controleren \(ga niet door\) mislukt.
1. Zodra de API voor upgradeconformiteit controleren succesvol is, kunt u het upgradescript uitvoeren.

| Eindpunt | /bin/dxml/upgrade/3xto4x |
| --- | --- |
| Type aanvraag | **POST** Dit manuscript is een verzoek van de POST vandaar zou via agenten zoals Postman moeten worden uitgevoerd. |
| Verwachte reactie | - Als de migratie is voltooid, kunt u XML Documentation-oplossing versie 4.0 installeren.<br>- Als er fouten zijn, herstelt u het laatste controlepunt en deelt u de foutlogboeken samen met de API-uitvoer met het succesteam van de klant. |

**Migratietoewijzing**: De bovenstaande API migreert alle gegevens onder de bronlocatie naar de doellocatie.

| Bron | Doel |
|------|------|
| /content/fmdita | /var/dxml |
| /content/dxml | /var/dxml |
| /etc/fmdita | /libs/fmdita |

## Versie 4.0 installeren {#id23598G006XA}

1. Installeer versie 4.0 slechts als de verbeteringsstappen succesvol waren.
1. Download het versiepakket 4.0 van [Distributieportaal voor software voor Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html):

   - Als u UUID-versie van software gebruikt, zoekt u naar &quot;4.0 UUID Release for XML Documentation Solution for AEM 6.5&quot;.
   - Als u niet-UUID versie van software gebruikt, zoek naar &quot;4.0 Non-UUID Release for XML Documentation oplossing voor AEM 6.5.&quot;
Upload het pakket naar de bestaande AEM serverinstantie\(s\) met behulp van CRX Package Manager en installeer het pakket.

   >[!NOTE]
   >
   > Wacht tot alle systeemcomponenten zijn gestart.

1. Wis de browsercache nadat u het pakket hebt geïnstalleerd.
1. Als een verzender op AEM instantie Auteur wordt gevormd, voer de volgende stappen uit:
   - Zorg ervoor dat het volgende wordt verwerkt in verzendersregels:
   - Het URL-patroon/home/users/\*/preferences is whitelisted.
   - Het URL-patroon /libs/cq/security/userinfo.json wordt niet in de cache opgeslagen.
1. Verzendcache wissen \(om eventuele `clientlibs` in cache geplaatst\).

## Upgrade naar versie 4.2 {#id22A3F500SXA}

De upgrade naar versie 4.2 is afhankelijk van de huidige versie van Hulplijnen voor Experience Managers.

Als u versie 4.0, 4.1 of 4.1.x gebruikt, kunt u rechtstreeks upgraden naar versie 4.2.

****Vereisten****

Voordat u het upgradeproces voor de Experience Manager Guides 4.2 start, moet u controleren of:

1. Bijgewerkt naar Experience Manager Guides versie 4.0, 4.1 of 4.1.x.
1. Alle vertaaltaken zijn afgesloten.
1. Het logniveau is gewijzigd in **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` klasse en voeg deze logboeken in een nieuw logboekdossier toe, bijvoorbeeld `logs/translation_upgrade.log.`

>[!NOTE]
>
> Sluit alle actieve revisies. Als de revisietaken niet worden afgesloten tijdens de upgrade naar 4.2, nemen de oudere revisietaken in uitvoering voortdurend gebruikers op de oudere revisiepagina&#39;s. De revisietaken die na de upgrade worden gemaakt, geven de nieuwste updates in de functionaliteit weer.

## Versie 4.2 installeren {#id2245IK0E0EV}

1. Download het versiepakket 4.2 van [Distributieportaal voor software voor Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installeer het pakket versie 4.2.
1. Nadat u de pakketinstallatie hebt voltooid, wacht u op het volgende bericht in de logbestanden:

   `Completed the post deployment setup script`

   Het bovenstaande bericht geeft aan dat alle installatiestappen zijn voltooid.

   Als u om het even welke volgende prefix van de FOUT ontmoet, rapporteer hen aan uw team van het klantensucces:

   - Fout tijdens een setupscript voor implementatie na plaatsing
   - Uitzondering tijdens het exporteren van de MAP voor vertaling
   - Kan vertaalkaart van v1 naar v2 voor eigenschap niet importeren
1. Upgrade de insteekmodule Zuurstofaansluiting die wordt vrijgegeven met versie 4.2 \(indien nodig\).
1. Wis de browsercache nadat u het pakket hebt geïnstalleerd.
1. U kunt de aanpassingen blijven bijwerken zoals in de volgende sectie wordt beschreven.

## Nadat u versie 4.2 hebt geïnstalleerd {#id2326F02004K}

>[!IMPORTANT]
>
> Hi-tech-sjabloon wordt niet weergegeven op een geüpgrade server. Als u de hi-tech sjabloon op uw server wilt opnemen, kunt u deze kopiëren: Bron: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Nadat u de Gidsen van de Experience Manager installeert, kunt u de diverse configuraties samenvoegen toepasselijk van de onlangs geïnstalleerde versie aan uw opstelling.

>[!NOTE]
>
> Het dampupdate-assetmodel kan worden aangepast. Dus als er aanpassingen zijn uitgevoerd, moeten we de aanpassingen en Experience Manager-hulplijnen synchroniseren in de werkkopie van het model.

1. **Workflow DAM-update-element \(wijzigingen na verwerking\):**

1. URL openen:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Selecteren **Workflow voor DAM-update-middelen**.
1. Klikken op **Bewerken**.
1. Als de **Initiator DXML Post Process** is, zorgt u ervoor dat de aanpassingen worden gesynchroniseerd.
1. Als de **Initiator DXML Post Process** -component ontbreekt, voert u de volgende stappen uit om deze in te voegen:

1. Klikken **Component invoegen** \(Verantwoordelijk voor de naverwerking van de gidsen van de Experience Manager als laatste stap in het proces\).
1. Vorm **Processtap** met onderstaande details:

   **Tabblad Algemeen**

   **Titel:** Initiator DXML Post Process

   **Beschrijving**: Initiatorstap van DXML-nabewerkingsproces die een slingertaak activeert voor DXML-naverwerking van het gewijzigde/gemaakte element

   **Tabblad Proces**

   - Selecteren **Initiator DXML Post Process** van de **Proces** vervolgkeuzelijst

   - Selecteren **Handler Advance**

   - Selecteren **Gereed**

1. Klikken **Sync** rechtsboven nadat de wijzigingen zijn aangebracht. Je ontvangt een melding over succes.

   >[!NOTE]
   >
   > Vernieuw en controleer of de aangepaste wijzigingen en de naverwerkingsstap van de Experience Manager Guides aanwezig zijn in het uiteindelijke workflowmodel.

1. Eenmaal **Workflow voor DAM-update-middelen** wordt gevalideerd, controleer de overeenkomende opstartconfiguraties. Ga hiertoe naar AEM Workflowinterface en open draagraketten.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Zoek en breng indien nodig wijzigingen aan in de volgende twee draagraketten \(die actief moeten zijn\) die overeenkomen met **Workflow voor DAM-update-middelen**:

1. Launcher for &quot;*Knooppunt gemaakt*&quot; for **Workflow voor DAM-update-middelen**- voor conditie `"jcr:content/jcr:mimeType!=video"`, moet de waarde &#39;Globbing&#39; zijn:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; moet `"event-user-data:changedByWorkflowProcess"`.
   - Launcher for &quot;*Knooppunt gewijzigd*&quot; for **Workflow voor DAM Update-middelen -** voor voorwaarde &quot;`jcr:content/jcr:mimeType!=video`&quot;,
   - De waarde &#39;Globbing&#39; moet als volgt zijn:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; moet `"event-user-data:changedByWorkflowProcess"`.
1. Nadat de upgrade is voltooid, zorgt u ervoor dat alle aanpassingen/overlays worden gevalideerd en bijgewerkt zodat ze overeenkomen met de nieuwe toepassingscode. Hieronder volgen enkele voorbeelden:
   - Alle componenten die worden overschreven door/libs/fmditor/libsc, moeten worden vergeleken met de nieuwe productcode en updates moeten worden uitgevoerd in overlay bestanden onder/apps.
   - Alle clientlibcategorieën die worden gebruikt van het product, dienen te worden gecontroleerd op wijzigingen. Overschreven configuraties \(voorbeelden verderop\) moeten worden vergeleken met de nieuwste configuraties om de nieuwste functies te krijgen:
   - elementmapping.xml
   - ui\_config.json\(kan zijn ingesteld in mapprofielen\)
   - gewijzigd `com.adobe.fmdita.config.ConfigManager`
   - Controleren of er in de aangepaste code oude paden werden gebruikt \(zoals vermeld in het dialoogvenster [Migratietoewijzing](#id2244LE040XA) sectie\) - zou aan de nieuwe wegen moeten worden bijgewerkt zodat de aanpassingen ook zoals verwacht werken.
1. Lees over om het even welke nieuwe configuraties die in de huidige versie \(controle worden gebracht [Opmerkingen bij de release](../release-info/release-notes-4.3.md)\) en controleer of de functionaliteit wordt beïnvloed en neem vervolgens de juiste actie. Een voorbeeld hiervan is &quot;Verbeterde bestands- en versieverwerking&quot; die is geïntroduceerd in versie 4.0, waarvoor u een configuratie moet inschakelen.

## Stappen om de bestaande inhoud te indexeren voor het gebruik van de nieuwe zoek- en vervangactie:

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe tekst zoeken en vervangen op kaartniveau te gebruiken:

- Een verzoek van een POST uitvoeren op de server \(met correcte verificatie\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Optioneel: u kunt specifieke paden van de kaarten doorgeven om deze te indexeren. Standaard worden alle kaarten geïndexeerd \|\|, bijvoorbeeld: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

- De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden -

`http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

- Als de taak is voltooid, reageert het bovenstaande verzoek van de GET met succes en vermeldt u of kaarten zijn mislukt. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

Als de upgradetaak mislukt en in het foutenlogboek de volgende fout wordt weergegeven:

&quot;De *query* meer dan *100000 knooppunten*. Om te voorkomen dat andere taken worden beïnvloed, is de verwerking gestopt.&quot;

Dit kan gebeuren omdat de index niet correct is ingesteld voor de query die wordt gebruikt in de upgrade. U kunt de volgende tijdelijke oplossing uitproberen:

1. Voeg de booleaanse eigenschap toe aan de oak-index damAssetLucene `indexNodeName` als `true` in het knooppunt.
   `/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Voeg een nieuw knooppunt toe met het naamfragment onder het knooppunt.

   `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
en stel de volgende eigenschappen in het knooppunt in:

   ```
   name - rep:excerpt
   propertyIndex - {Boolean}true
   notNullCheckEnabled - {Boolean}true
   ```

   De structuur van `damAssetLucene` moet er ongeveer als volgt uitzien:

   ```
   <damAssetLucene compatVersion="{Long}2" async="async, nrt" jcr:primaryType="oak:QueryIndexDefinition" evaluatePathRestrictions="{Boolean}true" type="lucene">
   <indexRules jcr:primaryType="nt:unstructured">
     <dam:Asset indexNodeName="{Boolean}true" jcr:primaryType="nt:unstructured">
       <properties jcr:primaryType="nt:unstructured">
         <excerpt name="rep:excerpt" propertyIndex="{Boolean}true" jcr:primaryType="nt:unstructured" notNullCheckEnabled="{Boolean}true"/>
       </properties>
       </dam:Asset>
     </indexRules>
   </damAssetLucene>    
   ```


   (samen met andere bestaande knooppunten en eigenschappen)

1. De index van de `damAssetLucene` index (door de herindexmarkering in te stellen als `true` en wachten tot het is `false` nogmaals (dit geeft aan dat de omkoppeling is voltooid). Het kan een paar uur duren, afhankelijk van de grootte van de index.
1. Voer de vorige stappen uit om het indexeringsscript opnieuw uit te voeren.


## Upgrade naar versie 4.2.1 {#upgrade-version-4-2-1}

De upgrade naar versie 4.2.1 is afhankelijk van de huidige versie van Hulplijnen voor Experience Managers.

Als u versie 4.1 of 4.1.x of 4.2 gebruikt, kunt u rechtstreeks een upgrade uitvoeren naar versie 4.2.1.

>[!NOTE]
>
>De nabewerking en indexering kunnen een paar uur duren. Wij adviseren u om het verbeteringsproces tijdens de off-piek uren te beginnen.

****Vereisten****

Voordat u het upgradeproces voor de Experience Manager Guides 4.2.1 start, moet u controleren of:

1. Bijgewerkt naar Experience Manager Guides versie 4.1, 4.1.x of 4.2.
1. Alle vertaaltaken zijn afgesloten.
1. Het logniveau is gewijzigd in **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` klasse en voeg deze logboeken in een nieuw logboekdossier toe, bijvoorbeeld `logs/translation_upgrade.log.`

>[!NOTE]
>
> Sluit alle actieve revisies. Als de revisietaken niet worden afgesloten tijdens de upgrade naar 4.2, nemen de oudere revisietaken in uitvoering voortdurend gebruikers op de oudere revisiepagina&#39;s. De revisietaken die na de upgrade worden gemaakt, geven de nieuwste updates in de functionaliteit weer.

## Versie 4.2.1 installeren

1. Download het 4.2.1-versiepakket van [Distributieportaal voor software voor Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installeer versie 4.2.1.
1. U kunt ervoor kiezen om de trigger te HIT om de upgradetaak voor de vertaalkaart te starten. Zie voor meer informatie [Triggerscript activeren via een Servlet](#enable-trigger-serverlet).


1. Nadat u de pakketinstallatie hebt voltooid, wacht u op het volgende bericht in de logbestanden:

   `Completed the post deployment setup script`

   Het bovenstaande bericht geeft aan dat alle installatiestappen zijn voltooid.

   Als u om het even welke volgende prefix van de FOUT ontmoet, rapporteer hen aan uw team van het klantensucces:

   - Fout tijdens een setupscript voor implementatie na plaatsing
   - Uitzondering tijdens het exporteren van de MAP voor vertaling
   - Kan vertaalkaart van v1 naar v2 voor eigenschap niet importeren
1. Upgrade de insteekmodule Zuurstofaansluiting die wordt vrijgegeven met versie 4.2 \(indien nodig\).
1. Wis de browsercache nadat u het pakket hebt geïnstalleerd.
1. U kunt de aanpassingen blijven bijwerken zoals in de volgende sectie wordt beschreven.

### Triggerscript activeren via een Servlet{#enable-trigger-serverlet}

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

In het bovenstaande antwoord JSON `lockNodePath` bevat het pad naar het knooppunt dat in de opslagplaats is gemaakt en dat naar de ingediende taak verwijst. Het wordt automatisch verwijderd als de taak is voltooid. Tot dan kunt u naar dit knooppunt verwijzen voor de huidige status van de taak.

Voorbeeldlogboek: Hieronder ziet u een voorbeeld van logboeken die in het logbestand worden weergegeven nadat u het script hebt geactiveerd.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Zoeken naar `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` en `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` voordat u verdergaat met de volgende stappen.



## Nadat u versie 4.2.1 hebt geïnstalleerd

>[!IMPORTANT]
>
> Hi-tech-sjabloon wordt niet weergegeven op een geüpgrade server. Als u de hi-tech sjabloon op uw server wilt opnemen, kunt u deze kopiëren: Bron: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

Nadat u de Gidsen van de Experience Manager installeert, kunt u de diverse configuraties samenvoegen toepasselijk van de onlangs geïnstalleerde versie aan uw opstelling.

>[!NOTE]
>
> Het dampupdate-assetmodel kan worden aangepast. Dus als er aanpassingen zijn uitgevoerd, moeten we de aanpassingen en Experience Manager-hulplijnen synchroniseren in de werkkopie van het model.

1. **Workflow DAM-update-element \(wijzigingen na verwerking\):**

1. URL openen:

   ```http
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
   ```

1. Selecteren **Workflow voor DAM-update-middelen**.
1. Klikken op **Bewerken**.
1. Als de **Initiator DXML Post Process** is, zorgt u ervoor dat de aanpassingen worden gesynchroniseerd.
1. Als de **Initiator DXML Post Process** -component ontbreekt, voert u de volgende stappen uit om deze in te voegen:

1. Klikken **Component invoegen** \(Verantwoordelijk voor de naverwerking van de gidsen van de Experience Manager als laatste stap in het proces\).
1. Vorm **Processtap** met onderstaande details:

   **Tabblad Algemeen**

   **Titel:** Initiator DXML Post Process

   **Beschrijving**: Initiatorstap van DXML-nabewerkingsproces die een slingertaak activeert voor DXML-naverwerking van het gewijzigde/gemaakte element

   **Tabblad Proces**

   - Selecteren **Initiator DXML Post Process** van de **Proces** vervolgkeuzelijst

   - Selecteren **Handler Advance**

   - Selecteren **Gereed**

1. Klikken **Sync** rechtsboven nadat de wijzigingen zijn aangebracht. Je ontvangt een melding over succes.

   >[!NOTE]
   >
   > Vernieuw en controleer of de aangepaste wijzigingen en de naverwerkingsstap van de Experience Manager Guides aanwezig zijn in het uiteindelijke workflowmodel.

1. Eenmaal **Workflow voor DAM-update-middelen** wordt gevalideerd, controleer de overeenkomende opstartconfiguraties. Ga hiertoe naar AEM Workflowinterface en open draagraketten.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Zoek en breng indien nodig wijzigingen aan in de volgende twee draagraketten \(die actief moeten zijn\) die overeenkomen met **Workflow voor DAM-update-middelen**:

1. Launcher for &quot;*Knooppunt gemaakt*&quot; for **Workflow voor DAM-update-middelen**- voor conditie `"jcr:content/jcr:mimeType!=video"`, moet de waarde &#39;Globbing&#39; zijn:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; moet `"event-user-data:changedByWorkflowProcess"`.
   - Launcher for &quot;*Knooppunt gewijzigd*&quot; for **Workflow voor DAM Update-middelen -** voor voorwaarde &quot;`jcr:content/jcr:mimeType!=video`&quot;, moet de waarde &#39;Globbing&#39; zijn:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` moeten `"event-user-data:changedByWorkflowProcess"`.

1. Nadat de upgrade is voltooid, zorgt u ervoor dat alle aanpassingen/overlays worden gevalideerd en bijgewerkt zodat ze overeenkomen met de nieuwe toepassingscode. Hieronder volgen enkele voorbeelden:
   - Alle componenten die worden overschreven door/libs/fmditor/libsc, moeten worden vergeleken met de nieuwe productcode en updates moeten worden uitgevoerd in overlay bestanden onder/apps.
   - Alle clientlibcategorieën die worden gebruikt van het product, dienen te worden gecontroleerd op wijzigingen. Overschreven configuraties \(voorbeelden verderop\) moeten worden vergeleken met de nieuwste configuraties om de nieuwste functies te krijgen:
   - elementmapping.xml
   - ui\_config.json\(kan zijn ingesteld in mapprofielen\)
   - gewijzigd `com.adobe.fmdita.config.ConfigManager`
   - Controleren of er in de aangepaste code oude paden werden gebruikt \(zoals vermeld in het dialoogvenster [Migratietoewijzing](#id2244LE040XA) sectie\) - zou aan de nieuwe wegen moeten worden bijgewerkt zodat de aanpassingen ook zoals verwacht werken.
1. Lees over om het even welke nieuwe configuraties die in de huidige versie \(controle worden gebracht [Opmerkingen bij de release](../release-info/release-notes-4.2.1.md)\) en controleer of de functionaliteit wordt beïnvloed en neem vervolgens de juiste actie. Een voorbeeld hiervan is &quot;Verbeterde bestands- en versieverwerking&quot; die is geïntroduceerd in versie 4.0, waarvoor u een configuratie moet inschakelen.

## Stappen om de bestaande inhoud te indexeren voor het gebruik van de nieuwe zoek- en vervangactie:

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe tekst zoeken en vervangen op kaartniveau te gebruiken:

- Zorg ervoor dat de `damAssetLucene` indexering is voltooid. Het kan een paar uur duren, afhankelijk van de hoeveelheid gegevens die aanwezig is op de server. U kunt bevestigen dat het opnieuw indexeren is voltooid door te controleren of het veld voor opnieuw indexeren in
  `http://<server:port>/oak:index/damAssetLucene`.  Ook als u aanpassingen hebt toegevoegd in `damAssetLucene`kan het zijn dat u deze opnieuw moet toepassen.

- Een verzoek van een POST uitvoeren op de server \(met correcte verificatie\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optioneel: u kunt specifieke paden van de kaarten doorgeven om deze te indexeren. Standaard worden alle kaarten geïndexeerd \|\| Bijvoorbeeld: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- U kunt ook een hoofdmap doorgeven om de DITA-kaarten van een specifieke map (en de bijbehorende submappen) te indexeren. Bijvoorbeeld: `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Wanneer zowel de parameter paths als de hoofdparameter worden doorgegeven, wordt alleen de parameter paths gebruikt.

- De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Als de taak is voltooid, reageert het bovenstaande verzoek van de GET met succes en vermeldt u of kaarten zijn mislukt. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.


## Upgrade naar versie 4.3.0 {#upgrade-version-4-3}

De upgrade naar versie 4.3.0 is afhankelijk van de huidige versie van Hulplijnen voor Experience Managers. Als u versie 4.2 of 4.2.x gebruikt, kunt u rechtstreeks upgraden naar versie 4.3.0.

>[!NOTE]
>
>De nabewerking en indexering kunnen een paar uur duren. Wij adviseren u om het verbeteringsproces tijdens de off-piek uren te beginnen.

****Vereisten****

Voordat u het upgradeproces voor de Experience Manager Guides 4.3.0 start, moet u controleren of:

1. Bijgewerkt naar Experience Manager Guides versie 4.2 of 4.2.x en hun respectieve installatiestappen voltooien.
1. Alle vertaaltaken zijn afgesloten.



## Versie 4.3.0 installeren

1. Download het 4.3.0-versiepakket van [Distributieportaal voor software voor Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installeer versie 4.3.0.
1. Wis de browsercache nadat u het pakket hebt geïnstalleerd.
1. Upgrade de `ui_config.json` bestand van de **XML Editor-configuratie** in het Mapprofiel.


## Nadat u versie 4.3.0 hebt geïnstalleerd

Nadat u de Gidsen van de Experience Manager installeert, kunt u de diverse configuraties samenvoegen toepasselijk van de onlangs geïnstalleerde versie aan uw opstelling.

## Stappen om de bestaande inhoud te posten om het verbroken koppelingsrapport te gebruiken


Voer de volgende stappen uit voor de naverwerking van de bestaande inhoud en het gebruik van het nieuwe verbroken koppelingsrapport:

1. (Optioneel) Als het systeem meer dan 100.000 dita-bestanden bevat, werkt u de `queryLimitReads` krachtens `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` naar een hogere waarde (een waarde die groter is dan het aantal aanwezige elementen, bijvoorbeeld 200.000) en vervolgens opnieuw te implementeren.

   | PID | Eigenschappensleutel | Waarde van eigenschap |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Waarde: 200000 <br> Standaardwaarde: 100000 |

1. Voer de volgende API&#39;s uit om naverwerking uit te voeren op alle bestanden:

   | Eindpunt | /bin/guides/reports/upgrade |
   |---|---|
   | Type aanvraag | **POST**  Dit manuscript is een verzoek van de POST vandaar zou via agenten zoals Postman moeten worden uitgevoerd. |
   | Verwachte reactie | De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden.<br> URL voorbeeld: `http://<server:port>/bin/guides/reports/upgrade` |

   | Eindpunt | /bin/guides/reports/upgrade |
   |---|---|
   | Type aanvraag | **GET** |
   | Param | jobId: geef de taak-id door die is ontvangen van de vorige postaanvraag. |
   | Verwachte reactie | - Zodra de taak is voltooid, reageert de GET-aanvraag met succes. <br> - Als er fouten optreden, deelt u de foutlogboeken samen met de API-uitvoer met het succesteam van de klant.  <br>URL voorbeeld: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Terugkeren naar de standaardwaarde of vorige bestaande waarde van `queryLimitReads` als u dit in stap 1 hebt gewijzigd.


4.3.1.

## Upgrade naar versie 4.3.1 {#upgrade-version-4-3-1}

De upgrade naar versie 4.3.1 is afhankelijk van de huidige versie van Hulplijnen voor Experience Managers. Als u versie 4.3.0, 4.2 of 4.2.1 gebruikt, kunt u rechtstreeks upgraden naar versie 4.3.1.

>[!NOTE]
>
>De nabewerking en indexering kunnen een paar uur duren. Wij adviseren u om het verbeteringsproces tijdens de off-piek uren te beginnen.

****Vereisten****

Voordat u het upgradeproces voor de Experience Manager Guides 4.3.1 start, moet u controleren of:

1. Bijgewerkt naar Experience Manager Guides versie 4.3.0, 4.2 of 4.2.1 en hun respectieve installatiestappen voltooien.
1. Alle vertaaltaken zijn afgesloten.
1. Het logniveau is gewijzigd in **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` klasse en voeg deze logboeken in een nieuw logboekdossier toe, bijvoorbeeld `logs/translation_upgrade.log`.


## Versie 4.3.1 installeren

1. Download het 4.3.1-versiepakket van [Distributieportaal voor software voor Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Installeer versie 4.3.1.
1. U kunt ervoor kiezen om de trigger te HIT om de upgradetaak voor de vertaalkaart te starten. Zie voor meer informatie [Triggerscript activeren via een Servlet](#enable-trigger-serverlet-4-3-1).


1. Nadat u de pakketinstallatie hebt voltooid, wacht u op het volgende bericht in de logbestanden:

   `Completed the post deployment setup script`

   Het bovenstaande bericht geeft aan dat alle installatiestappen zijn voltooid.

   Als u om het even welke volgende prefix van de FOUT ontmoet, rapporteer hen aan uw team van het klantensucces:

   - Fout tijdens een setupscript voor implementatie na plaatsing
   - Uitzondering tijdens het exporteren van de MAP voor vertaling
   - Kan vertaalkaart van v1 naar v2 voor eigenschap niet importeren
1. Upgrade de insteekmodule Zuurstofaansluiting die wordt vrijgegeven met versie 4.2 \(indien nodig\).
1. Wis de browsercache nadat u het pakket hebt geïnstalleerd.
1. U kunt de aanpassingen blijven bijwerken zoals in de volgende sectie wordt beschreven.

### Triggerscript activeren via een Servlet{#enable-trigger-serverlet-4-3-1}

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

In het bovenstaande antwoord JSON `lockNodePath` bevat het pad naar het knooppunt dat in de opslagplaats is gemaakt en dat naar de ingediende taak verwijst. Het wordt automatisch verwijderd als de taak is voltooid. Tot dan kunt u naar dit knooppunt verwijzen voor de huidige status van de taak.

Voorbeeldlogboek: Hieronder ziet u een voorbeeld van logboeken die in het logbestand worden weergegeven nadat u het script hebt geactiveerd.

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Zoeken naar `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` en `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` voordat u verdergaat met de volgende stappen.

## Nadat u versie 4.3.1 hebt geïnstalleerd



Nadat u de Gidsen van de Experience Manager installeert, kunt u de diverse configuraties samenvoegen toepasselijk van de onlangs geïnstalleerde versie aan uw opstelling.

>[!NOTE]
>
> Het dampupdate-assetmodel kan worden aangepast. Dus als er aanpassingen zijn uitgevoerd, moeten we de aanpassingen en Experience Manager-hulplijnen synchroniseren in de werkkopie van het model.

1. **Workflow DAM-update-element \(wijzigingen na verwerking\):**

1. URL openen:

   ```
   http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
   ```

1. Selecteren **Workflow voor DAM-update-middelen**.
1. Klikken op **Bewerken**.
1. Als de **Initiator DXML Post Process** is, zorgt u ervoor dat de aanpassingen worden gesynchroniseerd.
1. Als de **Initiator DXML Post Process** -component ontbreekt, voert u de volgende stappen uit om deze in te voegen:

1. Klikken **Component invoegen** \(Verantwoordelijk voor de naverwerking van de gidsen van de Experience Manager als laatste stap in het proces\).
1. Vorm **Processtap** met onderstaande details:

   **Tabblad Algemeen**

   **Titel:** Initiator DXML Post Process

   **Beschrijving**: Initiatorstap van DXML-nabewerkingsproces die een slingertaak activeert voor DXML-naverwerking van het gewijzigde/gemaakte element

   **Tabblad Proces**

   - Selecteren **Initiator DXML Post Process** van de **Proces** vervolgkeuzelijst

   - Selecteren **Handler Advance**

   - Selecteren **Gereed**

1. Klikken **Sync** rechtsboven nadat de wijzigingen zijn aangebracht. Je ontvangt een melding over succes.

   >[!NOTE]
   >
   > Vernieuw en controleer of de aangepaste wijzigingen en de naverwerkingsstap van de Experience Manager Guides aanwezig zijn in het uiteindelijke workflowmodel.

1. Eenmaal **Workflow voor DAM-update-middelen** wordt gevalideerd, controleer de overeenkomende opstartconfiguraties. Ga hiertoe naar AEM Workflowinterface en open draagraketten.

   ```http
   http://localhost:4502/libs/cq/workflow/content/console.html
   ```

   Zoek en breng indien nodig wijzigingen aan in de volgende twee draagraketten \(die actief moeten zijn\) die overeenkomen met **Workflow voor DAM-update-middelen**:

1. Launcher for &quot;*Knooppunt gemaakt*&quot; for **Workflow voor DAM-update-middelen**- voor conditie `"jcr:content/jcr:mimeType!=video"`, moet de waarde &#39;Globbing&#39; zijn:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - &#39;excludeList&#39; moet `"event-user-data:changedByWorkflowProcess"`.
   - Launcher for &quot;*Knooppunt gewijzigd*&quot; for **Workflow voor DAM Update-middelen -** voor voorwaarde &quot;`jcr:content/jcr:mimeType!=video`&quot;, moet de waarde &#39;Globbing&#39; zijn:

   ```json
   /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
   ```

   - `excludeList` moeten `"event-user-data:changedByWorkflowProcess"`.

1. Nadat de upgrade is voltooid, zorgt u ervoor dat alle aanpassingen/overlays worden gevalideerd en bijgewerkt zodat ze overeenkomen met de nieuwe toepassingscode. Hieronder volgen enkele voorbeelden:
   - Alle componenten die worden overschreven door/libs/fmditor/libsc, moeten worden vergeleken met de nieuwe productcode en updates moeten worden uitgevoerd in overlay bestanden onder/apps.
   - Alle clientlibcategorieën die worden gebruikt van het product, dienen te worden gecontroleerd op wijzigingen. Overschreven configuraties \(voorbeelden verderop\) moeten worden vergeleken met de nieuwste configuraties om de nieuwste functies te krijgen:
   - elementmapping.xml
   - ui\_config.json\(kan zijn ingesteld in mapprofielen\)
   - gewijzigd `com.adobe.fmdita.config.ConfigManager`


## Stappen om de bestaande inhoud te indexeren

>[!NOTE]
>
> U hoeft deze stappen niet uit te voeren als u een upgrade uitvoert van 4.3.0 of 4.2.1.

Voer de volgende stappen uit om de bestaande inhoud te indexeren en de nieuwe tekst zoeken en vervangen op kaartniveau te gebruiken:


- Een verzoek van een POST uitvoeren op de server \(met correcte verificatie\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optioneel: u kunt specifieke paden van de kaarten doorgeven om deze te indexeren. Standaard worden alle kaarten geïndexeerd \|\| Bijvoorbeeld: `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


- De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(Bijvoorbeeld: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


- Als de taak is voltooid, reageert het bovenstaande verzoek van de GET met succes en vermeldt u of kaarten zijn mislukt. De met succes geïndexeerde kaarten kunnen van de serverlogboeken worden bevestigd.

## Stappen om de bestaande inhoud te posten om het verbroken koppelingsrapport te gebruiken

>[!NOTE]
>
> U hoeft deze stappen niet uit te voeren als u een upgrade uitvoert van 4.3.0

Voer de volgende stappen uit voor de naverwerking van de bestaande inhoud en het gebruik van het nieuwe verbroken koppelingsrapport:

1. (Optioneel) Als het systeem meer dan 100.000 dita-bestanden bevat, werkt u de `queryLimitReads` krachtens `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` naar een hogere waarde (een waarde die groter is dan het aantal aanwezige elementen, bijvoorbeeld 200.000) en vervolgens opnieuw te implementeren.

   | PID | Eigenschappensleutel | Waarde van eigenschap |
   |---|---|---|
   | org.apache.jackrabbit.oak.query.QueryEngineSettingsService | queryLimitReads | Waarde: 200000 <br> Standaardwaarde: 100000 |

1. Voer de volgende API&#39;s uit om naverwerking uit te voeren op alle bestanden:

   | Eindpunt | /bin/guides/reports/upgrade |
   |---|---|
   | Type aanvraag | **POST**  Dit manuscript is een verzoek van de POST vandaar zou via agenten zoals Postman moeten worden uitgevoerd. |
   | Verwachte reactie | De API retourneert een jobId. Als u de status van de taak wilt controleren, kunt u een aanvraag van een GET met taak-id naar hetzelfde eindpunt verzenden.<br> URL voorbeeld: `http://<server:port>/bin/guides/reports/upgrade` |

   | Eindpunt | /bin/guides/reports/upgrade |
   |---|---|
   | Type aanvraag | **GET** |
   | Param | jobId: geef de taak-id door die is ontvangen van de vorige postaanvraag. |
   | Verwachte reactie | - Zodra de taak is voltooid, reageert de GET-aanvraag met succes. <br> - Als er fouten optreden, deelt u de foutlogboeken samen met de API-uitvoer met het succesteam van de klant.  <br>URL voorbeeld: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |


1. Terugkeren naar de standaardwaarde of vorige bestaande waarde van `queryLimitReads` als u dit in stap 1 hebt gewijzigd.



**Bovenliggend onderwerp:**[ Downloaden en installeren](download-install.md)
