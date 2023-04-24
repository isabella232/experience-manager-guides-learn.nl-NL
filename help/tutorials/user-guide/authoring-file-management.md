---
title: Bestanden en mappen beheren
description: Leer hoe u bestanden en mappen kunt beheren
source-git-commit: cc0fbca257d82cc82db5b5da8d263309fd71de55
workflow-type: tm+mt
source-wordcount: '2502'
ht-degree: 0%

---


# Bestanden en mappen beheren {#id2116G0L08XA}

In deze sectie wordt uitgelegd hoe AEM hulplijnen de basisbestandsbewerkingen, zoals kopiëren, plakken, slepen en neerzetten en bestanden verwijderen, afhandelen. De volgende scenario&#39;s zijn mogelijk:

## Bestanden kopiëren en plakken

**Als het bestand een leesbare bestandsnaam heeft**

- *Als het bestand met dezelfde naam niet bestaat in de doelmap*: Er wordt een nieuwe kopie van het bestand gemaakt en er wordt ook een UUID aan toegewezen. Hier is de bestandsnaam gelijk aan de oorspronkelijke bestandsnaam.
- *Als het bestand met dezelfde naam al bestaat in de doelmap*: Er wordt een nieuwe kopie van het bestand gemaakt met het achtervoegsel \(zoals filename0.extension\). Er wordt ook een UUID toegewezen aan het nieuwe bestand.


**Als de bestandsnaam is gebaseerd op een UUID-patroon**

- *Als het bestand met dezelfde naam niet bestaat in de doelmap*: Er wordt een nieuwe kopie van het bestand gemaakt en er wordt ook een nieuwe UUID aan toegewezen op de nieuwe locatie. Hier is de bestandsnaam gelijk aan de UUID.
- *Als het bestand met dezelfde naam al bestaat in de doelmap*: Er wordt een nieuwe kopie van het bestand gemaakt en er wordt ook een nieuwe UUID aan toegewezen. De bestandsnaam is gelijk aan de UUID.


## Mappen kopiëren en plakken

**Map kopiëren en plakken op dezelfde locatie**

- *De map bevat bestanden met leesbare bestandsnamen*: Er wordt een nieuwe kopie van de map gemaakt met het achtervoegsel \(zoals mapnaam0\). Er wordt ook een nieuwe UUID toegewezen aan de bestanden in de map. De bestandsnamen blijven echter ongewijzigd.

- *De map bevat bestanden met bestandsnamen die zijn gebaseerd op een UUID-patroon*: Er wordt een nieuwe kopie van de map gemaakt met het achtervoegsel \(zoals mapnaam0\). Er wordt ook een nieuwe UUID toegewezen aan alle bestanden in de nieuwe map. De bestandsnamen worden ook gewijzigd; de bestandsnamen zijn gelijk aan de nieuwe UUID.


**Map kopiëren en plakken op een andere locatie**

- *De map bevat bestanden met leesbare bestandsnamen*: Er wordt een nieuwe kopie van de map gemaakt en er wordt ook een nieuwe UUID toegewezen aan alle bestanden in de map op de nieuwe locatie. Hier ziet u geen wijziging in de map- of bestandsnamen.

- *De map bevat bestanden met bestandsnamen die zijn gebaseerd op een UUID-patroon*: Er wordt een nieuwe kopie van de map gemaakt met dezelfde naam als de oorspronkelijke map. Er wordt ook een nieuwe UUID toegewezen aan alle bestanden in de nieuwe map. De bestandsnamen worden ook gewijzigd; de bestandsnamen zijn gelijk aan de nieuwe UUID.


## Bestanden slepen en neerzetten

**Slepen en neerzetten met leesbare bestandsnamen**

