---
title: Inhoud vertalen in AEM hulplijnen
description: Leer hoe u inhoud kunt vertalen
source-git-commit: 9fe396dcfd2e3570ec386c958d7d4efdb4d608e5
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---


# Inhoud vertalen {#id181GB0400UI}

Automatiseer de vertaling van pagina-inhoud, elementen en door de gebruiker gegenereerde inhoud om meertalige websites te maken en te onderhouden. Om vertaalworkflows te automatiseren, integreert u de leveranciers van vertaaldiensten met AEM en creeert projecten voor het vertalen van inhoud in veelvoudige talen. AEM ondersteunt workflows voor het vertalen van mensen en machines.

- Menselijke vertaling: Inhoud wordt naar uw vertaalbureau verzonden en door professionele vertalers vertaald. Wanneer de vertaalde inhoud is voltooid, wordt deze geretourneerd en in AEM geïmporteerd. Wanneer uw vertaalprovider is geïntegreerd met AEM, wordt inhoud automatisch uitgewisseld tussen AEM en de vertaalprovider

- Machinevertaling: De vertaalservice zet uw inhoud direct om


Voor het vertalen van inhoud worden de volgende stappen uitgevoerd:

1. AEM verbinden met uw [vertaalserviceprovider](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) en maken [configuraties van het framework voor vertaalintegratie](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Koppel de pagina&#39;s van uw master taal aan de [vertaalservice en frameworkconfiguraties](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identificeer het type van [te vertalen inhoud](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [De inhoud voorbereiden voor vertaling](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) door de master taal te ontwerpen en de basispagina&#39;s van taalkopieën te maken.

1. Maken [vertaalprojecten](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) de te vertalen inhoud te verzamelen en het vertaalproces voor te bereiden.

1. Gebruik de vertaalprojecten om [de vertaling van de inhoud beheren](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) proces.


Wanneer uw vertaalservicebureau geen aansluiting voor integratie met AEM biedt, ondersteunt AEM het handmatig exporteren en importeren van vertaalde inhoud in XML-indeling.

>[!TIP]
>
> Zie de *Vertaling* Zie het gedeelte in de handleiding met aanbevolen procedures voor tips en trucs voor het vertalen van inhoud.

## Het tabblad Vertaling op het dashboard voor de DITA-kaart configureren

De optie van het Lusje van de Vertaling van de Huid wordt niet toegelaten door gebrek en u moet dit van configMgr toelaten. Voer de volgende stappen uit om het tabblad Vertaling op het dashboard voor de DITA-kaart te verbergen:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. Selecteer **Tabblad Vertaling verbergen** om het tabblad Vertalen op het kaartdashboard te verbergen.

   >[!NOTE]
   >
   > Deze eigenschap is standaard uitgeschakeld en het tabblad Vertalen is beschikbaar op het kaartdashboard.

1. Klikken **Opslaan**.

## Op componenten gebaseerde vertaalworkflow configureren

Als de schakelaar voor de vertaalverkoper geen inhoud DITA steunt, dan moet de op component-gebaseerde vertaalwerkschema worden toegelaten. Als deze optie is ingeschakeld, wordt de vertaalbare inhoud verzonden als metagegevens over elementen. Deze workflow werkt alleen als de connector ondersteuning biedt voor het vertalen van metagegevens van elementen.

Op basis van de vertaalworkflow die in uw installatie wordt gebruikt, moet de optie voor de vertaalworkflow op basis van componenten als volgt worden geconfigureerd:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. Configureer de **Op componenten gebaseerde DITA-omzettingsworkflow** -optie volgens uw instellingen:

   - Als u menselijke vertaling gebruikt, dan *Uitschakelen* de **Workflow voor op componenten gebaseerde omzetting** optie.

   - Als u automatische vertaling gebruikt, dan *Inschakelen* de **Workflow voor op componenten gebaseerde omzetting** optie.
   >[!NOTE]
   >
   > Als u vertaalschakelaar gebruikt, dan zorg ervoor dat u de schakelaar hebt gevormd zoals die in wordt beschreven *[Het framework voor vertaalintegratie configureren](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* in AEM documentatie.

1. Klikken **Opslaan**.


>[!IMPORTANT]
>
> Nadat u de vertaalconfiguraties hebt ingesteld, dient u de juiste Cloud Configuration in te stellen voor de taalmappen.

## Nabewerking van tijdelijke taalkopieën configureren

Wanneer u de vertaalworkflow start, maakt het systeem tijdelijke taalkopieën van de broninhoud. U kunt de nabewerking voor deze tijdelijke bestanden in- of uitschakelen. In de naverwerkingstransactie worden de inkomende en uitgaande referenties van de bestanden opgelost, wordt de documentstatus ingesteld, samen met andere bewerkingen. Als u naverwerking voor deze tijdelijke bestanden inschakelt, kan het voltooien van het vertaalproces langer duren. Daarom wordt aangeraden de optie voor nabewerking uit te schakelen.

De optie voor naverwerken van tijdelijke bestanden is standaard uitgeschakeld. U kunt deze optie configureren door de volgende stappen uit te voeren:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.config.ConfigManager** bundel.

1. Configureer de **Na het proces gemaakte taalkopieën** -optie volgens uw instellingen:

   - \(*Standaard*\) Als u de naverwerkingsbewerking niet wilt uitvoeren op de tijdelijke bestanden, dan *Uitschakelen* de **Na het proces gemaakte taalkopieën** optie.

   - Als u de naverwerkingsbewerking wilt uitvoeren op de tijdelijke bestanden, *Inschakelen* de **Na het proces gemaakte taalkopieën** optie.

1. Klikken **Opslaan**.


