---
title: Opmerkingen bij de release | Adobe Experience Manager Guides 4.2 release
description: Meer informatie over de opgeloste problemen en hoe u een upgrade uitvoert naar 4.2-versies van Adobe Experience Manager-hulplijnen
exl-id: 8a7fef77-63af-462f-89c5-054ab31e079b
source-git-commit: b7a6cb6086e94e2c0cbed8e35ca8d194a4fa36d4
workflow-type: tm+mt
source-wordcount: '1338'
ht-degree: 5%

---

# 4.2 Vrijgave van Adobe Experience Manager-hulplijnen (februari 2023)

In deze releasenotitie worden de instructies voor de upgrade, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie 4.2 van de Adobe Experience Manager-hulplijnen (later *Hulplijnen AEM*).

Voor meer informatie over de nieuwe functies en verbeteringen raadpleegt u [Nieuwe functies in 4.2-release van Adobe Experience Manager-hulplijnen](whats-new-4.2-release.md).

## Upgrade naar versie 4.2 van AEM hulplijnen

U kunt eenvoudig uw huidige versie van AEM hulplijnen upgraden naar versie 4.2. Voordat u verdergaat met de upgrade naar versie 4.2 van AEM hulplijnen, moet u rekening houden met de volgende punten:
* Als u versie 4.0, 4.1 of 4.1.x gebruikt, kunt u rechtstreeks upgraden naar versie 4.2.
* Als u versie 3.8.5 gebruikt, moet u een upgrade naar versie 4.0 uitvoeren voordat u een upgrade naar versie 4.2 uitvoert.
* Als u een versie gebruikt die ouder is dan 3.8.5, raadpleegt u de *Upgrade uitvoeren AEM hulplijnen* in de productspecifieke installatiehandleiding.

>[!NOTE]
>
>U moet AEM de dienstpak installeren alvorens AEM versie van Gidsen te bevorderen.

Zie voor meer informatie [Upgradeinstructies](assets/Adobe-Experience-Manager-Guides-Upgrade-Instructions-EN.pdf).

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM Guide 4.2.

### Adobe Experience Manager

**Niet-UUID**
Versie 6.5 Service Pack 15, 14, 13 of 12

**UUID**
Versie 6.5 Service Pack 15, 14, 13 of 12

Zie voor meer informatie de *Technische voorschriften* in de handleiding voor het installeren en configureren van Adobe Experience Manager-hulplijnen.

### FrameMaker en het Publiceren FrameMaker Server

| Geen | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.2 (Niet-UUID) | 2022 of hoger | 2020.2 of hoger* | 2022 of hoger | 2020.3 of hoger |
| 4.2 (UUID) | 2022 of hoger | 2020.2 of hoger* | 2022 of hoger | 2020.4 of hoger |
|  |  |  |  |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

### Zuurstofaansluiting

| Geen | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.2 (Niet-UUID) | 2.1-regelmatig-4 | 2.1-regelmatig-4 | 1.6 | 1.6 |
| 4.2 (UUID) | 2,8-uuid-8 | 2,8-uuid-8 | 2.3 | 2.3 |
|  |  |  |

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

### Authoring

