---
title: Werken met de basiskaarteditor
description: Leer hoe u met de Basic Map Editor kunt werken
source-git-commit: af5c64312a608affe95fd552b3dd1b2e05ea2b8e
workflow-type: tm+mt
source-wordcount: '1394'
ht-degree: 0%

---


# Werken met de basiskaarteditor {#id1942CM005Y4}

De Basis Redacteur van de Kaart verstrekt een gemakkelijke belemmering-en-dalingseigenschap om onderwerpen van uw AEM bewaarplaats toe te voegen om de kaart DITA of bookmap tot stand te brengen. U kunt geneste onderwerpen, relatietabellen \(reltable\), attributen en meta-gegevensinformatie toevoegen, en ook de kaart voor correctheid bevestigen.

>[!NOTE]
>
> Als uw beheerder de Geavanceerde optie van de Redacteur van de Kaart heeft toegelaten, dan zult u geen toegang tot de BasisRedacteur van de Kaart hebben. Alle kaartdossiers zullen in de Geavanceerde Redacteur van de Kaart door gebrek openen.

De volgende secties beschrijven de diverse functies beschikbaar in de Basis Redacteur van de Kaart.

## Onderwerpen toevoegen aan een kaartbestand {#id193CBL0505Z}

Zodra een kaartdossier wordt gecreeerd, moet u onderwerpen aan het kaartdossier toevoegen. Gebruikend de Basis Redacteur van de Kaart, kunt u onderwerpen, relatietabellen, of andere kaartdossiers toevoegen.

Voer de volgende stappen uit om uw kaartbestand te maken:

1. Navigeer in de interface Elementen naar het kaartbestand dat u wilt bewerken.

1. Als u het kaartbestand exclusief wilt vergrendelen, selecteert u het kaartbestand en klikt u op **Uitchecken**.

   >[!NOTE]
   >
   > Als u eenmaal een exclusief kaartbestand hebt vergrendeld, kunnen andere gebruikers de kaart niet meer bewerken. Ze kunnen echter wel aan de onderwerpen in het kaartbestand werken.

1. Selecteer het kaartbestand en klik op **Bewerken**.

   Het kaartbestand wordt geopend voor bewerking in de Kaarteditor. Gebruikend de Redacteur van de Kaart, bouwt u een kaart door de momenteel beschikbare onderwerpen te gebruiken die in de spoorstaaf van Verwijzingen worden getoond.

   ![](images/dita-map-01.png)

1. Met de **Verwijzingen** per spoor, navigeer naar de map die de onderwerpen of submaps bevat die u wilt toevoegen.

   >[!NOTE]
   >
   > U kunt onderwerpen of submaps van om het even welke omslag in de spoorstaaf van Verwijzingen toevoegen.

1. Om het eerste onderwerp aan de kaart toe te voegen, sleep-en-daling het onderwerp op de Basis Redacteur van de Kaart.

   >[!NOTE]
   >
   > Nadat u de eerste koppeling hebt toegevoegd, is de koppeling Nieuwe verwijzing toevoegen beschikbaar wanneer u de muisaanwijzer op een bestaand onderwerp in de kaart plaatst.

1. Als u volgende onderwerpen of een submap wilt toevoegen, sleept u het onderwerp of de submap naar de gewenste locatie in de kaart en zet u deze neer.

   Als u een sub-kaart aan uw kaart DITA toevoegt, wordt submap getoond als verbinding in de kaart DITA. Om alle onderwerpen van sub-kaart te bekijken, klik de sub-kaart verbinding. De inhoud van de submap wordt weergegeven op een nieuw tabblad.

   >[!NOTE]
   >
   > Als u een nieuw onderwerp op een bestaand onderwerp in de kaart laat vallen, krijgt u een bericht over het vervangen van het onderwerp. Klik ja als u het onderwerp wilt vervangen, Nr klikken als u niet het onderwerp wilt vervangen. U kunt CTRL+Z en CTRL+Y gebruiken om wijzigingen in de kaart ongedaan te maken of opnieuw uit te voeren.

