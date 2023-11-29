---
title: Voorinstellingen voor voorwaarden gebruiken
description: Zorg dat u weet hoe voorinstellingen voor voorwaarden in AEM hulplijnen worden gebruikt. Leer voorinstellingen voor voorwaarden in AEM maken, bewerken, kopiëren en verwijderen.
exl-id: f6865a34-abdd-4d23-b903-0211bebd13b7
source-git-commit: e8a912b0f8bc690fceade0b54bb36057a727ab33
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 0%

---

# Voorinstellingen voor voorwaarden gebruiken {#id1825FL004PN}

U kunt attributen in uw onderwerpen DITA en het gebruik bepalen vooraf ingesteld om te specificeren wat met de attributen in de definitieve output gebeurt. U kunt bijvoorbeeld kenmerken als versie 1.0 en versie 2.0 toevoegen aan uw inhoud en een voorinstelling voor voorwaarden gebruiken om versie 1.0 op te nemen voor versie 1.0 en versie 2.0 uit te sluiten. Op dezelfde manier kunt u kenmerken als OS Windows en OS Linux aan uw inhoud toevoegen en vervolgens de relevante inhoud voor uw definitieve uitvoer opnemen of uitsluiten volgens het besturingssysteem.

U kunt voorinstellingen voor voorwaarden op twee manieren maken:

* Van de Redacteur van het Web: Staat u toe om de voorwaarde tot stand te brengen en te leiden stelt voor een kaart DITA van de Redacteur van het Web vooraf in.
* Vanuit het kaartdashboard: Hiermee kunt u de voorinstellingen voor een DITA-kaart maken en beheren vanaf het kaartdashboard.


## Voorinstellingen voor voorwaarden in de webeditor

Met de hulplijnen voor Experience Managers kunt u voorinstellingen voor voorwaarden beheren vanuit de webeditor en deze gebruiken in de voorinstellingen voor uitvoer om de uiteindelijke uitvoer te genereren.
U kunt de voorinstellingen voor voorwaarden maken en weergeven, de kenmerken weergeven en de acties voor de huidige kaart beheren vanuit de **Voorinstellingen voorwaarde** in de webeditor.

<img src="images//manage-condtions-presets.png" alt= "Voorinstellingen voor voorwaarden in een webeditor" width="800" border="1px">



### Een voorinstelling voor een voorwaarde maken

De **Voorinstellingen voorwaarde** In deze weergave vindt u gedetailleerde informatie over de voorinstellingen voor voorwaarden, zoals de kenmerken, waarden en handelingen.
U kunt een voorwaardenvooraf ingesteld van de onderwerpen tot stand brengen door de volgende stappen uit te voeren:

1. In de **Bewaarplaats** opent u het DITA-kaartbestand in de Kaartweergave.
1. Selecteer de **Beheren** tab.
1. Selecteren **Voorinstellingen voorwaarde** links. De lijst met voorinstellingen voor voorwaarden die voor de DITA-kaart zijn gedefinieerd, wordt weergegeven.
1. Selecteer het plus-pictogram naast **Voorinstellingen voorwaarde** om de **Nieuwe voorinstelling voorwaarde** in.
1. Voer een unieke naam in voor de voorinstelling.

   >[!NOTE]
   >
   > Er wordt een fout weergegeven als het naamveld leeg is of als u een ongeldig teken of een naam invoert die gelijk is aan een bestaande voorinstelling voor voorwaarden. U kunt een koppelteken &#39;-&#39; of onderstrepingsteken &#39;_&#39; gebruiken als scheidingsteken.

