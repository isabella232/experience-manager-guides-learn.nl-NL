---
title: API's die zijn gebaseerd op Java om te werken met DITA-kaarten
description: Meer informatie over de op Java gebaseerde API's voor werken met DITA-kaarten
source-git-commit: fad5049962f258bbe59c7d172436d82b3d6cd68f
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 0%

---


# API&#39;s die zijn gebaseerd op Java om te werken met DITA-kaarten {#id175UB30E05Z}

Met de volgende op Java gebaseerde API&#39;s kunt u werken met DITA-kaarten in AEM hulplijnen. Deze API&#39;s zijn beschikbaar in de vorm van een bundel. U moet deze bundel in uw code omvatten om deze APIs te gebruiken.

Details bundel:

- Groep-id: **com.adobe.fmdita**

- Artefact-id: **api**

- Versie: **3,2**

- Pakket: **com.adobe.fmdita.api.maps**

- Klassegegevens:

  ```JAVA
  public class MapUtilities extends Object
  ```

  De klasse MapUtilities bevat methoden voor het ophalen van metagegevens uit een DITA-kaartbestand.


## DITA-kaart met afhankelijke personen downloaden

De `zipMapWithDependents` Deze methode maakt een ZIP-bestand dat een DITA-kaart bevat, samen met alle afhankelijke elementen, zoals onderwerpen waarnaar wordt verwezen, submappen, afbeeldingen en DTD&#39;s. Het .zip dossier voor de kaart DITA wordt gecreeerd gebaseerd op een bepaalde basislijn.

U kunt hiermee ook dezelfde structuur \(bovenliggende en onderliggende mappen\) behouden of een vlakke bestandsstructuur maken in één map voor alle afhankelijke bestanden.

>[!IMPORTANT]
>
> De API genereert een uitzondering en kan geen ZIP-bestand maken als een van de afhankelijke bestanden ontbreekt.

**Syntaxis**:

```JAVA
public static void zipMapWithDependents(Session session, 
                     String sourcePath, 
                     String baseline, 
                     OutputStream outputStream,
                     boolean flatFS) 
                     throws RepositoryException, IOException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`sourcePath`|Tekenreeks|Pad \(in de AEM opslagplaats\) van het DITA-kaartbestand dat moet worden gedownload.| |`outputStream`|java.io.OutputStream|The stream to write the ZIP to.| |`baseline`|String|De titel van de basislijn die wordt gebruikt om de versie van de inhoud op te halen. <br> **Opmerking:** De waarde is hoofdlettergevoelig.| |flatFS|Boolean|\(Optioneel\) Als deze waarde is ingesteld op true, wordt een platte structuur van bestanden geretourneerd in het ZIP-bestand. Als uw DITA-kaart bijvoorbeeld verwijst naar inhoud in meerdere mappen, worden alle bestanden waarnaar wordt verwezen, in één map geplaatst. Als er bestanden met dezelfde naam zijn, wordt de naam van deze bestanden gewijzigd door een numeriek achtervoegsel toe te voegen. Alle verwijzingen \(in kaart DITA en onderwerpen \) worden automatisch behandeld, aangezien zij gebaseerd op de nieuwe plaats van dossiers in de vlakke omslagstructuur worden bijgewerkt. Als de waarde false is, blijft de mapstructuur ongewijzigd in het ZIP-bestand. Als de DITA-kaart verwijst naar bestanden van meerdere locaties, worden al deze locaties ook gemaakt in het ZIP-bestand. Wanneer u het ZIP-bestand herstelt, wordt de exacte mapstructuur gemaakt op de doellocatie. <br> De standaardwaarde voor deze parameter is false.|

**Retourneert**: De inhoud van het ZIP-bestand wordt naar de `outputStream`.

**Uitzondering**: Throws ``javax.jcr.RepositoryException``, `java.io.IOException`.

## DITA-kaart downloaden met afhankelijke personen \(Asynchroon\)

U kunt ook een DITA-kaart met afhankelijkheden downloaden in een asynchrone modus. Deze benadering is nuttiger voor grotere kaarten DITA.

De `zipMapWithDependents` Deze methode maakt een ZIP-bestand dat een DITA-kaart bevat, samen met alle afhankelijke elementen, zoals onderwerpen waarnaar wordt verwezen, submappen, afbeeldingen en DTD&#39;s. Het .zip dossier voor de kaart DITA wordt gecreeerd gebaseerd op een bepaalde basislijn.

U kunt hiermee ook dezelfde structuur \(bovenliggende en onderliggende mappen\) behouden of een vlakke bestandsstructuur maken in één map voor alle afhankelijke bestanden.

>[!NOTE]
>
> Dit knooppunt wordt na enige tijd automatisch verwijderd op basis van de configuratie output.history.purgetime, indien gedefinieerd, of 5 dagen als standaard.

**Syntaxis**:

```JAVA
public static CompletableFuture<Node> zipMapWithDependencies(Session session,
                     String sourcePath, 
                     String baseline, 
                     boolean flatFS) 
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`sourcePath`|Tekenreeks|Pad \(in de AEM opslagplaats\) van het DITA-kaartbestand dat moet worden gedownload.| |`baseline`|String|De titel van de basislijn die wordt gebruikt om de versie van de inhoud op te halen. <br> **Opmerking:** De waarde is hoofdlettergevoelig.| |flatFS|Boolean|\(Optioneel\) Als deze waarde is ingesteld op true, wordt een platte structuur van bestanden geretourneerd in het ZIP-bestand. Als uw DITA-kaart bijvoorbeeld verwijst naar inhoud in meerdere mappen, worden alle bestanden waarnaar wordt verwezen, in één map geplaatst. Als er bestanden met dezelfde naam zijn, wordt de naam van deze bestanden gewijzigd door een numeriek achtervoegsel toe te voegen. Alle verwijzingen \(in kaart DITA en onderwerpen \) worden automatisch behandeld, aangezien zij gebaseerd op de nieuwe plaats van dossiers in de vlakke omslagstructuur worden bijgewerkt. Als de waarde false is, blijft de mapstructuur ongewijzigd in het ZIP-bestand. Als de DITA-kaart verwijst naar bestanden van meerdere locaties, worden al deze locaties ook gemaakt in het ZIP-bestand. Wanneer u het ZIP-bestand herstelt, wordt de exacte mapstructuur gemaakt op de doellocatie.<br> De standaardwaarde voor deze parameter is false.|

