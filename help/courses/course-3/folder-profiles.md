---
title: Mapprofielen
description: Mapprofielen maken en gebruiken voor AEM hulplijnen
exl-id: 5a0daa68-51ae-42d0-8320-6e8bdb1fe545
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 0%

---

# Mapprofielen

AEM biedt snelle toegang tot configuratiehulpmiddelen. Door de Profielen van de Omslag aan te passen, kunnen de verschillende afdelingen of de producten unieke malplaatjes, auteursmilieu&#39;s, voorwaardelijke attributenprofielen, Fragmenten, of zelfs de configuraties van de Redacteur van het Web hebben.

Voorbeeldbestanden die u voor deze les wilt gebruiken, staan in het bestand [mapprofielen.zip](assets/folderprofiles.zip).

>[!VIDEO](https://video.tv.adobe.com/v/342758?quality=12&learn=on)

## Mapprofielen openen

Configuraties worden beheerd via het pictogram Mapprofielen.

1. Klik in het navigatiescherm op de knop [!UICONTROL **Gereedschappen**] pictogram.

   ![Gereedschapspictogram](images/reuse/tools-icon.png)

1. Selecteren **Hulplijnen** in het linkerdeelvenster.

1. Klik op de knop [!UICONTROL **Mapprofielen**] tegel.

   ![Mapprofielen](images/reuse/folder-profiles-tile.png)

1. Selecteer het gewenste profiel. Kies bijvoorbeeld **Globaal profiel**, het standaardprofiel.

   ![Globaal profiel](images/lesson-3/global-profile-tile.png)

## Voorwaardelijke kenmerken bewerken in het algemene profiel

Zodra u het Globale Profiel hebt betreden kunt u zijn configuratie uitgeven. De instellingen voor het algemene profiel worden toegepast op alle gebruikers, tenzij anders aangegeven.

1. Selecteer in het algemene profiel de optie **Voorwaardelijke kenmerken** tab.

1. Klikken [!UICONTROL **Bewerken**] in de linkerbovenhoek van het scherm.

   ![Voorwaardelijke kenmerken](images/lesson-3/edit-conditional-attributes.png)

1. Klikken [!UICONTROL **Toevoegen**].

1. Vul de **Naam**, **Waarde**, en **Label** velden voor de nieuwe voorwaarde.

   ![new Condition](images/lesson-3/new-condition.png)

1. Klikken [!UICONTROL **Opslaan**] in de linkerbovenhoek van het scherm.
De nieuwe voorwaarde is nu beschikbaar voor alle gebruikers. U kunt het selecteren in het deelvenster Eigenschappen van inhoud en het toepassen op de gewenste inhoud.

## Een nieuw mapprofiel maken

Naast het standaard algemene profiel kunt u ook uw eigen aangepaste profielen maken.

1. Klik in het navigatiescherm op de knop [!UICONTROL **Gereedschappen**] pictogram.

   ![Gereedschapspictogram](images/reuse/tools-icon.png)

1. Selecteren **Hulplijnen** in het linkerdeelvenster.

1. Klik op de knop [!UICONTROL **Mapprofielen**] tegel.

   ![Mapprofielen](images/reuse/folder-profiles-tile.png)

1. Klikken [!UICONTROL **Maken**].

1. In het dialoogvenster Mapprofiel maken.

   a. Geef het profiel een naam.

   b. Geef een pad op.

   c. Klikken [!UICONTROL **Maken**].

   ![Mapprofiel maken](images/lesson-3/create-folder-profile.png)

Er wordt een tegel met de nieuwe profielnaam weergegeven op de pagina Mapprofielen.

## Beheerders toevoegen via het tabblad Algemeen

Administratieve gebruikers hebben rechten om de Voorwaardelijke Attributen, het Authoring Malplaatje, en de Voorinstellingen van de Output voor het Profiel van de Omslag bij te werken.

1. Klik op de tegel om het gewenste mapprofiel te openen.

   ![Mapprofiel bewerken](images/lesson-3/edit-folder-profile.png)

1. Selecteer **Algemeen** tab.

1. Klikken [!UICONTROL **Bewerken**] links boven in het scherm.

1. Selecteer onder Admin-gebruikers een gebruiker in het vervolgkeuzemenu of typ de naam van een gebruiker.

1. Klikken [!UICONTROL **Toevoegen**].

   U kunt desgewenst meerdere Admin-gebruikers toevoegen.

   ![Admin toevoegen](images/lesson-3/add-admin.png)

1. Klikken [!UICONTROL **Opslaan**] in de rechterbovenhoek van het scherm als alle gebruikers zijn toegevoegd.

Administratieve gebruikers worden nu toegewezen aan dit profiel.

## Een nieuw publiek toevoegen via het tabblad Voorwaardelijke kenmerken

Zodra u het Globale Profiel hebt betreden kunt u zijn configuratie uitgeven. De instellingen voor het algemene profiel worden toegepast op alle gebruikers, tenzij anders aangegeven.

1. Selecteer vanuit het gewenste mapprofiel de optie **Voorwaardelijke kenmerken** tab.

1. Klikken [!UICONTROL **Bewerken**] in de linkerbovenhoek van het scherm.

   ![Voorwaardelijke kenmerken 2 bewerken](images/lesson-3/edit-conditional-attributes-2.png)

1. Klikken [!UICONTROL **Toevoegen**].

1. Vul de **Naam**, **Waarde**, en **Label** velden voor de nieuwe voorwaarde.

   Klik op de knop [!UICONTROL **Plus**] Met sign kunt u extra waarde- en labelparen toevoegen voor het benoemde kenmerk.

   ![Voorwaarden toevoegen](images/lesson-3/add-conditions.png)

1. Klikken [!UICONTROL **Opslaan**] in de linkerbovenhoek van het scherm.

De nieuwe voorwaardelijke kenmerken zijn toegevoegd aan dit profiel.

## Kies een sjabloon en een kaart op het tabblad Ontwerpsjablonen

AEM Hulplijnen worden geleverd met ontwerpsjablonen en -kaarten die niet in de box staan. U kunt deze beperken tot specifieke auteurs. Standaard worden de sjablonen opgeslagen op de middelenlocatie in de map DITA-sjablonen.

1. Selecteer het tabblad Ontwerpsjablonen in het gewenste mapprofiel.

1. Klik op Bewerken in de linkerbovenhoek van het scherm.

1. Voeg een Kaartsjabloon toe.

   a. Van de **Kaartsjablonen** selecteert u een optie in de beschikbare kaarten.

   b. Klikken [!UICONTROL **Toevoegen**].

   ![Kaartsjablonen](images/lesson-3/map-templates.png)

1. Voeg een onderwerpsjabloon toe.

   a. Van de **Onderwerpsjablonen** selecteert u een optie in de beschikbare sjablonen.

   ![Onderwerpsjablonen](images/lesson-3/topic-templates.png)

1. Klikken [!UICONTROL **Toevoegen**].

1. Voeg desgewenst aanvullende onderwerpsjablonen toe.

1. Als u klaar bent, klikt u op [!UICONTROL **Opslaan**] links boven in het scherm.

De nieuwe ontwerpsjablonen zijn toegevoegd aan dit profiel.

## Niet-essentiële voorinstellingen verwijderen op het tabblad Voorinstellingen voor uitvoer

U kunt elke uitvoervoorinstelling configureren op basis van het mapprofiel. Uitvoervoorinstellingen die niet nodig zijn, moeten worden verwijderd.

1. Selecteer vanuit het gewenste mapprofiel de optie **Voorinstellingen uitvoer** tab.

1. Schakel in het linkerdeelvenster de selectievakjes in van alle voorinstellingen die niet vereist zijn.

   ![Voorinstellingen verwijderen](images/lesson-3/delete-presets.png)

1. Klikken [!UICONTROL **Voorinstelling verwijderen**] in de linkerbovenhoek van het scherm.

1. Klik in het dialoogvenster Voorinstelling verwijderen op [!UICONTROL **Verwijderen**].

   ![Verwijderen](images/lesson-3/delete.png)

De enige voorinstellingen voor uitvoer die worden weergegeven, zijn de voorinstellingen die worden gebruikt.

## Een fragment uploaden vanaf het tabblad Configuratie van de XML-editor

1. Selecteer vanuit het gewenste mapprofiel de optie **XML Editor-configuratie** tab.

1. Klik onder Fragmenten van de XML-editor op [!UICONTROL **Uploaden**].

   ![Fragment uploaden](images/lesson-3/upload-snippet.png)

1. Navigeer naar een eerder gemaakt fragment.

1. Klikken [!UICONTROL **Openen**].

1. Klikken [!UICONTROL **Opslaan**] links boven in het scherm.

U hebt met succes de Configuratie van de Redacteur gewijzigd om Fragmenten op te nemen.

## Geef het mapprofiel op in de opslagplaats

In de Editor ziet u de resultaten van de wijzigingen die u hebt aangebracht in de mapprofielen.

1. Navigeren naar **Weergave opslagplaats**.

1. Klik op de map voor de inhoud waarmee u wilt werken.

1. Klik op de knop [!UICONTROL **Gebruikersvoorkeuren**] op de bovenste werkbalk.

   ![Gebruikersvoorkeuren](images/lesson-3/hr-user-prefs.png)

1. Selecteer in het dialoogvenster Gebruikersvoorkeuren het gewenste mapprofiel in het vervolgkeuzemenu.

   ![Gebruikersvoorkeuren selecteren](images/lesson-3/select-user-pref.png)

1. Klikken [!UICONTROL **Opslaan**].

U hebt het mapprofiel toegepast op uw inhoud. Nu, wanneer u een nieuw onderwerp DITA creeert, zult u een beperkte lijst van onderwerptypes zien die op het Profiel van de Omslag wordt gebaseerd. De voorwaarde van het publiek bevat de Globale montages evenals die specifiek voor het Profiel van de Omslag. In het geüploade fragmentbestand is een set standaardfragmenten gemaakt waaruit u kunt kiezen. Op het dashboard Kaart worden de beperkte uitvoervoorinstellingen weergegeven.
