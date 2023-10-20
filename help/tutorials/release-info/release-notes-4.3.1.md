---
title: Opmerkingen bij de release | Upgradeinstructies en opgeloste problemen in de Adobe Experience Manager Guides 4.3.1 release
description: Meer informatie over de opgeloste problemen en hoe u een upgrade uitvoert naar 4.3.1-versies van Adobe Experience Manager-hulplijnen
source-git-commit: eb22fe5d4872b0e5c6594869193799fd9e64d95d
workflow-type: tm+mt
source-wordcount: '1216'
ht-degree: 4%

---

# 4.3.1 Vrijgave van Adobe Experience Manager-hulplijnen (oktober 2023)

In deze releasenotitie worden de instructies voor de upgrade, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie 4.3.1 van de Adobe Experience Manager-hulplijnen (later genoemd als *Hulplijnen Experience Manager*).

Zie voor meer informatie over de nieuwe functies en verbeteringen [Nieuwe functies in 4.3.1-release van Adobe Experience Manager-hulplijnen](./whats-new-4.3.1-release.md).

## Upgrade naar versie 4.3.1 van de Experience Manager-hulplijnen


U kunt eenvoudig uw huidige versie van Hulplijnen upgraden naar versie 4.3.1. Voordat u verdergaat met de upgrade naar versie 4.3.1 van de Experience Manager-hulplijnen, moet u rekening houden met de volgende punten: u kunt de huidige versie van de Experience Manager-hulplijnen bijwerken naar versie 4.3.1


- Als u versie 4.3.0, 4.2 of 4.2.1 gebruikt, kunt u rechtstreeks upgraden naar versie 4.3.1.
- Als u versie 4.1 of 4.1.x gebruikt, moet u een upgrade naar versie 4.3.0, 4.2 of 4.2.x uitvoeren voordat u een upgrade naar versie 4.3.1 uitvoert.
- Als u versie 4.0 gebruikt, moet u een upgrade naar versie 4.2 uitvoeren voordat u een upgrade naar versie 4.3.1 uitvoert.
- Als u versie 3.8.5 gebruikt, moet u een upgrade naar versie 4.0 uitvoeren voordat u een upgrade naar versie 4.2 uitvoert.
- Als u een versie hebt die ouder is dan 3.8.5, raadpleegt u de sectie Upgradehulplijnen voor Experience Managers in de productspecifieke installatiehandleiding.


>[!NOTE]
>
>U moet AEM de dienstpak installeren alvorens de versie van de Gidsen van de Experience Manager te bevorderen.

Zie voor meer informatie [Upgradeinstructies](../install-guide/upgrade-xml-documentation.md).

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door de release van Experience Manager Guides 4.3.1.

### Adobe Experience Manager

**4.3.1 Niet-UUID**
Versie 6.5 Service Pack 18, 17, 16, 15 of 14

**4.3.1 UUID**
Versie 6.5 Service Pack 18, 17, 16, 15 of 14

Zie voor meer informatie de *Technische voorschriften* in de handleiding Adobe Experience Manager-hulplijnen installeren en configureren.

### FrameMaker en FrameMaker Publishing Server

| Geen | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (niet-UUID) | 2022 of hoger | 2020.2 of hoger* | 2022 of hoger | 2020.3 of hoger |
| 4.3.1 (UUID) | 2022 of hoger | 2020.2 of hoger* | 2022 of hoger | 2020.4 of hoger |
| | | | |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

### Zuurstofaansluiting

| Geen | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1 (niet-UUID) | 2.3-regelmatig-5 | 2.3-regelmatig-5 | 1.6 | 1.6 |
| 4.3.1 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2.3 | 2.3 |
|  |  |   |



### Versie van basissjabloon

| Naam van componentenpakket | Versie van componenten | Sjabloonversie |
|---|---|---|
| Experience Manager Guides Components Content Package for Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

### Authoring

- De uren van de middag worden niet geplaatst in **Datum** voor de vaststelling van basislijnen. (12712)
- Kan de JSON-code niet plakken in het dialoogvenster `<codeblock>` -element van de webeditor. (12326)
- Niet-opgeslagen versiewijzigingen en de indicatoren daarvoor worden niet weergegeven voor grote bestanden. (11784)
- Tijdens het bewerken in de Koreaanse taal verandert het eerste teken in de standaardwaarde. (10049)

- Het voorvoegsel wordt gedupliceerd in de voorvertoningsmodus van de webeditor. (13133)
- `Choicetable` rijen worden niet weergegeven of kunnen niet worden geselecteerd. (12616)
- De Redacteur van het Web werpt bevestigingsfouten in specifieke scenario&#39;s wanneer het creëren van een onderwerp gebruikend een douaneschema. (12576)
- De verwijzingen van het ditaval onderwerpmalplaatje leiden tot geen exemplaar in de inhoudsomslag wanneer het creëren van een kaart van het kaartmalplaatje. (12150)

- Het zoekvak in DITA-kaarten heeft geen knop Sluiten. (11867)
- Bij het opslaan van lange dossiers in de Redacteur van het Web, `DirtyChecker` Hiermee wordt een uitzondering gegenereerd met een lange stacktracering en worden de logbestanden gevuld. (11860)
- Het creëren van onderwerpen DITA vereist de toestemming van de Schrapping op de overeenkomstige omslagknoop, hoewel de kaart met schrijftoestemming kan worden gecreeerd. (11706)
- De Redacteur van het Web toont een onjuiste titel wanneer een schuine streep aanwezig is. (10949)

