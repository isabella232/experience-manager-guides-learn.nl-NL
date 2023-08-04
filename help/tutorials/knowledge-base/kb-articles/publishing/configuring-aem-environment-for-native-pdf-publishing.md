---
title: AEM omgeving configureren voor publicatie op eigen PDF
description: AEM omgeving configureren voor publicatie op eigen PDF
exl-id: 40266ca0-0b0b-4418-b606-f70270addbaa
source-git-commit: 45dfe6078039001327e91ae85ea2a5beeacb2d59
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 1%

---

# AEM omgeving configureren voor publicatie op eigen PDF

AEM Hulplijnen bevatten een native PDF-publicatieprogramma waarmee gebruikers de inhoud kunnen ontwerpen, ontwikkelen en publiceren in de PDF-indeling.

Het biedt de mogelijkheid om verschillende paginalay-outs, CSS-sjablonen te maken en de PDF-sjablonen samen met de paginalay-outs en CSS te ontwerpen.

De stappen voor het configureren van deze native PDF in AEM hulplijnen verschillen afhankelijk van het besturingssysteem. Gebruik de onderstaande configuratiestappen op basis van het besturingssysteem waarop AEM is geïnstalleerd.

## Vereisten

Minimumeisen voor het instellen van native PDF:

- Java Platform, Standard Edition 8 of 11 JDK (Java SE Development Kit) en JRE (Java SE Runtime Environment) zijn geïnstalleerd
- AEM 6.5 SP13, SP12, SP11 of SP10
- Hulplijnen 4.1 en hoger (niet-UUID of UUID)

De inheemse PDF het publiceren motor heeft Oracle JDK nodig om de knoopmodules in de AEM crx-quickstart omslag te produceren. De volgende besturingssystemen worden standaard ondersteund:

- Windows 10, Windows 2019-server en hoger.
- Linux - (RHEL 8 en hoger, CentOS 7 en hoger, Ubuntu 18 en hoger)
- Mac OS (gebaseerd op Intel)

## Configuratiestappen voor Windows Server (JAVA 11/8)

1. Zorg ervoor dat AEM server uitvalt.
2. Klik in de taakbalk van Windows met de rechtermuisknop op het Windows-pictogram en selecteer Systeem.
3. Klik onder Verwante instellingen in het venster Instellingen op Geavanceerde systeeminstellingen.
4. Klik op het tabblad Geavanceerd op Omgevingsvariabelen.
5. Klik in het gedeelte Systeemvariabelen op &quot;_Nieuw_&quot; om een nieuwe omgevingsvariabele te maken.
6. Voer een variabelenaam in als JAVA_HOME.
7. Geef in het waardeveld het installatiepad voor Java op en klik op OK.

   Bijvoorbeeld:

   JAVA 11:

   C:\Program Files\JAVA\jdk-11.0.15.1

   JAVA 8:

   C:\Program Files\JAVA\ jdk1.8.0_144

8. Voeg een pad uit systeemvariabelen toe en klik op Bewerken.

9. Binnen de variabelen van de Weg verstrekken nu de waarde van de weg van de Server en klik O.K.

   Bijvoorbeeld:

   JAVA 11:

   %JAVA_HOME%\bin\server\

   JAVA 8:

   %JAVA_HOME%\jre\bin\server\

10. Klik nogmaals op OK in het dialoogvenster Omgevingsvariabelen.
11. Klik nogmaals op OK in het dialoogvenster Systeemeigenschappen.
12. Start nu de AEM.
13. Genereer native PDF op basis van voorinstellingen in de webeditor.

## Configuratiestappen voor Linux Server (RHEL7/centOS 7)

1. Zorg ervoor dat de AEM-server uitvalt
2. Verifieer de variabele JAVA_HOME door echo $JAVA_HOME te doen
3. Als de variabele JAVA_HOME niet is ingesteld, volgt u stap 4. Anders gaat u rechtstreeks naar stap 5.
4. De variabele JAVA_HOME instellen met de onderstaande opdrachten op basis van de geïnstalleerde Java-versie

   Bijvoorbeeld:

   JAVA 11:

   1. export JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. PATH=$PATH exporteren: $JAVA\_HOME/bin
   3. LD\_LIBRARY\_PATH=/usr/lib/jvm/jdk-11.0.15.1/lib/server:/usr/java/jdk-11.0.15.1/lib/server

   JAVA 8:

   1. export JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. PATH=$PATH exporteren: $JAVA\_HOME/bin

