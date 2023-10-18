---
title: Inleiding
description: Inleiding tot de API-naslaggids voor AEM
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
source-git-commit: 112085153aaf246289bd8f91657c95e986df482e
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---

# Inleiding {#id1761C0007W7}

Adobe Experience Manager-hulplijnen \(later doorverwezen naar *Hulplijnen AEM*\) is een complete bedrijfsoplossing die Adobe Experience Manager \(AEM\) in staat stelt om componentcontentbeheeroplossing \(CCMS\) mogelijkheden te bieden voor het maken en leveren van DITA-inhoud. Klanten hebben via programmacode toegang tot AEM werkstromen van hulplijnen om deze te integreren met andere bedrijfstoepassingen. Deze APIs kan ook door Adobe partners worden gebruikt om de waardebepaling van AEMGidsen te verbeteren door zijn functionaliteit uit te breiden of het met andere toepassingen of de diensten te integreren.

## Hulplijnen-API&#39;s AEM

De API&#39;s voor hulplijnen voor AEM zijn in twee indelingen beschikbaar: HTTP en Java. Deze API&#39;s maken belangrijke functies van AEM hulplijnen beschikbaar voor toepassingsontwikkelaars. Met deze functies kunnen ontwikkelaars hun eigen plug-ins maken om de workflows uit de doos uit te breiden. De API&#39;s zijn beschikbaar voor het beheren van uitvoer voor DITA-inhoud, het werken met DITA-kaarten, het toevoegen van voorwaardelijke kenmerken aan profielen op mapniveau en het converteren van HTML- en Word-documenten naar DITA-indeling.

## De JAR&#39;s installeren op uw lokale Apache Maven-opslagplaats {#install-jar-local}

Als u de JAR-bestanden die door AEM hulplijnen worden weergegeven, wilt kunnen gebruiken, moet u ze installeren in uw lokale Apache Maven-opslagruimte. Voer de volgende stappen uit om de JAR&#39;s te installeren op uw locatie in Maven-opslagplaats:

1. Pak de inhoud van het bestand \(.zip\) van het pakket AEM hulplijnen uit op uw lokale systeem.

2. Navigeer naar de volgende map in het pad voor geëxtraheerde inhoud bij de opdrachtprompt:

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Voer de volgende opdracht uit om de API-bundel te installeren in uw lokale Maven-opslagruimte:

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

   >[!NOTE]
   >
   > In het bovenstaande bevel, zou X.x met het daadwerkelijke versieaantal in de parameters van Dfile en van de Versie moeten worden vervangen.

4. \(*Optioneel*\) Installeer afhankelijkheid in de opslagplaats van uw lokale Maven-project. U kunt dit bereiken door een map te maken in uw Maven-project en vervolgens het dialoogvenster `mvn install` opdracht gegeven in de vorige stap met de volgende extra parameter:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   Als u vervolgens de lokale opslagmap van het project toegankelijk wilt maken voor het Maven-ontwikkelproces, voegt u een `repository` -element in het bovenliggende bestand pom.xml, zoals hieronder wordt weergegeven:

   ```XML
   <repositories>
      <repository>
         <id>project-repository</id>
         <url>file://${project.basedir}/repository</url>
      </repository>
   </repositories>
   ```


Dit proces installeert de API JARs in de lokale Maven bewaarplaats.

## De service-API JAR gebruiken in een Maven-project

Nadat u de API JAR&#39;s in uw lokale Maven-opslagruimte hebt geïnstalleerd, voert u de volgende stappen uit om de JAR in uw projecten te gebruiken:

1. Voeg JAR aan uw codebasis toe en bewijs het aan de gegevensopslagplaats van de codebasis onder een omslag, zoals &quot;gebiedsdelen&quot;. De mapnaam is afhankelijk van de basishiërarchie van de code.

