---
title: Kaarten maken op basis van aangepaste sjablonen
description: Leer hoe u kaarten maakt op basis van aangepaste sjablonen
exl-id: 02513148-3876-4549-962a-9984f619030f
source-git-commit: 9196d7b1094149f06067c153b9c02c2cd20c18af
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 0%

---

# Kaarten maken op basis van aangepaste sjablonen {#id225VF0808MP}

U kunt aangepaste kaartmalplaatjes tot stand brengen en hen gebruiken om kaarten DITA samen met de onderwerpmalplaatjes en kaartmalplaatjes tot stand te brengen die in het kaartmalplaatje van verwijzingen worden voorzien

U kunt naar andere kaartmalplaatjes en onderwerpmalplaatjes van het aangepaste kaartmalplaatje verwijzen. De genoemde kaartmalplaatjes kunnen naar diverse kaartmalplaatjes, onderwerpmalplaatjes, onderwerpen, kaarten, beelden, video&#39;s, en andere activa verwijzen. Het aangepaste kaartsjabloon kan u zeer gemakkelijk helpen de kaartsjablonen en de volledige doorverwezen omslagstructuur te herhalen. Deze aangepaste sjablonen zijn vooral handig voor het maken en opnieuw maken van meerdere kaarten met recursieve structuren en verwijzingen.

>[!NOTE]
>
> Onderwerpsjablonen worden niet recursief gemaakt. Slechts onderwerpmalplaatjes die direct binnen het kaartmalplaatje zijn worden geproduceerd en om het even welk onderwerpmalplaatje binnen een onderwerpmalplaatje wordt eenvoudig bedoeld in de ouder direct.

## Aangepaste sjablonen maken

Met AEM hulplijnen kunt u aangepaste mappen en onderwerpen maken in de map dita-templates. U kunt deze aangepaste malplaatjes gebruiken om uw kaart en onderwerp tot stand te brengen. U kunt deze sjablonen ook met uw auteurs delen en deze gebruiken om hun bestanden te maken. Met behulp van deze sjablonen kunt u de auteurs toestaan afzonderlijke kopieën te maken van bepaalde bronnen die zich in de sjabloonmap bevinden.

>[!NOTE]
>
> Bronnen die alleen worden doorverwezen naar en behouden over, moeten zich buiten de sjabloonmap bevinden.


