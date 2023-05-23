---
title: Standaardwoordenboek AEM aanpassen
description: Leer hoe u AEM standaardwoordenboek kunt aanpassen
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---


# Standaardwoordenboek AEM aanpassen {#id209SD8000WU}

De Redacteur van het Web kan worden gevormd om AEM spellingcontrole of browser spellingcontrole te gebruiken. Als u ervoor kiest om met AEM spellingcontrole te werken, dan krijgt u de flexibiliteit om uw lijst van douanewoorden te bepalen. Deze aangepaste woorden worden vervolgens toegevoegd aan het AEM-woordenboek en deze woorden worden niet gemarkeerd als \(incorrect\) in de webeditor.

Voer de volgende stappen uit om uw lijst van douanewoorden tot stand te brengen, die in AEM woordenboek wordt toegevoegd:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het volgende knooppunt:

   /apps/fmdita/config

1. Maak een nieuw bestand met de naam user\_dictionary.txt.

1. Open het bestand en voeg een lijst toe met woorden die u in het aangepaste woordenboek wilt definiëren.

   In de volgende schermafbeelding ziet u een lijst met aangepaste woorden die aan het bestand user\_dictionary.txt is toegevoegd:

   ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1. Sla het bestand op en sluit het.


Auteurs moeten hun Web Editor-sessie opnieuw starten om de lijst met aangepaste woorden in AEM woordenboek bij te werken.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)

