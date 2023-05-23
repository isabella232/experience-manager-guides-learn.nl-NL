---
title: Opmerkingen bij de release | Nieuwe functies in de release van Adobe Experience Manager Guides 4.2
description: Leer de nieuwe en verbeterde functies in 4.2-versies van Adobe Experience Manager Guides
source-git-commit: a54ada55dad4ff8da8eee3dccb5ad9028b4cdc9e
workflow-type: tm+mt
source-wordcount: '2417'
ht-degree: 0%

---

# Nieuwe functies in 4.2-release van Adobe Experience Manager-hulplijnen (februari 2023)

Dit artikel behandelt de nieuwe en verbeterde functies in versie 4.2 van de Gidsen van Adobe Experience Manager (later genoemd *Hulplijnen AEM*).

Voor meer informatie over de upgrade-instructies, compatibiliteitsmatrix en de problemen die in deze release zijn opgelost, raadpleegt u de [Opmerkingen bij de release](release-notes-4.2.md) artikel.

## Rapporten genereren vanuit de webeditor

AEM de Gidsen komen met een eigenschap in de Redacteur van het Web die u toelaat om de algemene volledigheid van uw technische documenten te controleren en rapporten voor hen te produceren.
U kunt de onderwerpenlijst bekijken en de meta-gegevens van alle verwijzingen voor de huidige kaart van
**Rapporten** in de webeditor.

**De weergave Lijst met onderwerpen genereren**

U kunt de Lijst van het Onderwerp produceren die gedetailleerde informatie over uw onderwerpen, zoals het verwijzingstype, documentstaat, en auteur verstrekt. U kunt CSV ook produceren om de huidige momentopname van de onderwerpen in de kaart te downloaden DITA.

**Metagegevens beheren en documentstatus wijzigen**

U kunt markeringen op een individueel onderwerp toepassen of de bulketiketterende eigenschap gebruiken om veelvoudige markeringen op veelvoudige onderwerpen, een kaart DITA, of een sub-kaart toe te passen. U kunt de documentstatus van alle geselecteerde onderwerpen ook wijzigen in de volgende mogelijke algemene documentstatus.

<img src="assets/web-editor-metadata-panel.png" alt="metagegevens beheren" width="600">

## Nieuwe UX voor de revisiefunctionaliteit

AEM gidsen verstrekt nu een betere UX die u helpt de onderwerpen herzien die voor overzicht worden gedeeld. In de meest recente ervaring zijn de volgende verbeteringen beschikbaar voor de revisiefunctionaliteit:

* Vernieuwde gebruikersinterface
* Het paneel van voorwaarden dat u toestaat om de inhoud volgens de beschikbare voorwaarden in het onderwerp te benadrukken.
* Elke opmerking in het opmerkingenvenster is gekoppeld aan de corresponderende tekst in het huidige onderwerp. Hiermee kunt u de tekst met opmerkingen herkennen.
* De opmerkingen worden weergegeven in de volgorde van de tekst met opmerkingen in het document.
* De naam van de revisietaak wordt weergegeven in de revisiewerkstroom.
* Selecteer de routekaart voor de overzichtstaak die wordt gebruikt om alle belangrijkste verwijzingen en verklarende woordenlijsttermijnen op te lossen die in de overzichtsinhoud worden gebruikt.
* Contextuele werkbalk waarmee u tekst snel kunt markeren of doorhalen.
* Met het menu Opties kunt u uw eigen opmerkingen bewerken of verwijderen.
* Voor verouderde commentaren, hebt u toegang tot zij-aan-zij mening die u helpt de vorige versie van het onderwerp met huidige overzichtsversie vergelijken
* Wanneer u de filters gebruikt, worden de opmerkingen in het rechtervenster gefilterd op basis van de selectie en wordt het aantal opmerkingen in het linkervenster dienovereenkomstig bijgewerkt.


<img alt="controletaak" src="assets/comment-pop-up-panel.png" width="600">


Raadpleeg voor meer informatie de *Onderwerpen of kaarten controleren* in de handleiding Adobe Experience Manager-hulplijnen gebruiken.

