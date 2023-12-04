---
title: Java-API om te werken met mapprofielen
description: Meer informatie over de op Java gebaseerde API om met mapprofielen te werken
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 0%

---

# Java-API om te werken met mapprofielen {#id175UB30E05Z}

Met de volgende op Java gebaseerde API kunt u voorwaardelijke kenmerken toevoegen aan een profiel op mapniveau. Deze API is beschikbaar in de vorm van een bundel. U moet deze bundel in uw code omvatten om deze APIs te gebruiken.

Details bundel:

- Groep-id: **com.adobe.fmdita**

- Artefact-id: **api**

- Versie: **3,2**

- Pakket: **com.adobe.fmdita.api.profiles**

- Klassegegevens:

  ```JAVA
  public class FolderProfileUtils extends Object
  ```

  De **`FolderProfileUtils`** bevat een methode voor het toevoegen van voorwaardelijke kenmerken in een mappenprofiel.


## Voorwaardelijke kenmerken toevoegen aan een mapprofiel

De ``addAttributeProfiles`` Hiermee voegt u voorwaardelijke kenmerken toe aan een mapprofiel.

**Syntaxis**:

```JAVA
public static boolean addAttributeProfiles
(List
<String> attributeNames, 
List
    <String> values, 
List
        <String> labels,
String profileName, 
Session session) throws GuidesApiException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |``attributeNames``|String|Een lijst met kenmerknamen.| |``values``|String|Een lijst met waarden voor de opgegeven kenmerken.| |`labels`|String|Een lijst met labels voor de `attribute`- `value` paren. [1](#fntarg_1)| |`profileName`|String|De naam van het profiel op mapniveau waarop deze kenmerken, waarden en labels moeten worden toegepast. **Belangrijk:** Alle bestaande kenmerken-waarden-labels die in het profiel zijn gedefinieerd, worden overschreven.| |`session`|javax.jcr.Session|Een geldige JCR-sessie.|

**Retourneert**:
`true` voor succes. In het geval van een mislukking, veroorzaakt het een uitzondering.

**Uitzondering**: Throws ``java.lang.Exception`` in de volgende scenario&#39;s:

- Kan de API niet ophalen `resourceResolverFactory` object. In dat geval moet u de bundel opnieuw starten.
- Als parameters die aan de API worden doorgegeven ongeldig zijn.
- Als de API wordt aangeroepen via een niet-geautoriseerde gebruikerssessie, bijvoorbeeld de gebruiker die geen beheerder is voor het opgegeven mapprofiel.

[1](#fnsrc_1) De `attributeNames`, `values`, en `labels` op dezelfde index in een arraylijst moet overeenkomen met dezelfde vermelding.
