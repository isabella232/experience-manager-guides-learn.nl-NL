---
title: Inhoud vertalen
description: Leer hoe u inhoud kunt vertalen
source-git-commit: 4d54c52b8771b0c5a40018cfec3a6586029af2fb
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 0%

---


# Inhoud vertalen {#id181GB0400UI}

Automatiseer de vertaling van pagina-inhoud, elementen en door de gebruiker gegenereerde inhoud om meertalige websites te maken en te onderhouden. Om vertaalworkflows te automatiseren, integreert u de leveranciers van vertaaldiensten met AEM en creeert projecten voor het vertalen van inhoud in veelvoudige talen. AEM ondersteunt workflows voor het vertalen van mensen en machines.

- Menselijke vertaling: de inhoud wordt naar uw vertaalbureau verzonden en door professionele vertalers vertaald. Wanneer de vertaalde inhoud is voltooid, wordt deze geretourneerd en in AEM geïmporteerd. Wanneer uw vertaalprovider is geïntegreerd met AEM, wordt inhoud automatisch uitgewisseld tussen AEM en de vertaalprovider

- Machinevertaling: de vertaalservice zet uw inhoud direct om


Voor het vertalen van inhoud worden de volgende stappen uitgevoerd:

1. AEM verbinden met uw [vertaalserviceprovider](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) en configuraties voor vertaalintegratie maken.

1. Koppel de pagina&#39;s van uw taalmaster aan de vertaalservice en frameworkconfiguraties.

1. Het type van [te vertalen inhoud](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [De inhoud voorbereiden voor vertaling](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) door het taalstramien te ontwerpen en de basispagina&#39;s van taalkopieën te maken.

1. Maken [vertaalprojecten](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) de te vertalen inhoud te verzamelen en het vertaalproces voor te bereiden.

1. Gebruik de vertaalprojecten om [de vertaling van de inhoud beheren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) proces.


Wanneer uw vertaalservicebureau geen aansluiting voor integratie met AEM biedt, ondersteunt AEM het handmatig exporteren en importeren van vertaalde inhoud in XML-indeling.

>[!TIP]
>
> Zie de *Vertaling* in de handleiding voor aanbevolen procedures voor het vertalen van inhoud.

## Het tabblad Vertaling op het dashboard voor de DITA-kaart configureren

Voer de volgende stappen uit om het tabblad Vertaling op het dashboard voor de DITA-kaart te verbergen:

1. Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken.
1. Geef in het configuratiebestand de volgende \(eigenschap\)-details op om het tabblad Vertaling op het kaartdashboard te configureren:

   | PID | Eigenschappensleutel | Waarde van eigenschap |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Boolean \( true/ false\).<br> **Standaardwaarde**: `true` |

   >[!NOTE]
   >
   > Deze configuratie is standaard ingeschakeld en het tabblad Vertalen is niet beschikbaar op het kaartdashboard.


## Op componenten gebaseerde vertaalworkflow configureren

Als de schakelaar voor de vertaalverkoper geen inhoud DITA steunt, dan moet de op component-gebaseerde vertaalwerkschema worden toegelaten. Als deze optie is ingeschakeld, wordt de vertaalbare inhoud verzonden als metagegevens over elementen. Deze workflow werkt alleen als de connector ondersteuning biedt voor het vertalen van metagegevens van elementen.

Op basis van de vertaalworkflow die in uw installatie wordt gebruikt, moet de optie voor de vertaalworkflow op basis van componenten worden geconfigureerd. Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\)-details op om de workflow voor op componenten gebaseerde omzetting te configureren:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Booleaans: <br> - Als u menselijke vertaling gebruikt, dan *Uitschakelen* \( `false`\) de **Workflow voor op componenten gebaseerde omzetting** -optie. <br> - Als u automatische vertaling gebruikt, *\( inschakelen `true`\)* de **Workflow voor op componenten gebaseerde omzetting** -optie. |

>[!NOTE]
>
> Als u vertaalschakelaar gebruikt, dan zorg ervoor dat u de schakelaar hebt gevormd zoals die in wordt beschreven *[Het Kader voor de Integratie van de Vertaling vormen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* onderwerp in AEM documentatie.

>[!IMPORTANT]
>
> Nadat u de vertaalconfiguraties hebt ingesteld, dient u de juiste Cloud Configuration in te stellen voor de taalmappen.

## Nabewerking van tijdelijke taalkopieën configureren

Wanneer u de vertaalworkflow start, maakt het systeem tijdelijke taalkopieën van de broninhoud. U kunt de nabewerking voor deze tijdelijke bestanden in- of uitschakelen. In de naverwerkingstransactie worden de inkomende en uitgaande referenties van de bestanden opgelost, wordt de documentstatus ingesteld, samen met andere bewerkingen. Als u naverwerking voor deze tijdelijke bestanden inschakelt, kan het voltooien van het vertaalproces langer duren. Daarom wordt aangeraden de optie voor nabewerking uit te schakelen.

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\)-details op om de naverwerking van tijdelijke taalkopieën te configureren:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Booleaans: <br> - Als u de naverwerkingsbewerking niet wilt uitvoeren op de tijdelijke bestanden, *Uitschakelen* \( false\) de **Na het proces gemaakte taalkopieën** -optie.<br> - Als u de naverwerkingsbewerking wilt uitvoeren op de tijdelijke bestanden, *Inschakelen* \( true\) de **Na het proces gemaakte taalkopieën** -optie.<br> **Standaardwaarde**: false |

