---
title: Rapport voor hergebruik van inhoud
description: Rapport voor hergebruik van inhoud leren gebruiken
source-git-commit: bb7a8d49e5425b7fc856277c054558c75394fcb2
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---


# Rapport voor hergebruik van inhoud {#id205BB900OQD}

Een ander nuttig rapport dat u kunt produceren is het Rapport van de Hergebruik van de Inhoud. Dit rapport berekent het gemiddelde percentage van het inhoudsgebruik, dat zeer nuttig voor projectmanagers en bedrijfseigenaars is om de hoeveelheid inhoud te zien die wordt opnieuw gebruikt.

>[!TIP]
>
> Voor een goede werking van het Rapport voor hergebruik van inhoud moet u de nabewerkingsworkflow inschakelen. Neem contact op met de systeembeheerder voor het inschakelen van workflows na verwerking.

Voer de volgende stappen uit om het Rapport voor hergebruik van inhoud weer te geven:

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.

1. Selecteren **Hulplijnen** in de lijst met gereedschappen.

1. Klik op de knop **Rapport voor hergebruik van inhoud** tegel.

1. Klikken **Bladeren** om een weg te kiezen waar uw onderwerpen verblijven of de weg manueel in te gaan.

   Het rapport wordt gegenereerd door de inhoud in de bovenliggende en alle onderliggende mappen te scannen.

1. Klikken **Rapport genereren** om het Rapport voor hergebruik van inhoud op te halen.

   ![](images/content-reuse-uuid.png)

   De rapportpagina bestaat uit twee delen:

   - **Rapportoverzicht:**

      Hiermee geeft u het gemiddelde hergebruik van inhoud weer, dat wordt berekend als Instanties voor hergebruik van inhoud/Totaal aantal onderwerpen. Dit rapport houdt rekening met alle verwijzingen naar directe inhoud op het eerste niveau en onderwerpverwijzingen voor berekening. De Instanties voor hergebruik van inhoud wordt berekend als de som van waarden in het veld Aantal keren opnieuw gebruikt. Het onderwerp dat het meest wordt hergebruikt is ook vermeld in de Samenvatting van het Rapport. Het klikken op de verbinding van het onderwerp in het Meest gebruikte Onderwerp opent de voorproef van het onderwerp.

   - **Details:**

      De sectie Details bevat de volgende kolommen:

      - **Titel**: De titel van het onderwerp. Als u op de titelkoppeling van het onderwerp klikt, wordt de voorvertoning van het onderwerp geopend.

      - **UUID**: De universeel unieke id \(UUID\) van het bestand.

      - **Grootte**: Bestandsgrootte in bytes.

      - **Status**: De huidige status van het document - Concept, In-Review of Reviewed.

      - **Aantal opnieuw gebruikte tijden**: Aantal tijden het overeenkomstige onderwerp is opnieuw gebruikt. Dit is berekend als de som van de vermeldingen in de kolommen waarnaar wordt verwezen min 1.

      - **Verwezen door**: De onderwerpen waarin het overeenkomstige onderwerp is van verwijzingen voorzien. Hier worden alleen de directe verwijzingen \(first level\) in overweging genomen. Meerdere onderwerpen worden gescheiden door komma&#39;s. UUID van het referenced dossier wordt ook vermeld tussen haakjes.Het klikken op de de titelverbinding van het onderwerp opent de onderwerpvoorproef.


>[!NOTE]
>
> U kunt het Rapport voor hergebruik van inhoud ook exporteren in CSV-indeling. Klik hiertoe op de koppeling Exporteren naar CSV in de linkerbovenhoek van het scherm en kies een locatie waar u het CSV-bestand wilt opslaan. U kunt dit CSV-bestand vervolgens openen in elke CSV-editor.

**Bovenliggend onderwerp:**[ Rapporten](reports-intro.md)

