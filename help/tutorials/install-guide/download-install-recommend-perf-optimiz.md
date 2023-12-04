---
title: Recommendations for performance optimization
description: Meer informatie over de Recommendations voor het optimaliseren van prestaties
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '967'
ht-degree: 0%

---

# Recommendations for performance optimization {#id213BD0JG0XA}

## Gegevensopslag \(verplicht\) configureren

**Wat is de verandering?**
Stel de `minRecordLength` eigenschap aan een waarde van `100` onder de configuratie `org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.` Voor meer informatie over de opslag van de dossierdatum en S3- gegevensopslag, zie [Opslaan van knooppunten en gegevensopslag configureren in AEM 6](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/data-store-config.html) artikel.

>[!NOTE]
>
> Voor S3 gegevensopslag, hangt de kosten voor het handhaven van inhoud in gegevensopslag ook van het aantal verzoeken af. Daarom wanneer het doen van dit het plaatsen met S3-opstellingskosten per verzoek en geheim voorgeheugengrootte ook zou moeten worden overwogen.

**Wanneer configureren?**
Na de eerste installatie, maar voordat inhoud wordt gemigreerd. U moet deze verandering zelfs op een bestaand systeem uitvoeren, dat ervoor zorgt dat al nieuwe inhoud in gegevensopslag in plaats van segmentopslag wordt opgeslagen.

**Resultaat van deze wijziging**
De DITA-bestanden worden opgeslagen in de gegevensopslag in plaats van in de segmentopslag. Hierdoor blijft de grootte van de segmentwinkel binnen de aanbevolen limieten, waardoor de reactiesnelheid van het systeem wordt verbeterd.

## Lucene-index bijwerken \(verplicht\)

**Wat is de verandering?**
Sluit /var/dxml uit van eiken:index/lucene.

>[!NOTE]
>
> AEM Guides gebruikt nooit Lucene-indexen om te zoeken naar inhoud in het knooppunt /var/dxml.

**Wanneer configureren?**
Als u deze wijziging aanbrengt op een nieuw systeem voordat u inhoud migreert, is alleen het bijwerken van de eik:index/glucose vereist. Anders, op een bestaand systeem waar de inhoud reeds wordt gemigreerd, dan na het aanbrengen van de verandering in eiken:index/lucene, herbouwt indexen voor Lucene \ (*die enkele uren kan duren om te voltooien*\).

**Resultaat van deze wijziging**
Deze verandering verhindert /var/dxml knoop in de segmentopslag wordt geïndexeerd en wordt opgeslagen.

## Java-geheugenoptimalisatie \(verplicht\)

**Wat is de verandering?**
De JVM-beginparameters moeten zorgvuldig worden ingesteld op basis van de infrastructuur en de schijfgrootte. U wordt aangeraden Adobe Support te raadplegen om hulp te krijgen bij het openen van de ideale configuratie. U kunt echter zelf de volgende configuraties uitproberen:

- Stel de JVM-heapgrootte in op minimaal 1/4e van het totale beschikbare geheugen. De parameter gebruiken `-Xmx<size>` om de heapgeheugengrootte in te stellen. Stel de waarde in voor -`Xms` is gelijk aan `-Xmx`.

- Inschakelen `-XX:+HeapDumpOnOutOfMemoryError` en stel het pad in voor `-XX:HeapDumpPath=</path/to/folder``>`.

- Java GC-logbestand inschakelen als:

`* -XX:+PrintGCDateStamps`

`* -verbose:gc`

`* -XX:+PrintGCDetails`

`* -XX:+PrintTenuringDistribution`

`* -Xloggc:</path/to/gc.log>`

- Gebruik in het algemeen voor Java 11 G1GC \(`-XX:+UseG1GC`\) en voor Java 8 CMS gebruiken \(-`XX:+UseConcMarkSweepGC`\).

- Gebruik `-XX:NewRatio` om de grootte van het geheugen van de jonge generatie te bepalen. De standaardwaarde is 2, wat betekent dat 1/3 van het geheugen wordt gebruikt voor jonge generaties. Omdat er veel objecten zijn die snel worden gemaakt en vernietigd, wijst u met een waarde van 1/2 van het geheugen toe aan de jonge generatie.

- Het aantal objecten dat wordt bevorderd tot de oude generatie beheren met behulp van `-XX:MaxTenuringThreshold`. Gebruik de waarde 15 \(standaardwaarde\) om te vertragen wanneer objecten worden geconverteerd naar de oude generatie.

