---
title: Onderwerpen bewerken in de webeditor
description: Leer onderwerpen te bewerken in de webeditor. U kent verschillende bewerkingsfuncties om uw onderwerpbestanden in AEM hulplijnen te wijzigen.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 0%

---

# Onderwerpen bewerken in de webeditor {#id2056B040VUI}

De Redacteur van het Web komt met een waaier van het uitgeven eigenschappen die u gemakkelijk toestaan om uw onderwerpdossiers tot stand te brengen of te wijzigen. In het algemeen, zou u de volgende stappen uitvoeren om een onderwerp in de Redacteur van het Web uit te geven.

>[!IMPORTANT]
>
> Als u een toepassingsfout terwijl het werken aan de Redacteur van het Web tegenkomt, vernieuw de pagina om verder te werken.

1. Om veranderingen in uw onderwerp aan te brengen, klik binnen de tekstgrens van het vereiste element en begin het aanbrengen uitgeeft.

1. Als u een specifiek element wilt invoegen, klikt u aan het einde van het element waarna u het nieuwe element wilt invoegen en klikt u op het pictogram van het vereiste element op de werkbalk. U kunt ook de sneltoets gebruiken `Alt+Enter` om de **Element invoegen** popup.

   Er wordt een lijst met elementen weergegeven die in het onderwerp kan worden gebruikt. AEM Gidsen doet een intelligente plaatsing van elementen volgens hun geldige plaats in het onderwerp.

   >[!NOTE]
   >
   > U kunt ook kiezen welk pictogram in de werkbalk moet worden weergegeven door het dialoogvenster `ui_config.json` bestand bevindt zich op - `/etc/designs/fmdita/clientlibs/xmleditor/`. Neem voor meer informatie over het aanpassen van functies contact op met de systeembeheerder.

1. Nadat u het document hebt bewerkt, klikt u op **Opslaan**.

   >[!NOTE]
   >
   > Als u geen wijzigingen wilt doorvoeren in AEM opslagplaats, klikt u op **Sluiten** en klik vervolgens op **Sluiten zonder opslaan** in het dialoogvenster Niet-opgeslagen wijzigingen.

   **Browser vernieuwen tijdens bewerken van bestanden**
De Gidsen van de Experience Manager verleent de steun om browser te verfrissen terwijl u uw inhoud in de Redacteur van het Web uitgeeft. Met deze functie kunt u doorgaan met het bewerken van inhoud voor het geval u tijdens het werken een toepassingsfout tegenkomt. Als u de browser vernieuwt terwijl een of meer bestanden met niet-opgeslagen wijzigingen worden geopend voor bewerking, wordt u gewaarschuwd dat de niet-opgeslagen wijzigingen verloren kunnen gaan. U kunt de vernieuwingsbewerking annuleren en uw bestanden opslaan om de wijzigingen te behouden.

   Zelfs bij het verfrissen van browser, worden de meningen van de linkerzijde en het juiste paneel behouden in de Redacteur van het Web. Met de hulplijnen Experience Manager wordt de laatst opgeslagen status van de bestanden hersteld die in de webeditor zijn geopend wanneer u de browser vernieuwt. De bestanden die bijvoorbeeld in het deelvenster Opslagplaats worden geopend, worden opnieuw geopend. Het kaartvenster blijft samen met de eerder geopende kaart behouden.

   Het actieve onderwerp of de kaart DITA wordt opnieuw geopend in het inhoudsuitgevende gebied.

   Het rechterdeelvenster wordt ook opnieuw geopend en geeft dezelfde weergave weer als vóór het vernieuwen.

   **Werkkopie-indicator**
AEM Hulplijnen biedt de werkkopie-indicator die aangeeft of de huidige \(werkkopie\) van het bestand al dan niet synchroon is met de opgeslagen versie. Als u wijzigingen hebt aangebracht in uw huidige kopie en uw bestand niet hebt opgeslagen, wordt een \*-markering weergegeven samen met de titel op het tabblad Bestand van het onderwerp. Deze indicator dient als herinnering om uw wijzigingen op te slaan en verdwijnt wanneer u het bestand opslaat.

   ![](images/working-copy-text-update-indicator.png){width="550" align="left"}

   AEM Hulplijnen geven ook aan of de laatste opgeslagen \(werkende\) kopie van het bestand al dan niet synchroon is met de opgeslagen versie. Als u enkele niet-opgeslagen wijzigingen hebt aangebracht tussen de werkkopie en de laatst opgeslagen versie, wordt een \*-markering weergegeven samen met de versiegegevens die worden weergegeven in de rechterbovenhoek van het tabblad Bestandsbeheer van het onderwerp. Deze indicator dient als herinnering voor het opslaan en maken van een versie van de huidige \(werkende\) versie van het bestand.

   ![](images/version-update-indicator.png){width="550" align="left"}


**Bovenliggend onderwerp:**[ Werken met de webeditor](web-editor.md)