## Verbeterde vertaling

Nu hebt u gebruikersvriendelijkere verhogingen in het Dashboard van de Vertaling die u helpen uw documenten van de Redacteur van het Web gemakkelijk vertalen.


**De kolom Versielabel die aan het vertaaldashboard wordt toegevoegd**

In het vertaaldashboard, kunt u de kolom van het Etiket van de Versie ook zien. Hierdoor wordt het label voor de geselecteerde versie van het bronbestand weergegeven. Hiermee kunt u alle bestanden met een specifiek label selecteren en in één keer vertalen.

**Het versieverschil voor uit-synchronisatiebestanden van het vertaaldashboard weergeven**

Nu kunt u de verschillen tussen de geselecteerde versie en de laatste vertaalde bronversie van de onderwerpen controleren. U kunt er ook voor kiezen om de **Niet gesynchroniseerd** bestanden die zijn gebaseerd op de wijzigingen die zijn aangebracht tussen de twee versies van een onderwerp.

<img src="assets/translation-version-diff.png" alt="vertaalbord" width="600">



**Geef het versielabel door aan de doelversie**

Met AEM hulplijnen kunt u het label van het bronbestand aan het doelbestand doorgeven. Zo kunt u gemakkelijk de bronversie van het vertaalde bestand identificeren.

<img alt="vertaallabels" src="assets/translation-pass-source-label.png" width="600">

Als er bijvoorbeeld bronbestanden zijn waarop het versielabel Release 1.0 is toegepast, kunt u ook het bronlabel (Release 1.0) aan het vertaalde bestand doorgeven.

**Synchronisatie forceren voor niet-synchrone elementen**

Als u wijzigingen aanbrengt in sommige elementen, worden deze door AEM hulplijnen als Uit-synchroon gemarkeerd. U kunt de gewijzigde elementen opnieuw vertalen of de status Niet-gesynchroniseerd negeren. Als u bijvoorbeeld enkele kleine wijzigingen hebt aangebracht waarvoor geen vertaling nodig is, kunt u de status van de wijzigingen markeren als Bij synchroniseren.

**Vertaalprojecten in uitvoering voor een onderwerp of kaart weergeven**

Sommige verwijzingen op het vertaaldashboard zijn mogelijk in uitvoering. Nu AEM Gidsen verstrekt een eigenschap om u te helpen de lijst van alle Lopende vertaalprojecten (samen met de doeltaal) bekijken die de geselecteerde verwijzing bevatten.

Raadpleeg voor meer informatie de *Documenten vertalen vanuit de webeditor* in de handleiding Adobe Experience Manager-hulplijnen gebruiken.

## Produceer output in diverse formaten van de Redacteur van het Web

Nu kunt u de output voor uw onderwerpen of kaart DITA van de Redacteur van het Web gemakkelijk produceren. U kunt verschillende uitvoervoorinstellingen configureren, zoals AEM Site, PDF, HTML5, JSON (een indeling voor uitvoer zonder kop) en aangepaste uitvoer. Gebruik deze om de respectieve output te produceren. U kunt attributen in uw onderwerpen bepalen DITA en dan de voorwaarde gebruiken vooraf ingesteld om een voorwaarde toe te passen terwijl het publiceren van de output. U kunt de het publiceren eigenschap van de Basislijn ook gebruiken om een specifieke versie van uw kaart DITA of onderwerp selectief te publiceren.

**Uitvoervoorinstellingen voor Algemeen en Mapprofiel beheren**

AEM hulplijnen bieden u de functie om uitvoervoorinstellingen voor de algemene profielen en de mapprofielen te maken en te beheren. Vervolgens kunt u deze uitvoervoorinstellingen eenvoudig gebruiken om uitvoer te genereren voor alle mappen die betrekking hebben op dat algemene profiel of mapprofiel.

<img alt="voorinstelling toevoegen" src="assets/add-global-output-preset.png" width="400">