* Het linkerpaneel breekt bij het toevoegen van een lusje. (11126)
* Wijzigingen in de webeditor veroorzaken problemen met `<dl>` en `<dlentry>`. (11024)
* Sommige kenmerken worden niet behandeld als voorwaardelijk en veroorzaken problemen. (10895)
* Drie niveaus of meer genest `<indexterm>` niet genest zijn in native PDF-export. (10799)
* De inhoud verdwijnt in de hoofdtekst van een taak bij het schakelen van Auteur naar Bronweergave. (10735)
* Opmerkingen voor revisies worden verkeerd geplaatst in een revisietaak. (10625)
* `<conref>` Opmerking in een para-tag wordt niet weergegeven in de voorvertoningsmodus. (10559)
* Als u de backspace aan het einde van een lijstitem aanpast, wordt de hele lijst verwijderd. (10540)
* Het scherm wordt als leeg weergegeven in Chrome v106 bij het slepen en neerzetten op een element uit de gebruikersinterface (bijvoorbeeld vanuit het deelvenster Voorwaarden). (10524)
* De knop Automatisch inspringen ontbreekt op de werkbalk van het dialoogvenster **Bron** weergeven. (10448)
* Het eerste teken van een lijstitem gaat soms verloren wanneer de lijst in de editor wordt geschreven.( 10447)
* **Ongedaan maken** of **Opnieuw** werkt niet correct bij sommige bestanden. (10373)
* Aangepaste metagegevens blijven niet behouden bij kopiëren en plakken. (10367)
* Er treedt een fout op bij het kopiëren (ctrl+c) en plakken (ctrl+v) van inhoud. (10304)
* In het deelvenster Omtrek wordt geen inhoud weergegeven wanneer van de modus Auteur naar bron wordt geschakeld. (10296)
* Submap wordt niet gecreeerd wanneer het naar een hoofdkaart in Malplaatjes DITA verwijst. (10231)
* De kwesties van de navigatie komen in de Redacteur van het Web na 4.0 verbetering voor. (10159)
* Met de optie Ongedaan maken in de XML-editor gaat de gebruiker naar de bovenkant van de pagina. (10091)
* Node-eigenschappen worden verwijderd nadat een element is gekopieerd en geplakt. (10053)
* SVG-bestanden die aan DITA-onderwerpen worden toegevoegd, worden niet weergegeven in de voorbeeldmodus van de editor. (10010)
* Zoekresultaten voor zoeken en vervangen in de webeditor zijn niet leesbaar in de modus Donker. (9978)
* Er bestaat geen lader tijdens het maken van een kaart op basis van de kaartsjabloon. (9891)
* Conref in het onderwerpmalplaatje werkt niet en gekopieerde knoeiboelidentiteitskaart wordt niet bijgewerkt in het inhoudsexemplaar. (9890)
* Geen optie wordt getoond om de onderwerpen of kaartmalplaatje binnen subfolders van de onderwerp of kaartomslag te doorbladeren. (9889)
* Geen optie om een nieuw malplaatje op subfolders van onderwerpen of kaarten tot stand te brengen. (9888)
* De redacteur van XML werkt niet de beelden op onderwerpen bij. (9500)
* mimeType is hardcoded voor het creëren en bijwerken van activa DITA. (8979)
* Bij het selecteren van Vast afbreekstreepje in het dialoogvenster wordt een normaal afbreekstreepje ingevoegd **Speciaal teken invoegen** . (8919)
* De naam van de maker van de versie in Versiehistorie is &quot;fmdita-servicegebruiker&quot; voor de bestanden die via de interface Elementen zijn geüpload. (8910)
* De optie Bewerken werkt niet voor afbeeldingen wanneer u werkt in de interface Kolomweergave van elementen. (8758)
* DITA-onderwerp wordt niet automatisch bijgewerkt met wijzigingen die zijn aangebracht op **Eigenschappen** pagina. (8745)
* Terwijl het bewegen van elementen binnen het onderwerp in de Redacteur van het Web, toegewezen IDs op elementen wordt overschreven door auto-toegewezen IDs. (7895)

### Beheer

* Het kopiëren van een DITA-kaart-element (van de Asset UI) veroorzaakt onjuiste basislijnen in het gekopieerde element. (11218)
* Er wordt geen waarschuwingsbericht weergegeven bij het uploaden van een bestand dat groter is dan de limiet die is toegestaan in AEM (standaard 2 GB). (10817)
* Web Editor-basislijn | Het gedrag van de kolom Laatste is verschillend in het nieuwe basislijndashboard binnen de Redacteur van het Web. (10808)
* Vertaling | De vertaaltaak wordt niet gestart vanwege ongeldige /libs/fmdita/i18n/ja.json. (10543)
* Vertaling | Er is een fout opgetreden in een bereikvertaalproject dat is gemaakt op het vertaaldashboard (Menselijke vertaling). (10526)
* Vertaling | Nabewerking wordt geblokkeerd voor de gehele taalmap waarvan de middelen aanwezig zijn in een actief vertaalproject. (10332)
* Vertaling| Metagegevens en tags worden niet doorgegeven aan de vertaalde kopieën. (4696)
* Er worden meerdere pop-ups weergegeven voor elk element als de versie wordt gewijzigd en opgeslagen in de basislijneditor. (10399)
* De lekkage van de zitting komt bij com.day.cq.search.impl.builder.QueryBuilderImpl.createResourceResolver (QueryBuilderImpl.java:210) voor. (10279)
* Het videobestand ontbreekt vanaf de basislijn als de bovenliggende map ruimte in de naam bevat. (10031)

