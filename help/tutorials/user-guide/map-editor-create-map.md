---
title: Een kaart maken
description: Leer hoe u een kaart maakt
exl-id: d35ee09f-f951-4866-a2b1-e4b19f76e7a1
source-git-commit: 3bca42f0954afc2362ab24f369e698113324dbc3
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Een kaart maken {#id176FEN0D05Z}

AEM de Gidsen verstrekt twee out-of-the-box kaartmalplaatjes - kaart DITA en Bookmap. U kunt ook uw eigen kaartsjablonen maken en deze delen met uw auteurs om kaartbestanden te maken.

Voer de volgende stappen uit om een kaartbestand te maken:

1. Navigeer in de interface Elementen naar de locatie waar u het kaartbestand wilt maken.

1. Klikken **Maken** \> **DITA-kaart**.

1. Selecteer op de pagina Vervagen het type kaartsjablonen dat u wilt gebruiken en klik op **Volgende**.

   >[!NOTE]
   >
   > De manier waarop de onderwerpen in een kaartdossier worden bedoeld hangt van het kaartmalplaatje af. Als u bijvoorbeeld de sjabloon Kaart selecteert, verwijst het onderwerp naar \(`topicref`\) worden gebruikt om naar onderwerpen te verwijzen. In het geval van een Bookmap, worden de onderwerpverwijzingen gecreeerd gebruikend `chapter` element in DITA.

   ![](images/map-template.png){width="650" align="left"}

1. Geef op de pagina Eigenschappen de kaart op **Titel**.

1. \(Optioneel\) Geef het bestand op **Naam**.

   Als uw beheerder automatische bestandsnaam heeft geconfigureerd op basis van de UUID-instelling, ziet u geen optie om de bestandsnaam op te geven. Er wordt automatisch een op UUID gebaseerde bestandsnaam toegewezen aan het bestand.

   Als de optie voor het benoemen van bestanden beschikbaar is, wordt ook de naam automatisch voorgesteld op basis van de titel van uw kaart. Als u de naam van het kaartbestand handmatig wilt opgeven, moet u ervoor zorgen dat de bestandsnaam geen spaties, apostrof of accolades bevat en eindigt met `.ditamap`.

1. Klikken **Maken**.

   Het bericht Kaart gemaakt wordt weergegeven.

   Elk nieuw kaartbestand dat u maakt via de interface Middelen **Maken** \> **DITA-kaart** of de Redacteur van het Web wordt toegewezen een unieke kaartidentiteitskaart Bovendien wordt de nieuwe kaart opgeslagen als de meest recente werkkopie in DAM. Totdat u een revisie van een pas gemaakte kaart opslaat, ziet u geen versienummer in de Versiegeschiedenis. Als u de kaart opent om te bewerken, wordt de versie-informatie weergegeven in de rechterbovenhoek van het tabblad van het kaartbestand:

   ![](images/first-version-map-none.png){width="650" align="left"}

   De versieinformatie voor een pas gemaakte kaart wordt getoond zoals *none*. Wanneer u een nieuwe versie opslaat, krijgt deze een versienummer toegewezen als 1.0. Voor meer informatie over het opslaan van een nieuwe versie raadpleegt u [Opslaan als nieuwe versie](web-editor-features.md#save-as-new-version-id209ME400GXA).

   U kunt ervoor kiezen de kaart te openen om te bewerken in de geconfigureerde kaarteditor, of het kaartbestand op te slaan in de AEM opslagplaats.

   >[!NOTE]
   >
   > Om de Geavanceerde Redacteur van de Kaart te gebruiken, heb toegang tot het kaartdossier in de Redacteur van het Web. Als uw beheerder de Geavanceerde Redacteur van de Kaart als standaardredacteur in de kaartdossiers heeft gevormd, dan wordt het kaartdossier geopend direct in de Geavanceerde Redacteur van de Kaart voor het uitgeven. Zie *De Geavanceerde Kaarteditor instellen als standaard* in de sectie Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.


**Bovenliggend onderwerp:**[ Werken met de Kaarteditor](map-editor.md)
