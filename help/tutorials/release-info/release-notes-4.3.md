---
title: Opmerkingen bij de release | Upgradeinstructies en opgeloste problemen in de release van Adobe Experience Manager Guides 4.3.0
description: Meer informatie over de opgeloste problemen en hoe u een upgrade uitvoert naar 4.3.0-versies van Adobe Experience Manager-hulplijnen
source-git-commit: 756ba69360e1796e36f6cc1ef410443ef8cb4acb
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 4%

---

# 4.3.0 Release van Adobe Experience Manager Guides (juli 2023)

In deze releasenotitie worden de instructies voor de upgrade, de compatibiliteitsmatrix en de problemen behandeld die zijn opgelost in versie 4.3.0 van de Adobe Experience Manager-hulplijnen (later genoemd als *Hulplijnen AEM*).

Zie voor meer informatie over de nieuwe functies en verbeteringen [Nieuwe functies in de 4.3.0-release van Adobe Experience Manager-hulplijnen](./whats-new-4.3-release.md).

## Upgrade naar versie 4.3.0 van AEM hulplijnen


U kunt eenvoudig uw huidige versie van AEM hulplijnen upgraden naar versie 4.3.0. Voordat u verdergaat met de upgrade naar versie 4.3.0 van AEM hulplijnen, moet u rekening houden met de volgende punten: u kunt de huidige versie van AEM hulplijnen upgraden naar versie 4.3.0

- Als u versie 4.2 of 4.2.x gebruikt, kunt u rechtstreeks upgraden naar versie 4.3.0.
- Als u versie 4.1 of 4.1.x gebruikt, moet u een upgrade naar versie 4.2 of 4.2.x uitvoeren voordat u een upgrade naar versie 4.3.0 uitvoert.
- Als u versie 4.0 gebruikt, moet u een upgrade naar versie 4.2 uitvoeren voordat u een upgrade naar versie 4.3.0 uitvoert.
- Als u versie 3.8.5 gebruikt, moet u een upgrade naar versie 4.0 uitvoeren voordat u een upgrade naar versie 4.2 uitvoert.
- Als u een versie hebt die ouder is dan 3.8.5, raadpleegt u de sectie Upgrade AEM hulplijnen in de productspecifieke installatiehandleiding.



>[!NOTE]
>
>U moet AEM de dienstpak installeren alvorens AEM versie van Gidsen te bevorderen.

Zie voor meer informatie [Upgradeinstructies](../install-guide/upgrade-xml-documentation.md).

## Compatibiliteitsmatrix

In deze sectie wordt een overzicht gegeven van de compatibiliteitsmatrix voor de softwaretoepassingen die worden ondersteund door AEM Guide 4.3.0.

### Adobe Experience Manager

**4.3.0 Niet-UUID**
Versie 6.5 Service Pack 17, 16, 15 of 14

**4.3.0 UUID**
Versie 6.5 Service Pack 17, 16, 15 of 14

Zie voor meer informatie de *Technische voorschriften* in de handleiding Adobe Experience Manager-hulplijnen installeren en configureren.

### FrameMaker en FrameMaker Publishing Server

| Geen | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.0 (niet-UUID) | 2022 of hoger | 2020.2 of hoger* | 2022 of hoger | 2020.3 of hoger |
| 4.3.0 (UUID) | 2022 of hoger | 2020.2 of hoger* | 2022 of hoger | 2020.4 of hoger |
| | | | |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

### Zuurstofaansluiting

| Geen | Oxygeenaansluiting, Windows | Oxygeenconnector Mac | Bewerken in Oxygen Windows | Bewerken in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.0 (niet-UUID) | 2.3-regelmatig-5 | 2.3-regelmatig-5 | 1.6 | 1.6 |
| 4.3.0 (UUID) | 3.0-uuid-4 | 3.0-uuid-3 | 2.3 | 2.3 |
|  |  |   |

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

### Authoring

