---
title: Een onderwerp naar een inhoudsfragment publiceren
description: Leer hoe u een onderwerp naar een inhoudsfragment publiceert.
source-git-commit: 6cd7d2ec76f90a192dbcd0ef552789d42c23a4fb
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---


# Publiceren naar een inhoudsfragment

Inhoudsfragmenten zijn afzonderlijke stukken inhoud in AEM. Het zijn gestructureerde inhoud die is gebaseerd op een inhoudsmodel. Inhoudsfragmenten zijn zuivere inhoud zonder ontwerp- of layoutgegevens. Ze kunnen onafhankelijk van de kanalen worden ontworpen en beheerd die AEM ondersteunen. Inhoudsfragmenten zijn modulair, waarbij de inhoud wordt opgedeeld in kleinere componenten.

Met AEM hulplijnen kunt u een onderwerp of de elementen in een onderwerp naar een inhoudsfragment publiceren. U kunt een op JSON-Gebaseerde afbeelding tussen een onderwerp en een model van het inhoudsfragment tot stand brengen. Gebruik deze toewijzing om een onderwerp of de elementen binnen een onderwerp aan een inhoudsfragment te publiceren. Vervolgens kunt u inhoudsfragmenten op elke AEM site gebruiken of de details extraheren via API&#39;s die worden ondersteund door inhoudsfragmenten.


Voer de volgende stappen uit om een inhoudsfragment te maken:

1. Een [inhoudsfragmentmodel](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=en) in AEM Assets.
1. Maak een map waarin u de inhoudsfragmenten wilt opslaan die u maakt op basis van het fragmentmodel van de inhoud. Bijvoorbeeld &#39;stock-content-fragments&#39;.
1. Bewerk de eigenschappen van de map (bijvoorbeeld &quot;stock-content-fragments&quot;) en voeg het pad van de map toe, die het fragmentmodel van de inhoud in de cloudconfiguratie bevat.
Voeg bijvoorbeeld `/conf/we-retail` in de cloudconfiguratie. Deze configuratie verbindt alle modellen van het inhoudsfragment met de omslag.\
   ![gegevens over de cloudconfiguratie toevoegen aan de mapeigenschappen](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
   *Voeg de wolkenconfiguratie in de omslageigenschappen toe om het met de fragmentmodellen te verbinden.*
1. Selecteer het onderwerp dat u wilt publiceren in het dialoogvenster **Weergave opslagplaats**.
1. Van de **Opties** menu, selecteert u **Publiceren als** > **Inhoudsfragment**.
1. In de **Publiceren als inhoudsfragment** , vult u de volgende gegevens in:
   ![Het fragmentmodel en toewijzingsdetails toevoegen in het dialoogvenster Publiceren als inhoudsfragment](images/content-fragment-publish.png){width="500" align="left"}
   *Voeg het pad, het model en de toewijzingsdetails toe om een onderwerp of de elementen ervan te publiceren als een inhoudsfragment. U kunt een bestaand inhoudsfragment overschrijven.*

   * **Pad**: Blader en selecteer het pad van de map waarin u het inhoudsfragment wilt publiceren. U kunt ook een bestaand inhoudsfragment selecteren en publiceren.
   * **Titel**: Voer de titel van het inhoudsfragment in.
   * **Naam**: Voer de naam van het inhoudsfragment in.
   * **Model**: Selecteer het inhoudsfragmentmodel dat u wilt gebruiken om het inhoudsfragment te maken. De modellen worden gekozen uit de map die u hebt geconfigureerd in de cloudservices.
   * **Toewijzing**: Selecteer een toewijzing in de keuzelijst. De toewijzingen worden gekozen uit de *contentFragmentMapping.json* bestand.

     >[!NOTE]
     >
     >Uw beheerder kan de toewijzingen toevoegen in de *contentFragmentMapping.json* bestand.  Meer informatie over hoe [een toewijzing maken tussen een onderwerp en een inhoudsfragment](../install-guide/conf-content-fragment-mapping.md) in *Installatie- en configuratiehandleiding op locatie*.


   * Selecteer de **Overschrijven** Schakel het selectievakje in als het inhoudsfragment al bestaat en u het wilt overschrijven. AEM hulplijnen geeft een fout weer als u het selectievakje niet inschakelt en het inhoudsfragment al bestaat.
1. Klikken **Maken** om het inhoudsfragment te publiceren.
1. U kunt de inhoudsfragmenten voor een onderwerp bekijken onder de **Fragmenten** in de **Bestandseigenschappen**.

   ![De inhoudsfragmenten voor een onderwerp weergeven](images/topic-content-fragments.png){width="300" align="left"}

   *Bekijk de inhoudsfragmenten die aanwezig zijn voor een onderwerp en publiceer deze opnieuw.*

U kunt het inhoudsfragment ook opnieuw publiceren om het inhoudsfragment bij te werken met de meest recente inhoud van het DITA-onderwerp.



Nadat u de inhoudsfragmenten hebt gepubliceerd, kunt u deze ook op elke AEM site gebruiken.

