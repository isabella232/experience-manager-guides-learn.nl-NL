---
title: Native PDF-sjablonen maken en aanpassen
description: Leer hoe u Native PDF-sjablonen maakt en aanpast.
exl-id: 7660da8e-8a1e-4493-b99b-9b5de9a7483f
source-git-commit: 49fa930483f48cafd057002ee26c9499ce967c60
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 0%

---

# PDF-sjabloon {#PDF-template}

Het gebruik van een sjabloon zorgt voor consistentie in de indeling en structuur van de inhoud. Aangezien de malplaatjes vooraf worden bepaald, kunt u vermijden herwerk bij het formatteren kwesties die voor elk nieuw project of updates zich voordoen. Met sjablonen kunt u paginalay-outs ontwerpen, inhoud opmaken en verschillende instellingen toepassen om uw PDF aan te passen.

Auteurs kunnen de voorinstellingen voor PDF gebruiken om uitvoer te genereren, maar ontwikkelaars kunnen hun eigen sjablonen maken. Er zijn voorbeeldsjablonen die uit de doos worden verzonden en die verder kunnen worden aangepast of gedupliceerd door de ontwikkelaars volgens hun organisatorische vereisten.


## Een nieuwe PDF-sjabloon maken {#create-pdf-template}

U kunt aangepaste PDF-sjablonen maken met specifieke paginalay-outs en opmaak definiëren voor pagina-indelingscomponenten (zoals inhoudsopgave, index, woordenlijst) of DITA-componenten (zoals koptekst, alinea, lijst) met behulp van opmaakmodellen. U kunt een nieuwe sjabloon helemaal zelf maken of maken met een voorbeeldsjabloon.

Voer de volgende stappen uit om een nieuwe PDF-sjabloon te maken:
1. Ga in de webeditor naar de **Uitvoer** tab.
1. Vouw de linkerzijbalk uit en selecteer **Sjablonen**.
<img src="assets/create-pdf-template.png" alt="PDF-sjabloon maken" width="400">
1. Selecteer in het deelvenster **Sjablonen** het pictogram **+* naast **Sjablonen** en kies **PDF Sjabloon**.
1. Geef een naam voor de sjabloon op in het dialoogvenster **Nieuwe sjabloon**.
1. Klik op **Gereed**.

De nieuwe sjabloon wordt gemaakt en toegevoegd in het dialoogvenster *Sjablonen* deelvenster.

## Een PDF-sjabloon dupliceren {#duplicate-pdf-template}

Als u een nieuwe sjabloon wilt maken met dezelfde paginalay-outs en opmaak als die van een bestaande sjabloon, kunt u een kopie maken. Nadat een sjabloon is gedupliceerd, kunt u de componenten ervan naar wens verder aanpassen.

Voer de volgende stappen uit om een bestaande PDF-sjabloon te dupliceren:
1. Ga in de webeditor naar de **Uitvoer** tab.
1. Vouw de linkerzijbalk uit en selecteer **Sjablonen**.

   Hiermee opent u het deelvenster Sjablonen.
1. Houd de muisaanwijzer boven de sjabloon die u wilt dupliceren en selecteer de sjabloon (*Opties* pictogram) **...** en kiest u **Dupliceren** in het contextmenu.

   Hiermee opent u het dialoogvenster Sjabloon dupliceren.\
   <img src="assets/duplicate-template.png" alt="PDF-sjabloon dupliceren" width="250">
1. Geef een naam op voor het team.

   De **Naam** wordt vooraf ingevuld als een kopie van dezelfde naam als de bronsjabloon.

1. Als u een voorkeursnaam wilt opgeven, verwijdert u de vooraf ingevulde naam en geeft u een naam op.
1. Klikken **Gereed**.

   Onder Sjablonen wordt een gedupliceerde sjabloon gemaakt en toegevoegd.

## Een PDF-sjabloon aanpassen {#customize-pdf-template}

U kunt sjablonen aanpassen door de sjablooncomponenten aan te passen en stijlindelingen toe te passen aan de hand van opmaakmodellen.

Voer de volgende stappen uit om een PDF-sjabloon aan te passen:
1. Ga in de webeditor naar het tabblad Uitvoer.
1. Vouw de linkerzijbalk uit en selecteer Sjablonen.

   Hiermee opent u het deelvenster Sjablonen.
1. Voer een van de volgende handelingen uit om de componenten van een sjabloon weer te geven:

   * Selecteer het pictogram > naast een sjabloon of dubbelklik op de sjabloonnaam.
   * Houd de cursor boven een sjabloon, selecteer ... (pictogram Opties) en kies Bewerken in het contextmenu.

     Standaard wordt hiermee het deelvenster Instellingen in de sjablooneditor geopend.
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
   * Bronnen: Sla elementbestanden op die u moet aanpassen of PDF-sjablonen moet ontwerpen. Elementen zoals logo&#39;s, aangepaste lettertypen, achtergrondafbeeldingen en meer worden opgeslagen in de Bronnen. Zie voor meer informatie over het gebruik van bronnen [Werken met bronnen](components-pdf-template.md#work-with-resources).
   * Instellingen: configureer de uitvoerinstellingen voor het genereren van een PDF met behulp van de sjabloon. In deze sectie kunt u sjabloontoewijzing definiëren voor verschillende pagina&#39;s in een PDF, hoofdstukstartpagina, afdrukmarkeringen, citaten en meer.
U kunt ook de volgorde bepalen waarin ze in de uiteindelijke PDF-uitvoer moeten worden weergegeven.
Zie voor meer informatie over het toepassen van instellingen [Geavanceerde PDF-instellingen](components-pdf-template.md#advanced-pdf-settings).


1. Als u een sjablooncomponent wilt aanpassen, dubbelklikt u op een sjablooncomponent of selecteert u het pictogram > ervoor.

   Dubbelklik bijvoorbeeld *Pagina-indelingen* of selecteer de *>* pictogram voor *Pagina-indelingen* om de beschikbare paginalay-outs weer te geven.
1. Als u de gewenste wijzigingen hebt aangebracht, selecteert u *Alles opslaan* (of `Ctrl+S`).
