---
title: Toetsen
description: De sleutels staan u toe om veranderlijke informatie te omvatten aan wanneer het werken met DITA in AEM Gidsen
exl-id: cb64e094-fe6d-4a5e-8f0e-25ae58aaa2c6
source-git-commit: 1c4d278a05f2612bc55ce277efb5da2e6a0fa9a9
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---

# Toetsen

Verschillende materiaalsets kunnen vergelijkbare informatie bevatten die op bepaalde plaatsen moet worden aangepast. De sleutels staan u toe om veranderlijke informatie aan te omvatten wanneer het werken met DITA.

Voorbeeldbestanden die u voor deze les wilt gebruiken, staan in het bestand [keys.zip](assets/keys.zip).

>[!VIDEO](https://video.tv.adobe.com/v/342756?quality=12&learn=on)

## Toetsen inschakelen

1. Upload de set met beschikbare voorbeeldbestanden.

   a. Laad het ZIP-bestand.

   b. Vernieuw de AEM.

   c. Selecteer het bestand voor extractie.

   ![Postcode selecteren](images/lesson-9/select-zip.png)

   d. Klikken [!UICONTROL **Archief extraheren**] in de bovenste werkbalk.

   ![Werkbalk](images/lesson-9/extract-archive.png)

   e. Kies in het dialoogvenster de specifieke locatie voor bestanden die u wilt uitpakken, zoals een map met de naam Toetsen.

   f. Klikken [!UICONTROL **Volgende**].

   g. Sla eventuele conflicten over omdat deze niet bestaan voor inhoud die nog niet eerder is geüpload.

   h. Selecteren [!UICONTROL **Extraheren**] aan de rechterbovenhoek van het scherm.

2. Wanneer het uitpakken is voltooid, klikt u op [!UICONTROL **Ga naar de doelmap**].

   ![Bevestiging](images/lesson-9/go-to-target.png)

## Toetsen omzetten in waarden waarnaar wordt verwezen

Om sleutels correct te gebruiken, moet de Voorkeur van de Gebruiker een specifieke kaart als Kaart van de Wortel van verwijzingen voorzien. Binnen deze kaart is een inzameling van Sleutels, die samen binnen een topicgroep wordt gegroepeerd. Als u de kaart opent en de onderwerpen opent, worden de Toetsen omgezet in de waarden waarnaar deze kaart verwijst.

1. Geef een hoofdmap op.

   a. Open een kaart vanuit het scherm Toetsen.

   b. Gebruikersvoorkeuren configureren.

   c. Klik op de knop [!UICONTROL **Gebruikersvoorkeuren**] op de bovenste werkbalk.

   ![Werkbalk Boven](images/lesson-9/author-view.png)

   d. Klik op het sleutelpictogram om een **Hoofdmap** die wordt gebruikt om Toetsen op te lossen.

   e. Schakel de selectievakjes voor de gewenste elementen in.

   ![Vervolgkeuzelijst Elementen](images/lesson-9/select-assets.png)

   f. Klikken [!UICONTROL **Selecteren**].

   g. **Opslaan** de Voorkeuren van de Gebruiker.

2. Ga naar de **Kaartweergave**.

3. Open de opgegeven kaart.

De sleutels worden opgelost.

## Handmatig een nieuw sleutelbestand toevoegen

1. Open een kaart met een opgegeven hoofdmap.

2. Selecteer een toets.

   ![Key Dropdown](images/lesson-9/hybrid-key.png)

3. Voeg een nieuw sleutelwoord in.

   a. Klik op een geldige locatie op de kaart.

   b. Selecteer **Keydef** op de bovenste werkbalk.

   ![Keydef-werkbalk](images/lesson-9/key-icon.png)

   c. Voer in het dialoogvenster Keydef invoegen een unieke waarde in voor Toetsen die voor de definitie die u maakt, zinnig is.

   d. Klikken [!UICONTROL **Invoegen**].

4. Voeg topicmeta binnen keydef toe.

   a. Klik op de knop [!UICONTROL **Element invoegen**] op de bovenste werkbalk.

   ![Keydef-werkbalk](images/lesson-9/add-icon.png)

   b. Zoek en selecteer &#39;topicmeta&#39; in het dialoogvenster Element invoegen.

5. Voeg sleutelwoorden binnen topicmeta toe.

   a. Klik op de knop [!UICONTROL **Element invoegen**] op de bovenste werkbalk.

   ![Keydef-werkbalk](images/lesson-9/add-icon.png)

   b. Zoek in het dialoogvenster Element invoegen naar &quot;trefwoorden&quot; en selecteer deze.

6. Voeg een sleutelwoord binnen topicmeta toe.

   a. Klik op de knop [!UICONTROL **Element invoegen**] op de bovenste werkbalk.

   ![Keydef-werkbalk](images/lesson-9/add-icon.png)

   b. In de **Element invoegen** , zoekt en selecteert u &quot;trefwoord&quot;

7. Typ de waarde voor het trefwoord in het trefwoord.

Op de kaart zou uw keydef er nu ongeveer als volgt moeten uitzien:

![Keydef gereed](images/lesson-9/keydef.png)

## Een sleuteldefinitie configureren als een fragment

Fragmenten zijn kleine inhoudsfragmenten die over verschillende onderwerpen in uw documentatieproject opnieuw kunnen worden gebruikt. In plaats van handmatig elk sleuteldef te genereren, kunt u één enkel sleuteldef configureren als een fragment.

1. Selecteer een keydef-element op de kaart.

2. Klik in het contextmenu op [!UICONTROL **Fragment maken**].

3. Voeg een titel en beschrijving toe in het dialoogvenster Nieuw fragment.
U kunt ook bestaande toetsen of trefwoorddefinities uit de inhoud verwijderen.

4. Klikken [!UICONTROL **Maken**].

5. Selecteer in het linkerdeelvenster de optie **Fragmenten**.

6. Sleep het fragment dat u zojuist hebt gemaakt van het deelvenster Fragmenten naar de kaart.

7. Werk het toetsontwerp zo nodig bij met de eigenschappen van de inhoud.
Wanneer bewaard en verfrist, zal deze reeks Sleutels voor om het even welke gebruiker beschikbaar zijn die een kaart heeft bepaald die de zelfde Kaart van de Wortel bevat.
