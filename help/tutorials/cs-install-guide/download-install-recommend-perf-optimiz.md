---
title: Recommendations for performance optimization
description: Meer informatie over Recommendations voor optimalisatie van prestaties
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---


# Recommendations for performance optimization {#id213BD0JG0XA}

Houd rekening met de volgende punten voor het optimaliseren van prestaties:

- Voor een optimale inhoud en een optimale indexering gaat u naar [Zoeken en indexeren van inhoud optimaliseren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html) in AEM documentatie.

- Reparatie Xerces Jar bij gebruik van aangepaste DITA-OT voor publicatie. Dit is een verplichte configuratie, afhankelijk van uw gebruiksgeval. Deze wijziging is alleen vereist als u aangepaste DITA-OT gebruikt voor het publiceren van uitvoer.

  *Vereiste configuratie*: Vervang het bestand Xerces Jar in het aangepaste DITA-OT-pakket door het bestand OOTB dat u hebt verzonden. Het standaard OOTB xercesImpl-2.11.0.jar- dossier is beschikbaar binnen /libs/fmdita/dita \ _resources/DITA-OT.zip. Zorg ervoor dat u de naam van het bestand xercesImpl-2.11.0.jar wijzigt zodat dit overeenkomt met het oude bestand Xerces Jar dat wordt vervangen. Dit kan tijdens runtime worden gedaan.

  Deze verandering vermindert de het publiceren tijd en geheugengebruik terwijl het publiceren van kaarten DITA met een groot aantal onderwerpen.


**Bovenliggend onderwerp:**[ Downloaden en installeren](download-install.md)