**Wanneer configureren?**
Als u deze wijziging aanbrengt op een bestaand systeem, moet u het systeem opnieuw opstarten. In het geval van een nieuwe installatie moet deze wijziging worden aangebracht in het beginscriptbestand \(.bat of .sh\) voordat het systeem wordt gestart.

**Resultaat van deze wijziging**
Dit resulteert in optimale heapgrootte en gereguleerde uitvoering van GC.

## Clientbibliotheekminiatuur op Author-instantie \(optioneel\)

**Wat is de verandering?**
De clientbibliotheken moeten zo worden ingesteld dat ze in de ontwerpinstanties miniaturen. Zo zorgt u ervoor dat er minder bytes worden gedownload wanneer een gebruiker op verschillende locaties naar het systeem bladert. Als u deze wijziging wilt aanbrengen, stelt u de configuratie in **HTML Library Manager** vanaf de Felix-console.

**Wanneer configureren?**
Dit kan in runtime door de console van Felix of via codeplaatsing worden gedaan.

**Resultaat van deze wijziging**
Deze wijziging verbetert de laadtijd van pagina&#39;s op de instantie Auteur, aangezien er minder bytes worden overgedragen om de clientbibliotheken te laden.

## Configureer gelijktijdige publicatiethreads \(verplicht, afhankelijk van het gebruiksgeval\)

**Wat is de verandering?**
Deze wijziging is vereist als u DITA-OT gebruikt om uitvoer te publiceren en er ook een aantal gelijktijdige publicatiethreads is gedefinieerd.

Standaard stelt AEM hulplijnen de publicatiethreads in op het aantal CPU&#39;s+1. Het wordt echter aanbevolen deze waarde in te stellen op de helft \(1/2\) of een derde \(1/3\) van het totale aantal CPU&#39;s. Stel hiertoe de **Grootte generatiepool** eigenschap onder de configuratie `com.adobe.fmdita.publish.manager.PublishThreadManagerImpl` overeenkomstig de aanbevelingen.

**Wanneer configureren?**
Dit kan in runtime door de console van Felix of via codeplaatsing worden gedaan.

**Resultaat van deze wijziging**
Deze verandering zorgt ervoor dat op een lopende instantie van de Auteur alle middelen niet voor de het publiceren verrichtingen worden toegewezen. Hierdoor blijven de systeembronnen ook beschikbaar voor auteurs, wat resulteert in een betere gebruikerservaring.

## Batchgrootte van knooppunten configureren voor het genereren van AEM Site-uitvoer \(verplicht, afhankelijk van het gebruiksgeval\)

**wat is de verandering ?**
Deze wijziging is vereist als u AEM Sites-uitvoer genereert.

Stel de **Limiet voor AEM sitepagina&#39;s in heap** eigendom onder `com.adobe.fmdita.config.ConfigManager` op basis van de configuratie van uw systeem. Deze eigenschap definieert de batchgrootte van knooppunten die moeten worden vastgelegd wanneer de sitepagina&#39;s worden gegenereerd. Op een systeem met een groter aantal CPU&#39;s en een grotere heapgrootte kunt u bijvoorbeeld de standaardwaarde verhogen van `500` naar een groter aantal. U moet de uitvoering met de gewijzigde waarde testen om tot een optimale waarde voor deze eigenschap te komen.

**Wanneer configureren?**
Dit kan in runtime door de console van Felix of via codeplaatsing worden gedaan.

**Resultaat van deze wijziging**
Een hoger aantal **Limiet voor AEM sitepagina&#39;s in heap** Deze eigenschap optimaliseert het genereren van de AEM Site-uitvoer.

## Het aantal naverwerkingsthreads \(verplicht, afhankelijk van het gebruiksgeval\) optimaliseren

**Wat is de verandering?**
Deze wijziging is vereist als u DITA-inhoud bulksgewijs uploadt.

Stel de **Threads na verwerking** eigendom onder `com.adobe.fmdita.config.ConfigManager` tot `1`.

**Wanneer configureren?**
Dit kan tijdens runtime worden gedaan.

**Resultaat van deze wijziging**
Deze wijziging verkort de naverwerkingstijd bij bulkupload van DITA-bestanden.

**Bovenliggend onderwerp:**[ Downloaden en installeren](download-install.md)
