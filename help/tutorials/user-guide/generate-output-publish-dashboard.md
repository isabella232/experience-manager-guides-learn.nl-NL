---
title: Publicatietaken beheren met het dashboard Publiceren
description: Publicatietaken beheren met het publicatiedashboard in AEM hulplijnen. Zorg dat u weet hoe u toegang krijgt tot het publicatiedashboard en annuleer een publicatietaak.
exl-id: 5ede608d-f905-44b7-9147-ab678ad68ee7
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 0%

---

# Publicatietaken beheren met het dashboard Publiceren {#id205CC08305Z}

Wanneer u een grote reeks het publiceren taken hebt die op uw systeem lopen, wordt het praktisch onmogelijk om elke kaart afzonderlijk te controleren DITA om zijn het publiceren taak te controleren. AEM de Gidsen geeft de beheerders en uitgevers één verenigde mening van alle het publiceren taken die in het systeem lopen. Een lijst met alle actieve publicatietaken is beschikbaar op het dashboard Publiceren.

Het publicatiedashboard geeft een volledig overzicht van alle publicatietaken die momenteel in het systeem worden uitgevoerd.

![](images/publish-dashboard.png){width="800" align="left"}

Het publicatiedashboard bevat de volgende gegevens:

- **Kaarttitel** - De titel van een kaartbestand dat momenteel wordt gepubliceerd of zich in de publicatiewachtrij bevindt.

- **Bestandsnaam** - De bestandsnaam van de DITA-kaart.

- **Uitvoervoorinstelling** - Naam van de uitvoervoorinstelling die wordt gebruikt om de uitvoer te genereren.

- **Geactiveerd door** - Gebruikersnaam van de gebruiker die de publicatietaak heeft gestart.

- **Gestart op** - Datum en tijdstip waarop de publicatietaak is gestart.

- **Verstreken tijd** - Tijd sinds wanneer de het publiceren taak in het systeem loopt.

- **Pictogram Verwijderen** - Een publicatietaak annuleren of beëindigen.

Het linkerdeelvenster van het publicatiedashboard biedt de volgende filteropties:

- **Uitvoervoorinstelling** - Selecteer een of meer uitvoervoorinstellingen waarvoor u de momenteel actieve publicatietaken wilt weergeven. In de volgende schermafbeelding worden de publicatietaken gefilterd om alleen die taken weer te geven die gebruikmaken van de voorinstelling AEM Site-uitvoer:

  ![](images/publish-dashboard-preset-filter.png){width="800" align="left"}

- **Geactiveerd door** - Selecteer een gebruikersnaam in de lijst om de publicatietaken weer te geven die door de geselecteerde gebruiker zijn gestart.

- **Kaart** - Selecteer een kaartbestand in de lijst om de publicatietaken weer te geven die voor de geselecteerde kaart worden uitgevoerd.

## Het dashboard Publiceren openen {#id205CC100DY4}

Voer de volgende stappen uit om toegang te krijgen tot het dashboard Publiceren:

>[!NOTE]
>
> Alleen een beheerder of uitgever heeft toegang tot het dashboard Publiceren.

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.

1. Selecteren **Hulplijnen** in de lijst met gereedschappen.

1. Klik op de knop **Dashboard publiceren** tegel.

   Het dashboard Publiceren wordt geopend met een lijst van alle actieve publicatietaken in het systeem.

   Als u op de verbinding van de Naam van het Dossier klikt, wordt de DITA kaartconsole van de geselecteerde kaart getoond.

   ![](images/publish-dashboard-click-filename-link.png){width="800" align="left"}


>[!NOTE]
>
> U kunt het publicatiedashboard ook openen via het tabblad Uitvoer terwijl u uitvoer genereert via het kaartdashboard. Zie voor meer informatie [De status van de uitvoergeneratietaak weergeven](generate-output-for-a-dita-map.md#viewing_output_history).

## Een publicatietaak annuleren

Voer de volgende stappen uit om een taak van de outputgeneratie van het Publish Dashboard te annuleren:

1. [Het dashboard Publiceren openen](#id205CC100DY4).

1. Klik in de lijst met actieve publicatietaken op het pictogram Verwijderen van een taak die u wilt annuleren.

   ![](images/publish-dashboard-cancel-task.png){width="800" align="left"}

1. Klikken **Ja** op de bevestigingsberichtvraag van de Annulering.

   De opdracht Annuleren wordt geaccepteerd en de annulering wordt geprobeerd zolang de taak actief blijft. Zodra de taak met succes wordt geëindigd, wordt het verwijderd uit de momenteel actieve takenlijst. De status van de taak wordt ook bijgewerkt in de DITA kaartconsole zoals Geannuleerd. In de volgende screenshot *HTML 5* taak wordt geannuleerd vanaf het publicatiedashboard en de status ervan wordt ook gewijzigd in de DITA-kaartconsole.

   ![](images/cancelled-output-task.png){width="800" align="left"}


**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)
