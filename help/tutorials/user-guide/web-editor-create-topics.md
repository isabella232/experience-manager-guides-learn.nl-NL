---
title: Onderwerpen maken
description: Leer om types van onderwerpen te creëren DITA gebruikend douanesjablonen in de Webredacteur van AEM Gidsen.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 0%

---

# Onderwerpen maken {#id2056AL00O5Z}

AEM de Gidsen staat u toe om DITA onderwerpen van type - onderwerp, taak, concept, verwijzing, verklarende woordenlijst, DITAVAL, en meer tot stand te brengen. Naast het creëren van onderwerpen die op de uit-van-de-doos malplaatjes worden gebaseerd, kunt u uw douanesjablonen ook bepalen. Deze sjablonen moeten aan het mapprofiel worden toegevoegd om weer te geven in de sjabloonselectie, de blauwdruk en de webeditor.

De configuratie van het algemene profiel en het mapprofiel is alleen beschikbaar voor gebruikers met beheerdersrechten op mapniveau. Voor meer informatie over het instellen van algemene profielen en mapprofielen raadpleegt u *Ontwerpsjablonen configureren* in Adobe Experience Manager-hulplijnen installeren en configureren voor uw installatie.

Voer de volgende stappen uit om een onderwerp tot stand te brengen:

1. In Elementen UI, navigeer aan de plaats waar u het onderwerp wilt tot stand brengen.

1. Als u een nieuw onderwerp wilt maken, klikt u **Maken** \> **DITA-onderwerp**.

1. Selecteer op de pagina Vervagen het type DITA-document dat u wilt maken en klik op **Volgende**.

   ![](images/create_dita_topic.png){width="800" align="left"}

   Door gebrek, verstrekt AEM Gidsen de het meest algemeen gebruikte DITA onderwerpmalplaatjes. U kunt meer onderwerpmalplaatjes volgens uw organisatorische vereisten vormen, zie *Ontwerpsjablonen configureren* in Adobe Experience Manager-hulplijnen installeren en configureren voor uw installatie.

   >[!NOTE]
   >
   > In de lijstmening van Activa UI, wordt het DITA onderwerptype getoond in de kolom van het Type als Onderwerp, Taak, Concept, Verwijzing, Verklarende vermelding, of DITAVAL. De kaart DITA wordt getoond als Kaart.

1. Geef op de pagina Eigenschappen het document op **Titel**.

1. \(Optioneel\) Geef het bestand op **Naam**.

   Als uw beheerder automatische bestandsnaam heeft geconfigureerd op basis van de UUID-instelling, ziet u geen optie om de bestandsnaam op te geven. Er wordt automatisch een op UUID gebaseerde bestandsnaam toegewezen aan het bestand.

   Als de optie voor het benoemen van bestanden beschikbaar is, wordt ook de naam automatisch voorgesteld op basis van de optie **Titel** van uw document. Als u de documentnaam handmatig wilt opgeven, moet u ervoor zorgen dat de **Naam** bevat geen spaties, apostrof of accolades en eindigt met .xml of .dita. Standaard vervangt AEM hulplijnen alle speciale tekens door koppeltekens. Raadpleeg de sectie Bestandsnamen in de handleiding met aanbevolen procedures voor tips en trucs voor het benoemen van DITA-bestanden.

1. Klikken **Maken**. Het bericht Gemaakt onderwerp wordt weergegeven.

   U kunt verkiezen om het onderwerp voor het uitgeven in de Redacteur van het Web, of sparen het onderwerpdossier in de AEM bewaarplaats te openen.

   Elk nieuw onderwerp dat u van Elementen UI creeert **Maken** \> **DITA-onderwerp** of de Redacteur van het Web wordt toegewezen een unieke onderwerpidentiteitskaart De waarde van deze id is de bestandsnaam zelf. Bovendien wordt een nieuw document opgeslagen als de meest recente werkkopie van het onderwerp in DAM. Totdat u een revisie van een pas gecreeerd onderwerp opslaat, zult u geen versieaantal in de Geschiedenis van de Versie zien. Als u het onderwerp voor het uitgeven opent, wordt de versieinformatie getoond in de juiste hoogste hoek van het onderwerpdossier tabel:

   ![](images/topic-version-none_cs.png){width="550" align="left"}

   De versieinformatie voor een nieuw gecreeerd onderwerp wordt getoond zoals *none*. Wanneer u een nieuwe versie opslaat, krijgt deze een versienummer toegewezen als 1.0. Voor meer informatie over het opslaan van een nieuwe versie raadpleegt u [Opslaan als nieuwe versie](web-editor-features.md#save-as-new-version-id209ME400GXA).


>[!NOTE]
>
> Als uw beheerder uw Redacteur van het Web heeft gevormd om dossiers uit te checken alvorens uit te geven, dan zult u niet een dossier kunnen uitgeven tot u het uitcheckt. Op dezelfde manier, als gevormd, zult u worden gevraagd om het even welk uitgecheckt dossier in te checken alvorens het te sluiten.

>[!IMPORTANT]
>
> Zodra u uw onderwerp DITA hebt gecreeerd, houd sparen de veranderingen in uw het werk exemplaar en creeer een nieuwe versie zodra u de updates aan uw onderwerp hebt voltooid.

**Bovenliggend onderwerp:**[ Onderwerpen maken en voorvertonen](create-preview-topics.md)
