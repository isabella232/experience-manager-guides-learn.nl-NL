---
title: Een DITA-project maken
description: Leer hoe u een DITA-project maakt
exl-id: 6dc88ac4-249a-4da2-9787-a58370e281ca
source-git-commit: 8823669fd29e8a40a41f9ca5d654b38fbea8e2fa
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Een DITA-project maken {#id1645HA00NM6}

AEM Gidsen verstrekt een DITA projectmalplaatje dat u kunt gebruiken om uw overzichtstaken tot stand te brengen en te beheren.

U kunt een DITA-project maken en het vervolgens gebruiken om uw revisies te starten. Met een project kunt u een deadline definiëren en de taken en tijd bepalen die nodig zijn om de overzichtstaak te voltooien waarvoor u het project hebt gemaakt.

U kunt teamleden aan een project toevoegen die dan diverse rollen - Auteurs, Recensenten, en Uitgevers zouden kunnen worden toegewezen.

Zodra u uw project DITA hebt gecreeerd, kunt u uw overzicht van de Redacteur van het Web of de Hulp UI van Activa in werking stellen. Zie voor meer informatie [Onderwerpen ter controle verzenden](review-send-topics-for-review.md#).

En als een auteur een revisiewerkstroom start, krijgen de geselecteerde leden van het project een e-mailmelding. Voor het configureren van e-mailmeldingen raadpleegt u *E-mailsjablonen aanpassen* in Installeer en configureer as a Cloud Service Adobe Experience Manager-hulplijnen.

Voer de volgende stappen uit om een DITA-project tot stand te brengen:

1. Open Projectconsole.

   U kunt tot de console van Projecten ook toegang hebben gebruikend volgende URL:

   ```http
   http://<server name>:<port>/projects.html
   ```

1. Klikken **Maken** \> **Project** om de wizard Project maken te starten.

   ![](images/project-console-63.png){width="650" align="left"}

1. Selecteer op de pagina Project maken de optie **DITA-project** sjabloon en klik op **Volgende**.

1. Voer op de pagina Projecteigenschappen de volgende gegevens in:

   Informatie in de **Basis** tab:

   ![](images/create-project.png){width="650" align="left"}

   - Voer de **Titel**, **Beschrijving**, en **Vervaldatum**.

   - U kunt desgewenst een miniatuur kiezen voor het project.

   - Door gebrek, wordt u gemaakt de eigenaar van het project. Meer gebruikers toevoegen aan dit project:
   1. Voer een gebruiker in of kies een gebruiker in het menu **Gebruiker** vervolgkeuzelijst.

   1. Kies een gebruikerstype - Auteurs, Revisoren of Uitgevers.

      >[!NOTE]
      >
      >U zult andere gebruikerstypes in deze drop-down lijst zien, maar voor een DITA- project zou u slechts van Auteurs, Recensenten, of het gebruikerstype van Uitgevers moeten kiezen. Zelfs als u een gebruiker van een verschillend type toevoegt, zal die gebruiker tot geen enkele DITA-specifieke eigenschappen kunnen toegang hebben beschikbaar in AEM Gidsen.

   1. Klikken **Toevoegen**.

      >[!NOTE]
      >
      >Als u AEM versie 3.5 van Gidsen gebruikt of vroeger, wordt u getoond een optie om een DITA kaartdossier te selecteren om zeer belangrijke verwijzingen voor onderwerphet uitgeven, voorproef en overzichtswerkschema&#39;s op te lossen. In 3.6 en recentere versies, kunt u de wortelkaart door de Redacteur van het Web plaatsen. Zie voor meer informatie de [Gebruikersvoorkeuren](web-editor-features.md#id2087G0P40SB) in de webeditor. Een andere manier om de wortelkaart te plaatsen is door het bij de globale of omslag-vlakke profielen te vormen. Zie voor meer informatie *Profielen op algemeen niveau of mapniveau configureren* in de Installatie- en configuratiehandleiding.
   Informatie in de **Geavanceerd** tab:

   - Voer een naam in voor het project. Deze naam wordt gebruikt om URL voor dit project tot stand te brengen.



1. Klikken **Maken**.

   Het dialoogvenster Project gemaakt wordt weergegeven.

1. Klikken **Openen** om uw projectpagina te openen.


**Bovenliggend onderwerp:**[ Onderwerpen of kaarten controleren](review.md)