- Het onderwerpbestand wordt niet ontgrendeld in de webeditor, hoewel de optie Bestand ontgrendelen en de optie Niet opslaan zijn geselecteerd. (12558)
- Kan een bestand niet uitchecken in de webeditor, ondanks dat u de optie NO hebt gekozen om de wijzigingen vóór het inchecken te verwijderen. (12557)
- De knopinfo voor de pictogrammen voor vergrendelen en ontgrendelen van bestanden op de hoofdwerkbalk in de webeditor is niet consistent met de pictogrammen die worden weergegeven in de weergave Opslagplaats.(12555)
- De optie Uitchecken annuleren en ontgrendelen wordt weergegeven voor een bestand in de webeditor dat nog niet is uitgecheckt in de Kaartweergave. (12556)
- Kan de PDF-elementen niet selecteren in de bestaande &quot;topicref&quot;-koppelingen. (12477).
- Bij het samenvoegen en splitsen in de tabellen genereert AEM hulplijnen 4.2 extra tabelcellen. (11793)
- In de weergave Opslagplaats kunnen de onderwerpen of afbeeldingen na gebruik van de functie Zoeken/Filteren niet meer worden gesleept. (12396)
- De zoekresultaten worden uitgeschakeld in het deelvenster Zoeken en vervangen nadat een doorzocht bestand is geopend. (12142)
- De cijfertoets &#39;8&#39; op het zijtoetsenbord werkt niet in de editor voor AEM hulplijnen. (12106)
- De inline-/weergavekenmerken worden niet weergegeven in de layoutweergave van de webeditor. (12498)
- Bestanden uploaden in de insteekmodule Oxygen voor AEM hulplijnen werkt niet in cloudservices als u dat hebt! in de bestandsnaam. (12207)
- De configuratie van de globale profiel-UI komt niet overeen met het mapprofiel. (11970)
- Inhoudsverwijzingen worden verbroken wanneer DITA-bestanden worden gekopieerd en geplakt. (11959)
- Kan inhoudsfragment niet bewerken in de kolomweergave met AEM hulplijnen geïnstalleerd. (7342)
- Inhoud gaat verloren wanneer een onverpakt xref zich onder subelementtags bevindt. (12532)
- De goedkeuringswerkstroom werkt niet wanneer de documentstatus wordt gewijzigd in &quot;eindstatus&quot; in de bestandseigenschappen van het rechterdeelvenster. (11026)
- Elementinterface | In de lijstweergave kunnen de overbelaste beschikbare kolommen niet worden samengevoegd. (11528)
- Keyref wordt niet opgelost in de kaartweergave. (11490)
- Het bovenste menu wordt niet weergegeven wanneer u door de XML-editor navigeert. (10868)
- `conref` in tag ph | Het weergegeven dialoogvenster Bladeren is onjuist. (9481)
- Lokale koppelingen naar andere elementen worden niet opgelost in de webeditor. (8790)
- De functie Matches() werkt niet in de functie schema. (11224)
- In de Insteekmodule van Zuurstof voor AEM Gidsen, neemt de optie om een kaart DITA in de Redacteur van de Kaart van DITA van het Web te openen aan oude UI. (12633)


### Beheer

- Het veld &quot;title&quot; in de metagegevenseigenschappen van de DITA-kaart wordt overschreven door `<title>` -element voor de kaart. (10702)
- Wanneer u probeert de versie van onderwerpen in de basislijn te openen of bij te werken, wordt de lader &quot;Fetching information from the server&quot; voor onbepaalde tijd uitgevoerd.(12478)


### Controleren

- Nieuwe revisie-interface | De voorwaarden benadrukken, en tonen verberg werk anders dan hoe zij in de Redacteur van het Web werken. (11628)

### Publiceren

- Publiceren mislukt bij het wijzigen van de naam van een Native PDF-voorinstelling. (12564)
- Als u een Native PDF-sjabloon dupliceert, wordt de standaardsjabloonlocatie gebruikt in plaats van de beschikbare aangepaste sjabloonlocatie. (12563)
- Native PDF | De metagegevens voor de taal kunnen niet in de gegenereerde PDF worden ingesteld om te voldoen aan WCAG 2.0. (12407)
- Publiceren naar AEM site mislukt bij het lezen van tijdelijke bestanden uit pod die mogelijk zijn vernieuwd of opnieuw zijn gestart. (12113)
- Native PDF | Aangepaste kenmerken worden niet doorgegeven aan tijdelijke HTML- of PDF-engine. (DXML-12005)
- Native PDF | Java OutOfMemoryError treedt op bij het publiceren van grote inhoud. (11789)
- Native PDF | Xref drukt de inhoud van href onderwerptitel in plaats van het etiket Xref. (11322)
- Native PDF | De sjablooninstellingen voor PDF kunnen niet worden opgeslagen. (10751)
- Native PDF | De tekst breidt zich voorbij de kolombreedte uit bij het opnemen van meerdere voorkeuren. (10876)
- Native PDF | `<note>``</note>` element genereert geen extra bereiktitel van het type. (10549)
- JSON-uitvoer | De `fmUuid` eigenschap op het JCr:content-knooppunt van JSON verschilt van de &quot;id&quot; in de JSON. (11564)
- JSON-uitvoer | Als de kaart en het onderwerp met dezelfde bestandsnaam aanwezig zijn, wordt JSON voor de kaart verwijderd. (11524)

## Bekend probleem

Adobe heeft het volgende bekende probleem voor AEM versie 4.3.0 van de Gidsen geïdentificeerd:

- De algemene pagina-indeling die in de sjabloon Standaard is gedefinieerd, wordt niet als standaardsjabloon toegepast.

  Oplossing: voeg de algemene paginalay-out toe als voorblad en achteromslag en dan begint deze voor elke pagina te komen.
- Het probleem doet zich voor in Sitezoekopdrachten terwijl u op de pagina AEM site-uitvoer op AEM Service Pack 16 of 17 zoekt.

  Oplossing:

   1. Bestand openen met pad: `/libs/foundation/components/search/search.jsp` in `crx/de`
   1. Regelnummer 234 vervangen door de volgende code:

      ```
      <a href="<c:url value="${hit.URL}" context="/"/>" onclick="trackSelectedResult(this, ${status.index + 1})"><%= xssAPI.filterHTML(((Search.Hit) pageContext.getAttribute("hit")).getTitle()) %></a>
      
      *(Add the missing closing anchor tag at the end).
      ```

   1. Sla het bestand op.