Deze algemene voorinstellingen worden weergegeven onder de **Uitvoer** tabblad van alle gerelateerde kaarten. U kunt ze gebruiken om de uitvoer voor alle verwante kaarten te genereren. U kunt de voorinstelling selecteren als de standaardvoorinstelling PDF om de PDF-uitvoer te genereren. U kunt ook **Bewerken**, **Naam wijzigen**, **Dupliceren**, of **Verwijderen** een bestaande uitvoervoorinstelling van de **Opties** -menu.

>[!NOTE]
>
>Alleen gebruikers met beheerdersrechten op mapniveau kunnen voorinstellingen voor algemene profielen en mapprofielen maken.

## Tekst zoeken en vervangen op kaartniveau

U kunt nu zoeken naar bestanden in een kaart die specifieke tekst bevatten. De gezochte tekst wordt benadrukt in de dossiers. U kunt het gezochte woord of de gezochte uitdrukking met een ander woord of een uitdrukking binnen de dossiers ook vervangen. Selecteer **Eén exemplaar vervangen** pictogram om het huidige exemplaar en het **Alles vervangen in bestand** om alle instanties in het geselecteerde bestand te vervangen. U kunt **Alles vervangen** pictogram om alle instanties van de gezochte term in alle bestanden te vervangen.

<img src="assets/map-find-replace.png" alt="map zoeken vervangen" width="600">


Standaard zijn de opties **Bestand uitchecken vóór vervangen** en **Nieuwe versie maken na vervangen** zijn geselecteerd, wordt een bestand uitgecheckt voordat u de tekst vervangt en wordt een nieuwe versie gemaakt nadat de tekst is vervangen. U kunt de tekenreeks ook doorzoeken in de indirecte verwijzingen in de DITA-kaart. Deze optie is standaard uitgeschakeld, zodat de zoekopdracht alleen op de directe referenties wordt uitgevoerd.

## Layoutweergave in de Kaarteditor


Nu kunt u de volledige lay-out van een kaart DITA in de Redacteur van de Kaart bekijken. Wanneer u een kaart opent om te bewerken, wordt de layoutweergave van de Kaarteditor geopend. In deze weergave ziet u de kaarthiërarchie in een boomstructuurweergave. U kunt de onderwerpen in een kaart ook bewerken en ordenen of structureren.

<img src="assets/layout-view-map.png" alt=" layoutweergave" width="600">

De layoutweergave bevat een aparte werkbalk waarmee u veel taken kunt uitvoeren op de onderwerpen in een kaart.
U kunt onderwerpverwijzingen, onderwerpgroep, zeer belangrijke definities in een kaart opnemen. U kunt de onderwerpen in een kaart reorganiseren door ze omhoog, omlaag, links of rechts te verplaatsen. U kunt de onderwerpen ook slepen en neerzetten om ze in een kaart te verplaatsen. De Kaarteditor verstrekt ook de pictogrammen om dossiers te sluiten of te ontgrendelen, de versiegeschiedenis te controleren, en een beheer van het versielabel te doen.


De layoutweergave bevat ook de **Weergaveopties** om regelnummer weer te geven of te verbergen, het selectievakje weer te geven of te verbergen of de bestandsnaam of titel voor de onderwerpen in een kaart weer te geven.
U kunt de onderwerpen ook bekijken die op de voorwaardelijke filters worden gebaseerd die op hen worden toegepast.

Naast het organiseren van onderwerpen in het kaartdossier, kunt u verwijzingen ook toevoegen, bewegen, kopiëren, kleven, of schrappen gebruikend **Opties** beschikbaar voor een element in de layoutweergave.

<img src="assets/layout-inline-attributes.png" alt=" toewijzingskenmerken" width="600">


In het rechterdeelvenster worden de eigenschappen Inhoud en Kaart weergegeven in de layoutweergave van de Kaarteditor. Nu kunt u de meta-gegevensinformatie voor de onderwerpen of de kaart ook plaatsen. U kunt de Titel Nav, de Tekst van de Verbinding, Korte Beschrijving, en Sleutelwoorden voor het geselecteerde onderwerp of de kaart bepalen.

