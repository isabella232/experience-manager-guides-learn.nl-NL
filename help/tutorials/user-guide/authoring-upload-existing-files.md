---
title: Bestanden uploaden
description: Leer hoe u uw bestanden uploadt naar de AEM opslagplaats en fouten verwerkt. De middelen van de console van kennis gebruikersinterface, AEM Desktop app, activa bulkingestor, en gebruiken FrameMaker voor bulkupload.
exl-id: d6a73953-94dd-4fa5-b09c-5e4c77fead62
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 0%

---

# Bestanden uploaden {#id176FF000JUI}

U hebt waarschijnlijk een opslagplaats voor bestaande DITA-inhoud die u wilt gebruiken met AEM hulplijnen. Voor dergelijke bestaande inhoud kunt u de volgende methoden gebruiken om uw inhoud in bulk te uploaden naar AEM opslagplaats:

>[!IMPORTANT]
>
> Zie [Digitale middelen toevoegen aan Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) voor gedetailleerde informatie in de ondersteunde methoden voor het uploaden van inhoud in AEM.

## Gebruikersinterface middelenconsole

U kunt inhoud op uw bureaublad selecteren en in de AEM gebruikersinterface \(webbrowser\) naar de doelmap slepen. Zie voor meer informatie [Elementen uploaden](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) in AEM documentatie.

## Bureaubladapp AEM

Gebruik AEM bureaubladtoepassing als u een creatieve professional bent en de middelen op uw lokale bureaublad wilt beheren. U kunt deze elementen openen en bewerken met uw bureaubladtoepassingen. U kunt ook versies bijhouden en uw bestanden delen met andere gebruikers. Zie voor meer informatie [Bureaubladapp AEM](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## Bulkingestor

Als u grootschalige migraties en soms grote hoeveelheden inneemt, kunt u de inhoud uploaden met Asset bulksgewijs inslikken. Met dit hulpprogramma kunt u bulkinhoud uploaden uit ondersteunde datastores zoals Azure of S3. Zie voor meer informatie [Bulkingestor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## FrameMaker gebruiken voor bulkupload

Adobe FrameMaker wordt geleverd met een krachtige AEM-aansluiting waarmee u uw bestaande DITA en andere FrameMaker documenten \() eenvoudig kunt uploaden`.book` en `.fm`\) in AEM. U kunt verschillende functies voor het uploaden van bestanden gebruiken, zoals het uploaden van één bestand, het uploaden van een volledige map met of zonder afhankelijkheden \(zoals inhoudsverwijzingen, kruisverwijzingen en afbeeldingen\).

Zie de sectie voor meer informatie over het gebruik van de functie voor bulkupload in FrameMaker *Een CRX-map maken en bestanden uploaden* in FrameMaker gebruikershandleiding.

## Foutafhandeling tijdens het uploaden van inhoud {#id201MI0I04Y4}

Als een of meer bestanden niet kunnen worden geüpload, wordt na het uploadproces een vraag weergegeven met een lijst bestanden die niet zijn geüpload:

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

Voor meer informatie over hoe de verschillende scenario&#39;s voor het uploaden van bestanden eruit zien [DITA-inhoud uploaden](authoring-file-management.md#).

Als u een gereedschap gebruikt, zoals AEM bureaubladtoepassing of het bulksgewijs invoegen van middelen, wordt de handeling die op een gedupliceerd bestand wordt uitgevoerd, bepaald door een instelling op de AEM server. Neem contact op met de systeembeheerder voor informatie over deze configuratie.

**Bovenliggend onderwerp:**[ Inhoud beheren](authoring.md)
