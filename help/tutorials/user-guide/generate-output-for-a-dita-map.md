---
title: Produceer output voor een kaart DITA van de kaartconsole
description: Produceer output voor een kaart DITA van de kaartconsole in AEM Gidsen. Zorg voor meer informatie over het genereren van uitvoer en hoe u de status kunt bekijken, een uitvoertaak kunt annuleren en verwijderen.
exl-id: 98afbdd2-56d7-44b0-ad2a-25e9143c88f3
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '1416'
ht-degree: 0%

---

# Produceer output voor een kaart DITA van de kaartconsole {#id1825FG00UHT}

Voer de volgende stappen uit om output voor een kaart te produceren DITA:

1. Navigeer in de interface Elementen naar het DITA-kaartbestand dat u wilt publiceren en klik erop.

   De DITA kaartconsole verschijnt met de lijst van de Voorinstellingen van de Output beschikbaar om output te produceren.

1. Selecteer een of meerdere uitvoervoorinstellingen die u wilt gebruiken voor het genereren van de uitvoer.

   ![](images/generate-multiple-outputs-uuid.png){width="800" align="left"}

   >[!NOTE]
   >
   > Als u de AEM Site-uitvoer genereert, gebruikt het publicatieproces de structuur die in het dialoogvenster `.ditamap` bestand om AEM sitestructuur te maken.

1. Klik op het pictogram Genereren om het genereren van de uitvoer te starten.


