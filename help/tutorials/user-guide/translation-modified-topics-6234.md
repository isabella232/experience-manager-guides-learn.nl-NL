---
title: Gewijzigde onderwerpen vertalen
description: Leer hoe u een gewijzigd onderwerp opnieuw vertaalt in AEM hulplijnen.
exl-id: 48b868c3-27ec-4641-b40d-17a641be7497
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 0%

---

# Gewijzigde onderwerpen vertalen {#id16A5A0B6072}

Als u veranderingen in sommige onderwerpen aanbrengt, dan vereisen die onderwerpen re-vertaling. U kunt spoor van gewijzigde onderwerpen van kaart houden DITA. Klik in de map met de brontaalkopie op het DITA-kaartbestand en klik op het tabblad Vertaling. U kunt het statuut van elk onderwerp zien of het al dan niet hervertaling vereist.

Voer de volgende stappen uit om een gewijzigd onderwerp voor re-vertaling te verzenden:

1. Klik het DITA kaartdossier van de brontaalexemplaaromslag.

1. Klik op de knop **Vertaling** tab.

1. In de **Filter** links, selecteert u de **Talen vertalen** waarop u de status wilt controleren en klikken **Gereed**.

   U kunt de vertaalstatus voor elk onderwerp zien. De onderwerpen die een andere revisie van onderwerp beschikbaar hebben dan wat voor vertaling werd verzonden, tonen en **Verouderd** status.

   >[!NOTE]
   >
   > De vertaalwerkstroom vergelijkt de laatste opgeslagen revisie van het onderwerpdossier in de brontaalomslag met de vertaalde versie.

   Als u op de pijl klikt, ziet u meer details. u kunt de specifieke taalkopie zien die verouderd is.

   ![](images/out-of-sync-uuid.png){width="800" align="left"}

1. Klik het controlevakje om de onderwerpen te selecteren die u voor re-vertaling wilt verzenden.

   Wanneer u een datum selecteert die niet meer gesynchroniseerd is, worden de **Taalkopieën maken/bijwerken** verschijnt in het venster Verwijzingen en in het dialoogvenster **Synchronisatiestatus Buiten-de sluiten** knop boven de knop **Filter** pictogram.

   U kunt de **Synchronisatie negeren** knoop om de Verouderd status voor de onderwerpen in de kaart met voeten te treden DITA. Bijvoorbeeld, als u sommige veranderingen in de Engelse versie van het onderwerp aanbracht die geen vertaling vereist, kunt u deze knoop gebruiken en de status van Verouderd voor het geselecteerde onderwerp veranderen.

   >[!NOTE]
   >
   > Als u op de knop **Synchronisatiestatus Buiten-de sluiten** knoop, plaatst het de onderwerpstatus aan Up voor de geselecteerde onderwerpen van Verouderd.

1. Klikken **Taalkopieën bijwerken** en configureert u de vertaaltaak.

1. U kunt verkiezen om een nieuw vertaalproject tot stand te brengen of onderwerpen aan een bestaand vertaalproject toe te voegen. Verstrek de vereiste details om het vertaalproject te vormen.

1. Klikken **Start**.

   Er wordt een bevestigingsbericht weergegeven waarin wordt aangegeven dat het onderwerp voor vertaling is verzonden.

1. Navigeer aan het vertaalproject in de console van het Project. Er wordt een nieuwe vertaalopdrachtkaart gemaakt in de map. Klik op de ellips om de elementen van de map weer te geven.

   ![](images/incremental-job.PNG){width="300" align="left"}

1. Als u de vertaling wilt starten, klikt u op de pijl op de vertaalwerkkaart en selecteert u **Start** in de lijst. Een bericht geeft aan dat de taak is gestart.

   U kunt de status van het onderwerp dat wordt vertaald ook bekijken wanneer u de ellips bij de bodem van de kaart van de vertaalbaan klikt.

   >[!NOTE]
   >
   > Als u de vertaalservice Human gebruikt, moet u de inhoud exporteren voor vertaling. Zodra u de vertaalde inhoud hebt, dan moet u het terug in het vertaalproject invoeren.

1. Nadat de vertaling is voltooid, verandert de status in **Klaar voor revisie**. Klik op de ellips om de onderwerpdetails weer te geven en voer een van de volgende handelingen uit op de werkbalk:

   - Klikken **Tonen in elementen** de vertaling te bekijken en te verifiëren.

   - Klikken **Vertaling accepteren** als u van mening bent dat de veranderingen correct zijn vertaald. Er wordt een bevestigingsbericht weergegeven.

   - Klikken **Vertaling negeren** als u van mening bent dat het werk opnieuw moet worden gedaan. Er wordt een afwijzingsbericht weergegeven.

   >[!NOTE]
   >
   > Het is belangrijk het vertaalde element te accepteren of af te wijzen, anders blijft het bestand op de tijdelijke locatie en wordt het niet naar DAM gekopieerd.

1. Navigeer terug naar het DITA kaartdossier in de brontaalomslag in Activa UI. De opnieuw vertaalde onderwerpen zijn nu synchroon.


**Bovenliggend onderwerp:**[ Inhoud vertalen](translation.md)
