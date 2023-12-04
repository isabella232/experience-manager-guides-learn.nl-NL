---
title: Java-API's voor conversieworkflow
description: Meer informatie over de op Java gebaseerde API's voor de conversieworkflow
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Java-API&#39;s voor conversieworkflow {#id175UB30E05Z}

Met de volgende op Java gebaseerde API&#39;s kunt u HTML- en Word-documenten converteren naar DITA-indeling. Deze API&#39;s zijn beschikbaar in de vorm van een bundel. U moet deze bundel in uw code omvatten om deze APIs te gebruiken.

**Bundgegevens**:

- Groep-id: **com.adobe.fmdita**

- Artefact-id: **api**

- Versie: **3,2**

- Pakket: **com.adobe.fmdita.api.conversion**

- Klassegegevens:

  ```JAVA
  public class ConversionUtils extends Object
  ```

  De **ConversionUtils** -klasse bevat methoden voor het converteren van HTML- en Word-documenten naar DITA-indeling.


## HTML-documenten converteren

De `convertHtmlToDita` methode converteert HTML-documenten naar DITA-indeling.

**Syntaxis**:

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`inputFile`|Tekenreeks|Absoluut pad van de HTML-bronbestanden in AEM opslagplaats.| |`destPath`|String|Absoluut pad van de doellocatie waar de geconverteerde DITA-bestanden worden opgeslagen.| |`createRev`|Boolean|Opgeven of een revisie van de bestanden wordt gemaakt \( `true`\) op het opgegeven doel of niet \( `false`\). Dit wordt alleen overwogen wanneer de doellocatie een bestaande versie van de omgezette bestanden bevat.|

**Uitzondering**: Throws `RepositoryException`.

## Word-documenten converteren

De ``convertWordToDita`` Hiermee converteert u Word-documenten naar DITA-indeling.

**Syntaxis**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`inputFile`|Tekenreeks|Absoluut pad van de Word-bronbestanden in AEM opslagplaats.| |`destPath`|String|Absoluut pad van de doellocatie waar de geconverteerde DITA-bestanden worden opgeslagen.| |`style2tagMap`|String|Absoluut pad van het stijltoewijzingsbestand dat wordt gebruikt voor conversie.| |`createRev`|Boolean|Opgeven of een revisie van de bestanden wordt gemaakt \( `true`\) op het opgegeven doel of niet \( `false`\). Dit wordt alleen overwogen wanneer de doellocatie een bestaande versie van de omgezette bestanden bevat.|

**Uitzondering**: Throws `RepositoryException`.
