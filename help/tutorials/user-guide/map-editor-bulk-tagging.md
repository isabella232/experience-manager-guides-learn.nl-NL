---
title: Labels in bulk voor DITA-inhoud
description: Leer hoe u labels voor DITA-inhoud kunt uitknippen
source-git-commit: 528dd5d33f38c29809e7e7dafd77d860daaba8db
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---


# Labels in bulk voor DITA-inhoud {#id179SG0TN05Z}

Met labels kunt u inhoud groeperen of classificeren in de gegevensopslagruimte en ook in de gepubliceerde uitvoer. Als u labels op uw inhoud hebt toegepast, kunt u gemakkelijk verwante onderwerpen zoeken in een DITA-kaart die u kan helpen bij het ontwerpen van inhoud. Met de gepubliceerde uitvoer kunnen eindgebruikers de juiste inhoud sneller vinden met de juiste tags.

Met AEM hulplijnen kunt u de DITA-inhoud na een paar klikken labelen. U kunt de bulketiketterende eigenschap gebruiken om veelvoudige markeringen op veelvoudige onderwerpen, een kaart DITA, of op een sub-kaart toe te passen. U kunt ook labels toepassen op een afzonderlijk onderwerp. Tags zijn de native functie in AEM. Meer informatie over het maken en beheren van tags vindt u in het gedeelte [Tags beheren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) in AEM documentatie.

Standaard bieden AEM hulplijnen geen leestoegang aan gebruikers in de map waarin alle tags in de AEM zijn opgeslagen. Als u tags wilt gebruiken die zijn gedefinieerd in de AEM opslagplaats, moet u de systeembeheerder vragen toegang te verlenen tot de map waarin de tags zijn opgeslagen.

## Bulktags toepassen

Gebruik de functie voor bulkcodes om meerdere tags tegelijk toe te passen. Voer de volgende stappen uit om markeringen op uw onderwerpen in een kaart toe te passen DITA:

1. Navigeer in de interface Elementen naar het DITA-kaartbestand en klik erop.

   De DITA kaartconsole verschijnt tonend de lijst van Output stelt beschikbaar om output te produceren.

1. Klikken **Onderwerpen**.

   Een lijst van onderwerpen beschikbaar in de kaart DITA wordt getoond. De UUIDs van onderwerpen&#39; wordt getoond onder de onderwerptitel.

1. Selecteer de onderwerpen of submap waarop u tags wilt toepassen.

   ![](images/apply-tags-uuid.png)


   >[!NOTE]
   >
   > In de bovenstaande schermafbeelding ziet u een submap die is geselecteerd en uitgevouwen. Bij het selecteren van de submap worden ook alle onderwerpen onder de submap geselecteerd.

1. Klikken **Labels toepassen**.

   Het dialoogvenster Codes selecteren wordt geopend.

1. Selecteer een of meer tags die u wilt toepassen op de geselecteerde onderwerpen.

1. Bevestig uw selectie.

   De geselecteerde markeringen worden toegepast op de onderwerpen en naast de onderwerptitel getoond.

   >[!NOTE]
   >
   > Na het toevoegen van markeringen aan uw onderwerpen, als u een onderwerp beweegt of schrapt, dan worden de markeringen voor die onderwerpen ook verwijderd. Nochtans, blijft dat onderwerp in de kaart tot u het verwijdert.


## Tags toepassen op een afzonderlijk onderwerp

Voer de volgende stappen uit om markeringen op een individueel onderwerp toe te passen:

1. In Elementen UI, navigeer aan en selecteer het onderwerpdossier waarop u markeringen wilt toepassen.

1. Klik op de werkbalk op **Eigenschappen**.

   De eigenschappenpagina van het onderwerp wordt weergegeven.

1. Klik op het tabblad Standaard op het pictogram Bladeren naast **Tags** veld.

1. Selecteer een of meer tags die u op het geselecteerde onderwerp wilt toepassen.

1. Bevestig uw selectie.

1. Klikken **Labels toepassen**.

   De geselecteerde labels worden toegepast op het onderwerp en weergegeven in het veld Codes.

1. Klikken **Opslaan en sluiten**.


## Labels verwijderen

Naar gelang uw bedrijfsbehoeften, kunt u de het etiketteren informatie voor om het even welk DITA onderwerp veranderen. U kunt gemakkelijk alle markeringen meteen verwijderen of slechts die markeringen verwijderen die op het onderwerp ongeldig zijn.

Voer de volgende stappen uit om alle markeringen uit één of meerdere onderwerpen te verwijderen:

1. Navigeer in de interface Elementen naar het DITA-kaartbestand en klik erop.

   De DITA kaartconsole verschijnt tonend de lijst van Output stelt beschikbaar om output te produceren.

1. Klikken **Onderwerpen**.

   Een lijst van onderwerpen beschikbaar in de kaart DITA wordt getoond.

1. Selecteer de onderwerpen waarvan u tags wilt verwijderen.

1. Klikken **Labels verwijderen**.

   >[!NOTE]
   >
   > Als het pictogram Codes verwijderen niet zichtbaar is, controleert u of u de functie Codes verbergen niet hebt ingeschakeld.

1. Klik in het dialoogvenster Verwijderen bevestigen op **OK** om labels uit de geselecteerde onderwerpen te verwijderen.


## Tags tonen of verbergen

Als u een lange lijst van markeringen hebt die op uw onderwerpen worden toegepast, dan zou u het een beetje omslachtig kunnen vinden om te navigeren. U kunt eenvoudig tags verbergen in de weergave van de DITA-kaartconsole door op het pictogram Codes verbergen te klikken. Als de labels niet zichtbaar zijn, worden ook alle tags weergegeven wanneer u op Tags tonen klikt.

**Bovenliggend onderwerp:**[ Metagegevens beheren](manage-metadata.md)

