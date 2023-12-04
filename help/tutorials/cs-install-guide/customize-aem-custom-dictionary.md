---
title: Standaardwoordenboek AEM aanpassen
description: Leer hoe u AEM standaardwoordenboek kunt aanpassen
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Standaardwoordenboek AEM aanpassen {#id209SD8000WU}

De Redacteur van het Web kan worden gevormd om AEM spellingcontrole of browser spellingcontrole te gebruiken. Als u ervoor kiest om met AEM spellingcontrole te werken, dan krijgt u de flexibiliteit om uw lijst van douanewoorden te bepalen. Deze aangepaste woorden worden vervolgens toegevoegd aan het AEM-woordenboek en deze woorden worden niet gemarkeerd als \(incorrect\) in de webeditor.

Voer de volgende stappen uit om uw lijst van douanewoorden tot stand te brengen, die in AEM woordenboek wordt toegevoegd:

1. Maak het bestand user\_dictionary.txt met een lijst met woorden die u in het aangepaste woordenboek wilt definiëren.

   >[!NOTE]
   >
   > Elk aangepast woord moet op een nieuwe regel worden gedefinieerd.

1. Sla het bestand op de volgende locatie op in de Git-opslagplaats van uw Cloud Manager:

   /apps/fmdita/config

1. Sla het bestand op.

   Leg de wijzigingen vast en voer de Cloud Manager \(CI/CD\)-pijplijn uit om configuratiewijzigingen te implementeren.


Auteurs moeten hun Web Editor-sessie opnieuw starten om de lijst met aangepaste woorden in AEM woordenboek bij te werken.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