### Publiceren

* De regeneratie van het onderwerp werkt niet voor sommige scenario&#39;s. (10635)
* Publiceren via PDF mislukt bij het genereren van de uitvoer voor een dubbele voorinstelling (van een bestaande voorinstelling). (10584)
* De knop Logbestand weergeven werkt niet als het genereren van de PDF mislukt voor een voorinstelling. (10576)
* De luisteraar van de uitgever toont niet de gevraagde gegevens in info- logboeken, en het bevat ook sommige junk logboeken.( 10567)
* Native PDF | PDF genereren mislukt met een Null-aanwijzeruitzondering. (10950)
* Native PDF | conkeyref wordt niet opgelost in de gegenereerde uitvoer. (10564)
* Native PDF | Problemen treden op met de metagegevens van een kaart waarnaar in de uitvoer van de PDF moet worden verwezen.( 10556)
* Native PDF | Problemen treden op bij het roteren van de tabelkop. (10555)
* Native PDF | Problemen doen zich voor bij het verwijderen van onderwerpen met verwerkingsrol=&#39;resource-only&#39;. (10554)
* Native PDF | Lege toetsaanslagen worden weergegeven in PDF-uitvoer. (10553)
* Native PDF | Genest `<indexterm>` niet genest zijn in native PDF-export. (10521)
* Native PDF | Native PDF gebruikt inline stijl in plaats van klassenaam voor de gegenereerde tags. (10498)
* Native PDF | Geneste topicref in aanhangsels worden allemaal omgezet in h1 in de tijdelijke HTML.( 10454)
* Native PDF | Kan de onderwerpen over de voorgrond niet verbergen in de inhoudsopgave. (10355)
* Native PDF | Kenmerk tabelframe niet doorgegeven aan de tijdelijke HTML (als klasse). (10353)
* Native PDF | Tijdelijke HTML-bestanden voegen de klassen colsep en rowsep toe aan <td> en <th> zelfs als hun waarde 0 in bronDITA is. (10352)
* Native PDF | Als u de paginanummers opnieuw instelt in de hoofdstuklayout, wordt de nummering vanaf het einde van het vorige hoofdstuk gestart. (10154)
* Native PDF | De belangrijkste verwijzingen voor keydefs met beeld of externe verbindingen worden niet opgelost. (10063)
* Native PDF | Bijlage wordt weergegeven als een hoofdstuk in gegenereerde PDF. (9829)
* Het tabblad Sjabloon in de XML-editor wordt niet weergegeven bij Mapprofielbeheerders. (10266)
* Het publiceren van de basislijn ontbreekt voor PDF die gebruikend het Publiceren FrameMaker Server 2020 wordt geproduceerd. (10551)
* Er treedt een toepassingsfout op wanneer u op de knop Bewerken klikt nadat u alle voorinstellingen hebt geselecteerd via het selectievakje Voorinstellingen uitvoer in het pop-upvenster Snel genereren. (10388)
* Als op het tabblad Uitvoer in de webeditor meer voorinstellingen beschikbaar zijn, kan in de sectie Voorinstellingen niet verticaal worden geschoven en worden niet alle beschikbare voorinstellingen weergegeven. (9787)
* Kan voorinstellingen niet verwijderen uit de uitvoerworkflow tijdens het publiceren via de Editor. (9100)
* Peer-koppeling wordt weergegeven als normale tekst in plaats van als een koppeling op de gegenereerde pagina. (7774)

## Bekend probleem

Adobe heeft het volgende bekende probleem voor de release van AEM Hulplijnen 4.2 geïdentificeerd:

* Gebruikers kunnen revisiebewerkingen zelfs uitvoeren nadat de revisietaak is voltooid.
