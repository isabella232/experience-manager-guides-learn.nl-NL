---
title: Aangepaste DITA-OT en DITA-specialisatie gebruiken
description: Leer hoe u aangepaste DITA-OT- en DITA-specialisatie gebruikt
source-git-commit: 5ac066bb8db32944abd046f64da11eeb1bdbe467
workflow-type: tm+mt
source-wordcount: '2075'
ht-degree: 0%

---


# Aangepaste DITA-OT en DITA-specialisatie gebruiken {#id181GAJ0005Z}

De Open Toolkit DITA \(DITA-OT \) is een reeks op Java-Gebaseerde, open-bronhulpmiddelen die verwerking voor kaarten DITA en onderwerpinhoud verstrekken. Met AEM hulplijnen kunt u eenvoudig aangepaste DITA-OT-plug-ins importeren en gebruiken. Na het importeren kunnen AEM hulplijnen zo worden geconfigureerd dat de aangepaste DITA-OT-plug-in wordt gebruikt om uitvoer in elke gewenste indeling te genereren. Als de uitvoer wordt gegenereerd, selecteert u gewoon de optie DITA-OT en AEM hulplijnen gebruiken de aangepaste DITA-OT-plug-in om de vereiste uitvoer te genereren.

Als u Ant-parameters wilt verwerken terwijl u uitvoer publiceert, biedt AEM hulplijnen u een eenvoudige manier om dit te doen. U kunt opgeven welke Ant-parameters u wilt gebruiken en dezelfde parameters vervolgens door het publicatieproces worden verwerkt.

