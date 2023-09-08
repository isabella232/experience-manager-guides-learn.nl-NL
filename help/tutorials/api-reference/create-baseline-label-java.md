---
title: API's die zijn gebaseerd op Java om te werken met basislijnen en labels
description: Meer informatie over de op Java gebaseerde API's om met basislijnen en labels te werken
source-git-commit: fad5049962f258bbe59c7d172436d82b3d6cd68f
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 0%

---


# API&#39;s die zijn gebaseerd op Java om te werken met basislijnen en labels {#id175UB30E05Z}

Met de volgende op Java gebaseerde API&#39;s kunt u basislijnen maken en labels toevoegen aan bestanden in een basislijn. Deze API&#39;s zijn beschikbaar in de vorm van een bundel. U moet deze bundel in uw code omvatten om deze APIs te gebruiken.

Details bundel:

- Groep-id: **com.adobe.fmdita**

- Artefact-id: **api**

- Versie: **3,5**

- Pakket: **com.adobe.fmdita.api.baselines**

- Klassegegevens:

  ```JAVA
  public class BaselineUtils extends Object
  ```

  De **BaselineUtils** klasse bevat methoden voor het maken van basislijnen en het toepassen van labels op bestanden in een basislijn.


## Een basislijn maken

De basislijnmethode maken heeft twee versies: een voor XML Documentation-oplossing versie 3.5 en een andere voor versies ouder dan 3.5 release \(die versies 3.4, 3.3 en 3.2 bevat). Met versie 3.5 API kan basislijn worden gemaakt met een label, directe verwijzingen en indirecte verwijzingen in een kaartbestand.

De andere versie van de API gebruikt de datum en tijd om een basislijn te maken. Deze API blijft behouden voor achterwaartse compatibiliteit met systemen die gebruikmaken van XML Documentation-oplossing 3.4, 3.3 of 3.2.

**Syntaxis \(voor versie 3.5\)**:

```JAVA
public static String createBaseline(Session session, 
String sourcePath, 
String baselineTitle, 
String label, 
LinkedHashMap directContext, 
LinkedHashMap indirectContext) 
throws GuidesApiException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie. De gebruikerssessie moet zowel lees- als schrijfmachtigingen hebben voor de DITA-kaart en lees machtigingen voor alle referentiebestanden in de basislijn.| |`sourcePath`|Tekenreeks|Absoluut pad van het DITA-kaartbestand in AEM opslagplaats.| |`baselineTitle`|String|Een unieke titel voor de basislijn.| |`label`|String|Selecteer de versie van een onderwerp waarop het opgegeven label is toegepast.| |`directContext`|LinkedHashMap&lt;string object=&quot;&quot;>|De configuraties op basis waarvan het onderwerp \(inhoud\) waarnaar rechtstreeks wordt verwezen wordt geselecteerd, wordt de volgorde in de kaart gevolgd om een versie op te lossen. <br> Als na herhaling op alle toetsen van de kaart geen versie wordt gevonden, mislukt het maken van de basislijn. <br> Als HashMap leeg \ is (verzend lege en niet ongeldige kaart voor gebrek \), dan door gebrek wordt het, bevolkt als: <br>`directContext.put("label", label);` <br> `directContext.put("latest", true);` <br> Als u wilt dat bij het maken van de basislijn alleen een versie van een bepaald label wordt gekozen en dat deze versie mislukt als deze versie niet bestaat, plaatst u de knop `label` en het label waarop u basislijn wilt maken.| |`indirectContext`|LinkedHashMap&lt;string object=&quot;&quot;>|De configuraties op basis waarvan het onderwerp \(inhoud waarnaar wordt verwezen) onrechtstreeks wordt geselecteerd, wordt de volgorde in de kaart gevolgd om een versie op te lossen. <br> Als na herhaling op alle toetsen van de kaart geen versie wordt gevonden, mislukt het maken van de basislijn. <br> Als HashMap leeg \ is (verzend lege en niet ongeldige kaart voor gebrek \), dan door gebrek, wordt het bevolkt als: <br>`indirectContext.put("label", label);` <br>`indirectContext.put "pickAutomatically", null);` <br> Als u wilt dat het de nieuwste versie is in plaats van automatisch een versie op te halen, vervangt u: <br>`indirectContext.put("pickAutomatically", null);` <br> _met:_ <br>`indirectContext.put("latest", true)`|

**Retourneert**: De naam van de basislijn, de knooppuntnaam van de basislijn in de gegevensopslagruimte JCR. De titel van de nieuwe basislijn wordt aan de gebruiker getoond op de pagina Basislijn voor de kaart DITA.

**Uitzondering**: Throws ``ItemExistExceptiom`` als er al een basislijn met dezelfde titel bestaat.

**Syntaxis \(voor versies 3.4, 3.3 en 3.2\)**

```JAVA
public static String createBaseline
(Session session, 
String sourcePath, 
String baselineTitle, 
Date versionDate) throws GuidesApiException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie. De gebruikerssessie moet zowel lees- als schrijfmachtigingen hebben voor de DITA-kaart en lees machtigingen voor alle referentiebestanden in de basislijn.| |``sourcePath``|Tekenreeks|Absoluut pad van het DITA-kaartbestand in AEM opslagplaats.| |`baselineTitle`|String|Een unieke titel voor de basislijn.| |`versionDate`|Datum|De basislijn wordt gecreeerd gebruikend de versies van onderwerpen\ (direct van de kaart DITA van verwijzingen \) zoals op deze datum. Geef de datum op in `d-MM-yyyy H:mm` formaat.|

