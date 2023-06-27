---
title: Kaartverzameling gebruiken voor het genereren van uitvoer
description: Leer hoe te om de Inzameling van de Kaart voor outputgeneratie te gebruiken
exl-id: 32e3af6c-9670-42cc-8dbe-9f99fbc60adf
source-git-commit: 22f88ae4097a6067ed65a963ad6765f6f8c24f36
workflow-type: tm+mt
source-wordcount: '898'
ht-degree: 0%

---

# Kaartverzameling gebruiken voor het genereren van uitvoer {#id1723F20G0HS}

In elke organisatie kan een product meerdere typen documentatie hebben. Als uitgeverspecialist, zou u willen controleren welke output u voor welk document wilt produceren. Bovendien moet u meerdere documenten met één klik in batch publiceren.

AEM de Gidsen verstrekt u de capaciteit om uw inhoud voor het publiceren te organiseren door een dashboard te gebruiken genoemd de Inzameling van de Kaart. Met een kaartverzameling kunt u alle verschillende typen documenten in één eenheid samenstellen. U kunt kiezen welk type van output u voor elk document in uw Inzameling van de Kaart wilt produceren. Bovendien kunt u output ook produceren en de vooruitgang van de outputgeneratie van het het publiceren dashboard zien.

De Inzameling van de kaart geeft u een optie om te bekijken als er om het even welke verandering in om het even welke kaart van de laatst gepubliceerde output is. U kunt de details op het lusje van Kaarten en van Voorinstellingen van uw Inzameling van de Kaart bekijken en dan de output indien nodig opnieuw publiceren. Voor meer informatie, zie het Toevoegen van een kaart aan een kaartinzameling.

## Een kaartverzameling maken en DITA-kaarten toevoegen

Voer de volgende stappen uit om een Kaartverzameling te maken en DITA-kaarten toe te voegen aan de verzameling:

1. Klik in de interface Middelen op **Verzamelingen toewijzen**.

   Als de koppeling Verzamelingen toewijzen niet beschikbaar is, selecteert u de optie **Navigatie** en klik op **Verzamelingen toewijzen**.

   ![](images/access-map-collection-left-rail.png){width="350" align="left"}

1. Ga een Titel voor uw kaartinzameling in.
1. Klikken **Maken**.

   Een bericht van het Succes wordt getoond bij verwezenlijking van de kaartinzameling.

1. Klikken **Sluiten** op het bericht Succes.

   Het nieuwe kaartbestand wordt weergegeven op de pagina Kaartweerzamelingen.

1. Klik op het grijze vak in de tegel van de verzameling die u wilt bewerken.
1. Klikken **Bewerken** en klik vervolgens op **Kaarten toevoegen**.
1. Zoek en voeg de DITA-kaarten toe die u aan de verzameling Kaarten wilt toevoegen.

   Standaard worden alle voorinstellingen en landinstellingen die aan de kaart zijn gekoppeld, automatisch toegevoegd.

1. Selecteer de gewenste uitvoer door de schuifknop in of uit te schakelen.
1. Klikken **Gereed**.

   De DITA kaartdossiers worden toegevoegd aan uw Inzameling van de Kaart.

   ![](images/maps_presets_62_63.png){width="800" align="left"}

De volgende filteropties en kaartdetails worden getoond op de inzamelingspagina:

- **Filter:** In de laatste spoorstaaf worden de volgende filters getoond:
   - **Gewijzigd**: U kunt Ja of Nee selecteren. Als u ja selecteert, slechts zullen de gewijzigde kaarten DITA in de Kaarten en de Vooraf ingestelde lijst worden getoond.
   - **Voorinstelling**: Selecteer een voorinstelling waarvoor u de kaartbestanden wilt uitfilteren. Als u bijvoorbeeld *Site AEM* voorinstelling, worden alleen de kaarten weergegeven die de *Site AEM* uitvoervoorinstelling geconfigureerd op deze apparaten.
   - **Taal**: U kunt om het even welke beschikbare taalcodes selecteren en slechts de geselecteerde taal in de Kaarten en Vooraf ingestelde lijst tonen.
