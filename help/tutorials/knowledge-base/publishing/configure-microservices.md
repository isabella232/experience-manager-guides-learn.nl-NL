---
title: Nieuwe op microservice gebaseerde publicatie configureren voor as a Cloud Service AEM hulplijnen
description: Leer hoe u nieuwe op microservice gebaseerde publicaties voor AEM hulplijnen kunt configureren.
source-git-commit: afbc1712cf45dd0b570e20683946af6a86edae7e
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 0%

---

# Nieuwe op microservice gebaseerde publicatie configureren voor as a Cloud Service AEM hulplijnen

Met de nieuwe publicatiemicroservice kunnen gebruikers tegelijkertijd grote publicatiewerklasten uitvoeren op AEM as a Cloud Service hulplijnen en het toonaangevende Adobe I/O Runtime-serverplatform benutten.

Voor elke publicatieaanvraag AEM as a Cloud Service hulplijnen wordt een aparte container uitgevoerd die horizontaal wordt geschaald volgens de wensen van de gebruiker. Dit biedt gebruikers de mogelijkheid om meerdere publicatieverzoeken uit te voeren en betere prestaties te krijgen dan hun grote AEM.

Aangezien de nieuwe service voor publicatie in de cloud wordt beveiligd door verificatie op basis van Adobe IMS JWT, moeten klanten de onderstaande stappen volgen om hun omgevingen te integreren met veilige, op token gebaseerde verificatieworkflows en de nieuwe, op de cloud gebaseerde schaalbare publicatieoplossing te gaan gebruiken.


## IMS-configuraties maken in Adobe Developer Console

**Rol vereist om de conflicten tot stand te brengen**: Systeembeheerder

Voer de volgende stappen uit om IMS-configuraties te maken in Adobe Developer Console:

1. Open Developer Console: `https://developer.adobe.com/console`.

1. Overschakelen op **Projecten** van boven.

   <img src="assets/projects-tab.png" alt="tabblad Projecten" width="500">

1. Als u een nieuw, leeg project wilt maken, selecteert u **Leeg project** van de **Nieuw project maken** vervolgkeuzelijst.

   <img src="assets/create-new-project.png" alt="nieuw project maken" width="500">

1. Selecteren **API** van de **Toevoegen aan project** vervolgkeuzelijst om IO Management API aan uw project toe te voegen.

   <img src="assets/add-project.png" alt="project toevoegen" width="300">

   <img src="assets/io-management-api.png" alt="io-beheer" width="500">

1. Maak een nieuw paar met een persoonlijke of openbare sleutel terwijl u de API toevoegt. De persoonlijke sleutel wordt dan automatisch naar uw systeem gedownload.

   <img src="assets/generate-key-pair.png" alt="sleutelpaar genereren" width="500">

1. Sla de geconfigureerde API op.

   <img src="assets/save-api.png" alt="api opslaan" width="600">

1. Ga terug naar **Projecten** en klik op **Overzicht van project** links.

   <img src="assets/project-overview.png" alt="projectoverzicht" width="500">

1. Klikken **Downloaden** bovenaan om de service JSON te downloaden.

   <img src="assets/download-json.png" alt="download json" width="500">

U hebt nu de JWT-verificatiedetails geconfigureerd en ook de persoonlijke sleutel en de servicedetails JSON gedownload. Houd deze twee bestanden bij de hand, aangezien deze bestanden in de volgende sectie zijn vereist.

### IMS-configuratie toevoegen aan de omgeving

Voer de volgende stappen uit om configuratie IMS aan het milieu toe te voegen:

1. Open Experience Manager en selecteer vervolgens uw programma met de omgeving die u wilt configureren.
1. Overschakelen op **Omgevingen** tab.
1. Klik op de naam van de omgeving die u wilt configureren. Hiermee navigeert u naar de pagina Informatie over omgeving.
1. Overschakelen op **Configuratie** tab.
1. Upload de persoonlijke sleutel en het project JSON zoals hieronder in het schermafbeelding wordt getoond. Zorg ervoor u de zelfde namen en configuratie gebruikt zoals hieronder benadrukt.

   <img src="assets/ims-config-environment.png" alt="ims-configuraties" width="500">

>[!NOTE]
>
> U moet de inhoud van het JSON-bestand met persoonlijke sleutel en servicedetails openen, kopiëren en in de waardekolom van het deelvenster Configuratie plakken, zoals in de bovenstaande schermafbeelding wordt getoond.

Zodra u de configuratie IMS aan het milieu hebt toegevoegd, voer de volgende stappen uit om deze eigenschappen met AEM Gidsen te verbinden gebruikend OSGi:

1. Voeg de onderstaande twee bestanden toe in uw Git-projectcode voor cloudbeheer (zie voor de bestandsinhoud) [Aanhangsel](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Zorg ervoor dat de toegevoegde bestanden worden gedekt door uw `filter.xml`.
1. Leg de Git-wijzigingen vast en duw erop.
1. Voer de pijpleiding in om de veranderingen op het milieu toe te passen.

Zodra dit wordt gedaan, zou u de nieuwe op microservice-gebaseerde wolkenpublicatie moeten kunnen gebruiken.

## Aanhangsel {#appendix}

**Bestand**:
`com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`

**Inhoud**:

```
{
  "service.account.details": "$[secret:SERVICE_ACCOUNT_DETAILS]",
  "private.key": "$[secret:PRIVATE_KEY]"
}
```

**Bestand**: `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`

**Inhoud**:

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
/>
```
