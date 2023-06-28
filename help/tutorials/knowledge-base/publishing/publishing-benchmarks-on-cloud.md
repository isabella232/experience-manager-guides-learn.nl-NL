---
title: Gidsen die Benchmarks op AEMaaCS publiceren
description: Begrijp systeembeperkingen bij het publiceren op AEM Cloud.
exl-id: cc6e38b9-6276-4147-beda-93f66368e15d
source-git-commit: 06a55ef933f9e7941cef2337212a830413a478af
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# AEM Publishing Benchmarks op AEMaaCS

AEM de cloud-service Hulplijnen kent momenteel een aantal beperkingen voor het publiceren van kaartgrootten die het team van hulplijnen actief moet oplossen.

Het team van gidsen heeft een scalable het publiceren microservice geïntroduceerd om grote kaarten en veelvoudige gezamenlijke het publiceren te steunen. Meer informatie over de nieuwe publiceer microservice vindt u in [publicatie microservicearchitectuur](publish-microservice-architecture-and-performance.md)

Zie voor het configureren van de nieuwe publicatieservice voor elke AEM cloudomgeving [configureren van nieuwe op microservice gebaseerde publicaties](configure-microservices.md)


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
