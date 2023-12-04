---
title: Op Java gebaseerde API om met uitvoergeneratie te werken
description: Meer informatie over de op Java gebaseerde API om met uitvoergeneratie te werken
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 0%

---

# Op Java gebaseerde API om met uitvoergeneratie te werken {#id175UB30E05Z}

Met de volgende op Java gebaseerde API kunt u uitvoer genereren voor een DITA-kaart. Deze API is beschikbaar in de vorm van een bundel. U moet deze bundel in uw code omvatten om deze APIs te gebruiken.

Details bundel:

- Groep-id: **com.adobe.fmdita**

- Artefact-id: **api**

- Versie: **3,4**

- Pakket: ****com.adobe.fmdita.api.maps****

- Klassegegevens:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  De **`PublishUtils`** klasse bevat een methode voor het genereren van uitvoer voor een of meer uitvoervoorinstellingen.


## Uitvoer genereren

De ``generateOutput`` Deze methode genereert uitvoer voor een DITA-toewijzingsbestand met de opgegeven uitvoervoorinstellingen.

**Syntaxis**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |``sourcePath``|Tekenreeks|Pad \(in de AEM opslagplaats\) van het DITA-kaartbestand waarvoor de uitvoer moet worden gegenereerd.| |``outputName``|Tekenreeks|Naam van de uitvoervoorinstelling\(s\) die moet worden gebruikt om uitvoer te genereren. U kunt meerdere uitvoervoorinstellingen opgeven met behulp van het scheidingsteken \(&quot;\|&quot;\) van de pipe, bijvoorbeeld `aemsite\|pdfoutput`.|

**Uitzondering**: Throws ``javax.jcr.RepositoryException``, `java.io.IOException`, en `java.lang.Exception`.
