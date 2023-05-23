---
title: Opmerkingen bij de release | Nieuwe functies in de release van Adobe Experience Manager Guides 4.2.1
description: Leer de nieuwe en verbeterde functies in 4.2.1-releases van Adobe Experience Manager-hulplijnen
source-git-commit: 6a1c6383f827bcd1e388290a793b69d372b7e7ce
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 0%

---

# Nieuwe functies in versie 4.2.1 van Adobe Experience Manager-hulplijnen (mei 2023)

Dit artikel behandelt de nieuwe en verbeterde functies in versie 4.2.1 van de Gidsen van Adobe Experience Manager (later genoemd *Hulplijnen AEM*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u de [Opmerkingen bij de release](release-notes-4.2.1.md) artikel.

## Navigeer van de Redacteur van het Web aan de AEM homepage

Nu kunt u gemakkelijk van de Redacteur van het Web aan de pagina van de Navigatie van de AEM navigeren.

![](assets/web-editor-launch-page.png){width="800" align="left"}

* Klik op de knop **Hulplijnen** icon (![](assets/aem-guides-icon.png) ), om terug te gaan naar de AEM navigatiepagina.


Zie voor meer informatie [Navigatiepagina AEM](../user-guide/web-editor-launch-editor.md#id2056BG00RZJ).

## Geavanceerde ondersteuning voor metagegevens in PDF-publicaties

AEM Hulplijnen bieden nu geavanceerde ondersteuning voor de metagegevens die zijn toegewezen aan de metagegevens in de uitvoer van de PDF. De opties voor metagegevens bevatten informatie over het document en de inhoud ervan, zoals de naam van de auteur, de documenttitel, trefwoorden, copyrightinformatie en andere gegevensvelden.

<img src="assets/pdf-metadata.png" alt=" native PDF-metagegevens">

U kunt een XMP importeren en AEM hulplijnen kunnen de gegevens uit het bestand kiezen. U kunt ook de namen en waarden van metagegevens opgeven met het vervolgkeuzemenu. U kunt ook aangepaste metagegevens toevoegen door deze rechtstreeks in het naamveld te typen.

Zie voor meer informatie **Metagegevens** functiebeschrijving in [Een voorinstelling voor PDF-uitvoer maken](../web-editor/native-pdf-web-editor.md).

### Verbeterd deelvenster Omtrekweergave

AEM hulplijnen biedt een verbeterd deelvenster Omtrekweergave waarin u de hiërarchische weergave kunt zien van de elementen die in het document worden gebruikt.

<img src="assets/select-element-content-outline-view_cs.png" alt=" native PDF-metagegevens">

De omtrekweergave biedt de volgende verbeteringen:

* Het vervolgkeuzemenu Weergaveopties wordt boven in het deelvenster Omtrekweergave weergegeven. Als een element een id, kenmerk en tekst heeft, kunt u deze selecteren in het vervolgkeuzemenu en ze samen met het element weergeven. De attributen die in het paneel van de Mening van het Overzicht kunnen worden getoond worden bepaald door de montages van de Attributen van de Vertoning die door uw beheerder binnen zijn gevormd **Editor-instellingen**.

* Met de zoekfunctie kunt u naar een element zoeken op basis van de naam, id, tekst of kenmerkwaarde.

Voor meer details, zie de de eigenschapbeschrijving van de mening van het Overzicht in [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.

## Genereer het Multimedia-rapport uit de webeditor

AEM de Gidsen verstrekt de eigenschap om de rapporten voor uw technische documenten te produceren.  Met deze functie kunt u de onderwerpenlijst weergeven en de metagegevens van uw documenten beheren. Nu kunt u ook de multimedia zien die in alle verwijzingen naar de huidige kaart wordt gebruikt vanaf de **Rapporten** in de webeditor.

U kunt het multimediapport genereren dat gedetailleerde informatie bevat over de multimedia die wordt gebruikt in uw verwijzingen in de huidige kaart. U hebt de flexibiliteit om de dossiers van verschillende media te filtreren en te sorteren die in het rapport worden vermeld.
U kunt CSV ook produceren om de huidige momentopname van multimedia te downloaden die in de kaart DITA wordt gebruikt.

<img src="assets/web-editor-reports-multimedia.png" alt="multimediapport" width="600">

Voor meer details, zie Genereer een de eigenschapbeschrijving van het multimediapport in [DITA kaartrapport van de Redacteur van het Web](../user-guide/reports-web-editor.md) sectie.

## Native PDF | De bar van de verandering om op veranderde onderwerpen in Inhoudsopgave te wijzen

Met AEM hulplijnen kunt u nu snel de gewijzigde onderwerpen in de inhoudsopgave van de PDF-uitvoer identificeren.  Het toont een veranderingsbar op de linkerzijde van de veranderde onderwerpen in TOC. U kunt op het onderwerp in TOC klikken en de gedetailleerde veranderingen bekijken.

<img src="assets/change-marker-toc.png" alt="Markeerteken in inhoudsopgave wijzigen " width="500">

Zie voor meer informatie [Werken met aangepaste wijzigingsbalken](../native-pdf/change-bar-style.md).



## Native PDF | De paginamarkering opmaken in de voetnootcomponent

Nu kunt u de paginamarkering opmaken in de voetnoten. U kunt bijvoorbeeld vierkante haakjes toevoegen of de kleur ervan wijzigen. Met deze stijlen kunnen gebruikers gemakkelijk de paginamarkeringen in het document herkennen.

Zie voor meer informatie [Aangepaste stijlen gebruiken in voetnoten](../native-pdf/footnote-number-style.md).

## Video- of audiobestanden openen en afspelen in de webeditor

AEM Hulplijnen bieden nu de functie om de audio- of videobestanden te openen en af te spelen in de webeditor. U kunt het volume of de weergave van de video wijzigen. In het snelmenu hebt u ook de opties om **Downloaden**, wijzigen **Afspeelsnelheid**, of weergave **Beeld-in-beeld**.

<img src="assets/video-web-editor.png" alt="video afspelen" width="600">

Zie de beschrijving van de functie Weergave opslagplaats in het dialoogvenster [Linkerdeelvenster](../user-guide/web-editor-features.md#id2051EA0M0HS) sectie.
