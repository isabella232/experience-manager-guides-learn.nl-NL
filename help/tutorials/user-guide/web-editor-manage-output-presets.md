---
title: Uitvoervoorinstellingen voor Algemeen en Mapprofiel beheren
description: Leer hoe u voorinstellingen voor algemene profielen en mapprofielen als gebruikers met beheerdersrechten maakt, bewerkt, hernoemt, dupliceert en verwijdert in AEM hulplijnen.
exl-id: 549c9fe2-77f8-423c-8b3e-b43e56055732
source-git-commit: e8a912b0f8bc690fceade0b54bb36057a727ab33
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 0%

---

# Uitvoervoorinstellingen voor Algemeen en Mapprofiel beheren {#id22BLJ0D0V1U}

De voorinstellingen voor Algemeen en Mapprofiel zijn alleen beschikbaar voor gebruikers met beheerdersrechten op mapniveau.

Als beheerder kunt u met AEM hulplijnen uitvoervoorinstellingen voor de algemene profielen en de mapprofielen maken en beheren. Vervolgens kunt u deze uitvoervoorinstellingen eenvoudig gebruiken om uitvoer te genereren voor alle mappen die betrekking hebben op dat algemene profiel of mapprofiel.

Voer de volgende stappen uit om een uitvoervoorinstelling voor de algemene profielen en mapprofielen te maken:

1. Selecteer de DITA-kaart waarvoor u een uitvoervoorinstelling wilt maken.
1. Selecteer de **Onderwerpen bewerken** van de **Opties** menu van het kaartbestand. Het kaartdossier wordt geopend voor het uitgeven in de Redacteur van het Web.
1. In de **Uitvoer** selecteert u het plus-pictogram (+) om een uitvoervoorinstelling voor uw DITA-kaart te maken.

   ![](images/add-global-output-preset.png){width="350" align="left"}

1. Voer de volgende gegevens in het dialoogvenster **Voorinstelling toevoegen** dialoogvenster:
   - Type
   - Naam
   - Doel \(voor voorinstelling voor kennisdatabase\)
1. Selecteer de **Toevoegen aan mapprofiel** Schakel het selectievakje in om een uitvoervoorinstelling voor het gerelateerde mapprofiel te maken en klik vervolgens op **Toevoegen**. De voorinstelling wordt gemaakt en wordt weergegeven onder de **Uitvoer** tabblad van alle gerelateerde kaarten. \( ![](images/global-preset-icon.svg)\) geeft een voorinstelling voor een mapprofielniveau aan.
1. Voer de configuratiedetails in. Voor meer informatie over uitvoervoorinstellingen raadpleegt u [Uitvoervoorinstellingen](./generate-output-understand-presets.md).

   >[!NOTE]
   >
   > Deze voorinstellingen die aan het mappenprofiel worden toegevoegd, zijn onafhankelijk van de kaarten. De mapspecifieke configuraties zijn dus niet aanwezig voor deze voorinstellingen.

1. U kunt de **Voorinstelling genereren** bovenaan om de uitvoer te genereren voor de toewijzingen die betrekking hebben op de gemaakte uitvoervoorinstelling. De status van het productieproces van de uitvoer wordt weergegeven. Als u de uitvoer wilt weergeven, plaatst u de muisaanwijzer boven het onderwerp en klikt u op **Uitvoer weergeven**.

>[!NOTE]
>
> AEM de Gidsen verstrekt ook een uit-van-doos PDF vooraf ingestelde output om de output voor uw kaarten te produceren DITA.

**Overige bewerkingen in het menu Opties**

U kunt ook de volgende bewerkingen uitvoeren op de voorinstelling via het menu Opties:

- Selecteer de voorinstelling als standaard-PDF-voorinstelling. Vervolgens wordt de geselecteerde voorinstelling gebruikt als de standaardvoorinstelling om de PDF-uitvoer te genereren met de opdracht **Downloaden als PDF** voor een kaart.
- **Bewerken**, **Naam wijzigen**, **Dupliceren**, of **Verwijderen** een bestaande uitvoervoorinstelling van de **Opties** -menu.

>[!NOTE]
>
> Wanneer een uitvoervoorinstelling in algemene profielen en mapprofielen wordt verwijderd, wordt deze weergegeven in alle verwante mappen en wordt de voorinstelling niet weergegeven onder de **Uitvoer** tab.

**Bovenliggend onderwerp:**[ Werken met de webeditor](web-editor.md)