- *Slepen en neerzetten op dezelfde locatie*: U kunt de volgende opties kiezen: **Bestaand bestand overschrijven\(s\)**, **Beide bestanden behouden** en een optie om een versie van de bestaande werkkopie te maken.

   ![](images/uuid-human-readable-drag-drop-same-location.PNG){width="650" align="center"}

   Als u **Bestaand bestand overschrijven\(s\)** en vervangt het bestand dat wordt geüpload de huidige werkversie van het bestaande bestand op de oorspronkelijke locatie. De UUID wordt niet gemaakt of gewijzigd.

   Als u **Beide bestanden behouden** wordt een nieuwe kopie van het bestand gemaakt met het achtervoegsel \(zoals filename0.extension\). Er wordt ook een nieuwe UUID toegewezen aan het zojuist gekopieerde bestand.

   Als u met de optie Bestaande bestanden overschrijven een versie wilt maken van de bestaande werkkopie, wordt ook een nieuwe versie van de werkkopie van het document gemaakt.

   >[!NOTE]
   >
   > **Nieuwe versie maken voor geüpload bestand** moet worden ingeschakeld door uw beheerder. Als deze functie is ingeschakeld, wordt een nieuwe versie voor het geüploade bestand gemaakt. Als deze optie is uitgeschakeld, wordt er geen versie van het geüploade bestand gemaakt. Zie voor meer informatie *Nieuwe versie maken voor geüpload bestand* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.

   Als een bestand al is uitgecheckt voor bewerkingen door een andere gebruiker en u probeert het bestaande bestand te uploaden en te overschrijven, mislukt het en wordt een fout weergegeven.

   >[!NOTE]
   >
   >De **Uitgecheckt bestand tijdens uploaden overschrijven** moet door de beheerder worden uitgeschakeld. Als deze functie is ingeschakeld, kunt u uitgecheckte bestanden overschrijven. Als de functie niet is ingeschakeld, kan een uitgecheckt bestand niet worden overschreven. Zie voor meer informatie *Uitgecheckt bestand tijdens uploaden overschrijven* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.


- *Bestanden slepen en neerzetten op verschillende locaties*: Er wordt een nieuwe kopie van het bestand gemaakt en er wordt ook een nieuwe UUID aan toegewezen op de nieuwe locatie. Hier is de bestandsnaam gelijk aan de oorspronkelijke bestandsnaam.


**Slepen en neerzetten met bestandsnamen op basis van een UUID-patroon**

*Bestand naar dezelfde locatie slepen en neerzetten*: U kunt de volgende opties kiezen: **Bestaand bestand overschrijven\(s\)** samen met de optie om een versie van de bestaande werkkopie te maken.

![](images/uuid-drag-drop-same-location.PNG){width="650" align="center"}

Als het bestand wordt overschreven, is er geen wijziging in de bestandsnaam of de bijbehorende UUID.

Als u **Versie maken voor de bestaande werkkopie** wordt een nieuwe versie van de werkkopie van het document gemaakt; het nieuwe bestand wordt geüpload, er wordt ook een nieuwe versie van het bestand gemaakt en het wordt gemaakt als werkkopie van het document.

**Nieuwe versie maken voor geüpload bestand** moet worden ingeschakeld door uw beheerder. Als deze functie is ingeschakeld, wordt een nieuwe versie voor het geüploade bestand gemaakt. Als deze optie is uitgeschakeld, wordt er geen versie van het geüploade bestand gemaakt. Zie voor meer informatie *Nieuwe versie maken voor geüpload bestand* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.


*Bestanden slepen en neerzetten op een andere locatie*: U kunt de volgende opties kiezen: **Bestaand bestand overschrijven\(s\)**, **Bestand(en) verplaatsen naar nieuwe locatie** en een optie om een versie van de bestaande werkkopie te maken.

![](images/uuid-drag-drop-different-location.PNG){width="650" align="center"}

Als u **Bestaand bestand overschrijven\(s\)** en vervangt het bestand dat wordt geüpload het bestaande bestand op de oorspronkelijke locatie. De UUID wordt niet gemaakt of gewijzigd.

Als u **Bestand(en) verplaatsen naar nieuwe locatie** wordt het bestaande bestand naar de huidige locatie verplaatst en wordt vervolgens overschreven met het bestand dat wordt geüpload. Als u een bestand naar de nieuwe locatie verplaatst, worden bestaande verwijzingen van of naar het bestand niet verbroken.