2. Configureer de bestanden met projectpom.xml als volgt:

   Het bestand pom.xml van het bovenliggende project:

   >[!IMPORTANT]
   >
   > In het volgende codefragment moet X.x worden vervangen door het eigenlijke versienummer en de bestandsnaam van de API JAR. Deze informatie is dezelfde als in stap 3 van de [installatieproces](#install-jar-local).

   ```XML
   <plugin>
   
       <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
       <version>2.5.2</version>
   
       <configuration>
   
               <groupId>com.adobe.fmdita</groupId>
   
               <artifactId>api</artifactId>
   
               <version>X.x</version>
   
               <file>${basedir}/dependencies/fmdita/api-X.x.jar</file>
   
               <packaging>jar</packaging>
   
               <generatePom>true</generatePom>
   
       </configuration>
   
       <executions>
   
           <execution>
   
               <id>inst_fmdita</id>
   
                   <goals>
   
                       <goal>install-file</goal>
   
                   </goals>
   
                   <phase>clean</phase>
   
           </execution>
   
       </executions>
   </plugin>
   ```

   Het bestand pom.xml van de onderliggende module:

   ```XML
   <plugin>
      <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
      <configuration>
   
         <groupId>com.adobe.fmdita</groupId>
   
         <artifactId>api</artifactId>
   
         <version>3.6</version>
   
         <file>${basedir}/../dependencies/fmdita/api-3.6.jar</file>
   
         <packaging>jar</packaging>
   
         <generatePom>true</generatePom>
   
      </configuration>
   
      <executions>
   
         <execution>
   
            <id>inst_fmdita</id>
   
            <goals>
   
               <goal>install-file</goal>
   
            </goals>
   
            <phase>clean</phase>
   
         </execution>
   
      </executions>
   
   </plugin>
   ```


## De service-API JAR van de openbare Maven-opslagplaats configureren en gebruiken

Voer de volgende stappen uit om de dienst API JARs van de openbare Maven bewaarplaats in uw projecten te vormen en te gebruiken:

1. Om de dienst API JAR in een project te gebruiken, vorm AEM Gidsen openbare GeMaven bewaarplaats in uw pom.xml- dossier.
2. Configureer de openbare Maven-opslagplaats in het bestand settings.xml van Maven als volgt:

   ```XML
   <repository>
      <id>fmdita-public</id>
      <name>fmdita-public</name>
      <url>https://repo.aem-guides.com/repository/fmdita-public</url>
   </repository>
   ```

3. Zodra de bewaarplaats opstelling is, voeg de dienst API JAR als projectgebiedsdeel in het pom.xml- dossier van het project toe.

   >[!NOTE]
   >
   > Gebruik dezelfde versie van de API JAR als het pakket met AEM hulplijnen dat u op de server hebt geïnstalleerd.

4. Vorm de Geweven gebiedsdeel zoals hieronder getoond:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Zodra de dienst API JAR als projectgebiedsdeel in het pom.xml- dossier van het project wordt toegevoegd, kunt u AEM Gidsen Java APIs in uw project bouwen en gebruiken.

## API JAR gebruiken vanuit de Maven Central-opslagplaats voor AEM hulplijnen as a Cloud Service

Voor AEM as a Cloud Service hulplijnen is de API JAR geïmplementeerd in Maven Central. U kunt de API JAR zonder enige installatie gebruiken.

>[!NOTE]
>
> De naamgevingsconventie van de API-jar is bijgewerkt volgens de naamgevingsconventie voor invoegtoepassingen voor cloud.

Om API JAR te gebruiken, moet u het gebiedsdeel aan pom.xml van uw project toevoegen zoals hieronder getoond:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-guides-sdk-api</artifactId>
   <version>2022.5</version>
</dependency>
```

>[!NOTE]
>
> Aangezien de pakketten in de API JAR nog steeds hetzelfde zijn, is geen codewijziging vereist om deze API JAR in de bestaande wolkenprojecten te gebruiken.

## Aanvullende bronnen

Hier volgt een lijst met andere nuttige bronnen van AEM hulplijnen, die beschikbaar zijn op de [Meer informatie en ondersteuning](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) pagina:

- Handboek
- Installatie- en configuratiehandleiding
- Handleiding voor snel starten
- [Help-archiveringspagina](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(toegang tot oudere releasedocumentatie\)
