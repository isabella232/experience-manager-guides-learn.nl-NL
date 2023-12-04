---
title: Opmerkingen bij de release | Nieuwe functies in de Adobe Experience Manager-hulplijnen, release november 2023
description: Leer de nieuwe en verbeterde functies in de release van Adobe Experience Manager Guides van november 2023 as a Cloud Service.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 0%

---

# Nieuwe functies in de release van Adobe Experience Manager Guides van november 2023 as a Cloud Service

Dit artikel behandelt de nieuwe en verbeterde eigenschappen in versie November 2023 van de Gidsen van Adobe Experience Manager (later genoemd als *Experience Manager-hulplijnen as a Cloud Service*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u [Opmerkingen bij de release](release-notes-2023.11.0.md).

## Native PDF-verbeteringen

De volgende Native PDF-verbeteringen zijn uitgevoerd in de release van november 2023:

### PDF-sjablonen buiten de box gebruiken en dupliceren

De Gidsen van de Experience Manager verstrekt out-of-the-box of de malplaatjes van de fabrieksPDF. Dupliceer de PDF sjablonen van de factory om de aangepaste PDF-sjablonen te maken.

U kunt nu ook een voorbeeld van de miniatuurafbeelding voor een sjabloon bekijken terwijl u een sjabloon maakt en dupliceert. U kunt deze afbeelding ook bewerken of verwijderen. Deze functie is handig voor het brandmerken of het onderscheiden van sjablonen met vergelijkbare namen.
Meer informatie over de [PDF-sjabloon](../native-pdf/pdf-template.md).

![Sjabloon PDF dupliceren, dialoogvenster](assets/duplicate-template.png){width="550" align="left"}

*Een bestaande PDF-sjabloon dupliceren.*


### De volgorde van pagina&#39;s wijzigen en meerdere pagina&#39;s per vel publiceren

Naast het publiceren van de pagina&#39;s volgens het brondocument, kunt u ook de volgorde van pagina&#39;s in PDF wijzigen terwijl u een document met meerdere pagina&#39;s publiceert.  Dit biedt u de flexibiliteit om de pagina&#39;s in verschillende volgorden, zoals alle oneven, of alle even pagina&#39;s eerst te publiceren. U kunt de pagina&#39;s ook als een boek publiceren en lezen. U kunt ook het aantal pagina&#39;s bepalen dat u op één vel papier wilt publiceren. Voor meer informatie bekijkt u de [Paginaorganisatie](../native-pdf/components-pdf-template.md#page-organization) sectie.

### Woordenlijsttermen sorteren op basis van sorteersleutels

U kunt nu ook de woordenlijsttermen sorteren op basis van de sorteertoetsen. U kunt de tag &#39;sort-as&#39; gebruiken om een sorteersleutel voor de termen in de woordenlijst te definiëren. Vervolgens kunt u de termen sorteren op sorteertoetsen in plaats van op termen. Op deze manier kunt u de termen in de woordenlijst sorteren op basis van termen die in verschillende talen worden gebruikt. U kunt ook één sorteersleutel definiëren voor een woordenlijstterm met een woordgroep of woordgroep.
Voor meer informatie bekijkt u de [Geavanceerde PDF-instellingen](../native-pdf/components-pdf-template.md#advanced-pdf-settings).


### Verbeterd resourcebeheer voor Native PDF-sjablonen

De Gidsen van de Experience Manager heeft nu het middelbeheer voor de Malplaatjes van de Native PDF verbeterd. U kunt nu bronnen, zoals afbeeldingen, CSS-bestanden en lettertypebestanden, delen en opnieuw gebruiken voor meerdere Native PDF-sjablonen. Met deze verbetering, is het beheren van de middelen voor een grote reeks malplaatjes veel eenvoudiger. U hoeft geen dubbele bronnen voor elke sjabloon te maken en u kunt deze in een gedeelde map bewaren en ze in alle Native PDF-sjablonen gebruiken.
Voor meer informatie, bekijkt u [PDF-sjabloon](../native-pdf/pdf-template.md).

## Verbeteringen in de webeditor

De volgende verhogingen van de Redacteur van het Web zijn gedaan in de versie van november 2023:


### Bestanden weergeven op titel of bestandsnamen

U kunt nu de standaardmanier kiezen om de bestanden weer te geven in de webeditor. U kunt de lijst met bestanden weergeven op basis van de titels of de bestandsnamen in de verschillende deelvensters in de weergave Auteur.

![Dialoogvenster Gebruikersvoorkeuren](assets/user-preferences-2311.png){width="550" align="left"}

*De standaardmanier wijzigen om de bestanden weer te geven vanuit de **Gebruikersvoorkeuren**in.*


### Voorinstellingen voor voorwaarden beheren

U kunt voorwaardenattributen in uw onderwerpen bepalen DITA. Gebruik vervolgens de voorwaardelmerken in de voorinstelling voor voorwaarde om de inhoud in een DITA-kaart te publiceren. Met de hulplijnen voor Experience Managers kunt u nu ook voorinstellingen voor voorwaarden maken en beheren in de webeditor. U kunt ze ook gemakkelijk bewerken, dupliceren of verwijderen.

![Voorinstellingen voorwaarde op het tabblad Beheren van de webeditor ](assets/web-editor-manage-condition-presets.png){width="550" align="left"}

Voor meer informatie, bekijkt u [Voorinstellingen voor voorwaarden gebruiken](../user-guide/generate-output-use-condition-presets.md).

### Bestandstabbladen herstellen bij vernieuwen van browser

De Gidsen van de Experience Manager herstelt de staat van de geopende dossierlusjes in de Redacteur van het Web wanneer u browser vernieuwt. Voor meer informatie bekijkt u de **Browser vernieuwen tijdens bewerken van bestanden** deel onder [Onderwerpen bewerken in de webeditor](../user-guide/web-editor-edit-topics.md).

### Eenvoudig een element opheffen

Nu kunt u een element gemakkelijk ontkoppelen gebruikend de optie van het contextmenu van een element in de Redacteur van het Web. Hierdoor kunt u de tekst van het element gemakkelijk samenvoegen met het bovenliggende element.
Voor meer informatie bekijkt u de **Een element opheffen** van de [andere functies in de webeditor](../user-guide/web-editor-other-features.md).

### Sneltoetsen om de cursor te verplaatsen

Met de hulplijnen voor Experience Managers kunt u nu ook sneltoetsen gebruiken om de cursor in de webeditor te verplaatsen. Met de sneltoetsen kunt u snel één woord naar links of rechts verplaatsen. U kunt ook naar het begin of einde van de regel gaan met behulp van de sneltoetsen.
Nu kunt u ook sneltoetsen gebruiken om de cursor naar het begin van het volgende element of naar het einde van het vorige element te verplaatsen.
Meer informatie over de [sneltoetsen in de webeditor](../user-guide/web-editor-keyboard-shortcuts.md).
