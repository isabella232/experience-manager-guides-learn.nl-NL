---
title: Documenten vertalen vanuit de webeditor
description: Vertaal uw inhoud vanuit de webeditor naar meerdere talen. Leer hoe u een vertaalproject maakt, regels toevoegt, versies weergeeft en bestanden die niet gesynchroniseerd zijn, in AEM hulplijnen sluit.
exl-id: 02fc2b51-5b9a-4ad6-9e2e-726ab7602514
source-git-commit: 3cc7a9bf91881ed09173077be7d7fc7705295e4b
workflow-type: tm+mt
source-wordcount: '1904'
ht-degree: 0%

---

# Documenten vertalen vanuit de webeditor {#id21BKF0Z0YZF}

>[!TIP]
>
> Het wordt geadviseerd om deze eigenschap van de Vertaling van de Redacteur van het Web te gebruiken als u aan AEMGidsen as a Cloud Service versie van februari 2022 of later hebt bevorderd.

AEM Gidsen komt met een krachtige eigenschap in de Redacteur van het Web die u toelaat om uw inhoud in veelvoudige talen te vertalen. U kunt een nieuw vertaalproject creëren en later de vertaalbanen toevoegen aan het bestaande vertaalproject. U kunt ook een meertalig vertaalproject maken dat vertaaltaken voor alle geselecteerde talen omvat.

>[!NOTE]
>
> Uw beheerder kan het tabblad Beheren \(gebruikt voor vertaling\) in de webeditor configureren. Zie voor meer informatie *Vorm de vertaaleigenschap in de Redacteur van het Web* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.

## Voordat u begint

Voordat u de stappen in deze procedure uitvoert, moet u controleren of u de vereiste hoofdmap en doelmappen voor de taal hebt gemaakt

1. Maak een hoofdmap waarin u de broninhoud wilt opslaan. De hoofdmap moet worden gemaakt met de taalnaam \(zoals Engels\) of taalcode \(en\).
1. Maak de doelmappen waarnaar u de inhoud wilt vertalen. Als u bijvoorbeeld uw inhoud wilt omzetten in Duits of Frans, moet u een map maken met de naam \(voor Duits\) of -fr \(voor Frans\).

>[!NOTE]
>
> De hoofdmap en de doelmappen moeten op hetzelfde niveau worden gemaakt.

## Een vertaalproject maken

1. Open in het deelvenster Opslagplaats het DITA-kaartbestand in de kaartweergave.
1. Klik op de knop **Beheren** tab. In het deelvenster Vertaling wordt de hyperlinktitel van de DITA-kaart weergegeven, samen met de **Talen** lijst.
1. Van de **Talen** selecteert u de landinstelling waarnaar u het project wilt vertalen. U kunt **Alles** om uw project in alle beschikbare talen te vertalen.

   >[!NOTE]
   >
   > De lijst bevat de taalmappen en hun taalcodes. Frans \(fr\) en Duits \(de\).

   >[!IMPORTANT]
   >
   > Taal toont alleen de talen waarvoor een taalmap parallel aan de brontaal wordt gemaakt. Een taalmap die op een ander niveau is gemaakt, zoals één niveau lager in de brontaalmap, wordt ook niet weergegeven. Zorg ervoor dat u alle doeltaalmappen maakt op hetzelfde niveau als de brontaalmap.

   ![](images/translation-languages.png){width="350" align="left"}

