---
title: Nieuwe op microservice gebaseerde publicatie configureren voor as a Cloud Service AEM hulplijnen
description: Leer hoe u nieuwe op microservice gebaseerde publicaties voor AEM hulplijnen kunt configureren.
exl-id: 92e3091d-6337-4dc6-9609-12b1503684cd
source-git-commit: aa71a2b8ff5f83365ff2f3562bb2b77061a3da8e
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 0%

---

# Nieuwe op microservice gebaseerde publicatie configureren voor as a Cloud Service AEM hulplijnen

Met de nieuwe publicatiemicroservice kunnen gebruikers tegelijkertijd grote publicatiewerklasten uitvoeren op AEM as a Cloud Service hulplijnen en het toonaangevende Adobe I/O Runtime-serverplatform benutten.

Voor elke publicatieaanvraag AEM as a Cloud Service hulplijnen wordt een aparte container uitgevoerd die horizontaal wordt geschaald volgens de wensen van de gebruiker. Dit biedt gebruikers de mogelijkheid om meerdere publicatieverzoeken uit te voeren en betere prestaties te krijgen dan hun grote AEM.

>[!NOTE]
>
> Op microservices gebaseerde publicaties in AEM hulplijnen ondersteunen de typen PDF (zowel op basis van Native als DITA-OT), HTML5, JSON en CUSTOM van voorinstellingen voor uitvoer.

Aangezien de nieuwe service voor publicatie in de cloud wordt beveiligd door verificatie op basis van Adobe IMS JWT, moeten klanten onderstaande stappen volgen om hun omgevingen te integreren met beveiligde tokengebaseerde verificatieworkflows van de Adobe en de nieuwe, op de cloud gebaseerde schaalbare publicatieoplossing te gaan gebruiken.


## IMS-configuraties maken in Adobe Developer Console

**Rol vereist om de conflicten tot stand te brengen**: Systeembeheerder

Voer de volgende stappen uit om IMS-configuraties te maken in Adobe Developer Console:

1. Ontwikkelaarsconsole openen: `https://developer.adobe.com/console`.

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

U hebt nu de JWT-verificatiegegevens geconfigureerd en ook de persoonlijke sleutel en de servicedetails JSON gedownload. Houd deze twee bestanden bij de hand, aangezien deze bestanden in de volgende sectie zijn vereist.

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

1. Voeg de onderstaande twee bestanden toe in uw Git-projectcode voor cloudbeheer (zie voor de bestandsinhoud) [Bijlage](#appendix)).

   * `com.adobe.aem.guides.eventing.ImsConfiguratorService.cfg.json`
   * `com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService.xml`
1. Zorg ervoor dat de toegevoegde bestanden worden gedekt door uw `filter.xml`.
1. Leg de Git-wijzigingen vast en duw erop.
1. Voer de pijpleiding in om de veranderingen op het milieu toe te passen.

Zodra dit wordt gedaan, zou u de nieuwe op microservice-gebaseerde wolkenpublicatie moeten kunnen gebruiken.

## Veelgestelde vragen

1. Kan één sleutel worden gebruikt op veelvoudige wolkenmilieu&#39;s?
   * Ja, u kunt één privé sleutel produceren en het voor alle milieu&#39;s gebruiken, maar u moet milieuvariabelen voor alle milieu&#39;s vormen en de zelfde sleutel gebruiken.
1. Als de configuraties OSGi om microservice te gebruiken worden toegelaten, zal het het publiceren proces op lokale AEM server met de zelfde codebase werken?
   * Neen, indien de markering `dxml.use.publish.microservice` is ingesteld op `true` dan zoekt het altijd microservice configuraties. Set `dxml.use.publish.microservice` tot `false` zodat de uitgever op uw lokale computer kan werken.
1. Hoeveel geheugen wordt toegewezen aan het proces DITA wanneer het gebruiken van op microservice-gebaseerde het publiceren? Wordt dit aangestuurd via parameters van het DITA-profiel?
   * Bij publicatie op basis van microservices wordt geheugentoewijzing niet aangestuurd door parameters van het type DITA-profiel. Het totale beschikbare geheugen op de de dienstcontainer is 8 GB, waarvan 6 GB aan het DITA-OT proces wordt toegewezen.


## Bijlage {#appendix}

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
* `dxml.use.publish.microservice`: Schakel over om op microservice gebaseerde publicatie met DITA-OT in te schakelen
* `dxml.use.publish.microservice.native.pdf`: Schakel over om op microservice gebaseerde Native PDF-publicatie in te schakelen

```
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:jcr="http://www.jcp.org/jcr/1.0" xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          jcr:primaryType="sling:OsgiConfig"
          dxml.publish.microservice.url="https://adobeioruntime.net/api/v1/web/543112-guidespublisher/default/publishercaller.json"
          dxml.use.publish.microservice="{Boolean}true"
          dxml.use.publish.microservice.native.pdf="{Boolean}true"
/>
```
