---
title: Basislijnen maken en beheren vanuit de webeditor
description: Leer hoe te om basislijnen van de Redacteur van het Web tot stand te brengen en te beheren
exl-id: 9e390489-16f5-4f9a-a821-5150a66c2ed4
source-git-commit: 3bca42f0954afc2362ab24f369e698113324dbc3
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 0%

---

# Basislijnen maken en beheren vanuit de webeditor {#id223MB0ZF043}

>[!TIP]
>
> Het wordt geadviseerd om deze eigenschap van de Basislijn van de Redacteur van het Web te gebruiken als u aan AEM Gidsen as a Cloud Service versie van Maart of later hebt bevorderd.

AEM Gidsen verstrekt de eigenschap van de Basislijn die binnen de Redacteur van het Web wordt geïntegreerd die de gebruikers toestaat om basislijnen tot stand te brengen en hen te gebruiken om onderwerpen van verschillende versies te publiceren of te vertalen.

## Een basislijn maken

U kunt een basislijn van de Redacteur van het Web tot stand brengen door de volgende stappen uit te voeren:

1. Open het DITA-kaartbestand in de Kaartweergave in het deelvenster Opslagplaats.
1. Klik op de knop **Beheren** tab. De **Basislijn** geeft de basislijnen van de DITA-kaart weer.

   ![](images/baseline-manage.png){width="800" align="left"}

1. Op de **Basislijn** klikt u op + pictogram rechtsboven. U kunt een basislijn met een specifieke versie van de onderwerpen en van verwijzingen voorzien inhoud tot stand brengen beschikbaar op een specifieke datum en een tijd, of met een etiket dat voor een versie van onderwerpen wordt bepaald.
1. Voer een naam in voor de basislijn in **Naam basislijn**.
1. In **Basislijnoptie** U kunt **Bestandsversie gebruiken** of **Labels gebruiken** optie:

   **Bestandsversie gebruiken**: U kunt een statische basislijn met een specifieke versie van de onderwerpen en referenced inhoud tot stand brengen beschikbaar op een specifieke datum en een tijd, of met een etiket dat voor een versie van onderwerpen wordt bepaald:

   - In **Stel de meest recente versie in op basis van** Selecteer een van de volgende opties:


      1. **Datum** &lt;time stamp=&quot;&quot;>: Kies de versie van de onderwerpen op de opgegeven datum en tijd.
      1. **Label**: Selecteer deze optie als u de onderwerpen wilt selecteren op basis van het label dat op de onderwerpen is toegepast. Als voor de onderwerpen labels zijn opgegeven, worden de labels vermeld in de vervolgkeuzelijst. U kunt een label in de lijst kiezen. U kunt ook een label toevoegen in het tekstvak.\
         Wanneer u **Label,** u kunt de directe en indirecte referenties kiezen.
      - Voor directe verwijzingen binnen de kaart DITA, krijgt u een optie om de recentste versie van onderwerpen te gebruiken die niet het gespecificeerde etiket hebben op hen wordt toegepast.

      >[!NOTE]
      >
      > Als u een label invoert dat niet bestaat, selecteert u de optie **Geen basislijn maken** Dan ontbreekt de basislijnverwezenlijking en geeft een foutenmelding dichtbij de basislijnnaam in het paneel van de Basislijn.

      - Voor indirecte verwijzingen binnen de kaart DITA, krijgt u een extra optie om de recentste versie van onderwerpen te gebruiken die niet het gespecificeerde etiket hebben op hen wordt toegepast. U kunt ook **Automatisch kiezen** voor de inhoud waarnaar wordt verwezen, en het systeem kiest automatisch de versie van de inhoud waarnaar wordt verwezen die overeenkomt met de versie van de inhoud waarnaar wordt verwezen.

   Nadat u een label of versie hebt geselecteerd als op datum, worden alle onderwerpen waarnaar wordt verwezen en mediabestanden in de kaart dienovereenkomstig geselecteerd. Deze selectie van onderwerpen wordt niet getoond op het gebruikersinterface, maar het wordt bewaard in het achterste eind.

   **Labels gebruiken**: Selecteer deze optie voor het maken van de basislijn om de onderwerpen te kiezen op basis van het label dat op deze onderwerpen is toegepast.

   Basislijnen op basis van labels worden dynamisch bijgewerkt. Als u een basislijn genereert, een basislijn downloadt of een vertaalproject maakt met een basislijn, worden de bestanden dynamisch gekozen op basis van de bijgewerkte labels. Bijvoorbeeld, als u versie 1.2 van een onderwerp met Versie 1.0 van het Etiket voor de basislijn en recentere bijgewerkte versie 1.5 met Versie 1.0 van het Etiket hebt gebruikt, zal de basislijn dynamisch worden bijgewerkt, en versie 1.5 zal worden gebruikt.

   ![](images/dynamic-baseline.png){width="550" align="left"}

   - **Labels selecteren**: Als voor de onderwerpen labels zijn opgegeven, worden de labels vermeld in het dialoogvenster **Labels selecteren** vervolgkeuzelijst. U kunt de label\(s\) in de lijst kiezen. De eerst geselecteerde labels krijgen een hogere prioriteit dan de latere labels.