- Als de titel van een onderwerp een schuine streep &quot;/&quot;bevat, toont het lusje in de redacteur slechts de brieven die na dat komen. (13455)
- De voorvertoning van de afbeelding verdwijnt niet nadat de voorvertoning in de Editor is weergegeven. (13454)
- Enkele bestaande versie of de labels ervan worden na de upgrade naar 4.x niet weergegeven in Versiehistorie. (13247)
- Het deelvenster Versiehistorie in de gebruikersinterface Middelen bevat een onjuist tijdstempel voor de **Huidig** veld. (12624)
- Onderwerp met conref-titel wordt niet opgelost in de weergave Opslagplaats of Kaartweergave.(13304)


### Publiceren

- Native PDF | De volgorde van de onderwerpen is niet vast wanneer de PDF-uitvoer wordt gegenereerd. (13157)
- Native PDF| Geen standaardstijltag beschikbaar voor `<p>`element. (12559)
- Native PDF | Inline stijlen die worden toegepast op het inhoudsgebied, worden niet toegepast op de onderwerpen voor- en achtermaterie. (13510)
- De `DeliveryTarget` attribuut wordt niet verspreid bij het produceren van de output van de Plaats van de AEM.  (13132)
- De **Publiceren** De workflow blijft vastzitten tijdens het genereren van AEM Site-uitvoer voor inhoud met bepaalde fouten. (12000)

- Native PDF | Als u meerdere Xrefs toevoegt, wordt de tekst breder dan de kolombreedte. (13004)
- Native PDF | Wanneer het onderwerp en de titel zelfde identiteitskaart hebben, leidt het tot een misvormde generatie van de output van PDF. (12644)
- Native PDF | Bij het toevoegen van een outputklasse aan een ouder `<topicref>` element in een kaart DITA en het toepassen van douanestijl op de outputklasse, wordt het stileren toegepast op elementen binnen het onderwerplichaam, met inbegrip van sectitels. (12166)
- Incrementeel publiceren werkt niet als een DITA-kaart meerdere databases heeft. (12117)
- Site AEM | Bij het creëren van een kaart met keydef die aan een onderwerp als variabele richten en het toevoegen van verwerkings-rol=middel-slechts leidt tot sommige onverwachte pagina&#39;s. (12099)
- Als om het even welke activa van DAM van AEM in om het even welke output buiten de AEM plaats worden gebruikt, dan weerspiegelen de meta-gegevens &quot;jcr:createdBy&quot;niet de naam van de uitgever of de naam van de gebruiker die de kaart of het onderwerp DITA het laatst wijzigde. (12090)
- AEM Sites | DITA-kaart met padtekst in de navtitle (met niet-ondersteunde tekens) leidt tot onjuiste pagina-URL&#39;s. (11978)
- Native PDF | Problemen ter ondersteuning van topichead/topicmeta/navtitle in FrontMatting en Backissue. (11969)
- Native PDF | Het genereren van PDF voor grote documenten kost veel tijd. (11955)
- Native PDF | Als de naam van een voorinstelling wordt gewijzigd, wordt een NullPointerException gegenereerd terwijl een PDF-uitvoer wordt gegenereerd. (11889)
- De `<conref>` inhoud wordt niet weergegeven in de PDF-uitvoer. (11131)
- Er wordt een extra spatie toegevoegd in het dialoogvenster `<div>` elementen bij het schakelen tussen de weergave Auteur en Bron in de paginaopmaakeditor. (10750)
- De inhoud die in AEM Cloud Manager wordt gerepliceerd, is niet zichtbaar in de publicatie-instantie. (9564)


### Beheer

- Versiehistorie wordt niet weergegeven, zelfs niet als de `dc:format` eigenschap is niet aanwezig voor een element. (10463)
- De verwijzing van de inhoud is gebroken exemplaar-kleeft DITA- dossiers wanneer onderwerpidentiteitskaart niet het zelfde als GUID is. (12614)
- In dynamische basislijnen wordt de lijst met labels niet gehaald uit de directe referenties van de werkkopie van een DITA-kaart. (11917)
- De basislijn toont het onjuiste aantal dossiers op het Dashboard van de Kaart wanneer het gebruiken van Browse alle onderwerpfunctionaliteit. (13265)
- In de Redacteur van het Web, toont de basislijn de titel voor de vorige versie in plaats van de geselecteerde versie van het DITA- dossier. (13444)

### Controleren

- In de revisie over een onderwerp worden onjuiste opmerkingen weergegeven. (13453)
- Met de knop Sluiten op de pagina Revisie in de hulplijnen voor Experience Managers gaan de gebruikers naar de AEM Homepage. (13535)
- De gehechtheid wordt niet getoond op het juiste paneel van de redacteur voor een onderwerp in-overzicht. (13011)



### Vertaling

- De basislijn die uit de **Vertaling** Het dashboard mislukt en wordt niet geopend in de doeltaal. (13466)

- Er worden nieuwe vertaalprojecten gemaakt in plaats van nieuwe banen toe te voegen aan de geselecteerde bestaande vertaalprojecten.  (10214)
- De titel van het vertaalde bestand wordt weergegeven in plaats van de titel van het bronbestand. (11630)
- Automatisch goedkeuren werkt soms niet, en de uitzonderingen komen voor als een onjuiste waarde bij de Status van de Vertaling wordt geplaatst. (13607)
- De basislijn die u exporteert vanaf het dashboard Vertalen mislukt en wordt niet geopend in de doeltaal. (12993)
- Sommige bestanden ontbreken bij het gebruik van basislijnen bij het vertalen. (13021)