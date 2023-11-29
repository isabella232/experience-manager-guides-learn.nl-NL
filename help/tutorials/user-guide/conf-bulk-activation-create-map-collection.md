---
title: Een verzameling bulkactiveringskaarten maken
description: Leer hoe u een bulkactiveringskaartverzameling maakt in AEM hulplijnen.
exl-id: ea0bd465-a2d9-488f-83e9-62b336233eb1
source-git-commit: e8a912b0f8bc690fceade0b54bb36057a727ab33
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 0%

---

# Een verzameling bulkactiveringskaarten maken {#id214GG0E90EV}

Voer de volgende stappen uit om een bulkactiveringskaartverzameling te maken:

1. Selecteren **Hulplijnen** in de lijst met gereedschappen.

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.

1. Klik op de knop **Bulk publicatiedashboard** tegel.

   Voor de eerste keer wordt een lege verzamelingspagina weergegeven. Als u eerder bulkactiveringsverzamelingen hebt gemaakt, worden deze op deze pagina weergegeven.

1. Klikken **Maken**.

1. Voer een titel in voor uw bulkactiveringskaartverzameling en klik op **Maken**.

   Een bericht van het Succes wordt getoond bij verwezenlijking van de bulkactivering kaartinzameling.

1. Klikken **Openen** op het bericht Succes.

1. Klikken **Bewerken** en klik vervolgens op **Kaarten toevoegen**.

1. Zoek en voeg de DITA-kaarten toe die u aan de bulkactiveringskaartverzameling wilt toevoegen.

   Standaard worden alle voorinstellingen en landinstellingen die aan de kaart zijn gekoppeld, automatisch toegevoegd.

1. Selecteer de gewenste uitvoer door de schuifknop in of uit te schakelen.

   U kunt meerdere uitvoervoorinstellingen kiezen voor alle beschikbare landinstellingen.

1. Klikken **Gereed**.

   De DITA kaartdossiers worden toegevoegd aan uw bulkactiveringskaartinzameling.

   ![](images/bulk-activation-collection-created.png){width="800" align="left"}


Op het tabblad Kaarten en Voorinstellingen vindt u informatie in de volgende kolommen:

- **Kaart**: geeft de titel van het DITA-kaartbestand weer.
- **Pad toewijzen**: geeft het volledige pad van het DITA-kaartbestand weer.

- **UUID**: Hiermee wordt de unieke id weergegeven die aan het bestand is gekoppeld.

- **Taal**: Geeft de taalcode van de DITA-kaart weer.
- **Voorinstelling**: Hiermee geeft u de titel weer van de uitvoervoorinstelling die in het kaartbestand is geconfigureerd. Het pictogram wordt ook weergegeven op basis van het type uitvoervoorinstelling.

  >[!NOTE]
  >
  > De kleine ![](images/global-preset-icon.svg) geeft een voorinstelling voor het mapprofielniveau aan.
- **gewijzigd**: Geeft aan of de DITA-kaart wordt bijgewerkt na de laatste publicatie. Op basis van deze informatie kunt u beslissen of u de uitvoer voor deze DITA-kaart wilt activeren.
- **Gegenereerd**: Geeft de datum en tijd weer van de laatst gegenereerde uitvoer.
- **Gepubliceerd**: Geeft de datum en tijd weer van de laatst gepubliceerde (of geactiveerde) uitvoer. Als u de koppeling selecteert, wordt **Activeringsresultaten** wordt weergegeven, die de logboekbestanden bevat met informatie over het hoofdpad waar de inhoud is geactiveerd.


De volgende filteropties zijn beschikbaar in het linkerdeelvenster:

- **gewijzigd**: U kunt Ja of Nee selecteren. Als u ja selecteert, slechts worden de gewijzigde kaarten DITA getoond. Een gewijzigde kaart is een kaart die is gegenereerd sinds deze voor het laatst is gepubliceerd.
- **Voorinstelling**: Selecteer een voorinstelling waarvoor u de kaartbestanden wilt uitfilteren. Als u bijvoorbeeld *Site AEM* voorinstelling, worden alleen de kaarten weergegeven die de *Site AEM* uitvoervoorinstelling geconfigureerd op deze apparaten.
- **Taal**: U kunt alle beschikbare taalcodes selecteren en alleen de geselecteerde taal weergeven op het tabblad Kaarten en Voorinstellingen.

- **Filter:** In de laatste spoorstaaf worden de volgende filters getoond:
- **Kaarten en voorinstellingen** tabel: de tabbladen Kaarten en Voorinstellingen hebben de volgende kolommen:

**Bovenliggend onderwerp:**[ Bulkactivering van gepubliceerde inhoud](conf-bulk-activation.md)
