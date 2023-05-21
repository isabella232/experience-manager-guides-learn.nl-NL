---
title: Voorinstellingen voor voorwaarden gebruiken
description: Leer hoe u voorinstellingen voor voorwaarden kunt gebruiken
exl-id: cd8f8196-ba03-4a4b-9ce8-2651de4e5cc2
source-git-commit: 8073716bccacbe8d6a158b44d5106b083e3a5dcd
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Voorinstellingen voor voorwaarden gebruiken {#id1825FL004PN}

U kunt attributen in uw onderwerpen DITA en het gebruik bepalen vooraf ingesteld om te specificeren wat met de attributen in de definitieve output gebeurt. U kunt bijvoorbeeld kenmerken als versie 1.0 en versie 2.0 toevoegen aan uw inhoud en een voorinstelling voor voorwaarden gebruiken om versie 1.0 op te nemen voor versie 1.0 en versie 2.0 uit te sluiten. Op dezelfde manier kunt u kenmerken als OS Windows en OS Linux aan uw inhoud toevoegen en vervolgens de relevante inhoud voor uw definitieve uitvoer opnemen of uitsluiten volgens het besturingssysteem.

## Een voorinstelling voor een voorwaarde maken

Voer de volgende stappen uit om een voorinstelling voor een voorwaarde te maken:

1. Klikken **Voorinstellingen voorwaarde** in de DITA kaartconsole.
1. Klikken **Maken** knop.
1. Geef een naam op voor de voorinstelling in **Voorwaarde naam**.
1. Selecteer een van de volgende standaardhandelingen uit **Standaardhandeling instellen op** vervolgkeuzelijst:

   - Inclusief
   - Uitsluiten
   - Passthrough
   - Markering De handeling wordt ingesteld als standaardhandeling voor alle kenmerken, ongeacht of deze worden toegevoegd aan de voorinstelling van de voorwaarde of niet.

   U hebt bijvoorbeeld 15 voorwaardelmerken in uw document en er zijn er vier opgenomen in de voorinstelling voor voorwaarden. Als u **uitsluiten** als standaardactie, wordt het toegepast op alle 15 attributen.

1. Voer een van de volgende handelingen uit om de kenmerken toe te voegen:
   - Klikken **Toevoegen** naar één kenmerk van de voorinstelling voor voorwaarden. U kunt deze stap herhalen om meer kenmerken toe te voegen.
   - Klikken **Alles toevoegen** om alle kenmerken toe te voegen aan de voorinstelling voor voorwaarden.
1. \(Optioneel\) Indien nodig, kunt u de standaardhandeling negeren die op de kenmerken in Stap 4 wordt toegepast. Voer een van de volgende handelingen uit:
   - Selecteer meerdere kenmerken en kies een handeling uit **De actie voor geselecteerde voorwaarden instellen op** en klik op **Toepassen**.
   - Selecteer een handeling voor een kenmerk in het menu **Handeling** vervolgkeuzelijst.
1. Klikken **Opslaan**.

## Een voorinstelling voor een voorwaarde bewerken

U kunt wijzigingen aanbrengen in een bestaande voorinstelling voor voorwaarden om de acties te wijzigen die worden toegepast op de kenmerken in de voorinstelling voor voorwaarden. Voer de volgende stappen uit om een voorinstelling voor een voorwaarde te bewerken:

1. Klikken **Voorinstellingen voorwaarde** in de DITA kaartconsole.
1. Klikken **Bewerken** knop.
1. Breng de vereiste wijzigingen aan voor alle kenmerken in de voorinstelling voor voorwaarden.
1. Klikken **Opslaan**.

## Een kopie maken van een voorinstelling voor voorwaarden

U kunt een kopie van een voorinstelling voor voorwaarden maken en deze vervolgens naar wens wijzigen. Voer de volgende stappen uit om een kopie van een voorinstelling voor een voorwaarde te maken:

1. Klikken **Voorinstellingen voorwaarde** in de DITA kaartconsole.
1. Klikken **Dupliceren** knop.

   >[!NOTE]
   >
   > De standaardnaam van de voorinstelling is `<selected condition preset name>_Duplicate`

   U kunt de naam naar wens wijzigen.

1. \(Optioneel\) Breng de vereiste wijzigingen aan voor alle kenmerken in de voorinstelling.
1. Klikken **Opslaan**.

## Voorinstelling voorwaarde verwijderen

U kunt een of meer voorinstellingen voor voorwaarden verwijderen uit het dialoogvenster **Voorinstelling voorwaarde** tabblad van de DITA-kaartconsole. Voer de volgende stappen uit om voorinstellingen voor voorwaarden te verwijderen:

1. Klikken **Voorinstellingen voorwaarde** in de DITA kaartconsole.
1. Selecteer de voorinstelling voor voorwaarden die u wilt verwijderen.
1. Klikken **Verwijderen** knop.
1. Klikken **Verwijderen** om de actie te bevestigen.

**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)
