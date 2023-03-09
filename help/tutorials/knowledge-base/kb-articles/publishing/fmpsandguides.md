---
title: FMPS- en AEM-hulplijnen
description: Publiceren met FMPS met behulp van AEM hulplijnen
source-git-commit: 82f010a97d0ed0e3c6351e6411e5955c79e0b01f
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---


# De het Publiceren van FrameMaker Server (FMPS) en Gidsen van de AEM

**AEM de integratie van Gidsen met het Publiceren FrameMaker Server zou uw oplossing kunnen zijn als u geautomatiseerde het publiceren van uitstekende kwaliteit zoekt.\
Met het onderstaande artikel kunt u FMPS met AEM hulplijnen instellen en uitvoeren.**

## Compatibiliteit van FMPS met AEM hulplijnen:

- Compatibiliteit met 4.1 AEM hulplijnen: [Koppeling](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)
- Compatibiliteit met 4.0 AEM-hulplijnen: [Koppeling](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Toekomstige release: [Koppeling](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Installatie:

### Hulplijnen AEM:

Installatie en configuratie verwijzen naar: [Koppeling](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS:

Voor FMPS-installatie kunt u verwijzen naar gegeven [Videokoppeling](https://www.youtube.com/watch?v=2deelyM5VA8&amp;t) of [Documentatie](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&amp;rhtocid=_2)

## Vereiste configuraties:

Uw inhoud DITA kan output gebruikend het Publiceren FrameMaker Server (FMPS) zijn. U kunt uitvoer maken in een van de vele indelingen die door FMPS worden ondersteund. In de Console van het Web, wijzig de volgende eigenschappen van de bundel com.adobe.fmdita.config.ConfigManager aan opstelling AEM Gidsen om FMPS te gebruiken.

Ga naar de URL Access http://\ als u de webconsole wilt openen&lt;server name=&quot;&quot;>:\&lt;port>/system/console/configMgr.

**Eigenschappen van configuratie en beschrijving ervan:** [Koppeling](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Test uitvoeren:

Met FMPS kunt u automatisch publiceren **PDF, responsieve HTML5**, en **Epub** voor uw DITA- en FM-middelen.

Van &quot;produceer PDF gebruikend&quot;menu, kies het Publiceren FrameMaker Server.

De gebruiker kan &quot;settings File(.sts)&quot; en &quot;ditaval. Filteren wordt uitgevoerd met ditaval op basis van de voorwaarden die u opgeeft.

- **bestand instellen**: FrameMaker /FMPS publiceert het plaatsen die al die montages bevat die u FMPS tijdens het publiceren wilt respecteren Bijvoorbeeld: Uitvoer genereren met de aangepaste sjabloon, Tekens en aflooptekens genereren (PDF), PDF genereren met inhoudsopgave, index, enz.
- **FMPS-voorinstelling:** De vooraf gedefinieerde combinatie van een bestand met instellingen en een ditaval-bestand. In plaats van afzonderlijke bestanden voor bewerkingen en instellingen te geven, kan de gebruiker vooraf een FMPS-voorinstelling maken die opnieuw kan worden gebruikt voor publicatiedoeleinden.

**Opmerking:** Als u geen van de instellingen of FMPS-voorinstellingen selecteert, publiceert FMPS met de standaardsysteeminstelling.

Als u een FMPS-voorinstelling hebt geselecteerd en ook instellingen/ditaval-bestand van AEM hebt opgegeven, is er een conflict tussen deze voorinstelling en krijgt de FMPS-voorinstelling voorrang op aangepaste instellingen/ditaval-bestand.

### Publiceren van basislijnen met FMPS:

U kunt uw reeds gemaakte basislijnen publiceren met versie FMPS2020.0.2 of hoger.

**Voorbeeld van FMPS-instellingenbestand (.sts-bestand) om aan de slag te gaan:** [Koppeling](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (decomprimeer dit bestand)

## Veelgestelde vragen en problemen oplossen:

- FMPS-publicatie mislukt met &quot;Timeout Exception&quot;.

Controleer en verhoog de waarde van &quot;FMPS timeout&quot; (Seconden) in /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;

- Kan de FMPS-voorinstelling niet ophalen in het vervolgkeuzemenu.

Zorg ervoor dat er een vooraf gedefinieerde FMPS-voorinstelling op de server is gemaakt en dat de verbindingsinstellingen correct zijn.

- Ik krijg blanco PDF bij het publiceren.

Als u UUID dan gebruikt zorg ervoor u &quot;Op UUUID gebaseerd van het Gebruik van verwijzingen&quot;in FrameMaker hebt gecontroleerd geeft Voorkeur uit en vice versa voor niet-UUID AEM gidsen.

- Mijn instellingen/ditaval worden niet toegepast in de uiteindelijke gepubliceerde uitvoer.

Zorg ervoor dat u niet gelijktijdig zowel een instellings-/bewerkbestand als een FMPS-voorinstelling selecteert. Verifieer manueel output gebruikend FrameMaker.

- De basislijn wordt niet gepubliceerd vanuit FMPS.

Publiceren in de basislijn is compatibel met de versie FMPS2020.0.2 of hoger.\
Zorg ervoor dat uw basislijn correct is gemaakt, om te controleren of u naar Onderwerpmap van het dashboard-onderwerp gaat en &quot;Basislijn gebruiken&quot; selecteert.

- Publiceer Taken van FMPS neemt meer tijd in beslag dan andere Motoren.

Er zal een ideale vaste kopbal van ongeveer zijn. 3-4 min slechts terwijl het publiceren van FMPS dan andere Motoren, als u het meer dan dat denkt is dan controle met uw beheerder FMPS of de Steun van de Adobe van het Contact.

## Overige bronnen:

[Leren en ondersteunen met FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[AEM Leren en ondersteunen](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[FrameMaker en de gemeenschap FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&amp;sort=latest_replies&amp;lang=all&amp;tabid=all)

[Gemeenschap voor AEM](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
