---
title: Native PDF | JVM-vlaggen configureren voor Native PDF Publishing
description: JVM-vlaggen configureren voor Native PDF Publishing
source-git-commit: cfb1197d0aad7ea3771bc6e1a73c02f540cef0c9
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---


# JVM-vlaggen configureren voor Native PDF Publishing

Native PDF-publicaties starten een apart JVM-proces om een PDF te genereren. Mogelijk moet u de configuraties van deze JVM aanpassen om verschillende scenario&#39;s te ondersteunen. Als u bijvoorbeeld grotere werklasten wilt uitvoeren, moet u de maximale heapgrootte verhogen die beschikbaar is voor het gepaaide JVM-proces.

Voer de volgende stappen uit om AEM Gidsen het Eigen PDF het Publiceren JVM vlaggen uit te voeren:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en selecteren de *com.adobe.fmdita.config.ConfigManager* bundel.

1. De eigenschap bijwerken **Opties voor Java-opdrachtregel voor native PDF** (*native.pdf.java.opts*) om standaard JVM-vlaggen door te geven.



1. Klikken **Opslaan**.