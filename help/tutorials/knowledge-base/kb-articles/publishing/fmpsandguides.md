---
title: Publiceren met gebruik van FrameMaker Publishing Server (FMPS) in AEM hulplijnen
description: Publiceren met FMPS met behulp van AEM hulplijnen
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Publiceren met gebruik van FrameMaker Publishing Server (FMPS) in AEM hulplijnen

AEM integratie van hulplijnen met FrameMaker Publishing Server kan uw oplossing zijn als u op zoek bent naar geautomatiseerde publicatie van hoge kwaliteit.\
Artikel helpt u bij het instellen en uitvoeren van FMPS met AEM.

## Compatibiliteit van FMPS met AEM hulplijnen

- Compatibiliteit met 4.1 AEM hulplijnen: [4.1-compatibiliteitsmatrix](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)
- Compatibiliteit met 4.0 AEM-hulplijnen: [4.0-compatibiliteitsmatrix](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Laatste release: [Nieuwste releasegegevens](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Installatie

Raadpleeg de volgende secties voor de installatie en configuratie van AEM hulplijnen en FMPS

### Hulplijnen AEM

Installatie en configuratie verwijzen naar: [4.1 installatie en configuraties](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Voor FMPS-installatie kunt u verwijzen naar gegeven [YouTube-koppeling](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) of [FMPS-installatie en -configuratie](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Vereiste configuraties

U kunt FrameMaker Publishing Server (FMPS) gebruiken om uw DITA-inhoud te genereren. FMPS ondersteunt een groot aantal uitvoerindelingen. Wijzig de volgende eigenschappen van de bundel &quot;com.adobe.fmdita.config.ConfigManager&quot;in de Console van het Web om AEM Gidsen te vormen om FMPS te gebruiken.

Ga naar de URL Access http://\ als u de webconsole wilt openen&lt;server name=&quot;&quot;>:\&lt;port>/system/console/configMgr.

**Eigenschappen van configuratie en beschrijving ervan** [4.1 installatie en configuratie](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Test uitvoeren:

Met FMPS kunt u automatisch publiceren **PDF, responsieve HTML5**, en **Epub** voor uw DITA- en FM-middelen.

Kies FrameMaker Publishing Server in het menu &quot;PDF genereren met&quot;.

De gebruiker kan &quot;settings File(.sts)&quot; en &quot;ditaval&quot; opgeven. Filteren wordt uitgevoerd met ditaval op basis van de voorwaarden die u opgeeft.

- **Bestand instellen**: Een FrameMaker/FMPS-bestand met publicatie-instellingen dat alle instellingen bevat die door FMPS moeten worden gerespecteerd bij publicatie. U kunt bijvoorbeeld uitvoer maken met een aangepaste sjabloon, markeringen en aflooptekens maken (PDF) en PDF maken met inhoudsopgave.
- **FMPS-voorinstelling:** Het is een vooraf gedefinieerde combinatie van een bestand met instellingen en een ditaval-bestand. In plaats van afzonderlijke bestanden voor bewerkingen en instellingen te geven, kan de gebruiker vooraf een FMPS-voorinstelling maken die opnieuw kan worden gebruikt voor publicatiedoeleinden.

**Opmerking:** De standaardsysteeminstelling wordt door FMPS gebruikt om te publiceren als u geen van de instellingen of de FMPS-voorinstelling kiest.

Dit is een conflict als u de FMPS-voorinstelling hebt gekozen en ook aangepaste instellingen of een tijdelijk bestand van AEM hebt opgegeven. In dit geval heeft de FMPS-voorinstelling voorrang op de aangepaste instellingen of het ditaval-bestand.

### Publiceren van basislijnen met FMPS:

U kunt uw reeds gemaakte basislijnen publiceren met versie FMPS2020.0.2 of hoger.

**Voorbeeld van FMPS-instellingenbestand (.sts-bestand) om aan de slag te gaan:** [Voorbeeld van FMPS-instellingenbestand](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (decomprimeer dit bestand)

## Veelgestelde vragen en problemen oplossen:

- ### FMPS-publicatie mislukt met &quot;Timeout Exception&quot;

>Controleer en verhoog de waarde van &quot;FMPS timeout&quot; (Seconden) in /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;

- ### Kan FMPS-voorinstelling niet ophalen in vervolgkeuzelijst

>Zorg ervoor dat er een vooraf gedefinieerde FMPS-voorinstelling op de server is gemaakt en dat de verbindingsinstellingen correct zijn.

- ### Ik krijg Lege PDF wanneer ik publiceer

>Als u UUID gebruikt, moet u de optie &quot;UUID-gebaseerde verwijzing gebruiken&quot; inschakelen in de voorkeuren voor FrameMakers bewerken en omgekeerd voor niet-UUID-AEM.

- ### Mijn instellingen/bewerkingen worden niet toegepast in de uiteindelijke gepubliceerde uitvoer

>Controleer of u niet tegelijkertijd de FMPS-voorinstelling en het instellings-/diaval-bestand kiest. Gebruik FrameMaker om de uitvoer handmatig te controleren.

- ### De basislijn wordt niet gepubliceerd vanuit FMPS

>FMPS2020.0.2 of latere versies zijn compatibel met publiceren op basislijn.
>Zorg ervoor dat uw basislijn correct werd gecreeerd; om te controleren, ga naar het Dashboard van de Kaart— Onderwerpen— Kaart van de Download en kies &quot;Basislijn van het Gebruik&quot;.
- ### Het publiceren van taken van FMPS kost meer tijd dan andere engines

>Wanneer u publiceert vanuit FMPS, is de ideale vaste headertijd ongeveer 3-4 minuten. Neem contact op met uw FMPS-beheerder of neem contact op met de ondersteuning voor Adoben als u denkt dat deze langer duurt.

## Overige bronnen:

[Leren en ondersteunen met FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[Leren en ondersteuning AEM hulplijnen](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[FrameMaker- en FMPS-community](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

[Gemeenschap voor AEM](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
