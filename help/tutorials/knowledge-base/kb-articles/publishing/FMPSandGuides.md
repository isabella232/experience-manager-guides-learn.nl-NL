---
source-git-commit: da88662ec770b12a25ba4afd876e6eeac793cfc5
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---


# De het Publiceren van FrameMaker Server (FMPS) en Gidsen van de AEM

**AEM de integratie van Gidsen met het Publiceren FrameMaker Server kon uw oplossing als u geautomatiseerde het publiceren van uitstekende kwaliteit kijkt.\
Met het onderstaande artikel kunt u FMPS instellen en uitvoeren met AEM hulplijnen.**

## Verenigbaarheid van FMPS met AEM hulplijnen:

- Compatibiliteit met de 4.1-richtsnoeren AEM: [Koppeling](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)

- Compatibiliteit met de 4.0-hulplijnen AEM: [Koppeling](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)

- Toekomstige release: [Koppeling](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Installatie:

### Hulplijnen AEM:

Installatie en configuratie verwijzen naar: [Koppeling](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS:

Voor FMPS-installatie kunt u verwijzen naar gegeven [Videokoppeling](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) of [Documentatie](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Vereiste configuraties:

Uw inhoud DITA kan output gebruikend het Publiceren FrameMaker Server (FMPS) zijn. U kunt uitvoer maken in een van de vele indelingen die door FMPS worden ondersteund.
In de Console van het Web, wijzig de volgende eigenschappen van de bundel com.adobe.fmdita.config.ConfigManager aan opstelling AEM Gidsen om FMPS te gebruiken.

Ga naar de URL Access http://\ als u de webconsole wilt openen&lt;server name=&quot;&quot;>:\&lt;port>/system/console/configMgr.

**Eigenschappen van configuratie en beschrijving ervan:** [Koppeling](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Test uitvoeren:

Met FMPS kunt u automatisch publiceren **PDF, responsieve HTML5**, en **Epub** voor uw DITA- en FM-middelen.

Van &quot;produceer PDF gebruikend&quot;menu, kies het Publiceren FrameMaker Server.

De gebruiker kan &quot;Settings File(.sts)&quot; en &quot;ditaval. Filteren vindt plaats met gebruik van Ditaval op basis van de omstandigheden die u opgeeft.

- **Bestand instellen**: FrameMaker /FMPS publiceert het plaatsen die al die montages bevat die u FMPS tijdens het publiceren wilt respecteren Bijvoorbeeld: ,Uitvoer genereren met aangepaste sjabloon,Tekens en aflooptekens genereren (PDF), PDF genereren met inhoudsopgave, index, enzovoort.
- **FMPS aanwezig:** Vooraf gedefinieerde combinatie van Ditaval- en Settings-bestand. In plaats van een afzonderlijk Ditaval- en instellingenbestand te geven, kan de gebruiker vooraf een FMPS-voorinstelling maken die opnieuw kan worden gebruikt voor publicatie.

**Opmerking:**  Als u geen instellingen of FMPS-voorinstelling selecteert, publiceert FMPS met de standaardsysteeminstelling.

Als u een FMPS-voorinstelling hebt geselecteerd en ook Settings/Ditaval-bestand hebt opgegeven van AEM, levert dit een conflict op en krijgt FMPS-voorinstelling voorrang op het aangepaste Settings/Ditaval-bestand.

### Publiceren van basislijnen met FMPS:

U kunt uw reeds gemaakte basislijnen publiceren met versie FMPS2020.0.2 of hoger.

**Voorbeeld van een FMPS-instellingenbestand (.sts-bestand) om aan de slag te gaan:** [Koppeling](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (decomprimeer dit bestand)

## Veelgestelde vragen en problemen oplossen:

- ### FMPS-publicatie mislukt met &quot;Timeout Exception&quot;

De waarde van &quot;FMPS timeout&quot; (Seconden) controleren en verhogen in /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;

- ### Kan FMPS-voorinstelling niet ophalen in vervolgkeuzelijst

Zorg ervoor dat u een vooraf gedefinieerde FMPS-voorinstelling hebt die op de server is gemaakt en dat de verbindingsinstellingen correct zijn.

- ### Ik krijg Blanco PDF bij het publiceren.

Als u UUID dan gebruikt zorg ervoor u &quot;Gebruik UUID gebaseerd het van verwijzingen voorzien&quot;in FrameMaker EditPreferences en vice versa voor niet UUID AEM gidsen hebt gecontroleerd

- ### Mijn instellingen/Ditaval worden niet toegepast in de uiteindelijke gepubliceerde uitvoer

Zorg ervoor u niet zowel het Plaatsen/Ditaval dossier als Vooraf ingestelde FMPS parallelle.Verifieer output manueel gebruikend FrameMaker selecteert

- ### Basislijn wordt niet gepubliceerd vanuit FMPS

Publiceren in de basislijn is compatibel met de versie FMPS2020.0.2 of hoger.\
Zorg ervoor dat uw basislijn correct is gemaakt. Om te controleren gaat u naar Kaart voor Dashboard Topic Download Map en selecteert u &quot;Basislijn gebruiken &quot;.

- ### Het publiceren van Taak van FMPS vergt meer tijd dan andere Motoren.

Er is een ideale vaste header van ongeveer. 3-4 min slechts terwijl het publiceren van FMPS dan andere Motoren, als u het meer dan dat denkt is dan controle met uw beheerder FMPS of de Steun van de Adobe van het Contact.

## Overige bronnen:

### [Leren en ondersteunen met FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

### [AEM Leren en ondersteunen](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

### [FrameMaker en de gemeenschap FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

### [AEM](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