Als u met het vervangen of verplaatsen van de bestanden de optie kiest om een versie te maken van de bestaande kopie, wordt een nieuwe versie gemaakt van de werkkopie van het document. het nieuwe bestand wordt vervangen op de bestaande locatie of naar de nieuwe locatie verplaatst.


## Bestanden bulksgewijs verplaatsen

AEM hulplijnen worden geleverd met het gereedschap Bulk verplaatsen, waarmee een beheerder een map met een groot aantal bestanden kan verplaatsen van de ene naar de andere locatie. Met dit gereedschap kunt u bestanden in een of meer mappen gemakkelijk naar een andere map in uw AEM opslagplaats verplaatsen. Een van de belangrijkste functies van dit gereedschap is dat het niet alleen een groot aantal bestanden verplaatst, maar ook de verwijzingen naar en van de bestanden die worden verplaatst, behoudt. U kunt het aantal bestanden dat u in batches kunt verplaatsen, bijstellen zonder de ontwerp- en publicatietaken te hinderen.

>[!NOTE]
>
> Het gereedschap Bulk verplaatsen werkt alleen op mapniveau. Als u individuele onderwerp of kaartdossiers wilt bewegen, dan gebruik het regelmatige verplaatsingshulpmiddel van AEM Activa UI.

Hier volgen enkele functies van het gereedschap Bulkbeweging:

- U kunt het aantal bestanden dat in elke batch moet worden verwerkt, bijstellen. Dit zou u kunnen vereisen om een paar tests in werking te stellen alvorens tot een optimaal aantal te komen dat uw systeem kan gemakkelijk behandelen.
- Auteurs- en publicatieservices worden probleemloos uitgevoerd zonder onderbreking van de verplaatsingsbewerking.
- Zorg dat u volledige controle hebt over het tijdsinterval tussen opeenvolgende \(uitvoeren van\) batchprocessen. Dit tijdinterval zorgt ervoor dat de naverwerkingsbewerking wordt voltooid voordat de volgende batch bestanden wordt gestart.

- Automatisch omgaan met mappen met dezelfde naam. Met deze functie zorgt u ervoor dat mappen die onder dezelfde naam worden verplaatst, niet worden overschreven.

- Automatische verwerking van verwijzingen naar en van de bestanden die worden verplaatst.


U moet rekening houden met de volgende punten voordat u het batchproces uitvoert:

- Als u van plan bent onderwerpen te verplaatsen die momenteel onder overzicht zijn, moet u het overzichtsproces over al dergelijke onderwerpen sluiten alvorens hen te bewegen. Als u de revisietaak niet sluit, wordt de revisie onderbroken.
- U moet op elk gewenst moment slechts één enkele verplaatsingsbewerking voor grote hoeveelheden uitvoeren. Dit verzekert juiste behandeling van verwijzingen naar en van de onderwerpen die worden bewogen.


Voer de volgende stappen uit om bestanden in bulk te verplaatsen:

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen.
1. Klik op de knop **Bulk verplaatsen** tegel.

   De pagina Bulk verplaatsen wordt weergegeven.

   ![](images/bulk-move-tool_cs.PNG){width="550" align="center"}