U kunt de huidige status van het verzoek van de outputgeneratie bekijken door op Output te klikken. Zie voor meer informatie [De status van de uitvoergeneratietaak weergeven](#viewing_output_history)

>[!IMPORTANT]
>
> Als een uitvoergeneratieproces voor een voorinstelling zich in de wachtrij of in uitvoering bevindt, kunt u geen andere uitvoergeneratietaak voor dezelfde voorinstelling starten.

U kunt de uitvoer van de PDF voor één of meerdere die outputvoorinstellingen produceren voor een kaart DITA van de Redacteur van het Web worden gecreeerd. Zie voor meer informatie [Met het deelvenster Snel genereren kunt u uitvoer voor de voorinstellingen genereren en weergeven](web-editor-quick-generate-panel.md#).

U kunt de output van de Plaats van de AEM voor één of meerdere onderwerpen, of de volledige kaart DITA van de Redacteur van het Web ook produceren. Zie voor meer informatie [Publiceren op basis van artikelen vanuit de webeditor](web-editor-article-publishing.md#id218CK0U019I).

## Incrementele productie van uitvoer {#generating_standalone_topic}

>[!NOTE]
>
> Incrementele uitvoergeneratie is alleen van toepassing op AEM Site-uitvoer. U kunt ook alleen DITA \(.dita/.xml\)-onderwerpen opnieuw genereren op basis van een DITA-kaart of submappen. Als u een kaart DITA, submap, onderwerpgroep, of een onderwerp met selecteert `@processing-role="resource-only"`De optie Opnieuw genereren is dan niet beschikbaar.

Er zou een aantal instanties kunnen zijn waar u slechts een paar onderwerpen in uw kaart zou bijwerken DITA en duw slechts die bijgewerkte onderwerpen levend. Om dergelijke scenario&#39;s te behandelen, staat AEM Gidsen u toe om stijgende output tot stand te brengen. Als u een paar onderwerpen hebt bijgewerkt, te hoeven u niet om de volledige kaart opnieuw te produceren DITA. U kunt alleen de bijgewerkte onderwerpen selecteren en opnieuw genereren.

Als uw kaart wordt bebroed en u één enkel onderwerp in die kaart hebt bijgewerkt, dan moet u de volledige kaart voor het bijgewerkte onderwerp of de inhoud regenereren om in de output te weerspiegelen. U zult niet de optie van de outputregeneratie op een onderwerpniveau krijgen, is het slechts beschikbaar op het \(gescheurde \) kaartniveau. Dit is van toepassing op de bovenliggende kaart en alle submaps.

Voer de volgende stappen uit om output voor een specifiek onderwerp of een groep onderwerpen opnieuw te produceren:

>[!IMPORTANT]
>
> Wanneer u de AEM Site-uitvoer opnieuw genereert, wordt de uitvoer gemaakt met de huidige versie van de bestanden en niet met de gekoppelde basislijn.

1. Navigeer in de interface Elementen naar het DITA-kaartbestand en klik erop.

   De DITA kaartconsole verschijnt met de lijst van de Voorinstellingen van de Output beschikbaar om output te produceren.

1. Selecteer de **Onderwerpen** tab.

   Een lijst van onderwerpen beschikbaar in de kaart DITA wordt getoond.

1. Selecteer de onderwerpen die u opnieuw wilt genereren.

   >[!NOTE]
   >
   > Als u nieuwe onderwerpen aan de kaart DITA hebt toegevoegd, zult u niet die nieuwe onderwerpen van hier kunnen produceren. U moet de onlangs toegevoegde onderwerpen eerst publiceren door de DITA kaart te gebruiken publiceert functie.

   ![](images/regenerate-topics.png){width="800" align="left"}

1. Klikken **Regenereren**.

   De pagina Geselecteerde onderwerpen opnieuw genereren wordt weergegeven.

1. Selecteer de uitvoervoorinstelling die u wilt gebruiken om de geselecteerde onderwerpen opnieuw te genereren.

1. Klikken **Regenereren** om het productieproces voor de uitvoer te starten.


>[!IMPORTANT]
>
> Als u een onderwerptitel anders noemt en het onderwerp regenereert, reflecteert de bijgewerkte onderwerptitel niet in de DITA kaartlijst van inhoud. Om de onderwerptitel in TOC bij te werken, moet u de volledige kaart DITA produceren.

U kunt de huidige status van het verzoek van de outputgeneratie bekijken door op Output te klikken. Zie voor meer informatie [De status van de uitvoergeneratietaak weergeven](#viewing_output_history).

## De status van de uitvoergeneratietaak weergeven {#viewing_output_history}

Zodra u de taak van de outputgeneratie voor een kaart in werking stelt of geselecteerde onderwerpen regenereert, verzendt AEM Gidsen deze taak naar de rij van de outputgeneratie. Deze rij wordt bijgewerkt in echt - tijd, die de status van elke taak van de outputgeneratie in de rij toont.

Voer de volgende stappen uit om de rij van de outputgeneratie te bekijken:

1. Navigeer in de interface Elementen naar het kaartbestand waarvoor u de status van de uitvoergeneratie wilt controleren en klik erop.

1. Klikken **Uitvoer**.

   ![](images/output-queued.png){width="800" align="left"}

   De pagina Uitvoer bestaat uit twee delen:

   - **Uitvoer in wachtrij:**

     Vermeldt de output die of wachten om worden geproduceerd of onder generatieproces zijn. De taken in de wachtrij of die momenteel worden uitgevoerd, worden vóór de naam van de voorinstelling weergegeven met een blauw kleurenpictogram. U kunt ook de instelling of voorinstelling voor het genereren van uitvoer vinden die wordt gebruikt voor de taak in de wachtrij, het type, de gebruiker die de taak heeft gestart, de tijd sinds het moment waarop de taak in de wachtrij wordt geplaatst en de huidige status.

     Klik op de koppeling voor toegang tot de **Dashboard publiceren** en bekijk de huidige actieve status. Een lijst met alle actieve publicatietaken is beschikbaar op het dashboard Publiceren. De **In wachtrij geplaatste uitvoerbestanden** en de **Dashboard publiceren** de verbinding wordt getoond slechts wanneer er output is die of wachten om worden geproduceerd of onder generatieproces zijn. Ze worden niet weergegeven wanneer de uitvoertaken zijn voltooid.Zie voor meer informatie over het publicatiedashboard [Publicatietaken beheren met het dashboard Publiceren](generate-output-publish-dashboard.md#).

   - **Gegenereerde uitvoer**

     Hiermee geeft u de uitvoertaken weer die zijn voltooid. Nogmaals, is de hier getoonde informatie gelijkaardig aan de Gloonde sectie van Output met een paar verschillen. U hebt nieuwe informatie in de vorm van het pictogram van het outputresultaat en de tijd van de outputgeneratie.

     In deze lijst kunt u taken uitvoeren die met succes zijn uitgevoerd, taken die met een bericht zijn uitgevoerd of mislukte taken. De geslaagde taken worden weergegeven met een groen kleurpictogram, de taken met een bericht hebben een oranje kleurpictogram en de mislukte taken worden weergegeven met een rood kleurpictogram.

     Voor alle taken maakt het publicatieproces een logbestand \(logs.txt\) dat kan worden geopend door op de koppeling in de kolom Gegenereerd op te klikken. Voor taken die zijn mislukt of berichten bevatten, kunt u het logbestand controleren. Dit wordt uitgelegd in de sectie [Logbestand weergeven en controleren](generate-output-basic-troubleshooting.md#id1822G0P0CHS).

     >[!NOTE]
     >
     > Wanneer u op een koppeling van de gegenereerde PDF-uitvoer klikt, wordt u gevraagd de PDF te downloaden. Dit is het standaardgedrag in AEM 6.5 en 6.4.


## Een uitvoergeneratietaak annuleren {#id2061H100T5Z}

Met AEM hulplijnen kunnen uitgevers op eenvoudige en eenvoudige wijze alle publicatietaken annuleren. Als uitgever kunt u een aan de gang zijnde het publiceren taak van de DITA kaartconsole of [Dashboard publiceren](generate-output-publish-dashboard.md#).

Voer de volgende stappen uit om een taak van de outputgeneratie van de DITA kaartconsole te annuleren:

1. Navigeer in de interface Elementen naar het kaartbestand waarvoor u een lopende uitvoergeneratietaak wilt annuleren en klik erop.

1. Klikken **Uitvoer**.

1. Houd de aanwijzer in de lijst Uitvoer in wachtrij boven een taak die u wilt annuleren.

1. Klik op de knop *Deze taak annuleren* pictogram.

   ![](images/cancel-publish-task-map-console.png){width="800" align="left"}

1. Klikken **Ja** op de bevestigingsberichtvraag van de Annulering.

   ![](images/confirm-cancel-output-map-condole.png){width="800" align="left"}

   Als de taak nog niet is gestart, wordt de opdracht Annuleren uitgevoerd op de taak. Voor een taak die wordt geannuleerd, wordt de Status geplaatst aan het Annuleren.

   Als de taak is geannuleerd, wordt deze naar de **Gegenereerde uitvoer** lijst met een **Geannuleerd** status. Wanneer u de muisaanwijzer op de geannuleerde taak plaatst, ziet u de naam van de gebruiker die de taak heeft geannuleerd. In de volgende screenshot *HTML 5* taak is geannuleerd.

   ![](images/cancelled-output-task.png){width="800" align="left"}


## Een uitvoertaak verwijderen uit de DITA-kaartconsole

Wanneer u veelvoudige output voor een kaart DITA produceert, over een periode de Gegenereerde lijst van Output voor zulk een kaart zeer lang wordt. Als uitgever kunt u de uitvoergeschiedenis van om het even welk kaartdossier schoonmaken door de verouderde taken uit te verwijderen *Gegenereerde uitvoer* lijst. Merk op dat de output niet uit het systeem wordt verwijderd, slechts wordt de ingang van de geproduceerde output verwijderd uit *Gegenereerde uitvoer* lijst.

Voer de volgende stappen uit om een uitvoertaak uit de Gegenereerde lijst van de Output te verwijderen:

1. Navigeer in de interface Elementen naar het kaartbestand waaruit u de taken wilt verwijderen en klik erop.

1. Klikken **Uitvoer**.

1. Houd de aanwijzer in de lijst Gegenereerde uitvoer boven een taak die u wilt verwijderen.

1. Klik op het verwijderpictogram.

   ![](images/delete-output-task.png){width="800" align="left"}

1. Klikken **Ja** op de bevestigingsberichtvraag van de Schrapping.

   De taak wordt verwijderd uit de lijst Gegenereerde uitvoer.


**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)
