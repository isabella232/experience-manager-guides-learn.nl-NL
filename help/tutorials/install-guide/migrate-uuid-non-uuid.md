---
title: Migratie van niet-UUID naar UUID-inhoud
description: Leer hoe u niet-UUID naar UUID-inhoud migreert
exl-id: 093b380e-9a8b-4e60-aeaa-3458e8c257f2
source-git-commit: 21edbb2f8a49213ea95fac8a957056711219e7e4
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Migratie van niet-UUID naar UUID-inhoud {#id226TI0U20XA}

>[!IMPORTANT]
>
> U kunt uw niet-UUID-inhoud migreren naar de UUID-server. Als u naar de UUID-server wilt migreren, moet er een niet-UUID-server zijn geïnstalleerd waarop AEM versie 4.0 is geïnstalleerd.

Voer de volgende stappen uit om uw niet-UUID-inhoud te migreren:

>[!NOTE]
>
> Elke stap is cruciaal en het ontbreken van een van de stappen kan leiden tot mislukte of beschadigde servergegevens. Zorg ervoor dat u alle stappen uitvoert.

1. Zorg ervoor dat **Launchers voor naverwerking inschakelen** in *com.adobe.fmdita.config.ConfigManager* en **Version Postprocessing inschakelen** in *com.adobe.fmdita.postprocess.version.PostProcessVersionObservation* zijn ingeschakeld.

   ```http
   http://<server name>:<port>/system/console/configMgr/com.adobe.fmdita.config.ConfigManager
   ```

1. Installeer de UUID-versie van de volgende hoofdversie boven de niet-UUID-versie. Als u bijvoorbeeld 4.0 niet-UUID-build gebruikt, moet u UUID-versie 4.1 installeren.

1. Schakel op het tabblad Launcher de volgende workflows uit en elke andere workflow die wordt uitgevoerd op /content/dam met behulp van draagraketten in `http://localhost:4502/libs/cq/workflow/content/console.html`:

   - **DAM Update-element** werkstroom
   - **DAM-metagegevensterugkoppeling** werkstroom

1. Uitschakelen **Launchers voor naverwerking inschakelen** in *com.adobe.fmdita.config.ConfigManager* en uitschakelen **Version Postprocessing inschakelen** in *com.adobe.fmdita.postprocess.version.PostProcessVersionObservation*.

   ```http
   http://<server name>:<port>/system/console/configMgr/com.adobe.fmdita.config.ConfigManager
   ```

1. Een afzonderlijk logger toevoegen voor `com.adobe.fmdita.uuid.upgrade.UuidUpgrade.`

   De browserreactie is ook beschikbaar op /content/uuid-upgrade/logs.

1. Voer de opgegeven query uit op een map met kleinere gegevens met `doReviews=false` voordat het wordt uitgevoerd op / content/dam: `http://localhost:4502/bin/dxml/uuid_upgrade?root=/content/dam/test&doReviews=false`

   >[!TIP]
   >
   >  U kunt controleren of alle bestanden in de map correct zijn bijgewerkt en alle functies werken alleen voor die map.

**Parameters voor de query:**

    - &quot;wortel&quot;: Hoofdmap waar upgrade moet plaatsvinden \(Gebruik /content/dam voor alle opslagplaats).\)
    - &quot;doReviews&quot;: true/false \(als revisies moeten worden bijgewerkt of niet. De standaardwaarde is false.\)
    - &quot;doBaselines&quot;: true/false \(Als basislijnen moeten worden bijgewerkt of niet. De standaardwaarde is true.\)
    - &quot;processLevel&quot;: -1\(mislukt zonder terugzetten\), 0\(mislukt met terugzetten\), 1\(mislukt met fouten\), 2\(bijgewerkt\) \(Wanneer script opnieuw wordt uitgevoerd na mislukking, worden alleen bestanden met &quot;fmUpgradeStatus&quot; &lt;= processLevel opnieuw verwerkt, anders wordt de toepassing genegeerd. De standaardwaarde is 1.\)
    - &quot;ignoreImageVersions&quot;: true/false \(negeert het verwerken van afbeeldingsversies.) De standaardwaarde is false.\)
    
    >[!OPMERKING]
    >
    > We kunnen de migratie van inhoud uitvoeren op mapniveau of op de volledige inhoud/dam of in dezelfde map \(migratie opnieuw uitvoeren\).

1. Nadat de server is gemigreerd, kunnen de volgende workflows en naverwerking blijven werken op de server:

   - **DAM Update-element** werkstroom
   - **DAM-metagegevens** werkstroom

>[!NOTE]
>
> Als sommige bestanden niet worden verwerkt of vóór de migratie beschadigd zijn, blijven ze zelfs na de migratie beschadigd.
