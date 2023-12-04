---
title: Opmerkingen bij de release | Adobe Experience Manager Guides as a Cloud Service, release april 2023
description: Release van Adobe Experience Manager Guides, april 2023 as a Cloud Service
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Nieuwe functies in april 2023 as a Cloud Service Adobe Experience Manager-hulplijnen

Dit artikel behandelt de nieuwe en verbeterde functies in versie april 2023 van Adobe Experience Manager-hulplijnen (later aangeduid als *Hulplijnen AEM as a Cloud Service*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u de [Opmerkingen bij de release](release-notes-2023.4.0.md) artikel.

## Geavanceerde ondersteuning voor metagegevens in PDF-publicaties

AEM Hulplijnen bieden nu geavanceerde ondersteuning voor de metagegevens die zijn toegewezen aan de metagegevens in de uitvoer van de PDF. De opties voor metagegevens bevatten informatie over het document en de inhoud ervan, zoals de naam van de auteur, de documenttitel, trefwoorden, copyrightinformatie en andere gegevensvelden.

<img src="assets/pdf-metadata.png" alt=" native PDF-metagegevens">

U kunt een XMP importeren en AEM hulplijnen kunnen de gegevens uit het bestand kiezen. U kunt ook de namen en waarden van metagegevens opgeven met het vervolgkeuzemenu. U kunt ook aangepaste metagegevens toevoegen door deze rechtstreeks in het naamveld te typen.


## Verbeterd deelvenster Omtrekweergave

AEM hulplijnen biedt een verbeterd deelvenster Omtrekweergave waarin u de hiërarchische weergave kunt zien van de elementen die in het document worden gebruikt.

<img src="assets/select-element-content-outline-view_cs.png" alt=" native PDF-metagegevens">

De omtrekweergave biedt de volgende verbeteringen:

* Het vervolgkeuzemenu Weergaveopties wordt boven in het deelvenster Omtrekweergave weergegeven. Als een element een id, kenmerk en tekst heeft, kunt u deze selecteren in het vervolgkeuzemenu en ze samen met het element weergeven. De attributen die in het paneel van de Mening van het Overzicht kunnen worden getoond worden bepaald door de montages van de Attributen van de Vertoning die door uw beheerder binnen zijn gevormd **Editor-instellingen**.

* Met de zoekfunctie kunt u naar een element zoeken op basis van de naam, id, tekst of kenmerkwaarde.


## Op microservices gebaseerde publicaties voor AEM hulplijnen as a Cloud Service

AEM de as a Cloud Service Gidsen verstrekt de eigenschap om grote het publiceren werkbelastingen met microdienst-gebaseerde het publiceren in werking te stellen en hefboomwerking het industrie-toonaangevende de serverplatform van Adobe I/O Runtime.

Nu in de versie van April kunt u veelvoudige het publiceren verzoeken tezelfdertijd in werking stellen en bulkoutput van PDF zeer efficiënt produceren gebruikend de op microdienst-gebaseerde Inheemse PDF het publiceren.
Zie voor meer informatie [Nieuwe op microservice gebaseerde publicatie configureren voor as a Cloud Service AEM hulplijnen](../knowledge-base/publishing/configure-microservices.md).