1. U kunt ook de volgende opties gebruiken:

   **Basislijn gebruiken:** U kunt een basislijn selecteren om uw project te vertalen. Klik op Basislijn gebruiken en kies een basislijn die op de kaart is gemaakt. Alle bestanden die deel uitmaken van de geselecteerde basislijn, worden weergegeven op de pagina Vertalen. Nadat de inhoud is vertaald, kunt u de vertaalde basislijn exporteren. Voor meer informatie over het exporteren van de vertaalde basislijn raadpleegt u [Vertaalde basislijn exporteren](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

   **Laatste versie gebruiken als ingeschakeld**: Kies of u de versie van de onderwerpen wilt filteren op basis van de aanmaakdatum en -tijd. Wanneer u een datum en tijd selecteert, wordt alleen de meest recente versie van de bestanden weergegeven die op of voor de geselecteerde datum en tijd zijn gemaakt.

1. Klikken **Toepassen**. Een lijst met details van onderwerpen en bijbehorende activa wordt getoond.
1. Selecteer de onderwerpen die u voor vertaling wilt verzenden. U kunt de onderwerp het filtreren opties voor de volgende kolommen ook gebruiken:

   - **Titel**: Titel van het bronbestand.  Houd de cursor boven de titel van het bronbestand om de titel van het doelbestand of het vertaalde bestand weer te geven.
   - **Bestandsnaam**: Naam van het bronbestand
   - **Bestandstype**: Type bronbestand. De beschikbare opties zijn Kaart, Onderwerp, en Beeld.
   - **Referentietype**: directe of indirecte verwijzingen
   - **Versie**: Versienummer van het bronbestand
   - **Versielabel**: Label voor de geselecteerde versie van het bronbestand
   - **Doelversie**: Versienummer van het doelbestand
   - **Documentstatus**: Status van het bronbestand. De beschikbare opties zijn Concept, In-Review en Reviewed.
   - **Doeltaal**: De taal waarnaar u het bronbestand wilt vertalen
   - **Vertaalstatus**: De beschikbare opties zijn: Niet gesynchroniseerd, Kopie ontbreekt, Bezig en Gesynchroniseerd.
   - **Doellabel**: Label voor de geselecteerde versie van het doelbestand
1. Klikken **Verzenden voor vertaling** in de rechterbovenhoek.

   ![](images/translation-send.png){width="800" align="left"}

1. Selecteer in het vervolgkeuzemenu de optie **Nieuw vertaalproject maken**.

   ![](images/translation-project-types.png){width="350" align="left"}

   Naast een nieuw vertaalproject kunt u ook uit de volgende opties kiezen:

   - U kunt ervoor kiezen **Een structuur maken** alleen voor het vertaalproject.
   - U kunt ervoor kiezen **Nieuw XLIFF-vertaalproject maken** om de XML-inhoud om te zetten in de XLIFF (XML Localization Interchange File Format). XLIFF is een open op XML-gebaseerde indeling die wordt gebruikt om de gegevensoverdracht tussen verschillende gereedschappen die in het vertaalproces van de inhoud worden gebruikt, te standaardiseren. AEM Hulplijnen ondersteunen XLIFF versie 1.2. In een XLIFF-project wordt de inhoud geëxporteerd naar de industriestandaard XLIFF-indeling, die aan vertalers kan worden geleverd. Met de XLIFF-indeling kunt u segmenten die u al tijdens de vertaalfase hebt vertaald, opnieuw gebruiken.\
     Nadat de inhoud XLIFF wordt vertaald, kan het in AEMGidsen worden ingevoerd die tot een vertaalde versie van het originele DITA- project leiden.

     >[!NOTE]
     >
     > XLIFF-export werkt alleen met de configuratie voor menselijke vertaling.

   - U kunt **Een nieuw meertalig vertaalproject maken** Dit omvat vertaaltaken voor alle talen die u hebt geselecteerd voor vertaling. Als u bijvoorbeeld Frans, Duits en Spaans hebt geselecteerd, wordt er een project met vertaalbanen voor alle drie de talen gemaakt.
   - Als u reeds een vertaalproject hebt, kunt u onderwerpen aan dat project toevoegen. Selecteer Toevoegen aan **Bestaand vertaalproject** in de projectlijst en kies een project in de lijst Bestaand vertaalproject. U kunt deze projecten op meest recente, stijgende, of dalende orde sorteren.

     >[!NOTE]
     >
     > Als uw bestaande project een bereikproject is, wordt de naam &#39;\(Scoping\)&#39; toegevoegd.

   - Als u het werkingsgebied voor een te vertalen project moet creëren, kunt u selecteren **Een nieuw vertaal-project met bereik maken**. Hierdoor worden de kopieën niet voor vertaling verzonden en blijft de oorspronkelijke vertaalstatus van de bestanden behouden. Er is geen effect op het exemplaar van de bestemmingstaal van de genoemde onderwerpen die voor scoping worden verzonden.
1. In de **Projecttitel** voert u een titel in voor het project.
1. Klikken **Maken** om een nieuw vertaalproject op te zetten.

   Een nieuw vertaalproject wordt gecreeerd met de geselecteerde versie van de onderwerpen. Op dit moment wordt een pop-upbericht weergegeven met de bevestiging dat het vertaalproject is gemaakt. Zodra alle exemplaren van de doeltaal in het vertaalproject beschikbaar zijn, krijgt u een bericht in Inbox. Zodra de doeltaalkopieën beschikbaar zijn in het vertaalproject, kunt u de vertaaltaak starten. Zie voor meer informatie [De vertaaltaak starten](translation-first-time.md#id225IK030OE8).

   >[!NOTE]
   >
   > Als u de vertaling voor een of meer onderwerpen in een vertaaltaak afwijst, kunt u **In uitvoering** de vertaalstatus van alle afgewezen onderwerpen wordt weer hersteld . De status van de bedoelde onderwerpen wordt gecontroleerd en teruggezet volgens de meest recente vertaalstatus. Ook, worden de vertaaldossiers die in het bestemmingsproject worden gecreeerd niet geschrapt zelfs als de vertaling voor hen wordt verworpen.

## De vertaalregels toevoegen

Met AEM hulplijnen kunnen uw beheerders de vertaalregels configureren. De indeling SRX (Segmentation Rules eXchange) is een standaard voor het uitwisselen van segmentatieregels tussen verschillende gebruikers en verschillende vertaalomgevingen. U kunt een map maken en uw aangepaste SRX-bestanden eraan toevoegen.

SRX-bestanden moeten een naam hebben `<language-code>.srx`. Bijvoorbeeld, en-US, of ar-AE.

>[Opmerking]
>De titel is niet hoofdlettergevoelig, dus je kunt &#39;en-US&#39;, &#39;en-us&#39; of &#39;EN-us&#39; hebben. Bovendien kunnen AEM hulplijnen &#39;-&#39; (afbreekstreepje) of &#39;_&#39; (onderstrepingsteken) oplossen. Dus je kunt &#39;en-US&#39; of &#39;en_US&#39; hebben.

U kunt deze bestanden ook in elke map plaatsen die zich in de hoofdmap met AEM elementen bevindt. `./content/dam`.



Zodra u de omslag hebt gecreeerd die de SRX dossiers bevat, kunt u de omslagweg in de Vertaling SRX plaatsconfiguratie binnen uw omslagprofiel toevoegen.

Het wordt aanbevolen dat u voor betere prestaties alleen SRX-bestanden in de map bewaart die in het mapprofiel is geconfigureerd.


AEM de Gidsen kiezen de regels SRX volgens de brontaal van het vertaalproject. Het zoekt een douaneSRX dossier voor een taal, en als u geen douaneSRX dossier bepaalt, dan plukt het de regels zoals per uit de doos vertaalregels.


Voor meer informatie over het instellen van algemene profielen en mapprofielen raadpleegt u *Ontwerpsjablonen configureren* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.

## Geef het versielabel door aan de doelversie

Met AEM hulplijnen kunt u het label van het bronbestand aan het doelbestand doorgeven. Zo kunt u gemakkelijk de bronversie van het vertaalde bestand identificeren.

Als u het label van de bronversie wilt toevoegen aan de doelkopie, moet uw systeembeheerder de optie selecteren **Bronversielabels doorgeven aan de doelversie** onder de **Vertaling** tab in **Editor-instellingen**.

Als u bijvoorbeeld bronbestanden met het versielabel hebt `Release 1.0` vervolgens kunt u het bronlabel \(`Release 1.0`\) naar het vertaalde bestand.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> Het bronlabel is slechts aan één doelversie gekoppeld. Als u het bronlabel naar een andere versie verplaatst, wordt dit automatisch weerspiegeld in het nieuwste doellabel.

## Versieverschil weergeven voor bestanden die niet zijn gesynchroniseerd 

AEM Gidsen verstrekt de eigenschap om de verschillen tussen de geselecteerde versie en de laatste vertaalde bronversie van de onderwerpen te controleren. U kunt ervoor kiezen om de **Niet gesynchroniseerd** op basis van de aangebrachte wijzigingen.

![](images/translation-version-diff.png){width="800" align="left"}

Selecteer de **Verschil tonen** pictogram \(![](images/show-difference-icon.svg)\) voor een onderwerp om de verschillen tussen de laatste vertaalde versie en de huidige versie van het geselecteerde dossier te zien.

>[!NOTE]
>
> **Verschil tonen** pictogram \(![](images/show-difference-icon.svg)\) wordt alleen weergegeven voor DITA-bestanden met de vertaalstatus **Niet gesynchroniseerd**.

De **Verschil in versie** wordt weergegeven. Het toont de **Laatst vertaalde versie** en de **Geselecteerde versie** nummer links. Het voorproefvenster toont de verschillen tussen de laatste vertaalde versie en de geselecteerde versie van het onderwerp.

![](images/version-diff.png){width="650" align="left"}

## Niet-synchrone elementen negeren

Als u wijzigingen aanbrengt in sommige elementen, zijn deze elementen niet meer synchroon. U kunt de gewijzigde elementen opnieuw vertalen of de status Niet-gesynchroniseerd negeren. Als u bijvoorbeeld enkele kleine wijzigingen hebt aangebracht waarvoor geen vertaling nodig is, kunt u de status van de wijzigingen markeren op Sync.

Voer de volgende stappen uit om de status Buiten-synchroniseren te negeren:

1. Selecteer de elementen waarvan u de status wilt wijzigen die niet meer gesynchroniseerd zijn.
1. Selecteer de **Sync markeren** knop \(![](images/translation-mark-in-sync-icon.svg)\) bovenaan. De **Sync markeren** wordt weergegeven.

   ![](images/translation-mark-in-sync.png){width="550" align="left"}

1. Klikken **Synchronisatie forceren**. De status wordt gesynchroniseerd ingesteld voor de geselecteerde elementen die niet gesynchroniseerd zijn.

>[!NOTE]
>
> **Sync markeren** knop \(![](images/translation-mark-in-sync-icon.svg)\) wordt alleen weergegeven voor elementen met de status Niet gesynchroniseerd.

## In uitvoering zijnde vertaalprojecten voor een kaart of een onderwerp weergeven

Sommige verwijzingen op het vertaaldashboard zijn mogelijk in uitvoering. Deze verwijzingen hebben een **In uitvoering** link onder **Vertaalstatus** kolom. Wanneer u op de koppeling klikt, wordt **Lopende projecten** wordt geopend. In het dialoogvenster ziet u de lijst met alle lopende vertaalprojecten \(samen met de doeltaal\) die de geselecteerde verwijzing bevatten.

>[!NOTE]
>
> U kunt de link In uitvoering zien voor de vertaalde projecten die zijn gemaakt in AEM release van februari 2023 of later met hulplijnen.

Klik op de naam van de verwijzing in het dialoogvenster om deze te openen in de voorvertoningsmodus. U kunt ook op het vertaalproject klikken om de vertaling te starten.

![](images/translation-in-progress.png){width="550" align="left"}

**Bovenliggend onderwerp:**[ Werken met de webeditor](web-editor.md)