1. **Indirecte verwijzingen**: Voor indirecte verwijzingen binnen de kaart DITA, krijgt u de volgende opties:

   - **Automatisch selecteren**: U kunt ervoor kiezen **Automatisch kiezen** voor de inhoud waarnaar wordt verwezen, en het systeem kiest automatisch de versie van de inhoud waarnaar wordt verwezen die overeenkomt met de versie van de inhoud waarnaar wordt verwezen.

   - **Geselecteerd label gebruiken**: U kunt een basislijn met het geselecteerde die etiket tot stand brengen voor een versie van onderwerpen wordt bepaald.
   - **De nieuwste versie of de werkkopie gebruiken**: Gebruik de recentste versie van onderwerpen die niet het gespecificeerde etiket hebben op hen wordt toegepast, of als geen versie is gecreeerd, dan gebruik het het werk exemplaar van de onderwerpen om de basislijn tot stand te brengen.
1. Klikken **Toepassen**.

De basislijn wordt gemaakt. De basislijnverwezenlijking gebeurt asynchroon, zodat kunt u aan andere dossiers in de Redacteur van het Web blijven werken. Zodra de basislijn wordt gecreeerd, wordt een pop-up bericht getoond bevestigend dat de basislijn is gecreeerd, en u ontvangt ook een Inbox- bericht voor het zelfde.

## Basislijnen beheren

U kunt uw bestaande basislijnen beheren met de verschillende functies op het basislijndashboard.

- U kunt zoeken naar een bestaande basislijn met het tekstvak in het deelvenster Basislijn. Gebruik de **Filter toepassen** om alle basislijnen weer te geven of de basislijnen weer te geven met de aanmaakstatus Voltooid, Bezig of Mislukt.
- Gebruik de **Vernieuwen** in het deelvenster Basislijn om opnieuw te controleren op alle basislijnen en een nieuwe lijst met basislijnen weer te geven voor de DITA-kaart die wordt geopend in de Kaartweergave.
- U kunt de inhoud van een bestaande basislijn weergeven of bewerken door te dubbelklikken op de basislijn in de lijst in het deelvenster Basislijn. In het basislijnbewerkingsvenster in het midden worden het DITA-kaartbestand, de inhoud of onderwerpen van de kaart en de inhoud waarnaar wordt verwezen, weergegeven.


![](images/baseline-options.png){width="550" align="left"}

U kunt ook de volgende bewerkingen op de basislijn uitvoeren vanuit het menu Opties:

- **Bewerken**, **Dupliceren,** of **Verwijderen** een bestaande basislijn.
- Bestaande labels toevoegen, verwijderen of wijzigen in het menu **Labels beheren** optie. Als uw beheerder vooraf bepaalde etiketten heeft gevormd, dan wordt u getoond die etiketten in Add drop-down lijst van het Etiket. Voor meer informatie over het toevoegen van labels raadpleegt u [Labels gebruiken](web-editor-use-label.md#).

   >[!NOTE]
   >
   > Het proces om etiketten toe te voegen of te verwijderen gebeurt asynchroon, zodat kunt u aan andere dossiers in de Redacteur van het Web blijven werken. Nadat het label is toegevoegd of verwijderd, wordt een pop-upbericht weergegeven met de bevestiging dat het label is toegevoegd of verwijderd. U ontvangt ook een melding in het Postvak IN.

- **Eigenschappen bewerken** van een bestaande basislijn die u hebt ingesteld tijdens het maken van de basislijn.
- De momentopname van een basislijn in een Csv- dossier met uitvoeren **Basislijn exporteren** optie.

**Basislijnfilters**

Het pictogram Filters in het dialoogvenster **Basislijnfilters** kunt u filters toepassen op de basislijn die is geopend in het basislijnbewerkingsvenster:

![](images/baseline-filter.png){width="350" align="left"}

- Filter de bestanden op bestandsnamen of op de bestandslocatie.
- Filter de bestanden op basis van de waarden voor verschillende kolommen, zoals Bestandstype, Referentietype, enzovoort.
- Kies de kolommen die u wilt weergeven in het basislijnbewerkingsvenster.

>[!NOTE]
>
> U kunt op een kolomkop klikken en de bestanden sorteren op basis van de kolommen in het basislijnbewerkingsvenster.

**Een basislijn opslaan of opnieuw instellen**

Nadat u de basislijn hebt bewerkt, kunt u op de knop **Opslaan** aan de bovenkant om de wijzigingen in de basislijn op te slaan. U kunt op de knop **Herstellen** als u de wijziging niet wilt opslaan en de basislijn opnieuw wilt instellen. Wanneer u op de knop **Herstellen** er verschijnt een waarschuwing dat niet-opgeslagen wijzigingen verloren gaan.

**Bovenliggend onderwerp:**[ Werken met de webeditor](web-editor.md)
