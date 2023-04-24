---
title: Opmerkingen bij de release | Adobe Experience Manager Guides as a Cloud Service, release april 2022
description: Release van Adobe Experience Manager Guides as a Cloud Service in april
exl-id: c735ba24-a803-454b-8723-57dacf90061b
source-git-commit: 67ba514616a0bf4449aeda035161d1caae0c3f50
workflow-type: tm+mt
source-wordcount: '799'
ht-degree: 2%

---

# Release van Adobe Experience Manager Guides as a Cloud Service in april

## Upgrade naar de release van april

Upgrade uw huidige [!DNL Adobe Experience Manager Guides] as a Cloud Service (later aangeduid als *[!DNL AEM Guides]as a Cloud Service*) door de volgende stappen uit te voeren:
1. Controle uit de Cloud Services Gespitcode en schakelaar aan de tak die in de Cloud Services wordt gevormd die aan het milieu beantwoordt u wilt bevorderen.
1. Bijwerken `<dox.version>` eigenschap in `/dox/dox.installer/pom.xml` bestand van de Git-code van de Cloud Services naar 2022.4.133.
1. Leg de wijzigingen vast en voer de Cloud Services-pijplijn uit om naar de release van april van [!DNL AEM Guides] as a Cloud Service.

## Compatibiliteitsmatrix

In deze sectie wordt de compatibiliteitsmatrix weergegeven voor de softwaretoepassingen die worden ondersteund door [!DNL AEM Guides] as a Cloud Service release april 2022.

### FrameMaker en het Publiceren FrameMaker Server

| FMPS | FrameMaker |
| --- | --- |
| Niet compatibel | 2020-update 4 en hoger |
|  |  |


### Zuurstofaansluiting

| Versie van de cloud AEM hulplijnen | Oxygeenaansluiting, Windows | Oxygeenconnector Mac |
| --- | --- | --- |
| 2022.4.0 | 2.5.6 | 2.5.6 |
|  |  |  |

*Basislijn en voorwaarden die in AEM zijn gemaakt, worden vanaf 2020.2 ondersteund in FMPS-releases.

## Nieuwe en verbeterde functies

Er zijn veel verbeteringen en nieuwe functies toegevoegd aan de webeditor:

### Verbeterde hoofdresolutie

Een DITA inhoudsbelangrijkste verwijzing neemt een deel van inhoud van één onderwerp in een andere op. Er wordt een toets gebruikt om de inhoud te zoeken. De belangrijkste verwijzingen verbonden aan een onderwerp DITA moeten worden opgelost. De geselecteerde hoofdmap heeft de hoogste prioriteit om toetsverwijzingen op te lossen.

![dialoogvenster Gebruikersvoorkeuren](assets/user-preferences.png)

Nu worden de belangrijkste verwijzingen opgelost op basis van de wortelkaart die in de volgende orde van prioriteit wordt geplaatst:

1. Gebruikersvoorkeuren
1. Deelvenster Kaartweergave
1. Mapprofiel

Zie voor meer informatie *Belangrijke verwijzingen oplossen* in de handleiding.

### Een aangepast deelvenster toevoegen in het linkerdeelvenster

Nu kunt u een aangepast deelvenster toevoegen in het linkerdeelvenster van de webeditor. U kunt een aangepast deelvenster gebruiken voor verschillende doeleinden, zoals het bieden van hulp of het testen voor een project. Als er een aangepast deelvenster is geconfigureerd, wordt dit ook weergegeven in de lijst met deelvensters in het dialoogvenster **Editor-instellingen**. U kunt schakelen tussen het weergeven of verbergen van het aangepaste deelvenster.

### Mogelijkheid om de documentstatus van onderwerpen in een DITA-kaart te wijzigen

Nu kunt u de documentstaat van geselecteerde onderwerpen binnen een kaart gemakkelijk veranderen DITA. U kunt de eigenschappen van geselecteerde onderwerpen in een kaart DITA van DITA ook openen en uitgeven **Meer opties** onder aan het deelvenster Kaartweergave.

![geselecteerde onderwerpeigenschappen](assets/map-view-properties.png)

### Versiegegevens die worden weergegeven in de modus Voorbeeld

De Redacteur van het Web helpt u in het beheren van uw versies. Nu kunt u de versie van het actieve onderwerp of kaart DITA in de hoogste juiste hoek van het het dossierlusje van het onderwerp op de wijze van de Voorproef van een onderwerp ook zien.

![voorvertoningsversie](assets/preview-version.png)

## Opgeloste problemen

De fouten die in verschillende gebieden zijn gecorrigeerd, worden hieronder weergegeven:

* Nieuwe labels worden niet automatisch weergegeven in het vervolgkeuzemenu Label toevoegen/verwijderen. Vernieuwen van basislijn is daarentegen vereist. (9249)
* Kan de titel van de basislijn niet bewerken als een basislijn is gemaakt op basis van labelcriteria. (9171)
* Publiceren van een taak met een basislijn blijft vastzitten in de status &quot;wachten&quot; als de basislijnstatus verandert in &quot;mislukt&quot;. (9194)
* Als u labels op directe verwijzingen verwijdert, worden de labels ook van indirecte verwijzingen verwijderd. (9257)
* Zoeken terwijl u typt, leidt tot ongewenste zoekverzoeken in de weergave Opslag. (9307)
* Problemen treden op wanneer een trefwoord wordt gebruikt in de titel voor tab. (9318)
* Basislijn mislukt bij het toevoegen van een label met spaties. (9362)
* AEM site-uitvoer geeft het glossusage-element niet correct weer. (8936)
* Console-fout treedt op bij het openen van het dialoogvenster **Uitvoer** in de webeditor. (8715)
* Foutbericht dat wordt weergegeven bij het publiceren van een handmatig recordtype via Salesforce is niet intuïtief. (8952)
* De instelling Valideren met voorwaardenkenmerken wordt niet onmiddellijk geopend. De gebruiker moet het bestand opnieuw openen om de validaties te kunnen zien. (9300)
* Metagegevens kunnen niet worden verwijderd als een DITA-kaart met metagegevens is gepubliceerd.  (9178)
* Het deelvenster Vertaling is zelfs zichtbaar bij het openen van de DITA-kaart in de Kaarteditor. (9053)
* Aangepaste DTD die door de gebruiker is gedefinieerd, heeft geen voorrang op standaard-DITA DTD die is ingesloten in DITA-OT. (9104)
* In de functie Native PDF mislukt het uploaden van de sjablonen voor niet-DITA- en niet-afbeeldingsbestanden. (9070)
* Het mechanisme van de vergunning voert twee vragen in plaats van één uit, in sommige gespecialiseerde scenario&#39;s. (9221)
* Het publiceren van de AEM-site mislukt bij het gebruik van aangepaste DTD. (9243)
* Met de voetnoot &#39;Bij gebruik naar referentie&#39; wordt niet naar de voetnootsectie in AEM site-uitvoer geschoven. (9234)

## Bekende problemen

Adobe heeft het volgende bekende probleem geïdentificeerd in de [!DNL AEM Guides] as a Cloud Service release april.

* De Redacteur van het Web meldt geen fout wanneer twee of meer basislijnen met de zelfde naam worden gecreeerd maar ruimte of gevalverschillen hebben. Bijvoorbeeld &quot;adobe&quot; en &quot;Adobe &quot; of &quot;Adobe&quot;.
* De zuurstofaansluiting loopt af en toe vast tijdens het frequent aanmelden of afmelden of schakelen tussen verschillende verificatietypen.