1. Geef de volgende gegevens op de pagina Bulk verplaatsen:

   - **Achtervoegsel toevoegen aan dubbele bestanden**: Als u mappen met dezelfde naam verplaatst, moet u deze optie selecteren. In de bovenstaande schermafbeelding kunt u bijvoorbeeld de opdracht **Bronpad** bevat de naam van de mappen die u wilt verplaatsen. De omslag genoemd onderwerp bestaat bij twee verschillende plaatsen — test-A en test-B. Wanneer u deze optie selecteert, worden de mappen verplaatst. De eerste verplaatste omslag zal onderwerp worden genoemd terwijl de tweede omslag topic0 zal worden genoemd. Met de verplaatsingsbewerking voegt u een achtervoegsel in de opeenvolgende reeks \(0, 1, 2, enzovoort\) toe aan de mappen met dezelfde naam.

      Als u mappen met dezelfde naam verplaatst zonder deze optie te selecteren, wordt de bewerking afgebroken met een bericht.

   - **Bronpad\(s\)**: Geef de locatie op van de mappen die u wilt verplaatsen. Meestal moet u de bronlocatie uit de adresbalk van de browser kopiëren en plakken. U kunt meerdere maplocaties opgeven door op de knop **Toevoegen** knop.

   - **Doelpad**: Geef de locatie op waar u de bronmappen wilt verplaatsen.

1. Klikken **Bulk verplaatsen**.

   Het systeem begint dossiers van de bron aan bestemmingsplaats te bewegen. Zodra het proces is voltooid, wordt onder aan de pagina een overzicht van het verplaatsingsproces weergegeven.

   ![](images/bulk-move-summary.PNG){width="650" align="center"}


## DITA-inhoud zoeken

AEM herkent standaard geen DITA-inhoud, waardoor het geen mechanisme biedt om DITA-inhoud in de opslagplaats te doorzoeken. AEM Gidsen voegt een laag bovenop AEM toe, die AEM toelaat om inhoud te begrijpen en te verwerken DITA. Met de functie DITA-inhoud zoeken in AEM hulplijnen kunt u zoeken naar DITA-inhoud in AEM opslagplaats.

>[!NOTE]
>
>Uw systeembeheerder kan **DITA-element** en vervolgens kunt u de functie gebruiken vanuit de gebruikersinterface van AEM Assets. Zie voor meer informatie *DITA Element-zoekcomponent toevoegen aan interface Middelen* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.

Met de zoekfunctie kunt u:

- Zoeken naar DITA-inhoud op basis van een elementwaarde; bijvoorbeeld: `author`= xml
- Zoeken naar DITA-inhoud op basis van een kenmerkwaarde. bijvoorbeeld: `@platform`= vensters
- Gebruik een combinatie van DITA-element en kenmerkwaarde; bijvoorbeeld: `author`= xml `AND` `@platform`= vensters

Voer de volgende stappen uit om te zoeken naar DITA-inhoud in AEM opslagplaats:

1. Open de interface Elementen.

1. Selecteer in het linkerspoor **Filters**.

   ![](images/left-rail-filter.png){width="450" align="center"}

   De filteropties voor inhoud worden weergegeven in de linkerrails. U zult ook het filtreren optie-Element DITA vinden, dat wordt gebruikt om inhoud te filtreren DITA.

   ![](images/dita-element-search.png){width="450" align="center"}

1. *\(Optioneel\)* In de **Zoekdirectory selecteren** , bladert u naar de locatie waarin u wilt zoeken.

1. In de **DITA-element** filter, levert u de **Elementnaam**, **Kenmerk** en een waarde waarnaar u wilt zoeken. Bijvoorbeeld om naar documenten te zoeken die `author` element waarvan `@type` creator u moet de informatie verstrekken zoals aangetoond in het volgende screenshot:

   ![](images/search-params.png){width="650" align="center"}

   De zoekcriteria die zijn ingevoerd in het **DITA-element** wordt boven aan de zoekbalk weergegeven. De bestanden die voldoen aan de zoekcriteria worden weergegeven in het dialoogvenster **Zoekresultaten** gebied.

   Houd rekening met de volgende punten bij het opgeven van de zoekcriteria:

   - Als u naar een exacte woordgroep wilt zoeken, voert u de woordgroep in het veld Waarde tussen aanhalingstekens in `"`woordzoekopdracht`"`.
   - U kunt maximaal drie zoekcriteria voor DITA-elementen toevoegen.
   - Als u veelvoudige onderzoekscriteria specificeert, dan zullen alle hen worden gecombineerd gebruikend de logica AND.
   - U kunt geen jokerteken gebruiken in uw zoekcriteria. Als u bijvoorbeeld wilt zoeken naar platform \(kenmerk\) met de waarde Windows, kunt u geen \*formulier of Windo?s opgeven.

