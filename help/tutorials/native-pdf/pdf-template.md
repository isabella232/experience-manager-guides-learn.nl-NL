---
title: Native PDF-sjablonen maken en aanpassen
description: Leer hoe u Native PDF-sjablonen maakt en aanpast.
exl-id: 7660da8e-8a1e-4493-b99b-9b5de9a7483f
source-git-commit: 9e806ae9a06eb77441e47413981f27f6e69bd2f9
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 0%

---

# PDF-sjabloon {#PDF-template}

Het gebruik van een sjabloon zorgt voor consistentie in de indeling en structuur van de inhoud. Aangezien de malplaatjes vooraf worden bepaald, kunt u vermijden herwerk bij het formatteren kwesties die voor elk nieuw project of updates zich voordoen. Met sjablonen kunt u paginalay-outs ontwerpen, inhoud opmaken en verschillende instellingen toepassen om uw PDF aan te passen.

## Factory- en aangepaste PDF-sjablonen

Er zijn enkele voorbeeldfabriekssjablonen die uit de doos worden verzonden en die de ontwikkelaars kunnen gebruiken als basissjablonen om aangepaste sjablonen te maken op basis van hun organisatorische vereisten.



## Een nieuwe PDF-sjabloon maken {#create-pdf-template}

U kunt aangepaste PDF-sjablonen maken met specifieke paginalay-outs en opmaak definiëren voor pagina-indelingscomponenten (zoals inhoudsopgave, index, woordenlijst) of DITA-componenten (zoals koptekst, alinea, lijst) met behulp van opmaakmodellen.

Voer de volgende stappen uit om een nieuwe PDF-sjabloon te maken:
1. Ga in de webeditor naar de **Uitvoer** tab.
1. Selecteren **Sjablonen** <img src="./assets/template.svg" alt= "sjabloonpictogram" width="25"> in het linkerdeelvenster.
<img src="assets/create-pdf-template.png" alt="PDF-sjabloon maken" width="400">
1. Selecteer in het venster **Sjablonen** het pictogram **+* naast **Sjablonen** en kies **PDF Sjabloon**.
1. Selecteer in het dialoogvenster **Nieuwe PDF-sjabloon** een fabriekssjabloon die u als basis wilt gebruiken om de aangepaste sjabloon te maken. U kunt ook het zoekvak gebruiken om te zoeken naar een sjabloon.
1. Geef een titel voor de sjabloon op.