**Retourneert**: De naam van de basislijn, de knooppuntnaam van de basislijn in de gegevensopslagruimte JCR. De titel van de nieuwe basislijn wordt aan de gebruiker getoond op de pagina Basislijn voor de kaart DITA.

**Uitzondering**: Throws ``RepositoryException.``

## Labels toepassen

De ``applyLabel`` een of meer labels toepassen op de bestanden in een basislijn.

**Syntaxis**:

```JAVA
public static void applyLabel(Session session,
                  String sourcePath,
                  String baselineName,
                  String label)
                  throws RepositoryException, WorkflowException, Exception
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`sourcePath`|Tekenreeks|Absoluut pad van het DITA-kaartbestand in AEM opslagplaats.| |``baselineName``|String|Naam van het basislijnknooppunt waarop het label moet worden toegepast. Als u de naam van het basislijnknooppunt wilt ophalen, kunt u de opdracht [\#id185NFF0085Z](#id185NFF0085Z) methode of controleer de basislijnknoop van de kaart DITA in CRXDE.<br> **Opmerking:** Label wordt toegepast op de versie van bestanden waarnaar rechtstreeks vanuit het kaartbestand in de basislijn wordt verwezen.| |`label`|String|Een label dat wordt toegepast op bestanden in de basislijn. Zorg ervoor dat het label niet de volgende tekens bevat: &amp;sol; &amp;komma; &amp;dubbelpunt; &amp;komma; &amp;komma; lbrack; &amp;komma; &amp;rbrack; komma; &amp;omkeren; komma; &amp;asteren; <br> Als u meerdere labels wilt instellen, scheidt u de labels met een komma, bijvoorbeeld Label1, Label2.|

**Uitzondering**: Throws `RepositoryException`.

## Labels verwijderen

De ``deleteLabel`` verwijdert een of meer labels uit de bestanden in een basislijn.

**Syntaxis**:

```JAVA
public static Map
<String, String> deleteLabel(Session session, 
String sourcePath, 
String baselineName, 
String label) throws GuidesApiException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`sourcePath`|Tekenreeks|Absoluut pad van het DITA-kaartbestand in AEM opslagplaats.| |`baselineName`|String|Naam van de basislijn vanwaar het label moet worden verwijderd. <br> **Opmerking:** Label wordt verwijderd uit de versie van bestanden waarnaar rechtstreeks wordt verwezen vanuit het kaartbestand in de basislijn.| |`label`|String|Een label dat uit bestanden in de basislijn moet worden verwijderd. <br> Als u meerdere labels wilt verwijderen, scheidt u de labels met een komma, bijvoorbeeld Label1, Label2.|

**Retourneert**: De kaart met *key:value* paar `path:deletedlabels` voor alle bestanden in de basislijn.

**Uitzondering**: Throws ``RepositoryException`, `VersionException`, `Exception``.

