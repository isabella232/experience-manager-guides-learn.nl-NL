---
title: Werken met basislijn
description: Leer hoe u met de basislijn werkt
exl-id: dcafab53-c388-48c3-9455-e4251cdda17d
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '1917'
ht-degree: 0%

---

# Werken met basislijn {#id1825FI0J0PF}

Met de functie Basislijn kunt u een versie van uw onderwerpen en elementen maken die u vervolgens kunt gebruiken voor publiceren of omzetten. Als uw DITA-kaart bijvoorbeeld `topicA` en `imageA`kunt u een basislijn maken om de derde versie van `topicA`, maar de vierde versie van `ImageA`. Als u eenmaal een basislijn hebt ingesteld, kunt u met één klik onderwerpen van verschillende versies publiceren of vertalen.

Het selecteren van een Basislijn is facultatief voor output vooraf instelt en een kaart DITA kan meer dan één Basislijn hebben. Elke uitvoervoorinstelling in een DITA-kaart kan echter maar aan één basislijn worden gekoppeld. Als er geen basislijn is opgegeven op het moment van publicatie, wordt de uitvoer gepubliceerd met de meest recente versie van de inhoud.

Op dezelfde manier is het optioneel om een basislijn te selecteren voor het vertalen van inhoud. Als u inhoud echter wilt vertalen met een basislijn, wordt de inhoud van de basislijn samen met de vertaalde kopieën opgeslagen. Vervolgens kunt u de vertaalde basislijn gebruiken om verdere bewerkingen uit te voeren, zoals deze delen met externe uitgevers of archiveren. Voor meer informatie over het exporteren van een vertaalde basislijn raadpleegt u [Vertaalde basislijn exporteren](#id196SE600GHS).

>[!TIP]
>
> Zie de *Basislijn* in de handleiding voor aanbevolen procedures voor het werken met basislijnen.

Uw beheerder kan het lusje van de Basislijn op het kaartdashboard vormen. Zie voor meer informatie *Het tabblad Basislijn van het DITA-kaartdashboard configureren* in de installatie- en configuratiehandleiding.

U kunt de functie Basislijn openen door de volgende stappen uit te voeren:

1. Navigeer in de interface Elementen naar het DITA-kaartbestand en klik erop.
1. Ga naar de **Basislijnen** tab.

Op het tabblad Basislijnen kunt u de volgende handelingen uitvoeren:

- [Een basislijn maken](#id195FI0I0MUQ)
- [Inhoud van een basislijn weergeven](#id195FI0I0TLN)
- [Basislijnen bewerken, dupliceren of verwijderen](#id195FI0I0YJL)
- [Labels toevoegen aan een basislijn](#id184KD0T305Z)

## Een basislijn maken {#id195FI0I0MUQ}

U kunt een Basislijn met een specifieke versie van de onderwerpen en van verwijzingen voorzien inhoud tot stand brengen beschikbaar op een specifieke datum en een tijd, of met een etiket dat voor een versie van onderwerpen wordt bepaald. U kunt de versies van geselecteerde onderwerpen individueel specificeren in een Basislijn zodat elke keer u de Basislijn in publiceert of vertaalwerkschema toepast, de geselecteerde onderwerpen en hun overeenkomstige versies inbegrepen voor outputgeneratie of vertaling zijn.

Voer de volgende stappen uit om een basislijn te maken:

1. Klik op de pagina Basislijnen op **Maken**.
1. Voer een naam in voor de basislijn in **Naam basislijn**.
1. In **Versie instellen op** selecteert u een van de volgende opties:

   - **Label**: Selecteer deze optie als u de onderwerpen wilt selecteren op basis van het label dat op de onderwerpen is toegepast. Voer een label in om de lijst te filteren op basis van de ingevoerde tekenreeks. In de uitgefilterde lijst kunt u een label kiezen om onderwerpen en andere elementen met het opgegeven label te selecteren.
   Wanneer u **Label** Bovendien krijgt u een extra optie om de nieuwste versie van onderwerpen te gebruiken waarop het opgegeven label niet is toegepast. Als u deze optie niet selecteert en er een onderwerp- of mediabestand is dat niet het opgegeven label heeft, mislukt het basislijnontwerpproces. Voor meer informatie over het toevoegen van labels raadpleegt u [Labels gebruiken](web-editor-use-label.md#).

   - **Versie ingeschakeld** &lt;*tijdstempel*\>: Kies de versie van de onderwerpen op de opgegeven datum en tijd. De tijd die u hier opgeeft, komt overeen met de tijdzone van uw AEM server. Als uw server bij een verschillende timezone is, dan zullen de onderwerpen volgens timezone van uw server en niet uw lokale timezone worden opgepikt.

   Nadat u een label of versie hebt geselecteerd als op datum, worden alle onderwerpen waarnaar wordt verwezen en mediabestanden in de kaart dienovereenkomstig geselecteerd. Deze selectie van onderwerpen wordt niet getoond op het gebruikersinterface, maar het wordt bewaard in het achterste eind.

1. Als u een verschillende versie voor één of meerdere onderwerpen wilt gebruiken, dan kunt u dit doen door die onderwerpen manueel te selecteren. Klikken **Onderwerp zoeken** selecteert u het onderwerp waarvoor u een andere versie wilt gebruiken. Van Uitgezocht een drop-down lijst van de Versie voor het geselecteerde onderwerp, selecteer een versie van het onderwerp dat u in de basislijn wilt gebruiken en klik **OK**.

   ![](images/baseline-select-version-drop-down.png){width="800" align="left"}

   De informatie over het onderwerp en het is geselecteerde versie wordt opgeslagen in het achterste deel. U kunt deze stap herhalen om de geselecteerde versie voor veelvoudige onderwerpen te veranderen.

1. Klik op de knop **Bladeren door alle onderwerpen** koppeling om alle onderwerpen en mediabestanden te laden die van de DITA-kaart worden verwezen. De UUID van onderwerpen en mediabestanden wordt ook weergegeven onder de titel van het onderwerp of de bestandsnaam \(media\).

   >[!NOTE]
   >
   > Als u een zeer grote reeks dossiers in uw kaart DITA, met genestelde kaarten en onderwerpen hebt, dan zou het klikken doorbladeren Alle Onderwerpen wat tijd kunnen vergen om alle dossiers te laden.

   De inhoud van de kaart wordt in de drie secties weergegeven: het kaartbestand, de inhoud \(onderwerpverwijzingen\) en de inhoud \(geneste onderwerpen, kaarten en andere elementen\) waarnaar wordt verwezen. Zodra u alle referenced inhoud beschikbaar hebt, kunt u de versie van het onderwerp individueel selecteren die u in uw basislijn wilt gebruiken.

   De **Versie** De drop-down lijst toont de beschikbare versies van de onderwerpen of de referenced inhoud. Voor de inhoud waarnaar wordt verwezen, kunt u een versie automatisch kiezen.

   Als u **Automatisch kiezen** voor de inhoud waarnaar wordt verwezen, kiest het systeem automatisch de versie van de inhoud waarnaar wordt verwezen die overeenkomt met de versie van de inhoud waarnaar wordt verwezen. Bijvoorbeeld, laten wij zeggen een onderwerp A een verwijzing naar beeld B heeft. Toen versie 1.5 van onderwerp A werd gecreeerd, was de versie van beeld B 1.2 in de bewaarplaats. Nu, wanneer een basislijn met versie 1.5 van onderwerp A met beeld B wordt gecreeerd die aan wordt geplaatst **Automatisch kiezen** kiest het systeem automatisch versie 1.2 van afbeelding B.

   Als u met de labels een basislijn maakt, **Automatisch kiezen** wordt toegepast op de versie van alle inhoud waarnaar wordt verwezen.

   Als de inhoud of elementen waarnaar wordt verwezen \(onderwerp, submappen, afbeeldingen of video&#39;s\) niet zijn omgezet in een versie \(zoals nieuw geüploade inhoud\), wordt bij het maken van een basislijn een versie voor dergelijke bestanden gemaakt. Als uw bestanden echter een versienummer hebben gekregen, wordt er geen incrementele versie voor deze bestanden gemaakt. Dit gedrag wordt bepaald door de instelling voor het automatisch maken van versies, die standaard is ingeschakeld. Dit is ook vereist voor het vertalen van inhoud waarbij in het vertaalproces wordt verwacht dat alle bestanden een versie hebben.

   >[!NOTE]
   >
   > Als u voor een bepaalde bron een andere versie wilt opgeven, kunt u dit doen door de gewenste versie te kiezen in het menu **Versie** vervolgkeuzelijst.

1. Klikken **Opslaan**.

## Inhoud van een basislijn weergeven {#id195FI0I0TLN}

U kunt de inhoud van een bestaande basislijn bekijken door op het tabblad Basislijnen te klikken en de gewenste basislijnversie in de lijst te selecteren. De basislijnpagina is verdeeld in drie delen - DITA kaartdossier, de inhoud van de kaart of onderwerpen, en de referenced inhoud. Als uw kaart submaps bevat, dan worden de onderwerpen van sub-kaart van verwijzingen voorzien ook getoond in de sectie van de Inhoud. De verschillende kolommen op de basislijnpagina worden hieronder beschreven:

- **Naam**: Hiermee geeft u de DITA-kaart of de titel van het onderwerp of de naam van het element weer, zoals de bestandsnaam van een afbeelding.

- **Type**: Hiermee geeft u het type of type element op de kaart weer, zoals DITA-kaart, DITA-onderwerp of afbeeldingsindeling.

- **Versie**: Hiermee geeft u de versie van het element weer dat beschikbaar is in de basislijn.

- **Datum en tijd van versie**: Hier worden de aanmaakdatum en -tijd van het element voor de geselecteerde versie weergegeven.

- **Laatste**: Hiermee geeft u aan of de meest recente versie van het element wordt gebruikt in de basislijn.

- **Bovenliggende kaart**: Als uw kaartdossier submaps bevat, dan bevat deze kolom de naam van de kaart waarin een onderwerp van verwijzingen wordt voorzien.

- **Label**: Hier worden de labels weergegeven die op de versie van het onderwerp zijn toegepast.

- **Verwezen door**: Deze kolom is alleen beschikbaar voor de inhoud waarnaar wordt verwezen. Het wijst op het ouderonderwerp van de referenced activa. Als een activa door veelvoudige onderwerpen wordt bedoeld, dan worden de onderwerpen gescheiden door komas.

## Basislijnen bewerken, dupliceren of verwijderen {#id195FI0I0YJL}

**Basislijnen bewerken**

Voer de volgende stappen uit om een bestaande basislijn te bewerken:

1. Selecteer de basislijn en klik op **Bewerken**.
1. Breng de vereiste wijzigingen aan in de basislijn. U kunt de naam en versie van het onderwerp of inhoud waarnaar wordt verwezen, wijzigen.
1. Klikken **Opslaan**.

**Basislijnen dupliceren**

Selecteer de basislijn en klik op **Dupliceren** om een kopie van een bestaande basislijn te maken. Geef een andere naam voor de basislijn op en kies het versienummer voor de onderwerpen en de inhoud waarnaar wordt verwezen en klik op **Opslaan**.

**Basislijnen verwijderen**

Selecteer de versie Basislijnen en klik op **Verwijderen** om een basislijn te verwijderen.

## Labels toevoegen aan een basislijn {#id184KD0T305Z}

Het toevoegen van labels aan elk onderwerp kan tijdrovend zijn. AEM de Gidsen verstrekt een enig-klikmechanisme om etiketten aan veelvoudige onderwerpen en van verwijzingen voorzien inhoud in een kaart toe te voegen DITA.

Voer de volgende stappen uit om een etiket aan veelvoudige onderwerpen en referenced inhoud in een kaart toe te voegen DITA:

1. Selecteer op de pagina Basislijnen een basislijn met de onderwerpen en inhoud waarnaar wordt verwezen waarop u een label wilt toevoegen.

   >[!NOTE]
   >
   > Zorg ervoor dat uw basislijn niet de recentste versie van om het even welk onderwerp of activa heeft. Een label kan alleen worden toegevoegd aan een onderwerp of element met versiebeheer.

1. Klikken **Labels toevoegen**.

   ![](images/add-label-baseline-uuid.png){width="800" align="left"}

1. In de **Label toevoegen** een uniek label opgeven dat aan deze basislijn moet worden gekoppeld.

   Als uw beheerder vooraf bepaalde etiketten heeft gevormd, dan wordt u getoond die etiketten in een drop-down lijst. U moet een label in de lijst kiezen.

1. Als u het label wilt toepassen op onderwerpen waarnaar wordt verwezen vanuit de submappen, selecteert u **Label toepassen op onderliggende kaarten en afhankelijke personen** optie.

   - Klikken **Toevoegen**.
Het gespecificeerde etiket wordt toegevoegd aan de kaart DITA en de referenced onderwerpen en inhoud.

      ![](images/label-added-baseline-uuid.png){width="650" align="left"}


## Vertaalde basislijn exporteren {#id196SE600GHS}

U kunt Basislijn gebruiken voor het vertalen van inhoud. U kunt bijvoorbeeld een basislijn voor versie 1.1 maken die klaar is voor vertaling in het Frans. Op het tabblad Vertaling moet u de basislijn gebruiken om uw inhoud te filteren en vervolgens de basislijn voor versie 1.1 van uw inhoud selecteren. Door basislijn te gebruiken voor het vertalen van inhoud, kunt u de inhoud eenvoudiger beheren.

Nadat de inhoud is vertaald, kunt u de vertaalde basislijn exporteren voor archivering of deze delen met verschillende teams in uw organisatie. U moet rekening houden met de volgende punten voordat u een vertaalde basislijn exporteert:

- Het exporteren van een basislijn is alleen mogelijk nadat de inhoud in de basislijn is vertaald. Als u een basislijn probeert te exporteren waarvoor de vertaling niet is gestart of niet is voltooid, wordt er een fout weergegeven.
- U kunt de basislijn alleen overbrengen voor een versie die al is vertaald. Als u bijvoorbeeld een basislijn hebt gemaakt voor versie 1.1 van uw inhoud en dezelfde basislijn is omgezet, kunt u deze basislijn exporteren. Als u echter een basislijn hebt gemaakt voor versie 1.2, die niet is omgezet, kunt u deze basislijn niet exporteren.
- Als er al een basislijn is geëxporteerd, kunt u de bestaande basislijn overschrijven door de optie *Bestaande basislijn overschrijven* tijdens het exporteren.

Voer de volgende stappen uit om een vertaalde basislijn te exporteren:

1. Open de kaart DITA die de vertaalde Basislijn bevat.

1. In de **Vertaling** tabblad, vouwt u de **Basislijn** optie beschikbaar in de linkerspoorstaaf.

   ![](images/export-baseline.png){width="800" align="left"}

1. Selecteer **Basislijn gebruiken** en kiest u de basislijn die u wilt exporteren.

1. Klikken **Basislijn exporteren**.

   De exportstatus wordt weergegeven. Als het proces succesvol is, dan wordt u getoond een bericht die de taal noemen waarvoor de Basislijn wordt uitgevoerd. In het geval van een fout, wordt de oorzaak van mislukking getoond.

   Als u de basislijn probeert te exporteren die al is geëxporteerd, wordt ook het foutbericht voor het maken van de basislijn weergegeven.

1. \(Optioneel\) Selecteer **Bestaande basislijn overschrijven** en klik vervolgens op **Basislijn exporteren**.


**Bovenliggend onderwerp:**[ Uitvoergeneratie](generate-output.md)
