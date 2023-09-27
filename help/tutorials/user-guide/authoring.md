---
title: Inhoud beheren
description: Inhoud beheren en uw rollen en machtigingen in AEM hulplijnen identificeren. Leer de belangrijkste concepten van inhoudsbeheer en het werken met globale of omslag-vlakke profielen.
exl-id: d2fa31a7-a8ce-4d17-bd4e-0f51ea751dca
source-git-commit: 3cc7a9bf91881ed09173077be7d7fc7705295e4b
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 0%

---

# Inhoud beheren {#id164JBG0M0T1}

Voordat u begint met het maken van inhoud, moet u vertrouwd raken met enkele basisbeginselen van inhoudsbeheer in AEM hulplijnen. Begin vervolgens met het maken van verschillende gebruikersgroepen en het ordenen van uw middelen.

## Belangrijkste concepten

Enkele belangrijke concepten van inhoudsbeheer in AEM zijn:

**Beheer van bedrijfsmiddelen**

AEM Guides gebruikt AEM Digital Asset Management \(DAM\) om uw DITA-bestanden te beheren. De bestanden die u uploadt of incheckt in de DAM worden opgeslagen als digitale elementen. U kunt uw middelen in AEM Assets beheren en bewerken. Zie voor meer informatie over middelenbeheer [Elementen beheren](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=en).

**Koppelingsbeheer**

Verplaats of wijzig de naam van bestanden of wijzig de mapstructuur in de opslagplaats voor inhoud zonder dat u zich zorgen hoeft te maken over verbroken verwijzingen. Alle verwijzingen naar en van de beïnvloede inhoud worden automatisch bijgewerkt. Hiermee krijgt u waarschuwingen wanneer u inhoud verwijdert waarnaar elders wordt verwezen, om onbedoelde onderbrekingen te voorkomen.

**Versies beheren**

AEM hulplijnen bieden versiebeheer voor uw digitale middelen. U kunt deze functionaliteit gemakkelijk van een DITA auteurstoepassing van keus toelaten. Uw schrijvers toestaan de standaardfuncties voor versiebeheer uit te voeren, zoals inchecken en uitchecken.

Zie voor meer informatie over het maken van versies of het terugkeren naar een specifieke versie [Vertakking, terugkeren en volgende versies](web-editor-preview-topics.md#id193PG0Y051X).

**Systeemeigen DITA-verwerking**

Terwijl AEM Gidsen de structuur van uw DITA- dossiers handhaaft, laat het AEM ook toe om DITA te behandelen gebruikend elementenafbeelding om de elementen DITA aan AEM componenten in kaart te brengen. De native DITA-afhandeling wordt gebruikt in functies zoals onderwerpvoorvertoning, AEM Sites-publicatie en de revisieworkflows.

## Uw rol en machtigingen identificeren {#id181TF0K0MHT}

AEM Hulplijnen bevatten drie groepen die buiten de doos vallen. Deze groepen zijn: *Auteurs*, *Revisoren*, en *Uitgevers*. Afhankelijk van de groep waaraan u bent gekoppeld, hebt u machtigingen om specifieke taken uit te voeren, zoals in de onderstaande tabel wordt vermeld. Zo kan het publiceren alleen worden uitgevoerd door een uitgever, maar niet door een auteur of een revisor. Op dezelfde manier kan een auteur een nieuw onderwerp tot stand brengen, en een recensent kan slechts een onderwerp herzien.

>[!TIP]
>
> Zie de *Machtigingen* in de gids met aanbevolen procedures voor aanbevolen procedures voor het instellen van gebruikersmachtigingen.

De volgende lijst maakt een lijst van diverse taken en de groepen die die taken kunnen uitvoeren:

| Taak | Auteurs | Revisoren | Uitgevers |
|----|-------|---------|----------|
| DITA-onderwerp maken | Ja |   | Ja |
| DITA-kaart maken | Ja |   | Ja |
| Verzamelingen toewijzen | Ja |   | Ja |
| Revisietaak maken | Ja |   | Ja |
| Revisieonderwerp[1](#fntarg_1) | Ja | Ja | Ja |
| Belangrijkste resolutie | Ja |   | Ja |
| Uitchecken/Inchecken | Ja |   | Ja |
| Onderwerp bewerken | Ja |   | Ja |
| Onderwerp verplaatsen | Ja |   | Ja |
| Eigenschappen van onderwerp bewerken | Ja |   | Ja |
| Kopiëren | Ja |   | Ja |
| Verwijderen | Ja |   | Ja |
| Delen | Ja |   | Ja |
| **Documentstatus** |
| Profiel documentstatus maken/bewerken |   |   | Ja |
| Documentstatus wijzigen[2](#fntarg_2) | Ja | Ja | Ja |
| **Functies beschikbaar in DITA-kaartconsole \(tabblad Uitvoervoorinstellingen\)** |
| Genereren |   |   | Ja |
| Bewerken |   |   | Ja |
| Dupliceren |   |   | Ja |
| Maken |   |   | Ja |
| Voorinstelling verwijderen |   |   | Ja |
| **Functies beschikbaar in DITA-kaartconsole \(tabblad Uitvoer\)** |
| Gegenereerde uitvoer weergeven | Ja |   | Ja |
| **Functies beschikbaar in DITA-kaartconsole \(tabblad Onderwerpen\)** |
| Revisietaak maken | Ja |   | Ja |
| Bewerken | Ja |   | Ja |
| **Functies beschikbaar in DITA-kaartconsole \(tabblad Basislijnen\)** |
| Maken |   |   | Ja |
| Bewerken |   |   | Ja |
| Dupliceren |   |   | Ja |
| Verwijderen |   |   | Ja |
| DITA-kaartconsole \(tabblad Rapporten\) | Ja |   | Ja |
| **Functies beschikbaar in DITA-kaartconsole \(Voorinstellingen voorwaarde\)** |
| Voorinstelling voorwaarde maken/bewerken |   |   | Ja |

[1](#fnsrc_1) Indien *Auteurs* en *Uitgevers* worden uitgenodigd voor een evaluatie.

[2](#fnsrc_2) Afhankelijk van de rechten die aan de gebruiker zijn verleend in het documentstatusprofiel.

## Voorwaarden voor het ontwerpen van inhoud

**Werken met algemene profielen of mapprofielen**

In een onderneming, kunnen de verschillende groepen of de producten verschillende auteursmalplaatjes, outputmalplaatjes, voorwaardelijke attributenprofielen \ (of onderwerpregelingen \), en de configuraties van de Redacteur van het Web gebruiken. Als u deze alleen op ondernemingsniveau \(of algemeen\) configureert, kunnen auteurs problemen ondervinden omdat ze sjablonen of profielen zien die voor hen niet relevant zijn.

Met AEM hulplijnen kunt u ontwerpsjablonen \(onderwerp of kaart\), uitvoersjablonen, voorwaardelijke kenmerken en webeditorconfiguraties op ondernemingsniveau \(algemeen\) en op mapniveau configureren. Op deze manier kunt u de configuraties voor verschillende afdelingen of producten in uw onderneming van elkaar scheiden.

Ook, kunt u de omslag-specifieke configuraties aan een afdeling of productbeheerders delegeren om het beleid te decentraliseren.

Voor meer informatie over het instellen van algemene profielen en mapprofielen raadpleegt u *Profielen op algemeen niveau of mapniveau configureren* in Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.
