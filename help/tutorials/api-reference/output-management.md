---
title: REST API's voor uitvoerbeheer
description: Meer informatie over REST API's voor uitvoerbeheer
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1175'
ht-degree: 0%

---

# REST API&#39;s voor uitvoerbeheer {#id175UB30E05Z}

De volgende REST API&#39;s zijn beschikbaar voor het beheer van uitvoer in AEM hulplijnen.

## Alle uitvoervoorinstellingen voor een DITA-kaart ophalen {#get-output-presets-dita-map}

Een methode van de POST die alle die outputvoorinstellingen terugwint voor een kaart DITA worden gevormd.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parameters**:\
|Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`:operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is `getalloutputs`.<br> **Opmerking:** De waarde is niet hoofdlettergevoelig.| |`sourcePath`|Tekenreeks|Ja|Absoluut pad van het DITA-kaartbestand.|

**Responswaarden**: Retourneert een array met JSON Output Preset-objecten, die elk object met de volgende elementen bevatten:

| Element | Beschrijving |
|-------|-----------|
| `outputName` | Naam van de uitvoervoorinstelling. Uitvoernamen zijn uniek in het bereik van de DITA-kaart waarin ze zijn gedefinieerd. |
| `outputType` | Type uitvoer dat is gegenereerd met deze voorinstelling, bijvoorbeeld AEM Site, PDF, EPUB of andere. De beschikbare opties zijn:<br>- AEMSITE <br>- PDF <br>- HTML5 <br>- EPUB <br>- AANGEPAST |
| `outputTitle` | Een beschrijvende naam voor de instellingen van de uitvoervoorinstelling. Hiermee definieert u de waarde voor de eigenschap Naam instellen voor de uitvoervoorinstelling. |
| `ditaValPathList` | Array met DITAVAL-bestandspaden die moet worden gebruikt om de gewenste uitvoer te genereren. |
| `targetPath` | Pad waar de uitvoer wordt gepubliceerd of opgeslagen. |
| `siteName` | *\(Voor AEM site-uitvoer\)* Naam van de AEM Site. |
| `templatePath` | *\(Voor AEM site-uitvoer\)* Pad van het sjabloonknooppunt dat moet worden gebruikt om de gewenste uitvoer te genereren. |
| `searchScope` | Geef het bereik voor de zoekopdracht op. De waarde voor deze parameter moet worden ingesteld op `local`. |
| `generateTOC` | *\(Voor AEM site-uitvoer\)* Geef op of een inhoudsopgave moet worden gegenereerd \(true\) of niet \(false\). |
| `generateBreadcrumbs` | *\(Voor AEM site-uitvoer\)* Geef op of de broodkruimels \(true\) moeten worden gegenereerd of niet \(false\). |
| `overwriteStrategy` | *\(Voor AEM site-uitvoer\)* Geef op of bestanden op de bestemming \(true\) worden overschreven of niet \(false\). |
| `pdfGenerator` | Geef de PDF-genereringsengine op die u wilt gebruiken. De mogelijke waarden zijn:<br>- DITAOT <br>- FMPS |

>[!NOTE]
>
> `DitaValPath` element wordt niet meer ondersteund.

## Uitvoervoorinstelling maken

Een methode van de POST die tot een nieuwe output vooraf instelt voor een kaart DITA.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`:operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is ``createoutput``.<br> **Opmerking:** De waarde is niet hoofdlettergevoelig.| |`sourcePath`|Tekenreeks|Ja|Absoluut pad van het DITA-kaartbestand.| |`outputTitle`|Tekenreeks|Ja|Een beschrijvende naam voor de instellingen van de uitvoervoorinstelling. Hiermee definieert u de waarde voor de eigenschap Naam instellen voor de uitvoervoorinstelling.<br> **Opmerking:** Wanneer een nieuwe uitvoervoorinstelling wordt gemaakt, stuurt het back-end systeem een unieke naam voor de uitvoervoorinstelling vanuit de opgegeven titel.| |`outputType`|Tekenreeks|Ja|Type uitvoer dat is gegenereerd met behulp van deze voorinstelling, bijvoorbeeld AEM Site, PDF, EPUB of andere. De beschikbare opties zijn:<br>- AEMSITE <br>- PDF <br>- HTML5 <br>- EPUB <br>- AANGEPAST|

**Responswaarden**: |Element|Beschrijving| |—|—| |`outputName`|Een unieke naam voor de nieuwe uitvoervoorinstelling. Deze naam wordt afgeleid van de waarde van `outputTitle` parameter.|

## Uitvoervoorinstelling opslaan

Een methode van de POST die veranderingen bewaart die in een outputvooraf ingesteld worden aangebracht.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`:operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is ``saveoutput``.<br> **Opmerking:** De waarde is niet hoofdlettergevoelig.| |`sourcePath`|Tekenreeks|Ja|Absoluut pad van het DITA-kaartbestand.| |`outputObj`|String|Ja|Een JSON-object dat eigenschappen bevat van de uitvoervoorinstelling die wordt bijgewerkt. De `outputObj.outputName` Deze eigenschap bevat de naam van de uitvoervoorinstelling die moet worden bijgewerkt. Voor de indeling van het JSON-object raadpleegt u de **Responswaarden** tabel in [Alle uitvoervoorinstellingen voor een DITA-kaart ophalen](#get-output-presets-dita-map).|

**Responswaarden**: Retourneert een HTTP 200 \(Successful\) reactie.

## Een specifieke uitvoervoorinstelling ophalen

Een POST-methode waarmee een bestaande uitvoervoorinstelling wordt opgehaald.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`:operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is `getoutput`. <br>**Opmerking:** De waarde is niet hoofdlettergevoelig.| |`sourcePath`|Tekenreeks|Ja|Absoluut pad van het DITA-kaartbestand.| |`outputName`|Tekenreeks|Ja|Naam van de uitvoervoorinstelling waarvoor de details moeten worden opgehaald.|