1. Selecteer **Maken**.
De nieuwe voorinstelling voor voorwaarden wordt toegevoegd aan de lijst.
1. Dubbelklik op een voorinstelling voor voorwaarden om de kenmerken en de handelingen weer te geven.
De **Attributen** worden alle kenmerken weergegeven die aan verwijzingen in de kaart zijn toegevoegd. In het rechterdeelvenster worden alleen de voorwaarden weergegeven die u hebt toegevoegd aan de voorinstellingen voor voorwaarden.
1. Voer een van de volgende handelingen uit om de kenmerken toe te voegen:
   * Selecteer een of meer kenmerken om alle waarden onder de kenmerken toe te voegen aan de voorinstelling voor de voorwaarde. U kunt bijvoorbeeld de opdracht `platform` alle waarden ervan toe te voegen.
   * Selecteer een of meer kenmerkwaarden om deze aan de voorinstelling voor voorwaarden toe te voegen. U kunt bijvoorbeeld de opdracht `Unix` en `Win` waarden van het platformkenmerk
   * Selecteer een willekeurig kenmerk en waardepaar en sleep dit naar het middelste deelvenster. U kunt bijvoorbeeld de opdracht `Unix` waarde van het platformattribuut en sleep het.
   * **Alles selecteren** om alle kenmerken en de bijbehorende waarden toe te voegen aan de voorinstelling voor voorwaarden.
Standaard is de actie voor een kenmerk `Include`.

1. Selecteren **Toevoegen**. U kunt deze stap herhalen om meer kenmerken toe te voegen. De kenmerken die u toevoegt, gaan van het midden naar het rechterdeelvenster.
1. Selecteer Verwijderen op de actiebalk bovenaan om de geselecteerde kenmerken in het rechterdeelvenster te verwijderen.
1. (Optioneel) Indien nodig kunt u de actie die op de kenmerken is toegepast, overschrijven.
Voer een van de volgende handelingen uit:
   * Selecteer voor een willekeurig kenmerk een van de volgende handelingen in de vervolgkeuzelijst Handeling.
      * Inclusief
      * Uitsluiten
      * Passthrough
      * Markering
   * Selecteer meerdere kenmerkrijen in het rechterdeelvenster en kies een handeling in de actiebalk bovenaan. U kunt bijvoorbeeld de actie Uitsluiten selecteren voor de geselecteerde kenmerken.
1. Selecteren **Opslaan** om de voorinstelling voor de voorwaarde op te slaan.

   >[!NOTE]
   >
   > U geeft een waarschuwing weer als u een andere voorinstelling selecteert of de voorinstelling sluit zonder deze op te slaan.

Als u een voorinstelling voor voorwaarden hebt gemaakt, wordt deze onder de **Voorinstellingen voorwaarde** vervolgkeuzelijst met voorinstellingen voor uitvoer. Meer informatie over hoe [PDF-uitvoer publiceren](../web-editor/native-pdf-web-editor.md).

### De naam van een voorinstelling voor een voorwaarde wijzigen

Voer de volgende stappen uit om de naam van een voorinstelling voor een voorwaarde te wijzigen:

1. Houd de muisaanwijzer boven een voorinstelling voor een voorwaarde in het dialoogvenster **Voorinstellingen voorwaarde** deelvenster.
1. Selecteren **Naam wijzigen** in het menu Opties om het dialoogvenster **Naam voorinstelling voorwaarde wijzigen** in.
1. Bewerk de naam van de voorinstelling voor voorwaarden.
1. Klikken **Naam wijzigen**.

### Voorinstelling voorwaarde dupliceren

Voer de volgende stappen uit om een voorinstelling voor een voorwaarde te dupliceren:

1. Houd de muisaanwijzer boven een voorinstelling voor een voorwaarde in het dialoogvenster **Voorinstellingen voorwaarde** deelvenster.
1. Selecteren **Dupliceren** in het menu Opties om het dialoogvenster **Voorinstelling voorwaarde dupliceren** in.
   >[!NOTE]
   >
   > De standaardnaam van de voorinstelling is `<selected condition preset name>_1`. U kunt de naam naar wens wijzigen.

1. Klikken **Dupliceren**.

### Voorinstelling voorwaarde verwijderen

Voer de volgende stappen uit om voorinstellingen voor voorwaarden te verwijderen:

1. Houd de muisaanwijzer boven een voorinstelling voor een voorwaarde in het dialoogvenster **Voorinstellingen voorwaarde** deelvenster.
1. Selecteren **Verwijderen** in het menu Opties om het dialoogvenster **Voorinstelling voorwaarde verwijderen** in.
1. Klikken **Verwijderen**.