- **Kaarten en voorinstellingen** tabel: In de tabel Kaarten en voorinstellingen vindt u informatie in de volgende kolommen:
   - **Kaart**: Toont de titel van het DITA kaartdossier.
   - **Taal**: Toont de taal van de kaart DITA.
   - **Voorinstelling**: Hiermee wordt het type uitvoervoorinstelling weergegeven dat op het kaartbestand is geconfigureerd.
   - **Gewijzigd**: Geeft aan of de DITA-kaart wordt bijgewerkt na de laatste publicatie. Gebaseerd op deze informatie, kunt u besluiten als u de output voor deze kaart wilt opnieuw publiceren DITA of niet.
   - **Laatst gegenereerd**: Hiermee geeft u de datum en tijd weer van de laatste gegenereerde uitvoer.

## Vorm en produceer de output gebruikend een Inzameling van de Kaart

Om de output te vormen en te produceren gebruikend een Inzameling van de Kaart, voer de volgende stappen uit:

1. Open de verzameling Kaarten. U kunt de verschillende uitvoervoorinstellingen bekijken, zoals de voorinstellingen AEM Site, PDF (inclusief native PDF), HTML5, EPUB en Aangepast. U kunt ook de voorinstellingen voor het algemene profiel en het mapprofiel weergeven die door de beheerder zijn gemaakt.

   De ![](images/global-preset-icon.svg) geeft een voorinstelling voor het mapprofielniveau aan.
1. \(Optioneel\) Voer naar wens een van de volgende handelingen uit:
   - Pas filters van de linkerspoorstaaf toe om de gewijzigde kaarten, de outputvooraf ingestelde, of de taal te filtreren.
   - Klik indien nodig op **Bewerken** en wijzig de gewenste uitvoer door de schuifknop in of uit te schakelen.



     >[!NOTE]
     >  
     > Nieuwe voorinstellingen worden standaard uitgeschakeld.

   - U kunt **Alle voorinstellingen voor mapprofielen in-/uitschakelen** voor een kaart DITA om alle omslagprofielen voor het in één keer te selecteren.


1. Voer een van de volgende handelingen uit:

   - Als u uitvoer van geselecteerde kaarten wilt genereren, selecteert u de kaartbestanden en klikt u op **Geselecteerde genereren**.
   - Om output van alle kaarten DITA met hun gevormde voorinstellingen te produceren, klik **Alles genereren**.
   >[!IMPORTANT]
   >
   > Als een proces voor het genereren van uitvoer voor een voorinstelling of een DITA-kaart zich in de wachtrij of in uitvoering bevindt, kunt u geen andere taak voor het genereren van uitvoer voor dezelfde voorinstelling of dezelfde kaart starten.


## Schrap een inzameling van de Kaart of een kaart DITA van de Inzameling van de Kaart

- Om een kaartinzameling te schrappen, selecteer een inzameling in de pagina van de Inzameling van de Kaart, en klik **Verwijderen**.
- Om een kaart DITA van een kaartinzameling te schrappen, open de Inzameling van de Kaart op Edit wijze, selecteer het DITA kaartdossier, en klik **Verwijderen uit verzameling**.

  Hierdoor worden ook eventuele voorinstellingen of landinstellingen die aan de DITA-kaart zijn gekoppeld, verwijderd uit de Map Collection.


## Annuleer een taak van de outputgeneratie van een Inzameling van de Kaart

Gelijkaardig aan de manier om een taak van de outputgeneratie van te annuleren [DITA-kaartconsole](generate-output-for-a-dita-map.md#id2061H100T5Z) of de [Dashboard publiceren](generate-output-publish-dashboard.md#), kunt u een taak van de outputgeneratie van een Inzameling van de Kaart annuleren. Open het lusje van Output van een Inzameling van de Kaart, ga naar de publicatietaak die u wilt annuleren, en klik **Deze taak annuleren** pictogram om de publicatietaak te annuleren.

![](images/cancel-publish-task-map-collection.png){width="800" align="left"}

**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)