5. Start AEM Server opnieuw en ga naar Stap 12 als u Hulplijnen versie 4.2 en hoger gebruikt.
6. Kopieer de &quot;_node_modules.zip_&quot; onder aan dit artikel toegevoegd aan de directory crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166/.
7. Open terminal in crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166/ locatie.
8. Knooppunt_modules-map verwijderen met onderstaande opdracht

   **rm -rf node_modules**

9. Knop_modules.zip decomprimeren met onderstaande opdracht

   **unzip node_modules.zip**

10. Als de opdracht unzip niet is geïnstalleerd/herkend, kan deze worden geïnstalleerd met de volgende opdracht

   **yum install unzip**

11. Installeer het fontconfig-pakket.
Opdracht: u installeert fontconfig
12. Genereer native PDF op basis van voorinstellingen in de webeditor.

**OPMERKING** : het pakket node_modules.zip kan worden gedownload [hier](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:295d8f03-41e1-429b-8465-2761ce3c2fb3).

Het handmatig importeren van de gedownloade knoopmodules voor het Linux-besturingssysteem is een oplossing voor gebruikers die op hulplijnen 4.1 of eerdere versies staan (stap 6-12)

## Configuratiestappen voor Mac-machine (JAVA 11/8)

1. Installeer Oracle JAVA 11 of Oracle JAVA 8.
2. Stel de omgevingsvariabele JAVA_HOME in op de geïnstalleerde JAVA-directory.
3. Open een Unix-shell.
(Bash wordt hier gebruikt voor vestiging de configuratie)

   Opdracht: nano ~/.bashrc

4. De variabele JAVA_HOME instellen met de onderstaande opdrachten op basis van de geïnstalleerde Java-versie

   Bijvoorbeeld:

   JAVA 11:

   export JAVA\_HOME= /Library/Java/JavaVirtualMachines/jdk-11.0.15.1.jdk/Contents/Home

5. Bashrc opnieuw laden

   Opdracht: bron ~/.bashrc.

6. Controleer of JAVA_HOME is ingesteld met behulp van opdrachtecho $JAVA_HOME

7. Voer de onderstaande drie opdrachten uit vanuit AEM installatiepad

   C:/{aem-installation-folder}/crx-quickstart/profiles/nodejs-b1aad0a7-9079-e56c-1ed8-6fcababe8166

   i) zoeken. -type d -exec chmod 0755 {} \; ii) zoeken. -type f -exec chmod 0755 {} \; iii) ./node-darwin/bin/node node-darwin/lib/node_modules/npm/bin/npm-cli.js —prefix. install —unsafe-perm —scripts-prepend-node-path

8. Controleren of Java is geïnstalleerd met de onderstaande opdracht

   i) Uitvoeren **./node-darwin/bin/node** bevel van /crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166 folder

   ![mac](../assets/publishing/mac.png)

   ii) a = require(&#39;java&#39;)

9. Installeer het fontconfig-pakket.
Opdracht: apt install fontconfig

10. Genereer native PDF op basis van voorinstellingen in de webeditor.

## Problemen oplossen

Hieronder ziet u de algemene fouten die kunnen optreden tijdens het genereren van PDF wanneer omgevingsvariabelen niet correct zijn ingesteld.

### Null pointer Exception in Windows/Mac OS

![null pointer uitzondering](../assets/publishing/null-pointer-exception.png)

Als het probleem zich blijft voordoen zelfs nadat de Java-omgeving is gecorrigeerd, moet u het volgende opnieuw valideren:

1. Controleer of de uitvoervoorinstelling correct is gedefinieerd of maak een nieuwe uitvoervoorinstelling zonder spaties.

2. Verifieer de folder van de knoopmiddelen bij /libs/fmdta/node_resources om ervoor te zorgen dat alle vereiste bibliotheken tijdens de installatie geïnstalleerd zijn.

### Ontbrekende bibliotheken in RHEL 7 Linux OS

![ontbrekende bibliotheken](../assets/publishing/missing-libraries.png)

### Time-out publicatieproces. Het proces is in de gegeven tijd niet voltooid

![time-out van publicatieproces](../assets/publishing/publish-process-timeout.png)

Valideer de time-outeigenschapswaarde voor het knooppunt nodejs in /var/dxml/profiles/b1aad0a7-9079-e56c-1ed8-6fcababe8166/nodejs in de CRX-opslagplaats. De standaardwaarde is 300.



Als u problemen ondervindt tijdens het uitvoeren van een van de bovenstaande stappen, plaatst u uw vraag op de Community voor AEM [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) voor hulp.
