---
title: Andere functies in de kaarteditors
description: Ontdek enkele veelvoorkomende functies in de Basic- en Advanced Map Editors. Leer hoe u belangrijke verwijzingen in de Kaart-editor kunt oplossen.
exl-id: ed6f42f6-b95e-4c4d-a648-6f29641a3488
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Andere functies in de kaarteditors {#id1942D0T0HUI}

Enkele veelvoorkomende functies in de Basic- en Advanced Map Editors zijn:

## Belangrijke verwijzingen oplossen {#id176GD01H05Z}

Een DITA-inhoudsreferentie, of `conkeyref` is een mechanisme om een deel van inhoud van één onderwerp in een andere op te nemen. Dit mechanisme gebruikt sleutel om van de inhoud de plaats te bepalen om te hergebruiken eerder dan het directe inhoud verwijzende mechanisme. Voor meer informatie over direct en indirect verwijzen in DITA, zie *DITA-adressering* in OASIS DITA Language Specification.

Als het onderwerp DITA bijbehorende zeer belangrijke verwijzingen heeft, dan moeten zij worden opgelost alvorens, een onderwerp te previewing uit te geven of te herzien.

De belangrijkste verwijzingen worden opgelost op basis van de wortelkaart die in de volgende orde van prioriteit wordt geplaatst:

1. Gebruikersvoorkeuren
1. Deelvenster Kaartweergave
1. Mapprofiel

De hoofdmap die u in de gebruikersvoorkeuren hebt geselecteerd, krijgt de hoogste prioriteit om toetsverwijzingen op te lossen, gevolgd door het deelvenster Kaartweergave en de hoofdmap van het mapprofiel. Als er dus geen kaart is ingesteld in de gebruikersvoorkeuren, wordt de kaart gebruikt die is geopend in het deelvenster Kaartweergave. Als er geen kaart is geopend in het deelvenster Kaartweergave, wordt de kaart die is ingesteld in de Mapprofielen gebruikt om de toetsverwijzingen op te lossen.

De belangrijkste verwijzingen kunnen binnen een DITA kaartdossier of een afzonderlijk DITA- dossier worden opgeslagen. In AEM Gidsen, kunt u zeer belangrijke verwijzingen of op het projectniveau of een zittingsniveau specificeren. Als er al een hoofdmap is gedefinieerd voor de gebruikerssessie, wordt deze gebruikt voor het oplossen van de toetsen. Anders wordt de standaardhoofdmap voor die map gebruikt. Als er geen standaardhoofdmap is geconfigureerd, worden de ontbrekende toetsverwijzingen gemarkeerd voor de gebruiker.

Er zijn verscheidene manieren om zeer belangrijke verwijzingen in een onderwerp op te lossen DITA door de kaart te bepalen DITA die op de volgende plaatsen moet worden gebruikt:

**Projecteigenschappen** - U kunt een wortelkaart voor het oplossen van zeer belangrijke verwijzingen bepalen terwijl het creëren van een Project in de sectie van de Eigenschappen van het Project.

Deze hoofdmap is van toepassing op alle elementen \(mappen en submappen\) die bij dat project horen. Voor inhoud die in veelvoudige projecten van verwijzingen wordt voorzien, wordt een alfabetische lijst van projecten gehandhaafd en de standaardwortelkaart verbonden aan het eerste project wordt gebruikt. U kunt ook de DITA-kaart kiezen die u wilt gebruiken in de lijst voor het oplossen van toetsverwijzingen.

**Voorvertoning onderwerp** - Klik in de modus Overzicht van onderwerpen op het pictogram Hoofdresolutie op de werkbalk en selecteer het DITA-bestand dat moet worden gebruikt voor toetsverwijzingen.

**Weergave Onderwerpen bewerken** - Klik op het pictogram Hoofdresolutie tijdens het bewerken van een DITA-onderwerp en selecteer het DITA-bestand dat u wilt gebruiken voor het oplossen van de belangrijkste referenties.

**Bovenliggend onderwerp:**[ Werken met de Kaarteditor](map-editor.md)