**Het statusfilter voor uitchecken in de zoekactie**

Naast het filter DITA-element kunt u met AEM hulplijnen ook naar inhoud zoeken op basis van hun uitcheckstatus. Dit is handig wanneer u snel bestanden wilt uitfilteren die momenteel door u zijn uitgecheckt en u deze weer wilt inchecken.

Voer de volgende stappen uit om naar bestanden te zoeken op basis van hun uitcheckstatus:

1. Open de interface Elementen.

1. Klikken **Filter** in het linkerspoor.
1. Voer het trefwoord in de zoekbalk in.
1. Pas de vereiste filters toe vanaf de linkerspoorstaaf.

   U kunt bijvoorbeeld **Afhandelingsstatus** filter om de uitgecheckte of ingecheckte onderwerpen te tonen. U kunt deze lijst verder verfijnen door de gebruiker of de groep te kiezen in de lijst Uitgecheckt door.

   Uw zoekresultaat wordt weergegeven.


## Bestanden verwijderen

Het verwijderen van bestanden uit AEM opslagplaats is een beperkte functie die wordt beheerd door uw systeembeheerder. Op basis van de configuraties kan het verwijderen van bestanden worden beperkt als ze:

- Uitgecheckt
- Inkomende of uitgaande referenties hebben

U kunt bestanden alleen verwijderen als u tot een specifieke gebruikersgroep behoort die gemachtigd is bestanden te verwijderen.

>[!NOTE]
>
> Voor meer informatie over de configuraties in bestandsbeheer raadpleegt u *Verwijderen van uitgecheckte bestanden voorkomen* en *Verwijderen van bestanden waarnaar wordt verwezen voorkomen* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.

Als uw beheerder alle gebruiker toestemming heeft gegeven om het bestand te verwijderen, wordt het volgende bericht weergegeven wanneer u bestanden met verwijzingen verwijdert:

![](images/allow_unsafe_delete-force-delete.PNG){width="650" align="center"}

In dit scenario kunt u bestanden met kracht verwijderen zonder de inkomende of uitgaande verwijzingen uit de bestanden te verwijderen.

Als de verwijdermachtigingen aan een specifieke gebruikersgroep worden gegeven, wordt ook het bovenstaande bericht weergegeven voor gebruikers die tot die groep behoren. Voor andere gebruikers wordt echter het volgende bericht weergegeven:

![](images/allow_unsafe_delete_for_delete_assets_group.PNG){width="650" align="center"}

In dit scenario, zullen de gebruikers niet worden toegestaan om dossiers te schrappen tot alle inkomende en uitgaande verwijzingen zijn verwijderd.

## Werken met mediabestanden

Mediabestanden zoals afbeeldingen en video&#39;s maken integraal deel uit van uw inhoud. Tijdens het uploaden en beheren van uw inhoud, werkt u mogelijk ook met mediabestanden.

Als het mediabestand wijzigingen heeft ondergaan, kunt u de bestanden in het dialoogvenster **Versiehistorie**.Om te weten te komen verandert in de verschillende versies van een media dossier:

1. Open het bestand in **UI Middelen**.
1. Selecteer het bestand waarvan u de versiegeschiedenis wilt weergeven.
1. Klik in het linkerspoor op **Versiehistorie** en selecteer een versie.
1. U kunt ook de miniaturen van de verschillende versies onder Versiegeschiedenis zien.

   ![](images/media-version-history-icon.png){width="800" align="center"}

1. Selecteer in de weergegeven versies de versie die u als basisversie wilt gebruiken en klik op **Voorvertoning versie**. De voorvertoning van de geselecteerde versie wordt weergegeven in het venster Versievoorvertoning.

   ![](images/media-version-preview.png){width="650" align="center"}


**Bovenliggend onderwerp:**[ Inhoud beheren](authoring.md)

