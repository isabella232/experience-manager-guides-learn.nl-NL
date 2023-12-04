---
title: Revisietaken beheren met het dashboard Revisie
description: Revisietaken beheren vanuit het dashboard Revisie in AEM hulplijnen. Leer de handelingen uitvoeren onder de taak, inhoud, tabblad revisoren en controleer de status van een revisietaak.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1300'
ht-degree: 0%

---

# Revisietaken beheren met het dashboard Revisie {#id2056B0Y70X4}

De werkstroom voor revisiebeheer kan verschillende taken bevatten. U kunt bijvoorbeeld revisoren toevoegen voor een bepaald onderwerp of de deadline voor een revisie verlengen. U kunt de revisietaak ook als volledig markeren als u denkt dat alle belanghebbenden hun feedback hebben gegeven. Deze taken kunnen worden beheerd met het dashboard Revisie.

Voer de volgende stappen uit om toegang te krijgen tot en gebruik te maken van het revisiedashboard:

>[!NOTE]
>
> U kunt revisietaken alleen beheren voor die projecten waarvoor u de auteur \(of aanvrager\) bent. Zelfs als u Revisor of Uitgever \(gebruiker\) bent, hebt u geen toegang tot de projecttaken.

1. In de **Projecten** Klik op het revisieproject dat u wilt beheren.

   Er wordt een deelvenster Project met taaktegels weergegeven.

   ![](images/review-management.png){width="800" align="left"}

1. Klik op de drie stippen in het dialoogvenster **Revisies** tegel.

   Het revisiedashboard wordt weergegeven. Het dashboard bevat een lijst met alle revisietaken die u hebt gemaakt.

   ![](images/review-dashboard.png){width="800" align="left"}

   Het revisiedashboard bevat de details over de revisietaak, zoals de taaknaam, die de revisie heeft gestart, de datum waarop de revisie is gestart, de datum waarop de revisie is gestart, de status, het aantal nieuwe opmerkingen dat niet is geaccepteerd of afgewezen door de auteur en de naam van de controleurs. De taken worden weergegeven in de volgorde van nieuw gemaakte taken naar oudere taken.

   >[!NOTE]
   >
   > Als u op de verbinding van de Taak van het Overzicht klikt, wordt het onderwerp of kaartdossier dat voor overzicht wordt verzonden geopend.