## Voorinstellingen voor voorwaarde van het kaartdashboard


### Een voorinstelling voor een voorwaarde maken

Voer de volgende stappen uit om een voorinstelling voor een voorwaarde te maken:

1. Selecteren **Voorinstellingen voorwaarde** in de DITA kaartconsole.
1. Klikken **Maken** knop.
1. Geef een naam op voor de voorinstelling in **Voorwaarde naam**.
1. Selecteer een van de volgende standaardhandelingen uit **Standaardhandeling instellen op** vervolgkeuzelijst:

   * Inclusief
   * Uitsluiten
   * Passthrough
   * Markering De handeling wordt ingesteld als standaardhandeling voor alle kenmerken, ongeacht of deze worden toegevoegd aan de voorinstelling van de voorwaarde of niet.

   U hebt bijvoorbeeld 15 voorwaardelmerken in uw document en er zijn er vier opgenomen in de voorinstelling voor voorwaarden. Als u **uitsluiten** als standaardactie, wordt het toegepast op alle 15 attributen.

1. Voer een van de volgende handelingen uit om de kenmerken toe te voegen:
   * Klikken **Toevoegen** naar één kenmerk van de voorinstelling voor voorwaarden. U kunt deze stap herhalen om meer kenmerken toe te voegen.
   * Klikken **Alles toevoegen** om alle kenmerken toe te voegen aan de voorinstelling voor voorwaarden.
1. \(Optioneel\) Indien nodig, kunt u de standaardhandeling negeren die op de kenmerken in Stap 4 wordt toegepast. Voer een van de volgende handelingen uit:
   * Selecteer meerdere kenmerken en kies een handeling uit **De actie voor geselecteerde voorwaarden instellen op** en klik op **Toepassen**.
   * Selecteer een handeling voor een kenmerk in het menu **Handeling** vervolgkeuzelijst.
1. Klikken **Opslaan**.

### Een voorinstelling voor een voorwaarde bewerken

U kunt wijzigingen aanbrengen in een bestaande voorinstelling voor voorwaarden om de acties te wijzigen die worden toegepast op de kenmerken in de voorinstelling voor voorwaarden. Voer de volgende stappen uit om een voorinstelling voor een voorwaarde te bewerken:

1. Selecteren **Voorinstellingen voorwaarde** in de DITA kaartconsole.
1. Klikken **Bewerken** knop.
1. Breng de vereiste wijzigingen aan voor alle kenmerken in de voorinstelling voor de voorwaarde.
1. Klikken **Opslaan**.

### Een kopie maken van een voorinstelling voor voorwaarden

U kunt een kopie van een voorinstelling voor voorwaarden maken en deze vervolgens naar wens wijzigen. Voer de volgende stappen uit om een kopie van een voorinstelling voor een voorwaarde te maken:

1. Selecteren **Voorinstellingen voorwaarde** in de DITA kaartconsole.
1. Klikken **Dupliceren** knop.

   >[!NOTE]
   >
   > De standaardnaam van de voorinstelling is `<selected condition preset name>_Duplicate`

   U kunt de naam naar wens wijzigen.

1. \(Optioneel\) Breng de vereiste wijzigingen aan voor alle kenmerken in de voorinstelling.
1. Klikken **Opslaan**.

### Voorinstelling voorwaarde verwijderen

U kunt een of meer voorinstellingen voor voorwaarden verwijderen uit het dialoogvenster **Voorinstelling voorwaarde** van de DITA kaartconsole. Voer de volgende stappen uit om voorinstellingen voor voorwaarden te verwijderen:

1. Selecteren **Voorinstellingen voorwaarde** in de DITA kaartconsole.
1. Selecteer de voorinstelling voor voorwaarden die u wilt verwijderen.
1. Klikken **Verwijderen** knop.
1. Klikken **Verwijderen** om de actie te bevestigen.

**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)