Zie voor meer informatie *Layoutweergave* in de handleiding Adobe Experience Manager-hulplijnen gebruiken.

## Deelvenster Snel genereren

AEM Hulplijnen biedt nu het deelvenster Snel genereren, waarmee u snel de uitvoer kunt genereren en weergeven voor voorinstellingen die voor uw DITA-kaart zijn gemaakt.

<img src="assets/quick-generate-map-view.png" alt=" snel genereren, deelvenster" width="600">

In de **Snel genereren** kunt u de lijst zien met alle uitvoervoorinstellingen die voor uw DITA-kaart zijn gemaakt. U kunt ook snel de uitvoer weergeven die voor de voorinstellingen is gegenereerd. Er wordt een geluids- of foutbericht weergegeven als de uitvoer is gegenereerd. U kunt het foutenlogboek ook bekijken dat details van de fout bevat die in het generatieproces voorkwam.

## Een dynamische basislijn maken op basis van labels

AEM hulplijnen biedt u nu de functie om dynamische basislijnen te maken op basis van labels. Als u een basislijn genereert, een basislijn downloadt of een vertaalproject maakt met een basislijn, worden de bestanden dynamisch gekozen op basis van de bijgewerkte labels. Deze eigenschap is handig aangezien u niet de basislijn moet wijzigen wanneer het bijwerken van de etiketten.

<img src="assets/dynamic-baseline.png" alt=" dynamische basislijn" width="400">

## Bestanden verwijderen en dupliceren uit het deelvenster Verplaats

U kunt nu gemakkelijk bestanden (één bestand tegelijk) verwijderen uit het dialoogvenster **Opties** menu van het geselecteerde bestand in het paneel van de gegevensopslagruimte. Er wordt een bevestigingsbericht weergegeven voordat u het bestand verwijdert. Als er vanuit een ander bestand niet naar het bestand wordt verwezen, wordt het bestand verwijderd en wordt een succesbericht weergegeven.

<img src="assets/options-menu-repo-view-file-level.png" alt="menu met bestandsopties " width="500">

U kunt ook een kopie of kopie van het geselecteerde bestand maken. Standaard wordt het bestand gemaakt met een achtervoegsel (zoals bestandsnaam_1.extension).


## Andere verbeteringen in de webeditor

* In AEM hulplijnen kunt u bepaalde veelvoorkomende bewerkingen voor afbeeldingen en mediabestanden uitvoeren met behulp van het contextmenu. Nu kunt u ook de geselecteerde afbeelding of media vinden in de opslagplaats of de voorvertoning van het bestand bekijken in de interface Middelen.

* De naam van het huidige mapprofiel wordt weergegeven als een label voor het pictogram Gebruikersvoorkeuren op de hoofdwerkbalk. Zo kunt u het mapprofiel identificeren waaraan u werkt.

* Wanneer u een kaart opent in de kaartweergave, wordt de titel van de huidige kaart weergegeven in het midden van de hoofdwerkbalk. Dit is handig om de gebruikers te laten weten welke kaart momenteel is geopend.

## Geselecteerde versies van bestanden wissen

Terwijl u inhoud maakt en onderhoudt, worden mogelijk veel versies gemaakt voor uw DITA-bestanden in uw opslagplaats. Met AEM hulplijnen kunt u oudere versies van uw DITA-bestanden uit de opslagplaats verwijderen en schijfruimte vrijmaken.

<img src="assets/preview-purge-report.png" alt="Voorvertoning rapport leegmaken" width="500">

AEM Hulplijnen verwijderen niet de eerste versie van het bestand of een versie die in een basislijn is opgenomen, of er is een label op toegepast. Met Leegmaken worden zelfs geen bestanden verwijderd die deel uitmaken van een vertaling- of revisiewerkstroom. U kunt het aantal versies kiezen dat u wilt behouden en ook de bestanden verwijderen die ouder zijn dan het gedefinieerde aantal dagen.