1. Selecteer een revisietaak.

   U ziet Bewerkingseigenschappen en [Status](#check-review-status-id199RF0A0UHS) in de werkbalk.

1. Als u op **Eigenschappen bewerken**, wordt de pagina Taakdetails weergegeven.

   De pagina Taakdetails bevat drie tabbladen: Taak, Inhoud en Revisoren. In de volgende secties worden de verschillende functies beschreven die onder elk tabblad beschikbaar zijn.


## Tabblad Taak

![](images/review-task-page.png){width="800" align="left"}

U kunt de volgende handelingen uitvoeren onder de **Taak** tab:

- De titel van de taak in het dialoogvenster **Titel** veld.
- Standaardtoewijzingen toevoegen in het dialoogvenster **Toewijzen aan** vervolgkeuzelijst. De revisoren die u hier toevoegt, hebben toegang tot alle onderwerpen die deel uitmaken van deze revisietaak. U kunt desgewenst meer revisoren verwijderen of selectief toevoegen aan specifieke onderwerpen in het menu [Het tabblad Revisoren](#reviewer-tab-id199RF0N0MUI).
- Werk de beschrijving van de taak bij in het dialoogvenster **Beschrijving** veld.
- Wijzig de **Vervaldatum**. U kunt de deadline voor het voltooien van de taak voorbereiden of uitstellen.
- Selecteer de optie om gebruikers te beperken tot het bekijken van alleen die onderwerpen die aan hen zijn toegewezen.
- Klikken **Bijwerken** om de gewijzigde details bij te werken.
- Klikken **Voltooid** de beoordelingstaak vóór de vervaldag als voltooid te markeren. Wanneer de taak van een individueel onderwerp als Voltooid wordt duidelijk, wordt de overzicht van het geselecteerde onderwerp gesloten. Nochtans, in het geval van onderwerpen die voor overzicht door een kaart DITA worden gedeeld, zal het merken van de DITA kaarttaak als Voltooid de overzicht van alle onderwerpen binnen de kaart sluiten die voor overzicht werden gedeeld.
- Klikken **Dupliceren** om een kopie van de revisietaak te maken. Het maken van een dubbele revisietaak lijkt op het maken van een nieuwe revisietaak. Zodra u de gedupliceerde taakwerkstroom start, wordt de pagina Revisietaak maken weergegeven. U moet de nieuwe taakdetails verstrekken zoals die in worden verklaard [Onderwerpen ter controle verzenden](review-send-topics-for-review.md#).

  Als u een overzichtstaak hebt geselecteerd die van een kaart DITA wordt gecreeerd, dan wordt u getoond de onderwerpen die een deel van de kaart zijn. U kunt dan de onderwerpen kiezen die u in de nieuwe overzichtstaak wilt omvatten.

  Als de overzichtstaak van één of veelvoudige onderwerpenoverzicht wordt gedupliceerd, dan slechts worden die onderwerpen getoond in de lijst van de overzichtstaak. U kunt deze onderwerpen ter controle delen met een andere set revisoren.

- Klikken **Sluiten** om naar de pagina Inbox te gaan.

## Inhoud, tabblad

![](images/review-content-page.png){width="800" align="left"}

U kunt de volgende handelingen uitvoeren onder de **Inhoud** tab:

- Wijzig de versie van het onderwerp dat ter controle wordt verzonden. U kunt de recentste versie van het onderwerp, versie zoals op datum, versie met specifiek etiket, of versie met een specifieke basislijn kiezen \(voor een kaart DITA \).

- Klikken **Bijwerken** om de bijgewerkte versie van het onderwerp met de controleurs te delen. De controleurs krijgen een e-mailbericht met de mededeling dat de nieuwere versie van het onderwerp ter controle is verzonden. De volgende keer dat een controleur het onderwerp opent, zien zij de bijgewerkte versie van het onderwerp.

  >[!NOTE]
  >
  > In het geval van een bijgewerkte versie van een onderwerp, worden de oude commentaren behouden ook in de nieuwere versie. Revisoren kunnen ook de verschillen tussen de twee versies zien.

- Klikken **Voltooid** de beoordelingstaak vóór de vervaldag als voltooid te markeren. Wanneer de taak van een individueel onderwerp als Voltooid wordt duidelijk, wordt de overzicht van het geselecteerde onderwerp gesloten. Nochtans, in het geval van onderwerpen die voor overzicht door een kaart DITA worden gedeeld, zal het merken van de DITA kaarttaak als Voltooid de overzicht van alle onderwerpen binnen de kaart sluiten die voor overzicht werden gedeeld.

- Klikken **Dupliceren** om een nieuwe overzichtstaak te creëren die de huidige taak als basis gebruikt.


## Het tabblad Revisoren {#reviewer-tab-id199RF0N0MUI}

![](images/reviewers-tab.png){width="800" align="left"}

U kunt de volgende handelingen uitvoeren onder de **Revisoren** tab:

- **Alles selecteren**: Hiermee selecteert u alle onderwerpen in de onderwerpenlijst. U kunt een partijverrichting gemakkelijk uitvoeren na het selecteren van alle onderwerpen.
- **Selectie wissen**: Hiermee wordt de selectie van de geselecteerde onderwerpen in de lijst met onderwerpen opgeheven.

  >[!NOTE]
  >
  > U kunt een onderwerp ook individueel selecteren of schrappen door op checkbox naast het onderwerp te klikken.

- **Toevoegen**: Hiermee geeft u het dialoogvenster Revisoren toevoegen weer. U kunt de naam typen van een revisor of gebruikersrol \(of groep\) die u als controleur wilt toevoegen aan de geselecteerde onderwerpen.
- **Verwijderen**: Hiermee geeft u het dialoogvenster Revisoren verwijderen weer. U kunt de naam typen van een revisor of gebruikersrol \(of groep\) die u als controleur wilt verwijderen uit de geselecteerde onderwerpen.
- **Opnieuw toewijzen**: Hiermee geeft u het dialoogvenster Revisoren opnieuw toewijzen weer. U kunt de naam typen van een revisor of gebruikersrol \(of groep\) waaraan u de revisietaak wilt toewijzen. Hiermee verwijdert u alle bestaande revisoren uit de geselecteerde onderwerpen en wijst u de nieuw geselecteerde revisoren toe aan deze onderwerpen.
- **Exporteren**: Hiermee kunt u de gegevens van de revisietaak exporteren in een CSV-bestand. Het bestand bevat details zoals het pad en de titel van het onderwerp, de naam van de controleur en de versie van de onderwerpen die ter controle zijn verzonden.
- **Revisoren bewerken**: Klik op de knop ![](images/edit_pencil_icon.svg)in de onderwerpenlijst wordt het dialoogvenster Revisoren bewerken weergegeven. U kunt revisoren voor het geselecteerde onderwerp toevoegen aan of verwijderen uit dit dialoogvenster.

## De status van een revisietaak controleren {#check-review-status-id199RF0A0UHS}

Als u een controletaak selecteert en op de hoofdpagina van het dashboard voor revisie klikt, **Status** wordt het statusrapport van de toetsingstaak weergegeven:

![](images/review-status-report.png){width="800" align="left"}

Het statusrapport voor de controletaak bevat de volgende details:

- Naam of namen van de controleur aan wie de revisietaak is toegewezen.
- De kolom Status geeft de revisiestatus aan. De status kan een van de volgende zijn:
   - **Niet gestart**: De revisor heeft de revisie-koppeling nog niet geopend.
   - **In uitvoering**: De controleur heeft de revisiekoppeling geopend en is bezig het onderwerp te evalueren.
   - **Voltooid**: De controleur heeft de revisie voltooid door de aan hem toegewezen controletaak te voltooien. De controletaak bevindt zich in het AEM-vak voor elke controleur.
- Wanneer een recensent een overzichtsverbinding opent en aan een bepaald onderwerp navigeert dat het onderwerp aan de Onderwerpen Gereviseerde lijst wordt toegevoegd. Op deze manier kunnen auteurs bepalen of de revisoren hun respectievelijke secties al dan niet hebben geopend. Eventuele opmerkingen worden tussen haakjes weergegeven.
- Het totale aantal opmerkingen over alle onderwerpen. In het geval van veelvoudige onderwerpen onder overzicht, wordt het aantal commentaren voor elk onderwerp vermeld \ (tussen haakjes \) naast de onderwerpnaam.
- De datum waarop een onderwerp voor het laatst is geopend door de revisor.

**Bovenliggend onderwerp:**[ Onderwerpen of kaarten controleren](review.md)
