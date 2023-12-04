---
title: Java-API voor het maken en activeren van pakketten
description: Meer informatie over de Java-API voor het maken en activeren van pakketten
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---

# Java-API voor het maken en activeren van pakketten {#id175UB30E05Z}

Met de volgende Java-API kunt u CRX-pakketten maken en activeren. Deze API is beschikbaar in de vorm van een bundel. U moet deze bundel in uw code omvatten om deze APIs te gebruiken.

Details bundel:

- Groep-id: **com.adobe.fmdita**

- Artefact-id: **api**

- Versie: **3,3**

- Pakket: **com.adobe.fmdita.api.crxactivate**

- Klassegegevens:

  ```JAVA
  public class CRXActivator
  ```

  De **`CRXActivator`** klasse bevat een methode voor het maken van CRX-pakketten en het repliceren ervan in de publicatieinstantie.


## Pakketten maken en activeren

De `activate` wordt een CRX-pakket gemaakt voor de instantie van de auteur en wordt zo nodig in de instantie publish gerepliceerd. Men veronderstelt dat de AEM replicatieparameters reeds opstelling op de auteursinstantie zijn geweest. Met deze methode wordt het CRX-pakket gemaakt op basis van een lijst met regels die als invoerparameters in een JSON-tekenreeks worden opgegeven.
>[!NOTE]
>
> Fouten die tijdens het maken of activeren zijn aangetroffen, worden naar het `outputstream`.

**Syntaxis**:

```JAVA
public static void activate
(
  String json, 
  OutputStream outputstream, 
  Session session
) 
throws GuidesApiException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`json`|String|JSON-tekenreeks die het te bouwen CRX-pakket bepaalt. Gebruik de volgende indeling om de JSON-tekenreeks te maken: <br>- `activate`: Is van het type Boolean \(`true`/`false`\). Bepaalt of het CRX-pakket dat in de auteurinstantie is gemaakt, wordt gerepliceerd naar de publicatie-instantie. <br> - `rules`: is van het type JSON Array. Een array met JSON-regels die opeenvolgend worden verwerkt om het CRX-pakket samen te stellen. <br> - `rootPath`: Is van het type String. Het basispad waarop de query&#39;s voor het knooppunt/de eigenschap worden uitgevoerd. Als er geen knooppunten/eigenschapquery&#39;s aanwezig zijn, worden het hoofdpad en alle knooppunten die zich onder het hoofdpad bevinden opgenomen in het CRX-pakket. <br> - `nodeQueries`: is van het type Regex Array. Een array van reguliere expressies die wordt gebruikt om specifieke bestanden op te nemen onder het hoofdpad. <br> - `propertyQueries`: is van het type JSON Array. Een array van JSON-objecten met elk JSON-object dat bestaat uit een XPath-query die moet worden uitgevoerd op het hoofdpad en de naam van een eigenschap die aanwezig is in elk JCR-knooppunt nadat de query is uitgevoerd. De waarde van de eigenschap in elk JCR-knooppunt moet een pad of een array van paden zijn. De paden in deze eigenschap worden toegevoegd aan het CRX-pakket.| |`outputstream`|java.io.OutputStream|This is used to write the result of various stage, such as query implementation, file inclusion, CRX package creation, or activation. Alle fouten die tijdens het maken of activeren zijn aangetroffen, worden naar de `outputstream`. Dit is handig voor foutopsporing.| |`session`|String|Een geldige JCR-sessie met activeringsmachtigingen.|

**Uitzondering**: Throws ``java.io.IOException``.

**Voorbeeld**: In het volgende voorbeeld wordt getoond hoe u een JSON-query bouwt:

```JSON
{
  "activate": true,
  "rules": [
    {
      "rootPath": "/content/dam/nested",
      "nodeQueries": [
        ".*\\.jpg",
        ".*\\.png",
        ".*\\.gif"        
      ]
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap"
    },
    {
      "rootPath": "/content/output/sites/hierarchy_ditamap",
      "propertyQueries": [
        {
          "query": "//*[@fileReference]",
          "property": "fileReference"
        }
      ]
    }
  ]
}
```

De voorbeeld-JSON-query bestaat uit de volgende regels:

- Alleen de .png-, .jpg- en .gif-afbeeldingen onder /content/dam/nested pad worden in het pakket opgenomen.
- Alle knooppunten onder /content/output/sites/shiërarchie\_ditamap worden opgenomen in het pakket.
- De paden in het dialoogvenster `fileReference` eigenschap van knooppunten onder /content/output/sites/shiërarchie\_ditamap wordt opgenomen in het pakket.
