---
title: REST API voor het maken en activeren van pakketten
description: Meer informatie over de REST API voor het maken en activeren van pakketten
source-git-commit: fad5049962f258bbe59c7d172436d82b3d6cd68f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 0%

---


# REST API voor het maken en activeren van pakketten {#id198CF0260Y4}

Met de volgende REST API kunt u CRX-pakketten maken en activeren.

## Pakket maken en activeren

Een methode van de POST die tot CRX pakket leidt en activeert.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/activate

**Parameters**: De aanvraagquery bestaat uit de tekenreeks JSON-regels. Het inhoudstype van het verzoek van de POST moet worden geplaatst aan `application/json; charset=UTF-8`.

**Voorbeeld**: In het volgende voorbeeld wordt de API-aanroep met de opdracht curl getoond:

    &quot;
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)&quot; http://&lt;*ave em-guides-server*>:&lt;*poort-nummer*>/bin/fmdita/activate
    &quot;
