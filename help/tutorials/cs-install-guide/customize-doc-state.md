---
title: Documentstatussen configureren
description: Leer hoe u documentstatussen kunt configureren
source-git-commit: e3b2fc8c96ce535bb91e7bce935720aa389a917a
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 0%

---


# Documentstatussen configureren {#id181GB0400UI}

AEM de Gidsen laat u de documentstaten voor uw onderwerpen DITA volgens de vereisten van uw organisatie bepalen. U kunt verschillende statussen van het document definiëren, van het begin tot het einde. De eerste status kan bijvoorbeeld Concept zijn en worden verplaatst naar Revisie, Goedgekeurd, Vertaald en tot slot naar Gepubliceerd.

Er zijn twee manieren waarop een onderwerp van één staat aan een andere kan overgaan - handboek en automatisch. De documentstatussen die in een profiel zijn gedefinieerd, kunnen worden gebruikt voor het handmatig wijzigen van de documentstatus. Dit kan van de pagina van Eigenschappen van een onderwerpdossier worden gedaan. U kunt ook bepalen wie het document van het ene naar het andere frame kan verplaatsen. Een auteur kan bijvoorbeeld een document maken en de standaardstatus van het document kan Concept zijn. Wanneer de auteur het document ter controle verzendt, kan hij de documentstatus wijzigen in In-Review. De controleur kan de documentstatus wijzigen in Goedgekeurd of in Concept op basis van het revisieproces. Als het document is goedgekeurd, kan de uitgever de documentstatus wijzigen in Vertaald of Gepubliceerd, afhankelijk van de workflow.

>[!NOTE]
>
> Als een gebruiker tot *beheerders* in een groep, kan de gebruiker de status van een document wijzigen vanuit een willekeurige status, ongeacht de overgangen van de documentstatus die in het systeem zijn gedefinieerd.

## Een documentstatus maken

AEM hulplijnen worden geleverd met een set standaarddocumentstatussen. Deze staten zijn:

- Concept
- Bewerken
- Evaluatieversie
- Goedgekeurd
- Bekeken
- Gereed

Deze standaardstaten zijn beschikbaar aan alle onderwerpen DITA die onder DAM worden gecreeerd. U kunt uw eigen documentstaten maken en deze toewijzen aan een specifieke map. Alle DITA-bestanden die in die map worden gemaakt, hebben vervolgens toegang tot de nieuwe documentstatussen.

Voer de volgende stappen uit om documentstatussen te maken met behulp van het mapprofiel:

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen.
1. Klik op de tegel Documentstatussen.

   De pagina Elementenstatussen wordt weergegeven. Standaard wordt op de pagina een standaardprofiel weergegeven.

1. Klikken **Profiel maken** en voert u de volgende gegevens in:
   - Voer in het veld Profiel de naam voor het profiel in.
   - Geef het pad op waarop u het nieuwe profiel wilt toepassen.
   - Geef de statussen van het document op in het dialoogvenster **Toegestane staten** krachtens **Staten**. De standaarddocumentstatussen zijn Concept, Bewerken, In-Review, Goedgekeurd en Gereed.-

     Klik op de knop **Toevoegen** om een documentstatus toe te voegen.

      - Klik op het pictogram Verwijderen om een documentstatus te verwijderen.

     >[!NOTE]
     >
     > Verwijder geen documentstatus als de documenten zich nog in die status bevinden. Als u een documentstatus verwijdert, kunt u de documentstatus van dergelijke documenten alleen wijzigen als u tot de *beheerder* gebruikersgroep.

   - Geef de beginstatus van het document op in het dialoogvenster **Beginstatus**.
   - Geef de eindstatus van het document op in het dialoogvenster **Eindstatus**.
   - De statusovergang van het document opgeven in **Van** en **Naar** krachtens **Overgang staat**.

      - Geef de gebruikers en gebruikersgroepen op die de documentstatus in **Groepen**.

      - Klik op de knop **Toevoegen** om een frameovergang toe te voegen.

      - Klik op het pictogram Verwijderen om een frameovergang te verwijderen.

     >[!NOTE]
     >
     > Een frameovergang niet verwijderen als de documenten zich nog in `From` status. Als u een frameovergang verwijdert, kunt u de documentstatus van dergelijke documenten alleen wijzigen als u tot de *beheerder* gebruikersgroep.

1. Klikken **Gereed**.

## Een kopie van een documentstatusprofiel maken

Afhankelijk van uw vereiste kunt u een kopie van een bestaand documentstatusprofiel maken. U kunt de kopie gebruiken als basis voor het maken van een ander documentprofiel.

