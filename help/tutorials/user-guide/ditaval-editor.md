---
title: DITAVAL-editor gebruiken
description: Leer hoe u DITAVAL-bestanden maakt en bewerkt met de DIVATAL Editor in AEM hulplijnen. Weet hoe de DITAVAL-editor DITAVAL-bestanden ondersteunt in auteur- en bronweergaven.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 0%

---

# DITAVAL-editor {#ditaval-editor}

DITAVAL-bestanden worden gebruikt om voorwaardelijke uitvoer te genereren. In één onderwerp, kunt u voorwaarden toevoegen gebruikend elementenattributen om inhoud te conditionaliseren. Vervolgens maakt u een DITAVAL-bestand waarin u de voorwaarden opgeeft die moeten worden opgepakt om inhoud te genereren en welke voorwaarde niet in de uiteindelijke uitvoer moet worden opgenomen.

Met AEM hulplijnen kunt u eenvoudig DITAVAL-bestanden maken en bewerken met de DITAVAL-editor. De DITAVAL-editor haalt de kenmerken \(of tags\) op die in uw systeem zijn gedefinieerd en u kunt deze gebruiken om DITAVAL-bestanden te maken of te bewerken. Ga voor meer informatie over het maken en beheren van tags in AEM naar [Tags beheren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/features/tags.html?lang=en) in AEM documentatie.

## DITAVAL-bestand maken

Voer de volgende stappen uit om een DITAVAL-bestand te maken:

1. Navigeer in de interface Middelen naar de locatie waar u het DITAVAL-bestand wilt maken.

1. Klikken **Maken** \> **DITA-onderwerp**.

1. Selecteer op de pagina Vervagen de sjabloon DITAVAL-bestand en klik op **Volgende**.

1. Geef op de pagina Eigenschappen de instelling **Titel** en **Naam** voor het DITAVAL-bestand.

   >[!NOTE]
   >
   > De naam wordt automatisch voorgesteld gebaseerd op de Titel van uw dossier. Als u de bestandsnaam handmatig wilt opgeven, moet u ervoor zorgen dat de naam geen spaties, apostrof of accolades bevat en eindigt met .ditaval.

1. Klikken **Maken**. Het bericht Gemaakt onderwerp wordt weergegeven.

   U kunt het DITAVAL-bestand openen om te bewerken in de DITAVAL-editor of het onderwerpbestand opslaan in de AEM-opslagplaats.


## DITAVAL-bestand bewerken

Voer de volgende stappen uit om een DITAVAL-bestand te bewerken:

1. Navigeer in de interface Elementen naar het DITAVAL-bestand dat u wilt bewerken.

1. Als u het bestand exclusief wilt vergrendelen, selecteert u het bestand en klikt u op **Uitchecken**.

1. Selecteer het bestand en klik op **Bewerken** om het bestand te openen in AEM DITAVAL-editor voor hulplijnen.

   Met de DITAVAL-editor kunt u de volgende taken uitvoeren:

   A: Linkerdeelvenster in-/uitschakelen Schakelt de weergave van het linkerdeelvenster in. Als u het DITAVAL-bestand hebt geopend via de DITA-kaart, worden de kaart en de opslagplaats weergegeven in dit deelvenster. Zie voor meer informatie over het openen van een bestand via de DITA-kaart [Onderwerpen bewerken via de DITA-kaart](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

   B: Met Opslaan slaat u de wijzigingen op die u in het bestand hebt aangebracht. Alle wijzigingen worden opgeslagen in de huidige versie van het bestand.

   C: Voeg bezit toe voeg één enkel bezit in uw DITAVAL dossier toe.

   ![](images/ditaval-editor-props.png)

   De eerste vervolgkeuzelijst bevat de toegestane DITA-kenmerken die u kunt gebruiken in het DITAVAL-bestand. Er zijn vijf kenmerken die worden ondersteund - `audience`, `platform`, `product`, `props`, en `otherprops`.

   De tweede drop-down lijst toont de waarden die voor de geselecteerde attributen worden gevormd. Dan, toont de volgende drop-down lijst de acties die u op de geselecteerde attributen kunt vormen. De toegestane waarden in de vervolgkeuzelijst Handeling zijn - `include`, `exclude`, `passthrough`, en `flag`. Zie de definitie van [prop](http://docs.oasis-open.org/dita/dita/v1.3/errata01/os/complete/part3-all-inclusive/langRef/ditaval/ditaval-prop.html#ditaval-prop) element in OASIS DITA-documentatie

   D: Voeg alle eigenschappen toe Als u met één klik alle voorwaardelijke eigenschappen of kenmerken wilt toevoegen die in uw systeem zijn gedefinieerd, gebruikt u de functie Alle eigenschappen toevoegen.

   >[!NOTE]
   >
   > Als het DITAVAL-bestand al alle gedefinieerde voorwaardelijke eigenschappen bevat, kunt u geen eigenschappen meer toevoegen. Er verschijnt een foutbericht in dit scenario.

   ![](images/ditaval-all-props.png)

1. Als u klaar bent met het bewerken van het DITAVAL-bestand, klikt u op **Opslaan**.

   >[!NOTE]
   >
   > Als u het bestand sluit zonder op te slaan, gaan de wijzigingen verloren. Als u geen wijzigingen wilt doorvoeren in AEM opslagplaats, klikt u op **Sluiten** en klik vervolgens op **Sluiten zonder opslaan** in de **Niet-opgeslagen wijzigingen** in.


## Weergaven DITAVAL-editor

AEM DITAVAL-editor van hulplijnen ondersteunt het weergeven van DITAVAL-bestanden in twee verschillende modi of weergaven:

**Auteur**: Dit is een typisch voorbeeld van de WYSISYG-weergave van de DITAVAL-editor. U kunt eigenschappen toevoegen of verwijderen met behulp van de eenvoudige gebruikersinterface, die de eigenschappen, waarden en handelingen in de vervolgkeuzelijst weergeeft. In de weergave Auteur kunt u een afzonderlijke eigenschap invoegen en alle eigenschappen met één klik invoegen.

U kunt ook de versie van het DITAVAL-bestand vinden waaraan u momenteel werkt door de aanwijzer op de bestandsnaam te plaatsen.

**Bron**: In de bronweergave wordt de onderliggende XML weergegeven waaruit het DITAVAL-bestand bestaat. Naast het uitvoeren van regelmatige tekstbewerkingen in deze weergave, kan een auteur ook eigenschappen toevoegen of bewerken met de slimme catalogus.

Om de Slimme Catalogus aan te halen, plaats de curseur aan het eind van om het even welke bezitsdefinitie en ga &quot;&lt;&quot; in. De redacteur zal een lijst van alle geldige elementen van XML tonen die u bij die plaats kunt opnemen.

![](images/ditaval-source-view.png)