U kunt kaart en onderwerpmalplaatjes op de volgende manieren tot stand brengen:
1. Het deelvenster Sjablonen van het deelvenster [Deelvenster Links](./web-editor-features.md#left-panel-id2051ea0m0hs)
1. [Sjablonen in interface Middelen](#templates-assets-ui)
1. [Menu Opties](#templates-in-assets-ui)

### Sjablonen in interface Middelen {#templates-assets-ui}

**Onderwerpsjabloon**

Voer de volgende stappen uit om een onderwerpmalplaatje tot stand te brengen:

1. In de **UI Middelen** Navigeer naar de map dita-templates.

   ![](images/dita-templates.png){width="800" align="left"}

1. Klikken **onderwerpen** map om deze te openen.Klik **\> DITA-sjabloon maken**.
1. Selecteer op de pagina Vervagen **Onderwerp** en klik vervolgens op **Volgende.**
1. Voor de pagina van Eigenschappen, specificeer het onderwerpmalplaatje **Titel**.
1. Geef het bestand op **Naam**

   >[!NOTE]
   >
   > De bestandsnaam moet de extensie .dita hebben.

1. \(Optioneel\) Voeg een beschrijving toe.
1. Klikken **Maken**. Het onderwerpmalplaatje creeerde bericht verschijnt. U kunt het onderwerpmalplaatje dan openen en het uitgeven.

**Kaartsjabloon**

Voer de volgende stappen uit om een kaartsjabloon te maken:

1. In de **UI Middelen** Navigeer naar de map dita-templates.
1. Klikken **maps** om deze te openen.
1. Klikken **\> DITA-sjabloon maken.**

   ![](images/create-dita-template.png){width="300" align="left"}

1. Selecteer op de pagina Vervagen **Kaart** en klik op **Volgende**.
1. Geef op de pagina Eigenschappen de kaartsjabloon op **Titel**.
1. Geef het bestand op **Naam**.

   >[!NOTE]
   >
   > De bestandsnaam moet de extensie .ditamap hebben.

1. (Optioneel\) Voeg een beschrijving toe.Klik op **Maken**. Het bericht voor het maken van de kaartsjabloon wordt weergegeven. Vervolgens kunt u de kaartsjabloon openen en bewerken. U kunt de verwijzingen voor de onderwerpmalplaatjes, kaartmalplaatjes, en ook andere activa in het kaartmalplaatje toevoegen.

### Menu Opties {#options-menu}

Voer de volgende stappen uit om een kaart- of onderwerpsjabloon te maken:

1. Selecteer de **Kaart** of **Onderwerp** in de huidige sjabloonmap. Bijvoorbeeld de map `dita-templates`.
1. Van de **Opties** menu, selecteert u **Kaartsjabloon maken** of **Onderwerpsjabloon maken**.

   De **Nieuwe kaartsjabloon maken** of de **Nieuwe onderwerpsjabloon maken** wordt geopend.
1. Voer de titel en de naam van de nieuwe sjabloon in.
1. Kies het type sjabloon dat u wilt maken in het menu **Sjabloon** vervolgkeuzelijst.

Het bericht voor het maken van de kaartsjabloon wordt weergegeven. U kunt de sjabloon toevoegen aan uw algemene profiel of mapprofiel. Het nieuwe malplaatje verschijnt dan in het onderwerp of kaartverwezenlijking proces, en u kunt kaarten of onderwerpen tot stand brengen gebruikend het.


Uw beheerder kan ook een map maken en deze zo configureren dat deze de map is waarin u de sjablonen kunt maken en opslaan.

Gebaseerd op uw opstelling leert hoe te om de weg van de malplaatjeomslag van douaneDITA te vormen:
<details>
    <summary> Cloud Services </summary>

Leer hoe u [aangepaste DITA-sjabloonmappad configureren](../install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) in de Installatie- en configuratiehandleiding van Cloud Servicen.
</details>

<details>
    <summary> Software op locatie</summary>

Leer hoe u [aangepaste DITA-sjabloonmappad configureren](../cs-install-guide/conf-template-tags-custom-dita-topic-template.md#configure-custom-dita-template-folder-path-id191lcf0095z) in de on-premise gids van de Installatie en van de Configuratie.
</details>

## De titel doorgeven die is gedefinieerd in de sjablonen

Als u de titel van het onderwerp of de kaart wilt doorgeven die binnen uw malplaatje wordt gebruikt aan de kaarten DITA die gebruikend dat malplaatje worden gecreeerd, gebruiks gekrulde steunen rond de titel.

Voorbeeld

```XML
<pubtitle>
   <mainpubtitle outputclass="booktitle">
   {title}
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>

The resultant DITA map with title "Rootmap1" will look like as follows:
<pubtitle>
   <mainpubtitle outputclass="booktitle">Rootmap1
   </mainpubtitle>
   <subtitle>Subtitle</subtitle>
</pubtitle>
```

>[!NOTE]
> Alleen het eerste exemplaar van de accolade wordt vervangen door een titel.

Als u geen krullende haakjes rond de titel gebruikt zal de resulterende kaart DITA slechts het eerste element worden gekozen en het nesten van de titel zal niet van het malplaatje worden gekozen en het zal als volgt kijken:

```XML
<pubtitle> Rootmap1 </pubtitle>
```

>[!NOTE]
> U kunt ook de accolades rondom de tekst gebruiken om de geneste structuur van de aangepaste sjablonen door te geven aan uw DITA-kaarten.

Voorbeeld

```XML
<title>    
    <sub>        
        <b>{title}</b>    
    </sub>
</title>
```




## De kaartsjabloon gebruiken om nieuwe kaarten te maken

>[!NOTE]
>
> Het kaartmalplaatje moet voor creatie door uw beheerder worden gevormd en ter beschikking gesteld. Zie voor meer informatie *Ontwerpsjablonen configureren* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.

Voer de volgende stappen uit om een kaart te creëren gebruikend het malplaatje van de douanekaart:

1. In de **UI Middelen** Navigeer naar de map waarin u de kaart wilt maken.
1. Klikken **\> DITA-toewijzing maken**.
1. Selecteer op de pagina Vervagen de kaartsjabloon die u wilt gebruiken en klik op **Volgende**. Als u bijvoorbeeld een kaartsjabloon &#39;test-template&#39; hebt gemaakt, selecteert u deze.
1. Geef op de pagina Eigenschappen de kaart op **Titel**.
1. Geef het bestand op **Naam**.

   >[!NOTE]
   >
   > De bestandsnaam moet de extensie .ditamap hebben.

1. Klikken **Maken**. Het bericht dat de kaart heeft gemaakt, wordt weergegeven.


De kaart genereert alle elementen waarnaar in de sjabloonmap wordt verwezen. Sommige soorten activa die in een kaart worden bedoeld kunnen als volgt zijn:

- Als de kaart de verwijzing naar een onderwerpmalplaatje bevat, wordt een exemplaar van het gecreeerd binnen de omslag, in de zelfde hiërarchie zoals in de onderwerpenomslag in `dita-templates` map.
- Als de kaart de verwijzing naar een kaartmalplaatje bevat, wordt een exemplaar van het gecreeerd binnen de omslag, in de zelfde hiërarchie zoals in de kaartomslag in `dita-templates` map.
- Als de kaart de generische verwijzing naar een onderwerp of kaart buiten bevat `dita-templates/topics` of `dita-templates/maps` -map, wordt alleen naar hetzelfde verwezen en er wordt geen kopie gemaakt.

  >[!NOTE]
  >
  > `dita-templates/topics` en `dita-templates/maps` zijn de standaardwegen in Gidsen en zijn configureerbaar.


  Als er een zeer belangrijke definitie van het onderwerpmalplaatje binnen het kaartmalplaatje is, wordt een nieuwe sleutel \ (daarom nieuw onderwerp \) gecreeerd en in de kaart bedoeld.

- Als een andere kaart of een onderwerp op het zelfde niveau in de omslag wordt gecreeerd, dan worden de namen van de pas gecreëerde activa toegevoegd met 0.1.2, etc. U kunt ervoor kiezen de kaart te openen om het kaartbestand te bewerken of op te slaan in de opslagplaats.

**Bovenliggend onderwerp:**[ Werken met de Kaarteditor](map-editor.md)