Voer de volgende stappen uit om een kopie van een documentstatusprofiel te maken:

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen.
1. Klik op de tegel Documentstatussen.

   De pagina Elementenstatussen wordt weergegeven.

1. Selecteer het documentstatusprofiel dat u wilt dupliceren en klik op **Profiel dupliceren**.
1. Breng vereiste veranderingen aan en klik **Gereed**.

## Een documentstatus of statusovergang verwijderen

>[!NOTE]
>
> Verwijder geen documentstatus of statusovergang als de documenten zich nog in de status of in een statusovergang bevinden. Als u een staat of een staatsovergang schrapt, zult u niet de documentstaat van dergelijke documenten kunnen veranderen tenzij u tot het behoort *beheerder* gebruikersgroep.

Voer de volgende stappen uit om een documentstatus of statusovergang te verwijderen uit een documentstatusprofiel:

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen.
1. Klik op de tegel Documentstatussen.

   De pagina Elementenstatussen wordt weergegeven.

1. Selecteer het documentstatusprofiel van de plaats waar u de documentstatus wilt verwijderen en klik op **Profiel bewerken**.
1. De documentstatus of statusovergang verwijderen en klikken **Gereed**.

## Een documentstatusprofiel verwijderen

Voer de volgende stappen uit om een documentstatusprofiel te verwijderen:

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen.
1. Klik op de knop **Documentstatussen** tegel.

   De pagina Elementenstatussen wordt weergegeven.

1. Selecteer het documentstatusprofiel dat u wilt verwijderen en klik op **Profiel verwijderen**.

## De documentstatuswijziging automatiseren

Als u de documentstatus niet handmatig wilt wijzigen, kunt u een workflow maken en de wijziging van de documentstatus automatiseren.

>[!NOTE]
>
> Geautomatiseerde workflows moeten in overeenstemming zijn met de documentstatussen en overgangen die in de configuratie zijn gedefinieerd. Het systeem voert geen controles uit op statuswijzigingen die via geautomatiseerde workflows zijn uitgevoerd.

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Workflow** in de lijst met gereedschappen.

1. Klik op de knop **Modellen** tegel.

1. Selecteer de relevante workflow, Lees de onderwerpen van de revisie.

1. Klikken **Bewerken**.

   De workflow wordt geopend op een nieuw tabblad.

1. Klikken **Bewerken** \(rechtsboven\).

1. Open de **Stappen** browser; gebruiken **Zijpaneel in-/uitschakelen** helemaal links van de bovenste werkbalk

1. Sleep de gewenste stap naar de gewenste locatie in het model.

1. Klik op de nieuwe stap die u in het workflowmodel hebt toegevoegd en selecteer **Configureren** van de componentwerkbalk

1. Open de **Proces** tab.

1. In de **Proces** vervolgkeuzelijst, selecteert u **Documentstatus instellen voor elk DAM-element**.

1. Selecteer **Handler Advance** optie.

   ![](assets/update-workflow-doc-state_cs.png)

1. In de **Argumenten** in het tekstvak, voert u een documentstatus in waarnaar u vanuit de geselecteerde workflow wilt overstappen.

   >[!NOTE]
   >
   > Zorg ervoor dat u de juiste documentstatus invoert in het tekstvak Argumenten. Als u een onjuiste waarde opgeeft, wordt de status van het document onjuist.

1. De wijziging bevestigen met **Opslaan en sluiten**.


## Goedkeuringswerkstroom inschakelen

AEM hulplijnen bieden een workflow voor documentgoedkeuring waarmee u de levenscyclus van het ontwikkelingsproces van uw document kunt bepalen. Voer de volgende stappen uit om de goedkeuringswerkstroom in te schakelen:

1. U kunt als beheerder het configuratiebestand van de gebruikersinterface downloaden door u aan te melden bij Adobe Experience Manager.

1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen en klik op de knop **Mapprofielen**.
1. Klik op de knop **Globaal profiel** tegel.
1. Selecteer **XML Editor-configuratie** en klik op **Bewerken** pictogram bovenaan
1. Klik op de knop **Downloaden** pictogram om het bestand ui\_config.json op uw lokale systeem te downloaden. Vervolgens kunt u wijzigingen in het bestand aanbrengen en het bestand vervolgens uploaden.
1. In de `ui_config.json` bestand, schakelt u de functie voor de goedkeuringswerkstroom in door het *functies* hieronder weergegeven:

   ```
   "features":  
   { 
      "approvalWorkflow":  true 
   }
   ```

1. Sla het bestand op en upload het.

