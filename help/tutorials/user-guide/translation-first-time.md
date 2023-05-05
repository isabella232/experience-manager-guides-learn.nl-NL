---
title: Aanbevolen procedures voor het vertalen van inhoud
description: Meer informatie over tips en trucs voor het vertalen van inhoud
exl-id: 4eff0f27-b3d1-4c6e-af88-bcb3f6d96990
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '1237'
ht-degree: 0%

---

# Aanbevolen procedures voor het vertalen van inhoud {#id1678G0S702F}

Houd rekening met het volgende punt voor het vertalen van inhoud:

- De map- en bestandsnamen moeten voldoen aan de naamgevingsstandaarden voor bestanden, zoals: er mogen geen spaties, apostrof, accolades, gelijktekens, speciale of niet-ASCII-tekens voorkomen.

- Als u inhoud in verschillende talen vertaalt, moet u omslagen tot stand brengen die aan elke taal beantwoorden. Elk van deze taalomslagen zal de inhoud bevatten die aan die taal beantwoordt. U kunt bijvoorbeeld mappen maken met de taalaanduiding, net als `de` voor het Duits, `fr` voor Frans enzovoort. U kunt ook mappen maken met de taal en regio-aanduidingen, zoals `fr-FR` voor Frans zoals gebruikt in Frankrijk of `fr-CA` voor Frans zoals gebruikt in Canada.
- In de doeltaal moeten ook de werkelijke landinstellingen worden geselecteerd volgens de doeltaalmappen op hun exemplaar.
- De cloudconfiguratie moet dezelfde zijn als die van de bronmap en er mag slechts één cloudconfiguratie in één map zijn. U kunt veelvoudige omslagen onder /conf tot stand brengen, als u veelvoudige vertaalschakelaars wilt gebruiken.
- Een map mag niet meer dan 1000 bestanden bevatten.
- Zorg ervoor dat de gebruiker die belast is met het initiëren van het vertaalproces, beschikt over de machtigingen Lezen, Wijzigen, Maken en Verwijderen voor de bronmappen en de doeltaalmappen.
- Aangezien het vertalen van inhoud verwezenlijking van een vertaalproject vereist, moet de gebruiker toegang hebben om project in AEM tot stand te brengen.
- Als u Voorwaardelijke voorinstellingen voor uw kaart wilt gebruiken, moet u deze maken voordat u het vertaalproces start. Omdat Voorwaardelijke voorinstellingen ook in de vertaalde versie van de kaart worden gebundeld, zorgt het creëren van voorinstellingen alvorens het vertaalproces in werking te stellen ervoor dat zij in de vertaalde versie beschikbaar zijn.
- Het proces voor het vertalen van inhoud moet worden gestart vanuit de DITA-kaartconsole en niet vanuit de AEM Assets-gebruikersinterface.
- De op componenten-gebaseerde DITA-omzettingsworkflow mag niet worden gebruikt als u inhoud via menselijke vertaling vertaalt. Deze optie moet echter worden gebruikt voor machinevertaling.
- De wereldwijd gebruikte inhoud en media die niet hoeven te worden gelokaliseerd, moeten buiten de taalkopieën worden gehouden.
- Alle algemene inhoud die moet worden gelokaliseerd, moet in een gemeenschappelijke omslag onder de taalomslag worden gehouden.

In de volgende afbeelding ziet u een voorbeeld van een mapstructuur in AEM wanneer u inhoud en drie taalkopieën hebt gebruikt.

![](images/aem-directory_structure.png){width="800" align="left"}

## Vertaalservice configureren

Voer de volgende stappen uit om de te gebruiken service voor het vertalen van mensen of machines te configureren:

1. Selecteer in de interface Elementen de brontaalmap.

1. Open de mapeigenschappen en ga naar **Cloud Services** tab.

1. In de **Cloud Services** , configureert u de vertaalservice die u wilt gebruiken.

   U kunt op computer gebaseerde of menselijke vertaling configureren.

   Zorg ervoor dat er slechts één configuratie voor vertaalschakelaar in één omslag is. De veelvoudige omslagen kunnen onder /conf worden gecreeerd, als er veelvoudige vertaalschakelaars zijn. Voor de brontaalmap moet een cloudconfiguratie zijn geselecteerd voordat het vertaalproces wordt gestart.

   >[!NOTE]
   >
   > Zie [Het framework voor vertaalintegratie configureren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) in AEM documentatie voor meer informatie over de integratie met de vertaaldiensten van derden.

1. Klikken **Opslaan en sluiten** om de bijgewerkte eigenschappen van de map op te slaan.


>[!TIP]
>
> Zie de *Vertaling* in de gids met aanbevolen procedures voor de aanbevolen procedures voor het vertalen van inhoud.

## Een nieuw vertaalproject maken

Voer de volgende stappen uit om een vertaalproject te maken:

>[!NOTE]
>
> Voordat u de stappen in deze procedure uitvoert, moet u controleren of u de vereiste hoofdmap en doelmappen voor de taal hebt gemaakt, zoals beschreven in het dialoogvenster [Aanbevolen procedures voor het vertalen van inhoud](#id1678G0S702F).

1. Klik in de interface Middelen op het DITA-kaartbestand.

1. Klik op de knop **Vertaling** tab.

1. Van de **Doeltalen** selecteert u de landinstelling waarnaar u het project wilt vertalen en klikt u op **Gereed**.

   Een Samenvatting en Details van onderwerpen en bijbehorende activa wordt getoond.

   >[!IMPORTANT]
   >
   > De **Doeltalen** alleen die talen weergeven waarvoor een taalmap is gemaakt parallel aan de brontaal. Een taalmap die op een ander niveau is gemaakt, zoals één niveau lager in de brontaalmap, wordt ook niet weergegeven. Zorg ervoor dat u alle doeltaalmappen maakt op hetzelfde niveau als de brontaalmap.

1. Selecteer de onderwerpen die u voor vertaling wilt verzenden.

   U kunt ook de volgende opties voor het filteren van onderwerpen gebruiken:

   >[!NOTE]
   >
   > Nadat u het vereiste filter hebt toegepast, klikt u op **Gereed** in het deelvenster Filter om onderwerpen te filteren op basis van uw selectie.

   - **Vertaalstatus**: Kies om onderwerpen te filteren op basis van hun vertaalstatus. De beschikbare opties zijn: Onsynchroon, Kopie ontbreekt, Bezig en Gesynchroniseerd.
   - **Zoeken**: Voer een of meerdere termen in om in de onderwerptitels te zoeken.
   - **Brontype**: Kies om onderwerpen te filteren op basis van hun bestandstypen. De beschikbare opties zijn: All, DITA, DITA Map, Resource.
   - **Bronversie gewijzigd na**: Kies of u een onderwerp wilt filteren op basis van de wijzigingsdatum en -tijd. Alle onderwerpen die na de gespecificeerde datum en de tijd worden gewijzigd worden getoond in de lijst.
   - **Basislijn**: Klik op Basislijn gebruiken en kies een basislijn die op de kaart is gemaakt. Alle bestanden die deel uitmaken van de geselecteerde basislijn, worden weergegeven op de pagina Vertalen. U kunt de gewenste bestanden vanaf de basislijn kiezen en doorgaan met het vertaalproces. Nadat de inhoud is vertaald, kunt u de vertaalde basislijn exporteren. Voor meer informatie over het exporteren van de vertaalde basislijn raadpleegt u [Vertaalde basislijn exporteren](generate-output-use-baseline-for-publishing.md#id196SE600GHS).
1. Klikken **Taalkopieën maken/bijwerken** onder aan het deelvenster Filter.

1. Van de **Project** list, selecteer **Nieuw vertaalproject maken**.

   >[!NOTE]
   >
   > Als u reeds een vertaalproject hebt, kunt u onderwerpen aan dat project toevoegen. Selecteren **Toevoegen aan bestaand vertaalproject** van de **Project** en kies een project in het menu **Bestaand vertaalproject** lijst.

1. In de **Projecttitel** voert u een titel in voor het project.

1. Selecteer **Inclusief DITA-kaart** optie om de kaart voor vertaling te verzenden.
1. Klikken **Start** om een nieuw vertaalproject op te zetten.

   Een nieuw vertaalproject wordt gecreeerd met de geselecteerde versie van de onderwerpen. Op dit moment wordt een pop-upbericht weergegeven met de bevestiging dat het vertaalproject is gemaakt. Zodra alle exemplaren van de doeltaal in het vertaalproject beschikbaar zijn, krijgt u een bericht in Inbox. Zodra de doeltaal een gebied kopieert dat beschikbaar is in het vertaalproject, kunt u dan doorgaan en de vertaaltaak starten.


## De vertaaltaak starten {#id225IK030OE8}

Voer de volgende stappen uit om de vertaaltaak te starten:

1. In de **Projecten** navigeer naar de projectmap die u voor lokalisatie hebt gemaakt.

1. Klik op het lokalisatieproject om de detailpagina te openen.

1. Klik op de pijl op de knop **Vertaaltaak** tegel en selecteer **Start** in de lijst om de vertaalworkflow te starten.

   >[!NOTE]
   >
   > Als u de vertaalservice Human gebruikt, moet u de inhoud exporteren voor vertaling. Zodra u de vertaalde inhoud hebt, dan moet u het terug in het vertaalproject invoeren.

1. Als u de status van de vertaaltaak wilt weergeven, klikt u op de ovaal onder aan het dialoogvenster **Vertaaltaak** tegel.


Nadat de vertaling is voltooid, verandert de status van de vertaaltaak in *Klaar voor revisie*. Om het vertaalproces te voltooien, moet u de vertaalde exemplaar en activa meta-gegevens van de Taaktegel van de Vertaling in de console van het Project goedkeuren.

>[!NOTE]
>
> Als u de vertaling voor een of meer onderwerpen in een vertaaltaak afwijst, kunt u **In uitvoering** de vertaalstatus van alle afgewezen onderwerpen wordt weer hersteld . De status van de bedoelde onderwerpen wordt gecontroleerd en teruggezet volgens de meest recente vertaalstatus. Ook, worden de vertaaldossiers die in het bestemmingsproject worden gecreeerd niet geschrapt zelfs als de vertaling voor hen wordt verworpen.

**Bovenliggend onderwerp:**[ Inhoud vertalen](translation.md)