>[!NOTE]
>
>  U kunt ook een miniatuur voor de sjabloon voorvertonen terwijl u een sjabloon maakt en dupliceert. De miniatuur bewerken of verwijderen met [**Eigenschappen**](#properties-option) in de **Opties** na het maken van de sjabloon.

1. Klikken **Maken**.

   De nieuwe sjabloon wordt gemaakt en toegevoegd in het dialoogvenster **Sjablonen** deelvenster.

## Een PDF-sjabloon dupliceren {#duplicate-pdf-template}

Als u een nieuwe sjabloon wilt maken met dezelfde paginalay-outs en opmaak als die van een bestaande sjabloon, kunt u een kopie maken. Nadat een sjabloon is gedupliceerd, kunt u de componenten ervan naar wens verder aanpassen.

Voer de volgende stappen uit om een bestaande PDF-sjabloon te dupliceren:
1. Ga in de webeditor naar de **Uitvoer** tab.
1. Selecteren **Sjablonen** <img src="./assets/template.svg" alt= "sjabloonpictogram" width="25"> in het linkerdeelvenster. Hierdoor wordt het **Sjablonen** venster.
1. Houd de muisaanwijzer boven de sjabloon die u wilt dupliceren en selecteer de sjabloon **...** *Opties* pictogram en kies **Dupliceren** in het contextmenu.

   Hierdoor wordt het **PDF-sjabloon dupliceren** in.

   <img src="assets/duplicate-template.png" alt="PDF-sjabloon dupliceren" width="350">

   *Selecteer een sjabloon dat u wilt dupliceren, bekijk een voorvertoning van de miniatuur en werk de titel bij in het dialoogvenster **PDF-sjabloon dupliceren**in.*

1. Geef een titel voor de sjabloon op.

   De **Titel** wordt vooraf ingevuld als een kopie van dezelfde titel als de bronsjabloon. Er verschijnt een foutbericht als de sjabloon met dezelfde titel bestaat.



1. Als u een voorkeurstitel wilt opgeven, verwijdert u de vooraf ingevulde titel en geeft u een titel op.
1. Klikken **Dupliceren**.

   Er wordt een dubbele sjabloon gemaakt en toegevoegd onder de **Sjablonen**.

## Andere bewerkingen op de sjablonen

U kunt ook de volgende bewerkingen uitvoeren op de sjablonen in het menu **Opties** menu:

<img src="assets/PDF-template-options.png" alt="PDF-sjabloon dupliceren" width="350">

### Verwijderen

Selecteer de optie Verwijderen om de geselecteerde sjabloon te verwijderen. Selecteer vervolgens Ja op de bevestigingsvraag.
De voorinstelling wordt verwijderd uit het dialoogvenster **Sjablonen**.

### Eigenschappen{#properties-option}

Selecteer deze optie om de eigenschappen van de sjabloon weer te geven en te bewerken. U kunt een voorvertoning van de bestaande miniatuur voor de sjabloon weergeven. U kunt de miniatuur ook bewerken of verwijderen. U kunt ook de titel en beschrijving van de sjabloon wijzigen.

### Weergeven in interface Elementen

Selecteer deze optie om de sjabloon weer te geven in de interface Middelen. Aangezien het de wortelplaats van het malplaatje opent, kunt u alle middelen van het malplaatje bekijken.

Nadat u de aangepaste sjabloon hebt gemaakt, kunt u deze kiezen in de paginalay-outs in de voorinstelling voor PDF-uitvoer.
Leer hoe u [een PDF-uitvoer publiceren](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/output-gen/web-editor/native-pdf-web-editor.html?lang=en).

>[!NOTE]
>
>Als voor uw map een mapprofiel is geconfigureerd, worden alleen de PDF-sjablonen weergegeven die in het mapprofiel zijn geconfigureerd.

Gebaseerd op uw opstelling kan uw beheerder de malplaatjes vormen:

<details>
<summary> Cloud Services </summary>

Voor meer informatie over het instellen van algemene profielen en mapprofielen, kunt u de [Sjablonen configureren](../cs-install-guide/conf-folder-level.md#id1889D0IL0Y4) in de installatie- en configuratiehandleiding voor Cloud Servicen.

</details>

<details>    
<summary>  Software op locatie </summary>

Voor meer informatie over het instellen van algemene profielen en mapprofielen, kunt u de [Ontwerpsjablonen configureren](../install-guide/conf-folder-level.md#create-custom-authoring-template-id1917d0eg0hj) in de on-premise gids van de Installatie en van de configuratie.

</details>

## Een PDF-sjabloon aanpassen {#customize-pdf-template}

U kunt sjablonen aanpassen door de sjablooncomponenten aan te passen en stijlindelingen toe te passen aan de hand van opmaakmodellen.

Voer de volgende stappen uit om een PDF-sjabloon aan te passen:
1. Ga in de webeditor naar de **Uitvoer** tab.
1. Vouw de linkerzijbalk uit en selecteer **Sjablonen**.

   Hierdoor wordt het **Sjablonen** deelvenster.
1. Voer een van de volgende handelingen uit om de componenten van een sjabloon weer te geven:

   * Selecteer het pictogram > naast een sjabloon of dubbelklik op de sjabloonnaam.
   * Houd de cursor boven een sjabloon en selecteer ... (**Opties** pictogram) en kies **Bewerken** in het contextmenu.

     Standaard wordt hiermee het dialoogvenster **Instellingen** in de sjablooneditor.
   <img src="assets/customize-pdf-template.png" alt="PDF-sjabloon aanpassen" width="350">

   >[!NOTE]
   >
   >  Uw beheerder kan de nieuwste sjablonen downloaden van het volgende pad en de bestaande sjablonen vervangen:
   >
   > `/libs/fmdita/pdf`

   De verschillende sjablooncomponenten die u kunt aanpassen, worden in de volgende secties gecategoriseerd:
   * Paginalay-outs: een typische PDF bevat verschillende pagina&#39;s, zoals een vooromslag of een titelpagina, inhoudsopgave, hoofdstuk, index, citaten, enzovoort. In de sectie Pagina-indelingen kunt u de vormgeving ontwerpen van verschillende pagina&#39;s waaruit de PDF zou bestaan. Voor meer informatie, bekijkt u [Pagina-indelingen](../native-pdf/components-pdf-template.md#page-layouts).

     Naast het uiterlijk kunt u ook de rangschikking van pagina-elementen definiëren, zoals de kop-, voettekst- en inhoudsgebieden op een pagina. Zie voor meer informatie over het aanpassen van de pagina-indeling [Paginalay-outs maken en aanpassen](components-pdf-template.md#create-customize-page-layout).

   * Stylesheets: Met de instellingen in de sectie Stijlvoorbladen kunt u de vormgeving van de onderdelen van de paginalay-out aanpassen, zoals de inhoudsopgave, index, woordenlijst, citaten en meer. Daarnaast kunt u ook de stijlen voor de DITA-inhoud aanpassen, zoals koppen, alinea&#39;s, lijsten en meer. Zie voor meer informatie over het gebruik van de stijlpagina&#39;s [Stylesheets gebruiken om PDF aan te passen](components-pdf-template.md#stylesheet-customization).
   * Bronnen: Sla elementbestanden op die u moet aanpassen of PDF-sjablonen moet ontwerpen. Elementen zoals logo&#39;s, aangepaste lettertypen, achtergrondafbeeldingen en meer worden opgeslagen in de Bronnen.
U kunt ook bronnen gebruiken die zich op een andere locatie in de opslagplaats bevinden. U hoeft geen dubbele bronnen voor elke sjabloon te maken en u kunt deze in een gedeelde map bewaren en ze in alle Native PDF-sjablonen gebruiken.

     Zie voor meer informatie over het gebruik van bronnen [Werken met bronnen](components-pdf-template.md#work-with-resources).
   * Instellingen: configureer de uitvoerinstellingen voor het genereren van een PDF met behulp van de sjabloon. In deze sectie kunt u sjabloontoewijzing definiëren voor verschillende pagina&#39;s in een PDF, hoofdstukstartpagina, afdrukmarkeringen, citaten en meer.
U kunt ook de volgorde bepalen waarin ze in de uiteindelijke PDF-uitvoer moeten worden weergegeven.
Zie voor meer informatie over het toepassen van instellingen [Geavanceerde PDF-instellingen](components-pdf-template.md#advanced-pdf-settings).


1. Als u een sjablooncomponent wilt aanpassen, dubbelklikt u op een sjablooncomponent of selecteert u het pictogram > ervoor.

   Dubbelklik bijvoorbeeld *Pagina-indelingen* of selecteer de *>* pictogram voor *Pagina-indelingen* om de beschikbare paginalay-outs weer te geven.

   >[!NOTE]
   >
   >U kunt een miniatuur en de beschrijving van de sjabloon ook bijwerken met de opdracht [**Eigenschappen**](#properties-option) in de **Opties** -menu.

1. Als u de gewenste wijzigingen hebt aangebracht, selecteert u *Alles opslaan* (of `Ctrl+S`).
