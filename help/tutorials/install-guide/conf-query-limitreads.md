---
title: Vorm het aantal LimitReads voor een vraag
description: Leer hoe te om het aantal LimitReads voor een vraag te vormen
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---


# Vorm het aantal LimitReads voor een vraag {#id231RC0HL0ID}

Voer de volgende stappen uit om het aantal knooppunten dat een query tegelijkertijd kan lezen, te verhogen:

1. Open de JMX-pagina van de Adobe Experience Manager-webconsole.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/jmx
   ```

1. Zoeken naar en klikken op **QueryEngineSettings**.

1. Kenmerkwaarde wijzigen voor de **LimietLezen** kenmerk.

1. Klikken **Opslaan**.


Wanneer u deze kenmerkwaarde verhoogt, helpt het u het rapport voor grotere kaarten te produceren DITA.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)

