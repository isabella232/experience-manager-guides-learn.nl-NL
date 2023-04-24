---
title: Spellingcontrole en zoeken/vervangen
description: Spellingcontrole gebruiken en zoeken/vervangen in AEM hulplijnen
exl-id: 5f39618d-a919-4d3c-a4de-2896f2d1bf20
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---

# Spellingcontrole en Zoeken/vervangen

De Editor voor AEM hulplijnen beschikt over krachtige mogelijkheden voor spellingcontrole en Zoeken en vervangen.

>[!VIDEO](https://video.tv.adobe.com/v/342768?quality=12&learn=on)

Een spelfout corrigeren

1. Zoek een fout in een open onderwerp, weergegeven met een rode onderstreping.

1. Houd Ctrl ingedrukt en klik op de secundaire muisknop in het woord.

1. Kies de juiste spelling in de suggesties.

Als de juiste spelling niet wordt voorgesteld, kunt u het woord altijd handmatig bewerken.

## Schakelen naar AEM spellingcontrole

U kunt een andere spellingcontrole dan het standaardwoordenboek van de browser gebruiken.

1. Navigeren naar **Editor-instellingen**.

1. Selecteer **Algemeen** tabblad Instellingen.

   ![Spellingcontrole configureren](images/lesson-11/configure-dictionary.png)

1. Er zijn twee opties:

   - **Spellingcontrole browser** — De standaardinstelling waarbij de spellingcontrole gebruikmaakt van het ingebouwde woordenboek van de browser.

   - **Spellingcontrole AEM** — gebruik dit om een lijst van het douanewoord te bouwen gebruikend AEM douanewoordenboek.

1. Kies **Spellingcontrole AEM**.

1. Klikken [!UICONTROL **Opslaan**].

Een aangepast woordenboek configureren

De beheerder kan de instellingen wijzigen zodat het AEM woordenboek aangepaste woorden zoals bedrijfsnamen herkent.

1. Ga naar de **Gereedschappen** venster.

1. Aanmelden bij **CRXDE Lite**.

   ![CRXDE Lite AEM UI](images/lesson-11/crxde-lite.png)

1. Ga naar de **_/apps/fmdita/config-knooppunt_**.

   ![CRXDE Lite Config-knooppunt](images/lesson-11/config-node.png)

1. Maak een nieuw bestand.

   a. Klik met de rechtermuisknop op de configuratiemap.

   b. Kies **Maken > Bestand maken**.

   ![Nieuw woordenboekbestand maken](images/lesson-11/new-dictionary-file.png)

   c. Geef het bestand een naam _**user_dictionary.txt**_.

   ![Tekst gebruikerswoordenboek](images/lesson-11/user-dictionary.png)

   d. Klikken [!UICONTROL **OK**].

1. Open het bestand.

1. Voeg een lijst met woorden toe die u in het aangepaste woordenboek wilt opnemen.

1. Klikken [!UICONTROL **Alles opslaan**].

1. Sluit het bestand.

Auteurs moeten mogelijk hun Web Editor-sessie opnieuw starten om de bijgewerkte lijst met aangepaste woorden in het AEM Woordenboek te krijgen.

## Zoeken en vervangen in één bestand

1. Klik op het pictogram Zoeken en vervangen op de bovenste werkbalk.

   ![Pictogram Vervangen zoeken](images/lesson-11/find-replace-icon.png)

1. Typ een woord of woordgroep in de onderste werkbalk.

1. Klikken [!UICONTROL **Zoeken**].

1. Typ zo nodig een woord om het gevonden woord te vervangen.

1. Klikken [!UICONTROL **Vervangen**].

## Zoeken en vervangen in de hele opslagplaats

1. Ga naar de **Bewaarplaats**.

1. Klik op de knop [!UICONTROL **Zoeken en vervangen**] pictogram linksonder in het scherm.

1. Klik op de knop [!UICONTROL **Instellingen tonen**] pictogram.

1. Kies

   - **Bestand uitchecken vóór vervangen** — als dit is ingeschakeld door een beheerder, wordt het bestand automatisch uitgecheckt voordat zoektermen worden vervangen.

   - **Alleen hele woorden** — hiermee wordt de zoekopdracht beperkt tot het exacte ingevoerde woord of de exacte ingevoerde woordgroep.

   ![Zoeken in vervangen in gegevensopslagruimte](images/lesson-11/repository-find-replace.png)

1. Klik op de knop [!UICONTROL **Filter toepassen**] pictogram om het pad te selecteren in de opslagplaats waar u de zoekopdracht wilt uitvoeren.

1. Voer de voorwaarden in die u wilt zoeken en vervangen.

1. Selecteer indien nodig **Nieuwe versie maken na vervangen**.

1. Klikken [!UICONTROL **Zoeken**].

1. Open het gewenste bestand en gebruik de pijlen om van het ene gevonden resultaat naar het volgende te navigeren.

   ![Interface voor navigatie zoeken vervangen](images/lesson-11/find-replace-navigation.png)