**Retourneert**: Het knooppunt van het ZIP-bestand is opgenomen in het dialoogvenster `CompletableFuture`klasse. De gebruiker kan doorgaan met asynchroon afhandelen en kan `.get()`methode van de toekomst om de draad te blokkeren wanneer de knoop nodig is. De geretourneerde waarde kan ook eindigen met een fout die kan worden afgehandeld met `.exceptionally()` methode.

## Een lijst met basislijnen ophalen

De ``getBaselineList`` de methode wint een lijst van alle basislijnen terug die voor een bepaalde kaart DITA bestaan.

**Syntaxis**:

```JAVA
public static List<HashMap<String,String>> getBaselineList( 
                  javax.jcr.Session session, 
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`sourcePath`|Tekenreeks|Pad \(in de AEM dataopslag\) van het DITA-kaartbestand waarvoor de basislijngegevens moeten worden opgehaald.|

**Retourneert**: Een lijst met `HashMap` objecten. Elk `HashMap` object vertegenwoordigt een basislijn en bevat de naam en titel van de basislijn.

**Uitzondering**: Throws ``javax.jcr.RepositoryException``.

## Een lijst met voorwaardelijke voorinstellingen ophalen

De ``getConditionalPresetList`` Deze methode haalt een lijst op met alle voorwaardelijke voorinstellingen die bestaan voor een bepaalde DITA-kaart.

**Syntaxis**:

```JAVA
public static List<HashMap<String,String>> getConditionalPresetList (
                  javax.jcr.Session session,
                  String sourcePath)
                  throws javax.jcr.RepositoryException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`sourcePath`|Tekenreeks|Pad \(in de AEM opslagplaats\) van het DITA-kaartbestand waarvoor de voorwaardelijke voorinstellingsgegevens moeten worden opgehaald.|

**Retourneert**: Een lijst met `HashMap` objecten. Elk `HashMap` Dit object vertegenwoordigt een voorwaardelijke voorinstelling en bevat de naam en titel van de voorwaardelijke voorinstelling.

**Uitzondering**: Throws ``javax.jcr.RepositoryException``.

## De gegevens van het DITAVAL-bestand ophalen voor een voorwaardelijke voorinstelling

De ``getDitavalFromConditionalPreset`` Hiermee wordt het pad opgehaald van het DITAVAL-bestand dat overeenkomt met een voorwaardelijke voorinstelling voor een bepaalde DITA-kaart.

**Syntaxis**:

```JAVA
public static String getDitavalFromConditionalPreset
    (Session session,
    String sourcePath, 
    String cpName) throws RepositoryException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`session`|javax.jcr.Session|Een geldige JCR-sessie.| |`sourcePath`|Tekenreeks|Pad \(in de AEM opslagplaats\) van het DITA-kaartbestand waarvoor het DITAVAL-bestand moet worden opgehaald.| |`cpName`|String|Naam van de voorwaardelijke voorinstelling in de DITA-kaart waarvoor het DITAVAL-bestand moet worden opgehaald.|

**Retourneert**: Het pad van het DITAVAL-bestand dat overeenkomt met de voorwaardelijke voorinstelling die is gedefinieerd in het DITA-kaartbestand.

## Hiermee worden alle afhankelijkheden voor een knooppunt opgehaald

De ``getAllDependencies`` methode keert alle gebiedsdelen van een bepaalde knoop terug.

**Syntaxis**:

```JAVA
public static List
<Node> getAllDependencies 
(Node rootNode) throws GuidesApiException
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`rootNode`|javax.jcr.Node|Het basisknooppunt waarvoor alle afhankelijkheden moeten worden opgehaald.|

**Retourneert**: Een knooppuntlijst die alle gebiedsdelen van de wortelknoop bevat.

