---
title: Alinea's in een onderwerp uitsluiten van vertaling
description: Hoe te om paragrafen binnen een onderwerp van vertaling uit te sluiten
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
source-git-commit: b5e64512956f0a7f33c2021bc431d69239f2a088
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Hoe te om paragrafen binnen een onderwerp van vertaling uit te sluiten

De eenvoudigste manier is om het kenmerk translatie=no te gebruiken.

+ Auteurs kunnen het aanvullende kenmerk invoegen als **translatie=no** in de alinea&#39;s die zij niet willen vertalen. De vertaalleverancier moet worden geïnformeerd en zij kunnen configuratie aan hun eind doen om de tekst met dit attribuut te negeren.
+ De machinevertaling OOTB (met de proefschakelaar van Microsoft Translation) vertoont hetzelfde gedrag.
+ Testen met Microsoft Translation: als u **translate=no** wordt de volledige alinea niet vertaald. Dit kenmerk kan op elk element worden gedefinieerd en de inhoud binnen dat element wordt niet vertaald.


Hier volgen enkele schermafbeeldingen die dit nader verklaren:

**Broninhoud**

![Broninhoud](assets/source-content.jpg)

**Vertaalde inhoud in het Spaans**

![Vertaalde inhoud in het Spaans](assets/trans-content.jpg)
