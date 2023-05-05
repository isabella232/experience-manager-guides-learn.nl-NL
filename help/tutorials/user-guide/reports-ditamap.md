---
title: DITA-kaartrapport van het kaartdashboard
description: Leer hoe te om het kaartrapport DITA van het kaartdashboard te bepalen
exl-id: 8ba1dc83-fa96-4ae0-bfa8-89b5a8949f08
source-git-commit: c74badebbcb4733fb9caa79c646b1d1e5c8bfe8e
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---

# DITA-kaartrapport van het kaartdashboard {#id205BB800EEN}

AEM de Gidsen verstrekt uw beheerders de rapporteringsmogelijkheden om de algemene integriteit van de documentatie te controleren alvorens het levend wordt geduwd of ter beschikking gesteld aan eind - gebruikers. Het DITA kaartrapport van het kaartdashboard in AEM Gidsen verstrekt waardevolle informatie zoals de ontbrekende onderwerpen, onderwerpen met ontbrekende elementen, UUID van referenced onderwerpen en media dossiers, en overzichtsstatus van elk onderwerp. Een gedetailleerd individueel onderwerp-vlakke rapport verstrekt ook inhoud-verwante informatie DITA zoals inhoudsverwijzingen en ontbrekende beelden of verwijzingen.

>[!NOTE]
>
> AEM Hulplijnen vernieuwen dit rapport bij elke gebeurtenis die een wijziging in het kaartbestand tot gevolg heeft of wanneer een verwijzing in het onderwerpbestand wordt bijgewerkt.

Voer de volgende stappen uit om het Rapport van de Kaart DITA te bekijken:

1. In Elementen UI, navigeer aan en klik op het DITA kaartdossier waarvoor u het rapport wilt bekijken.

1. Klikken **Rapporten**.

   ![](images/reports-page-uuid.png){width="800" align="left"}

   De pagina Rapporten bestaat uit twee delen:

   - **Overzicht van onderwerpen:**

      Hiermee geeft u de algemene samenvatting van het geselecteerde kaartbestand weer. Door het Overzicht te bekijken, kunt u snel het totale aantal onderwerpen in de kaart, ontbrekende onderwerpen, aantal onderwerpen kennen die elementen missen, de staat van onderwerpen - in Ontwerp, in Overzicht, of Gereviseerde staat hebben.

   - **Details:**

      Wanneer u op een onderwerp klikt, wordt een gedetailleerd rapport van het geselecteerde onderwerp getoond.

      ![](images/detailed-report-uuid.png){width="800" align="left"}

      Items gemarkeerd onder **A**, **B**, **C** en **D** worden hieronder beschreven:

      - **Onderwerp**: De titel van het onderwerp dat in de kaart DITA wordt gespecificeerd. Als u de muisaanwijzer op de titel van het onderwerp plaatst, wordt het volledige pad van het onderwerp weergegeven. Als het onderwerp problemen bevat, zoals ontbrekende verwijzingen of afbeeldingen, wordt een rode stip vóór de titel van het onderwerp weergegeven.

      - **Bestandsnaam**: Naam van het bestand.

      - **UUID**: De universeel unieke id \(UUID\) van het bestand.

      - **Auteur**: Gebruiker die het laatst aan dit onderwerp heeft gewerkt.

      - **Documentstatus**: De huidige status van het document - Concept, In-Review of Reviewed.

      - **Ontbrekende onderwerpen \(B\)**: Als er onderwerpen met gebroken verwijzingen zijn, dan zijn die onderwerpen vermeld onder de Ontbrekende lijst van Onderwerpen.

      - **Ontbrekende elementen**: Hier wordt het aantal ontbrekende afbeeldingen of verbroken kruisverwijzingen vermeld, indien van toepassing.

      - **Openen in Editor \(D\)**: Als u op dit pictogram klikt, wordt het onderwerp in de webeditor geopend.

   Items gemarkeerd onder **E** worden hieronder beschreven:

   - **Multimedia**: Het pad van de afbeeldingen die in het onderwerp worden gebruikt, wordt samen met de bijbehorende UUID weergegeven. Als u op het afbeeldingspad klikt, wordt de bijbehorende afbeelding geopend in een pop-upvenster. Verbroken afbeeldingskoppelingen worden weergegeven in rode kleuren.

   - **Content References**: De weg van de inhoud die in het onderwerp wordt bedoeld wordt getoond samen met zijn UUID. Als u op de titel van de genoemde inhoud klikt, wordt het overeenkomstige onderwerp geopend in de modus Voorbeeld.

   - **Kruisverwijzing**: Het pad van de inhoud waarnaar wordt verwezen, wordt samen met de bijbehorende UUID weergegeven. Als u op de titel van de genoemde inhoud klikt, wordt het overeenkomstige onderwerp geopend in de modus Voorbeeld. Verbroken kruisverwijzingen worden weergegeven in rode kleuren.

   - **Controleren**: Toont het statuut van de overzichtstaak van het onderwerp. U kunt de status \(open of close\), de vervaldatum en de toegewezen persoon voor het onderwerp in kwestie zien. Als u de onderwerpverbinding klikt, opent het het onderwerp op overzichtswijze.

   - **Gebruikt in**: Toont een lijst van andere onderwerpen of kaarten waar het onderwerp wordt gebruikt. De UUID van al dergelijke onderwerpen en kaarten is ook vermeld.



Naast het rapport voor elk individueel onderwerp, hebben de beheerders ook toegang tot informatie zoals het publiceren geschiedenis van een kaart DITA. Voor meer informatie over de geschiedenis van geproduceerde output, zie [De status van de uitvoergeneratietaak weergeven](generate-output-for-a-dita-map.md#viewing_output_history).

## CSV genereren van DITA-kaartrapport

U kunt CSV van een DITA kaartrapport downloaden en uitvoeren. CSV bevat het gedetailleerde DITA kaartrapport.

Voer de volgende stappen uit om CSV van een DITA kaartrapport te produceren:

1. Klikken **Rapport genereren** op top-left om het DITA kaartrapport te produceren.

   ![](images/generate-DITA-map-report.png){width="800" align="left"}

1. U ontvangt een melding als het rapport klaar is om te worden gedownload. Klikken **Downloaden** om CSV van het geproduceerde rapport te downloaden.

   ![](images/download-report-dialog.png){width="550" align="left"}


   U kunt CSV van het geproduceerde rapport van AEM bericht Inbox ook downloaden.

   Klik het geproduceerde rapport in Inbox om het rapport te downloaden.

   ![](images/report-inbox--notification.png){width="300" align="left"}

Zodra het rapport in Inbox wordt gedownload kunt u het rapport ook selecteren en het Open pictogram op de bovenkant gebruiken om het geselecteerde rapport te openen.

**Bovenliggend onderwerp:**[ Rapporten](reports-intro.md)