Voordat u de purgeerbewerking start, kunt u een voorvertoning van het rapport bekijken van de versies die worden gewist. Vervolgens kunt u besluiten de leegmaakbewerking te starten of te annuleren.

<img src="assets/download-purge-report.png" alt="PDownload purge-rapport" width="500">

Zodra de leegmaakbewerking is voltooid, kunt u het rapport leegmaken controleren om de gezuiverde bestanden te zien.

## Titel weergeven in plaats van UUID in de Zuurstofbewerker

Met AEM hulplijnen kunt u nu kiezen **Titel gebruiken in Editor en kaartbeheer** in Instellingen. Als u deze optie selecteert, wordt de titel van het bestand weergegeven op het tabblad van het bestand wanneer het wordt geopend in de Editor of DITA Maps Manager. Als u deze optie niet selecteert, wordt de UUID van het bestand weergegeven op het tabblad van het bestand.

## Gebruikersinterface met metagegevens beschikbaar voor PDF-voorinstellingen

U kunt de metagegevens instellen vanuit de uitvoervoorinstelling van een DITA-kaart. U kunt de metagegevens Titel, Auteur, Onderwerp en Trefwoorden instellen. Deze metagegevens worden toegewezen aan de metagegevens in de bestandseigenschappen van de uitvoer PDF. Deze metagegevens overschrijven de metagegevens die op boekniveau zijn gedefinieerd. U kunt de metagegevens specifiek definiëren in elke uitvoervoorinstelling en deze doorgeven aan de PDF van de uitvoer.

## Native PDF | PDF met wijzigingsbalk geeft het verschil tussen documentversies aan

Nu kunt u een PDF maken die de verschillen in inhoud tussen twee versies weergeeft met de wijzigingsbalk. U kunt de huidige versie vergelijken met een basislijn van de vorige versie of de twee geselecteerde basislijnversies vergelijken.

<img src="assets/pdf-change-version.png" alt="pdf-change-version" width="600">

Er wordt een wijzigingsbalk weergegeven in de PDF om de gewijzigde, ingevoegde of verwijderde inhoud aan te geven. U kunt ook het volgende doen:
* Ingevoegde inhoud in groene kleur en onderstreept weergeven
* De verwijderde inhoud rood weergeven en doorhalen

## Native PDF | Variabele-ondersteuning voor uitvoerpad en naam van PDF-bestand

U kunt nu ook de volgende variabelen gebruiken om het uitvoerpad en het PDF-bestand te definiëren. U kunt een enkele of een combinatie van variabelen gebruiken om de volgende opties te definiëren:
* `${map_filename}`
* `${map_title}`
* `${preset_name}`
* `${language_code}`
* `${map_parentpath}` (Alleen voor uitvoerpad)
* `${path_after_langfolder}` (Alleen voor uitvoerpad)

## Native PDF | Inhoudsopgave genereren voor DITA-kaarten en paginalay-outs opnieuw ordenen

Nu kunt u TOC in kaarten ook produceren DITA gebruikend een geavanceerde PDF het plaatsen van het malplaatje. U kunt de weergave van de verschillende paginalay-outs in- of uitschakelen en ook de positie ervan wijzigen.

## Native PDF | Een aangepaste bladwijzer toevoegen in PDF-uitvoer

Nu kunt u voor eenvoudige navigatie een aangepaste bladwijzer toevoegen aan een bepaalde inhoud in de uiteindelijke PDF-uitvoer. Dit zou aan TOC worden toegevoegd die van de onderwerp of sectietitels in uw kaart DITA wordt gecreeerd.

## Native PDF | Aangepaste stijl toepassen op inhoudsopgave-items en onderwerpinhoud

AEM de Gidsen verstrekt de eigenschap om douanemateriaal op de ingangen van TOC of een bepaald onderwerp in de output van PDF toe te passen. U kunt bijvoorbeeld de kleur wijzigen van de tekst in de inhoudsopgave en de titel van het onderwerp. U kunt stijlen ook toepassen op de volledige inhoud binnen het onderwerp.
