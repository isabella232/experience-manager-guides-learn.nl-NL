---
title: Gidsen die Benchmarks op AEMaaCS publiceren
description: Begrijp systeembeperkingen bij het publiceren op AEM Cloud.
source-git-commit: e64430bb968b18090c3981cc2d21ebe6593ba933
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 4%

---


# AEM Publishing Benchmarks op AEMaaCS

AEM de cloud-service Hulplijnen kent momenteel een aantal beperkingen voor het publiceren van kaartgrootten die het team van hulplijnen actief moet oplossen.

Het team van gidsen heeft reeds scalable geïntroduceerd [Microservice publiceren](publish-microservice-architecture-and-performance.md) om grote kaarten en veelvoudige gezamenlijke het publiceren te steunen. Voor nu, steunt deze microservice een ondergroep outputtypes en de steun voor andere types is in actieve ontwikkeling.

Zie voor het configureren van de nieuwe publicatieservice voor elke AEM cloudomgeving [Nieuwe op microservice gebaseerde publicatie configureren](configure-microservices.md)

## Uitvoeromgeving

    AEM: 2023.5.11983.20230511T173830Z
    Hulplijn toevoegen bij loslaten: 2023,6,0
    Sjabloon AEM site: OOTB-sjabloon voor hulplijnen AEM
    DITA-OT-versie: 3.5.4.
    Type publicatieworkflow: Publicatieworkflow splitsen
    Uitvoer ondersteund door microservice: Native PDF, PDF (Dita-OT)

## Productienummers uitvoer

| Uitvoertype | Kaartgrootte (onderwerpverwijzingen) | Uitvoeringstijd (in seconden) | Microservice publiceren |
|---------------|------------------------------|----------------------------|-----------------------|
| Site AEM | 3500 | 5220 | Nee |
| Native PDF | 3500 | 780 | Ja |
| PDF (DITA-OT) | 11000 | 960 | Ja |
| HTML5 | 3500 | 240 | Nee |
| Aangepast | 300 | 300 | Nee |

## Belangrijkste punten om te onthouden

- AEM Site maakt veel cq:paginaknooppunten en voegt deze af door ze tijdens de generatie afzonderlijk weer te geven. Daarom is het aan te raden om grote, meerdere gelijktijdige AEM Sitepublicaties niet uit te voeren, omdat dit het systeem kan overbelasten.
- AEM de tijd van de Plaatsgeneratie hangt van het gebruikte malplaatje af. De uitvoeringstijd kan toenemen als een complexe sjabloon wordt gebruikt.
- De uitvoeringstijd voor aangepaste publicatie is voor een voorbeelduitvoer. Aangepaste publicatietijd is uitsluitend afhankelijk van de eigen transformatielogica van de klant.