1. Klikken **Opslaan**.


## Functies beschikbaar op de werkbalk van de Basic Map Editor

Met de hoofdwerkbalk in de Basic Map Editor kunt u de volgende taken uitvoeren:

![](images/ditamap-toolbar-actions.png)

**A: Zoeken**

U kunt naar de vereiste onderwerpen van DAM zoeken en omvatten. Wanneer u op dit pictogram klikt, wordt het dialoogvenster Zoeken weergegeven:

![](images/search-dita-map.png)

Voer de trefwoorden in waarnaar u wilt zoeken. Deze trefwoorden komen overeen met de bestandsnaam, inhoud en zelfs kenmerkwaarden van het onderwerp. Als de zoekresultaten beschikbaar zijn, selecteert u het gewenste onderwerp en klikt u op de knop Controleren om de geselecteerde bestanden toe te voegen aan het einde van de kaartstructuur. U kunt de zoekresultaten filteren door de parameters Wijzigen van datum op te geven.

**B: Groep**

Klik checkbox links van de onderwerpen en klik Groep in de toolbar om de geselecteerde onderwerpen te groeperen. Voor meer informatie over het groeperen van onderwerpen, zie [topgroep](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) documentatie in OASIS DITA Language Specification.

**C: Verwijderen**

Klik checkbox links van een onderwerp en klik Schrapping in de toolbar om de geselecteerde onderwerpen van de kaart te verwijderen.

**D: Getallen tonen/Getallen verbergen**

Nummering \(of verbergen\) weergeven voor de onderwerpen in de kaart.

**E: Valideren**

Controleer of de kaart geldig is of fouten bevat.

**F: Standaardmodus/XML-modus**

In de **Standaardmodus** Als u op een onderwerpkoppeling klikt, wordt de voorvertoning van het onderwerp op een nieuw tabblad weergegeven. Klik op de knop **Standaardmodus** pictogram wijzigt modus in **XML-modus**. In **XML-modus**, toont het klikken overal in een onderwerpregel onderliggende XML van onderwerpverwijzingen binnen het onderwerp. In de XML-bronweergave is er een **Automatisch inspringen** Hiermee kunt u de XML-code opnieuw ordenen in een vorm die presenteerbaar en gemakkelijk leesbaar is. Als u een kaart handmatig bewerkt, voert de bronweergave ook validatiecontroles uit. Als uw XML fouten bevat, wordt hetzelfde gemarkeerd in het dialoogvenster **XML-modus** en u mag het DITA-kaartbestand niet opslaan. Als u XML voor de volledige kaart wilt bekijken, klik overal buiten de onderwerpgrens.


**Opmerking:** In de standaardmodus kunt u de sneltoetsen gebruiken om \(`Ctrl+z`\) of opnieuw uitvoeren \(`Ctrl+y`\) de laatste handeling.


![](images/dita-map-invalid-source.png)

**G: Eigenschappen van kaart**

Geef het dialoogvenster Eigenschappen kaart weer waarin u de kenmerken en metagegevens voor de kaart kunt instellen. Als u een kenmerk wilt toevoegen, klikt u op de knop **Toevoegen** in de linkerbenedenhoek van het dialoogvenster om het dialoogvenster **Kenmerk** vervolgkeuzelijst. Selecteer in de lijst het kenmerk dat u wilt toevoegen. Als voor het geselecteerde kenmerk vooraf gedefinieerde waarden zijn opgegeven in het DTD-bestand, worden deze waarden weergegeven in een nieuwe vervolgkeuzelijst. U kunt de gewenste waarde selecteren in de vervolgkeuzelijst. Als er geen vooraf gedefinieerde waarde is, wordt een tekstvak weergegeven waarin u een waarde voor het geselecteerde kenmerk kunt invoeren.

![](images/map-properties.png)

## Functies beschikbaar op onderwerpniveau in de Basic Map Editor

Wanneer u de muiswijzer over een onderwerp of een sub-kaartdossier in de Basis Redacteur van de Kaart beweegt, kunt u de volgende taken uitvoeren:

![](images/ditamap-actions.png)

**A: Naar links of rechts verplaatsen**

Klik op de pictogrammen voor pijl-links of pijl-rechts om het onderwerp naar links of rechts te verplaatsen. Als u een onderwerp op een dergelijke manier verplaatst, wordt dit een onderliggend onderwerp \(nesten\) of wordt \(nesten verwijderen\) verwijderd ten opzichte van het onderwerp erboven.

**B: Eigenschappen**

Klik op het pictogram Eigenschappen om het dialoogvenster Eigenschappen van Topicref te openen. In dit dialoogvenster kunt u de onderwerpkenmerken en metagegevens instellen. Voor meer informatie over de standaardonderwerpattributen en meta-gegevens, zie [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) documentatie in OASIS DITA Language Specification.


![](images/map-properties-metadata.png)

**C: Nieuwe verwijzing toevoegen**

Klik op het pictogram Nieuwe verwijzing toevoegen om een nieuwe verwijzing op hetzelfde niveau als het huidige onderwerp toe te voegen.

**D: Nieuwe sleuteldefinitie toevoegen**

Klik op het pictogram Key om een nieuwe sleuteldefinitie toe te voegen. Overschreven toetsen of toetsen die al in de kaart zijn gedefinieerd, worden rood weergegeven. Als u op het pictogram Eigenschappen op een sleuteldefinitie klikt, wordt het dialoogvenster Eigenschappen van keydef weergegeven.

## Werken met relatietabellen in de Basic Map Editor {#id1944B0I0COB}

AEM de kaartredacteurs van Gidsen komen met een krachtige eigenschap die u toestaat om relatietabellen in uw kaart te creëren en uit te geven DITA.

Voer de volgende stappen uit om met relatietabellen in de BasisRedacteur van de Kaart te werken:

1. In Elementen UI, navigeer aan de kaart DITA waarin u de relatietabel wilt tot stand brengen.

1. Klik op de kaart DITA om het in DITA kaartconsole te openen.

1. Selecteer **Onderwerpen** om een lijst van onderwerpen te zien beschikbaar in de kaart DITA.

   >[!TIP]
   >
   > Het lusje van Onderwerpen geeft u een optie om het kaartdossier met zijn gebiedsdelen te downloaden. Zie voor meer informatie [Een DITA-toewijzingsbestand exporteren](authoring-download-assets.md#id218UBA00IXA).

1. Klik in de hoofdwerkbalk op **Bewerken**.

   Het kaartbestand wordt geopend in de Basic Map Editor.

1. Selecteren **Releerbaar** op de werkbalk.

   ![](images/reltable.png)

1. De belemmering-en-dalingsonderwerpen van de onderwerpenlijst aan de Reltable redacteur.

   >[!NOTE]
   >
   > U kunt onderwerpen vanuit elke map toevoegen in de References-rail.

   ![](images/create-reltable.png)

1. Als u een koptekst wilt toevoegen aan uw relatietabel, klikt u op **Relheader toevoegen**.

1. Als u een kolom wilt toevoegen aan uw relatietabel, klikt u op **Een kolom toevoegen**.

   ![](images/complete-reltable.png)

1. Klikken **Opslaan**.


U kunt de volgende acties van de redacteur van de relatietabel ook uitvoeren:

**Rijen of kolommen verwijderen**

Als u een kolom uit de tabel wilt verwijderen, schakelt u het selectievakje in de kolomkop in en klikt u op Verwijderen. Als u een rij uit tabel wilt verwijderen, schakelt u het selectievakje in de eerste kolom van de desbetreffende rij in en klikt u op Verwijderen.

**Een onderwerp verwijderen**

Als u een onderwerp van uw lijst wilt schrappen, klik het dwarspictogram naast het onderwerp.

**De relatietabel verwijderen**

Als u de relatietabel wilt verwijderen, klikt u ergens buiten de relatietabel en klikt u op Verwijderen.

**Bovenliggend onderwerp:**[ Werken met de Kaarteditor](map-editor.md)