>[!NOTE]
>
> AEM hulplijnen worden geleverd met DITA-OT versie 3.3.2. AEM hulplijnen bieden echter ondersteuning voor DITA-OT versie 1.7 en hoger. Voor de volledige lijst van DITA-OT versies, zie [DITA-OT-versies](http://www.dita-ot.org/download).

>[!TIP]
>
> Zie de *Configuratie DITA-OT-profielen* en *Aangepaste DITA-OT gebruiken* in de handleiding met aanbevolen procedures vindt u de beste werkwijzen voor het gebruik van aangepaste DITA-OT-plug-ins.

## Aangepaste DITA-OT-plug-ins gebruiken {#id181NH1020L7}

Er zijn twee manieren om aangepaste insteekmodule DITA-OT te gebruiken voor publicatie. De eerste methode is het uploaden van de aangepaste DITA-OT plug-in naar de AEM opslagplaats. De andere methode is om de aangepaste DITA-OT-plug-in op uw server op te slaan, een profiel te maken en de locatie van de aangepaste DITA-OT-plug-in in uw profiel op te geven.

Standaard wordt bij AEM hulplijnen een vooraf geconfigureerd profiel geleverd met de configuraties van de standaardsjablonen die kunnen worden gebruikt voor het bewerken en publiceren van inhoud. U kunt aangepaste profielen maken met aangepaste sjablonen die u kunt gebruiken tijdens het bewerken van documenten en aangepaste DITA-OT-plug-ins voor het publiceren van inhoud.

Het standaard DITA-OT-pakket beschikbaar bij AEM hulplijnen wordt geleverd met Apache FOP XSL-FO-processor, die geen ondersteuning biedt voor het renderen van MathML-vergelijkingen. Als u MathML vergelijkingen in uw inhoud gebruikt, dan zorg ervoor dat u een MathML het teruggeven motorstop - binnen voor Apache FOP of gebruik een verschillende bewerker XSL-FO hebt geïntegreerd.

>[!IMPORTANT]
>
> Als u AEM Gidsen van versie 2.2 tot 2.5.1 of 2.6 hebt bevorderd, dan worden alle veranderingen die door configuratiemanager worden aangebracht automatisch gekozen en in het StandaardProfiel opgeslagen.

Voer de volgende stappen uit om aangepaste DITA-OT-plug-in te uploaden naar de AEM opslagplaats:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Download de `DITA-OT.ZIP` bestand.

   De locatie van de `DITA-OT.ZIP` bestand is `/libs/fmdita/dita_resources/DITA-OT.zip`.

   ![](assets/dita-ot-zip-in-crx.png)

1. Extraheer de inhoud van het ZIP-bestand op de server.

1. Gebruik een integratormechanisme voor DITA-OT-plug-ins om de nieuwe versie van DITA-OT te integreren met uw aangepaste DITA-OT-plug-in.

   >[!NOTE]
   >
   > Het klassepadscheidingsteken in het ZIP-bestand van de plug-in is afhankelijk van het besturingssysteem. Dit betekent dat als de server wordt gehost op Windows, het klassepadscheidingsteken anders is dan het scheidingsteken voor Linux. Voor meer informatie over het handmatig integreren van plug-ins raadpleegt u de *Plug-ins handmatig installeren* onderwerp in DITA-OT documentatie.

1. Maak het ZIP-bestand opnieuw met dezelfde naam \(`DITA-OT.ZIP`\) en de mapstructuur.

1. Upload het bijgewerkte ZIP-bestand weer naar de AEM-opslagplaats.

   Controleer het volgende voordat u het ZIP-bestand uploadt:

   - Voer de integrator \(om de aangepaste insteekmodule te installeren\) uit op een Mac/Linux-besturingssysteem om problemen met bestandsscheidingstekens te voorkomen - aangezien Windows en Linux-besturingssystemen verschillende bestandscheiders hebben, is de insteekmodule die is geïntegreerd in Mac/Linux OS compatibel met zowel Windows- als Linux-instellingen.
   - Zorg ervoor dat de `DITA-OT.ZIP` Het bestand bevat een map met de naam &quot;DITA-OT&quot; die alle relevante plug-ins en bestanden bevat.
   - Controleren of `DITA-OT.ZIP` Het bestand dat u maakt, is van mimeType: &quot;nt:file&quot; \(dit komt overeen met het primaire type ZIP-bestand wanneer geüpload naar AEM\). Gebruik een WebDAV-tool of code-implementatie om dit ZIP-bestand te uploaden naar het gewenste pad in AEM. \(Gebruik AEM pakketbeheer niet om dit ZIP-bestand te implementeren, omdat dit ZIP-bestand geen pakket met AEM inhoud is, maar slechts een archiefbestand.\)

   >[!NOTE]
   >
   > Het wordt aanbevolen het standaard DITA-OT-pakket niet te overschrijven. U moet uw aangepaste DITA-OT-pakket met uw plug-in uploaden naar een andere locatie onder de `apps` map.

1. Open het standaard DITA-profiel voor bewerken en sla dit op \(zonder updates uit te voeren\) zodat de wijzigingen van kracht worden.


Voer de volgende stappen uit om een nieuw profiel te maken en dit te configureren voor het gebruik van een aangepaste DITA-OT-plug-in die op uw server is opgeslagen:

1. Sla de aangepaste DITA-OT-insteekmodule op uw server op.

   >[!NOTE]
   >
   > De mapstructuur voor het opslaan van de aangepaste DITA-OT-plug-in moet als volgt zijn: `\*<parent-folder\>*\DITA-OT`.

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.

1. Selecteren **Hulplijnen** in de lijst met gereedschappen.

1. Klik op de knop **DITA-profielen** tegel.

   >[!NOTE]
   >
   > De standaardprofielgegevens worden weergegeven op de pagina Profielen. Als u AEM Gidsen van versie 2.2 tot 2.5.1 of 2.6 hebt bevorderd, dan worden alle veranderingen die door configuratiemanager worden aangebracht automatisch gekozen en in het StandaardProfiel opgeslagen.

1. U kunt het standaardprofiel bewerken, een nieuw profiel maken of instellingen in het standaardprofiel dupliceren om een nieuw profiel te maken.

   >[!NOTE]
   >
   > U kunt het standaardprofiel bijwerken, maar u kunt het niet verwijderen. Alle nieuwe profielen die u maakt, kunnen echter worden bewerkt en verwijderd.

1. Configureer de volgende eigenschappen voor het gebruik van de aangepaste DITA-OT-plug-in:

   | Eigenschapnaam | Beschrijving |
   |-------------|-----------|
   | **Profieleigenschappen** |
   | Profielnaam | Geef dit profiel een unieke naam. |
   | Uitvoer opnieuw gebruiken | *\(Optioneel\)* Als uw profiel is gebaseerd op een bestaand profiel, selecteert u deze optie. Als u deze optie selecteert, zorgt u ervoor dat AEM hulplijnen de inhoud van het DITA-OT-pakket niet opnieuw extraheert en het bestaande DITA-OT-pakket opnieuw gebruikt. |
   | Pad voor exporteren van profiel | *\(Optioneel\)* Geef het pad op waar DITA-OT op de schijf wordt gehouden. Standaard bundelt AEM hulplijnen een DITA-OT-pakket in de opslagplaats en wordt het op de schijf opgehaald bij dit pad.<br>**Opmerking** U kunt dit pad definiëren met een bestaande systeemvariabele of -eigenschap. Zie de beschrijving van [DITA-OT-omgevingsvariabelen](#id181NH0YN0AX) eigenschap voor meer informatie. |
   | Toegewezen pad | \(*Optioneel*\) Geef het pad op in de opslagplaats voor inhoud waarvoor dit profiel van toepassing is. U kunt meerdere locaties opgeven. |
   | **DITA-OT-eigenschappen** |
   | Tijdslimiet DITA-OT | \(*Optioneel*\) Geef de tijd op \(in seconden\) waarop AEM hulplijnen wachten op een reactie van de DITA-OT-plug-in. Als er geen reactie is ontvangen binnen de opgegeven tijd, wordt de publicatietaak beëindigd door AEM hulplijnen en wordt de taak gemarkeerd als mislukt. Ook, worden de mislukkingslogboeken ter beschikking gesteld in het dossier van het outputgeneratie. <br>Standaardwaarde: 300 seconden \(5 minuten\) |
   | DITA-OT PDF-argumenten | Geef de opdrachtregelargumenten op die door de aangepaste DITA-OT-plug-in worden verwerkt voor het genereren van de PDF-uitvoer. Geef voor alle aangepaste DITA-OT-profielen het volgende opdrachtregelargument op:`-lib plugins/org.dita.pdf2.fop/lib/` |
   | DITA-OT AEM argumenten | \(*Optioneel*\) Geef de aangepaste opdrachtregelargumenten op die door de aangepaste DITA-OT-plug-in worden verwerkt voor het genereren van de uitvoer van de AEM Site. |
   | DITA-OT bibliotheekpaden | \(*Optioneel*\) Geef de extra bibliotheekpaden van de DITA-OT-plug-in op. |
   | DITA-OT XML samenstellen | \(*Optioneel*\) Geef het pad op van het aangepaste Ant-constructiescript dat is gebundeld met de aangepaste DITA-OT-plug-in. Dit pad is relatief ten opzichte van de map DITA-OT op uw bestandssysteem. |
   | DITA-OT map Ant Script | \(Optioneel\) Geef het pad op van de map DITA-OT Ant-script. Dit pad is relatief ten opzichte van de map DITA-OT op uw bestandssysteem. |
   | DITA-OT-omgevingsvariabelen | *\(Optioneel\)* Omgevingsvariabelen opgeven die aan het DITA-OT-proces moeten worden doorgegeven. Standaard voegt AEM hulplijnen vier variabelen toe: `ANT_OPTS`, `ANT_HOME`, `PATH`, en `CLASSPATH`. <br> U kunt alle bestaande systeemomgevingsvariabelen of -eigenschappen opnieuw gebruiken om nieuwe omgevingsvariabelen samen te stellen. Als u bijvoorbeeld `JAVA_HOME` systeemvariabele gedefinieerd in uw systeem en u wilt een nieuwe omgevingsvariabele definiëren met de naam `JAVA_BIN` dat is gemaakt met `JAVA_HOME`. Vervolgens kunt u de definitie van `JAVA_BIN` als:<br> `JAVA_BIN= ${JAVA_HOME}/bin` <br> **Opmerking** U kunt ook eigenschappen van het Java-systeem gebruiken om omgevingsvariabelen te maken. Als AEM beginscript bijvoorbeeld een Java-systeemeigenschap definieert `java.io.tmpdir` aan een tijdelijke folder, kunt u dit bezit gebruiken om nieuwe variabele als te bepalen: `${java.io.tmpdir}/fmdita/dita_ot`. <br> **Belangrijk** Als u een bestaande systeemvariabele of -eigenschap opnieuw wilt gebruiken, moet deze binnen `${}`. |
   | DITA-OT-uitvoer overschrijven | *\(Optioneel\)* Als deze optie is geselecteerd, kunt u het DITA-OT-pakket opgeven dat beschikbaar is op uw lokale systeem om uitvoer te genereren met behulp van DITA-OT. Deze configuratie wordt geplaatst bij activering van ConfigManager. <br> Als u het pad wilt opgeven van een DITA-OT-pakket dat is opgeslagen op AEM server, schakelt u deze optie uit. |
   | AEM DITA-OT ZIP-pad/lokaal DITA-OT-mappad | Afhankelijk van uw selectie in Overschrijven DITA-OT Output, specificeer de volledige weg waar het douane DITA-OT.zip- dossier wordt opgeslagen. Dit zou het pad in uw AEM opslagplaats of lokaal systeem kunnen zijn. |
   | DITA-OT plug-inpad | Pad van de aangepaste insteekmodule. Deze plug-in wordt automatisch geïntegreerd met het hoofdpakket DITA-OT. |
   | Catalogi integreren | \(*Optioneel*\) Pad van de aangepaste DTD- en XSD catalog.xml-bestanden in de AEM-opslagplaats. Dit moet alleen worden opgegeven wanneer de catalogi ontbreken in het DITA-OT-pakket. Deze catalogi worden automatisch als een plug-in geïntegreerd met de hoofdmap DITA-OT. |
   | Catalogus systeem-id toevoegen | \(*Optioneel*\) Selecteer deze optie alleen als er openbare-id-items ontbreken in de catalogus of als de DITA-bestanden alleen de systeem-id&#39;s gebruiken die relatief zijn ten opzichte van het serverpad vanwaar ze worden geüpload. |
   | DITA-OT tijdelijk pad | *\(Optioneel\)* Geef een tijdelijke locatie op waar DITA-bestanden worden gekopieerd voor verwerking. Voordat DITA-OT bestanden verwerkt, worden ze naar deze tijdelijke locatie gekopieerd. Standaard is de locatie voor tijdelijke opslag: <br> **Opmerking** U kunt dit pad definiëren met een bestaande systeemvariabele of -eigenschap. Zie de beschrijving van [DITA-OT-omgevingsvariabelen](#id181NH0YN0AX) eigenschap voor meer informatie. |

   >[!NOTE]
   >
   >  Het installatieprogramma voor AEM hulplijnen maakt twee omgevingsvariabelen waarmee u het pad van de aangepaste DITA-OT-plug-inbestanden kunt opgeven. Deze omgevingsvariabelen zijn: DITAOT\_DIR, die het pad van de map DITA-OT op het bestandssysteem bevat; en DITAMAP\_DIR, die het pad bevat waar de DITA-kaartinhoud wordt geëxtraheerd op het bestandssysteem.

1. Klikken **Gereed** om het profiel op te slaan.


>[!NOTE]
>
> U kunt het aangepaste DITA-profiel exporteren als een pakket en uploaden naar de andere instanties van de AEM Guides om tijd te besparen. Zie voor meer informatie [Aanhangsel](appendix.md).

## DITA-specialisatie integreren {#id211MB0E00XA}

De specialisatie DITA is het proces om nieuwe structuren te creëren DITA door nieuwe elementen toe te voegen of bestaande elementen te verwijderen. Om een nieuw element te creëren DITA, kunt u een bestaand element DITA als basis nemen en het wijzigen volgens uw auteursvereisten. In wezen, staat de specialisatie DITA u toe om aangepaste informatiemodellen tot stand te brengen die aan uw bedrijfsvereisten voldoen terwijl het behouden van de voordelen van de bestaande architectuur DITA.

Met de functie Profiel kunt u aangepaste DITA-specialisatie-instellingen opslaan. Deze instellingen kunnen vervolgens worden gebruikt bij het ontwerpen en publiceren van aangepaste DITA-inhoud. AEM de Gidsen staat u toe om Openbare identiteitskaart en identiteitskaart van het Systeem in uw douane DTDs/XSDs te gebruiken.

>[!NOTE]
>
> AEM de Redacteur van het Web van Gidsen heeft geen steun voor XSDs.

Voer de volgende stappen uit om een nieuw profiel te creëren en het te vormen om gespecialiseerde DTDs en XSDs AEM Gidsen te gebruiken:

1. Maak op uw lokale computer een specialisatiemap met de gespecialiseerde DTD&#39;s en XSD&#39;s.

1. Geef de DTD-details op in het dialoogvenster `catalog.xml` bestand dat ook in de specialisatiemap moet worden opgenomen.

   >[!NOTE]
   >
   > In het geval van DITA 1.3, de standaardplaats voor DTD `catalog.xml` bestand in de AEM opslagplaats is: `/libs/fmdita/dita_resources/DITA-1.3/dtd/catalog.xml`.

1. Geef de XSD-details op in het dialoogvenster `catalog.xml` bestand dat ook in de specialisatiemap moet worden opgenomen.

   >[!NOTE]
   >
   > In het geval van DITA 1.3, is de standaardplaats voor XSD catalog.xml- dossier in de AEM bewaarplaats: `/libs/fmdita/dita_resources/DITA-1.3/xsd/catalog.xml`.

1. Upload de map naar de volgende locatie:

   `/libs/fmdita/dita_resources`

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.

1. Selecteren **Hulplijnen** in de lijst met gereedschappen.

1. Klik op de knop **DITA-profielen** tegel.

   >[!NOTE]
   >
   > De standaardprofielgegevens worden weergegeven op de pagina Profielen. Als u AEM Gidsen van versie 2.2 tot 2.5.1 of 2.6 hebt bevorderd, dan worden alle veranderingen die door configuratiemanager worden aangebracht automatisch gekozen en in het StandaardProfiel opgeslagen.

1. U kunt het standaardprofiel bewerken, een nieuw profiel maken of instellingen in het standaardprofiel dupliceren om een nieuw profiel te maken.

   >[!NOTE]
   >
   > U kunt het standaardprofiel niet verwijderen. Alle nieuwe profielen die u maakt, kunnen echter worden bewerkt en verwijderd.

1. In de **Schema** \> **Catalogus** instellingen, geeft u het pad op van de aangepaste DTD en XSD `catalog.xml` in uw AEM opslagplaats.

1. Selecteer **Catalogus systeem-id toevoegen** optie.

   >[!NOTE]
   >
   > Selecteer deze optie alleen als er items voor openbare id&#39;s ontbreken in de catalogus of als de DITA-bestanden alleen de systeem-id&#39;s gebruiken die relatief zijn ten opzichte van het lokale bestandspad van waaruit ze worden geüpload.

   Zie de eigenschappentabel in voor meer informatie over andere eigenschappen op de pagina Profielen [Stap 6](#id17A9F0D075Z) van de [Aangepaste DITA-OT-plug-ins gebruiken](#id181NH1020L7) sectie.

1. Klikken **Gereed** om het profiel op te slaan.


>[!NOTE]
>
> U kunt het aangepaste DITA-profiel exporteren als een pakket en uploaden naar de andere instanties van de AEM Guides om tijd te besparen. Zie voor meer informatie [Bijlage.md](appendix.md).