**Responswaarden**: |Element|Beschrijving| |—|—| |`outputName`|Naam van de uitvoervoorinstelling. Uitvoernamen zijn uniek in het bereik van de DITA-kaart waarin ze zijn gedefinieerd.| |`outputType`|Type uitvoer dat met deze voorinstelling is gegenereerd, bijvoorbeeld AEM Site, PDF, EPUB of andere. De beschikbare opties zijn:<br>- AEMSITE <br>- PDF <br>- HTML5 <br>- EPUB <br>- AANGEPAST <br>| |`outputTitle`|Een beschrijvende naam voor de instellingen van de uitvoervoorinstelling. Hiermee definieert u de waarde voor de eigenschap Naam instellen voor de uitvoervoorinstelling.| |`ditaValPathList`|Array van DITAVAL-bestandspaden die moet worden gebruikt om de gewenste uitvoer te genereren.| |`targetPath`|Pad waar de uitvoer wordt gepubliceerd of opgeslagen.| |`siteName`|\(Voor AEM Site-uitvoer\) Naam van de AEM Site.| |`siteTitle`|\(Voor AEM Site-uitvoer\) Titel van de AEM Site.| |`templatePath`|\(Voor AEM Site-uitvoer\) Het pad van het sjabloonknooppunt dat moet worden gebruikt om de gewenste uitvoer te genereren.| |`searchScope`|Specificeer de reikwijdte van de zoekopdracht. De waarde voor deze parameter moet worden ingesteld op `local`.| |`generateTOC`|\(Voor AEM Site-uitvoer\) Geef op of een inhoudsopgave moet worden gegenereerd \(true\) of niet \(false\).| |`generateBreadcrumbs`|\(Voor AEM Site-uitvoer\) Geef op of de broodkruimels \(true\) worden gegenereerd of niet \(false\).| |`overwriteFiles`|\(Voor AEM Site-uitvoer\) Geef op of bestanden op de bestemming \(true\) worden overschreven of niet \(false\).| |`pdfGenerator`|Geef de te gebruiken motor voor het genereren van PDF op. De mogelijke waarden zijn:<br>- DITAOT <br>- FMPS|

>[!NOTE]
>
> `DitaValPath` element wordt niet meer ondersteund.

## Uitvoer genereren

Een methode van de GET die output gebruikend één of meerdere output vooraf instelt produceert.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is `GENERATEOUTPUT`.<br> **Opmerking:** De waarde is hoofdlettergevoelig.| |`source`|Tekenreeks|Ja|Absoluut pad van het DITA-kaartbestand.| |`outputName`|Tekenreeks|Ja|Naam van de uitvoervoorinstelling\(en\) die moet worden gebruikt om uitvoer te genereren. U kunt meerdere uitvoervoorinstellingen opgeven met behulp van het scheidingsteken \(&quot;\|&quot;\) van de pipe, bijvoorbeeld `aemsite|pdfoutput`.|

**Responswaarden**: Retourneert een HTTP 200 \(Successful\) reactie.

## Incrementele uitvoer genereren

Een methode van GET die stijgende output voor een AEMPlaats gebruikend één of meerdere output vooraf instelt produceert.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is `INCREMENTALPUBLISH`. <br>**Opmerking:** De waarde is hoofdlettergevoelig.| |`contentPath`|JSON|Ja|Absoluut pad van het DITA-toewijzingsbestand en onderwerpbestanden, samen met de naam van uitvoervoorinstellingen. Gebruik het volgende voorbeeld als bouwsteen:|

```XML
{
   {   
   "ditamap": 
      "/content/dam/sample/sample.ditamap",   
   "topics": [     
      "/content/dam/sample/topic1.xml",     
      "/content/dam/sample/topic2.xml"   
         ],   
   "fullMaps": [     
      "/content/dam/sample/submap.ditamap"   
      ],   
   "maps": [     
      "/content/dam/sample/keyspace.ditamap"   
      ],   
   "outputs": [     
      "aemsite"   
      ] 
   }
}
```

- De `ditamap` attribuut neemt de absolute weg van de kaart DITA die wordt gebruikt om de output te produceren.
- De `topics` attribuut neemt een serie van onderwerpen die worden bijgewerkt en moeten opnieuw worden gepubliceerd.
- De `fullMaps` kenmerk bevat pad van de kaartbestanden \(zoals afgekapte submaps\) die samen met hun onderwerpen nodig zijn voor het genereren van de incrementele uitvoer.
- De `maps` kenmerk bevat pad van de kaartbestanden \(voor het oplossen van toetsruimteverwijzingen\) die zonder onderwerpen op de schijf zijn uitgepakt.
- De `outputs` Voor dit kenmerk wordt gebruikgemaakt van een array met namen van uitvoervoorinstellingen die worden gebruikt om de uitvoer te genereren.

**Responswaarden**: Retourneert een HTTP 200 \(Successful\) reactie.

## Uitvoervoorinstelling verwijderen

Een POST-methode waarmee een uitvoervoorinstelling wordt verwijderd.

**Aanvraag-URL**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/publishlistener

**Parameters**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`:operation`|String|Ja|Naam van de bewerking die wordt aangeroepen. De waarde van deze parameter is `deleteoutput`.<br> **Opmerking:** De waarde is niet hoofdlettergevoelig.| |`sourcePath`|Tekenreeks|Ja|Absoluut pad van het DITA-kaartbestand.| |`outputName`|Tekenreeks|Ja|Naam van de uitvoervoorinstelling die moet worden verwijderd.|

**Responswaarden**: Retourneert een HTTP 200 \(Successful\) reactie.
