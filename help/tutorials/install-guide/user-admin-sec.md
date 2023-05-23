---
title: Beheer en beveiliging van gebruikers
description: Leer hoe gebruikersbeheer en beveiliging werken
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 0%

---


# Beheer en beveiliging van gebruikers {#id181AED00G5Z}

Om tot eigenschappen in AEM Gidsen toegang te hebben en te vormen, moet u gebruikers creëren. Deze gebruikers kunnen dan toestemmingen worden toegewezen om tot alle of specifieke eigenschappen in AEM Gidsen toegang te hebben. Leer hoe te om gebruikersvergunning te vormen en te handhaven en ook de theorie achter te begrijpen hoe de authentificatie en de vergunning in AEM werken.

De volgende onderwerpen in AEM documentatie zullen u helpen het gebruikersbeleid en veiligheid-gerelateerde concepten en eigenschappen begrijpen:

- [Gebruikers en groepen in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

- [Machtigingen in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

- [Gebruikers en groepen beheren](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

- [Machtigingen beheren](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


## Gebruikersgroepen die zijn gemaakt met AEM hulplijnen {#id181TF0K0MHT}

AEM de Gidsen verstrekt drie uit-van-de-doos groepen om verschillende taken in een DITA- project te beheren. Deze groepen zijn: *Auteurs*, *Revisoren*, en *Uitgevers*. Afhankelijk van de groep waaraan een gebruiker is gekoppeld, mogen deze specifieke taken uitvoeren. Zo kan het publiceren alleen worden uitgevoerd door een uitgever, maar niet door een auteur of een revisor. Op dezelfde manier kan een auteur een nieuw onderwerp tot stand brengen, en een recensent kan slechts een onderwerp herzien.

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
| Openen in FrameMaker | Ja |   | Ja |
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

## Aanvullende opmerkingen over gebruikersgroepen

De volgende lijst bevat enkele aanbevelingen en punten die betrekking hebben op gebruikersgroepen en de bijbehorende machtigingen:

- Als u wilt dat een gebruiker de vertalings- of revisiewerkstroom start, moet u ervoor zorgen dat de gebruiker lid is van de *Uitgevers* en *projecten-beheerders groep*.

- Gebruikers moeten beschikken over de machtigingen voor lezen, maken, verwijderen en wijzigen die beschikbaar zijn in de mappen voor de bron- en doeltaal waaraan zij moeten werken.

- Als u een project creeert, bent u de eigenaar van het project met *Uitgevers* machtigingen. Andere gebruikers in een project kunnen hun teamleden zien, taken creëren, of werkschema&#39;s tot stand brengen, moeten zij gelezen toegang hebben op `/home/users` en `/home/groups` knooppunten. Eén manier om leesrechten toe te staan `/home/users` en `/home/groups` knooppunten is door leestoegang te geven tot de `projects-users` groep.

- *Revisoren* U kunt tot revisiecommentaren over een onderwerp toegang hebben en toevoegen onder overzicht van de console van het Project of van de verbinding van het inbox bericht. Deze toegang is ook alleen beschikbaar tot de tijd dat de revisietaak is geopend.

- Standaard, *Uitgevers* krijgen toegang en machtigingen voor de volgende mappen in DAM:

   - ``/var/dxml``-\> Lezen en schrijven

   - `/content/dam/fmdita-outputs` -\> Lezen en schrijven

   - `/content/output/sites` -\> Lezen en schrijven

   U moet expliciete lees- en schrijfmachtigingen aan de uitgever geven als u een andere locatie gebruikt dan de hierboven vermelde standaardpublicatielocaties.

- Alle gebruikers onder *Auteurs*, *Revisoren*, en *Uitgevers* groepen hebben leestoegang voor alle inhoud in DAM.

- Machtigingen op mapniveau moeten aan gebruikers worden toegewezen via de pagina voor gebruikersbeheer.

- Als u wilt dat uw gebruikers zoekbewerkingen op DAM kunnen uitvoeren, maakt u van uw gebruikers een lid van de *stuwdammen* groep.

- Als u beheerdersrechten aan een gebruiker wilt geven, kunt u dit doen door deze toegang te geven via AEM standaardgroepen, zoals *beheerders*, *projectbeheerders*, of OSGI-configuratie \(Felix console\).

- Als u een gebruiker rechten wilt geven om een documentstatus te wijzigen, moet u de gebruiker toevoegen in het gedeelte over statusovergang van het documentstatusprofiel.

[1](#fnsrc_1) Indien *Auteurs* en *Uitgevers* worden uitgenodigd voor een evaluatie.[2](#fnsrc_2) Afhankelijk van de rechten die aan de gebruiker zijn verleend in het documentstatusprofiel.

