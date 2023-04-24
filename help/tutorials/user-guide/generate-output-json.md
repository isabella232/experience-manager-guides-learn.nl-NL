---
title: JSON
description: Leer hoe u JSON gebruikt
source-git-commit: 8b6294425c6e60d1c5b37d98e99114014a104ee6
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---


# JSON {#id231KK0180T4}

U kunt de JSON-voorinstelling maken in de webeditor:

Open in het deelvenster Opslagplaats het DITA-toewijzingsbestand in de Kaartweergave en selecteer vervolgens op het tabblad Uitvoer het pictogram + om een uitvoervoorinstelling te maken. Selecteer vervolgens JSON in het keuzemenu Type in het dialoogvenster Voorinstelling toevoegen.

In de redacteur van het Web, zijn de volgende configuraties georganiseerd onder **Algemeen** tab:

- Uitvoerpad
- Indexbestand
- Voorwaarden toepassen met \(als de voorwaarden voor een kaart zijn gedefinieerd\)
- Basislijn gebruiken \(als een basislijn is gemaakt voor een kaart\)
- Eigenschappen die in de uitvoer moeten worden doorgevoerd
- Workflow na generatie

Zie voor meer informatie [JSON-configuratie](#id231KJA00REJ).

**Van het kaartdashboard**

Als u uitvoervoorinstellingen voor PDF wilt openen, klikt u op een DITA-toewijzingsbestand in de interface Middelen, klikt u op Voorinstellingen uitvoer en vervolgens op de optie HTML5. Klik in het dashboard Kaart op **Bewerken** bovenaan om de verschillende configuraties bij te werken, en klik dan **Opslaan**.

**JSON-configuratie**

De volgende opties zijn beschikbaar voor de JSON-voorinstelling:

>[!NOTE]
>
> U kunt het JSON-bestand ook bewerken in de webeditor.

| JSON-uitvoeropties | Beschrijving |
| --- | --- |
| Uitvoerpad | Het pad in uw AEM opslagplaats waar de JSON-uitvoer wordt opgeslagen. |
| Indexbestand | U kunt een naam geven voor het indexbestand dat u maakt voor de JSON-uitvoer. Standaard wordt de bestandsnaam van de DITA-kaart gekozen en wordt een achtervoegsel toegevoegd (zoals `map_filename_index.json`).<br><br>U kunt ook variabelen gebruiken bij het instellen van het indexbestand. Voor meer informatie over het gebruik van variabelen raadpleegt u [Variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam](generate-output-use-variables.md#id18BUG70K05Z). |
| Voorwaarden toepassen met | Selecteer een van de volgende opties:<br><br>* **Niets toegepast**: Selecteer deze optie als u geen voorwaarde wilt toepassen op de gepubliceerde uitvoer.<br>* **DITAVAL-bestand**: Selecteer DITAVAL-bestand(en) om gepersonaliseerde inhoud te genereren. U kunt meerdere DITAVAL-bestanden selecteren via het dialoogvenster Bladeren of door een bestandspad te typen. Gebruik het kruispictogram bij de bestandsnaam om het te verwijderen. DITAVAL-bestanden worden in de opgegeven volgorde geëvalueerd, zodat de voorwaarden die in het eerste bestand zijn opgegeven voorrang hebben op de voorwaarden die in latere bestanden worden vermeld. U kunt de bestandsvolgorde behouden door bestanden toe te voegen of te verwijderen. Als het DITAVAL-bestand naar een andere locatie wordt verplaatst of wordt verwijderd, wordt het niet automatisch verwijderd van het kaartdashboard. U moet de locatie bijwerken als bestanden worden verplaatst of verwijderd. U kunt de muisaanwijzer boven de bestandsnaam plaatsen om het pad te zien in de AEM opslagplaats waar het bestand is opgeslagen. U kunt alleen DITAVAL-bestanden selecteren en er wordt een fout weergegeven als u een ander bestandstype hebt geselecteerd.<br>* **Voorinstelling voorwaarde**: Selecteer een voorinstelling voor een voorwaarde in het keuzemenu om een voorwaarde toe te passen tijdens het publiceren van de uitvoer. De optie is zichtbaar als u een voorwaarde hebt toegevoegd op het tabblad Voorinstellingen voorwaarde van de DITA-kaartconsole. Zie voor meer informatie over voorinstellingen voor voorwaarden [Voorinstellingen voor voorwaarden gebruiken](generate-output-use-condition-presets.md#id1825FL004PN). |
| Basislijn gebruiken | Als u een basislijn voor de geselecteerde kaart hebt gecreeerd DITA, selecteer deze optie om de versie te specificeren die u wilt publiceren.<br><br>Zie [Werken met basislijn](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) voor meer details. |
| Eigenschappen die in de uitvoer moeten worden doorgevoerd | Selecteer de eigenschappen die u als metagegevens wilt verwerken. Deze eigenschappen worden ingesteld op de pagina Eigenschappen van de DITA-kaart of het bladwijzerbestand. De eigenschappen die u selecteert in de vervolgkeuzelijst, worden weergegeven onder het veld Eigenschappen.<br><br>**Opmerking**: U kunt ook aangepaste eigenschappen definiëren en de metagegevens doorgeven aan de uitvoer met DITA-OT-publicatie. Zie voor meer informatie [Werken met metagegevens](metadata-dita.md#id21BJ00QD0XA). |
| Workflow na generatie | Wanneer u deze optie kiest, wordt een nieuwe vervolgkeuzelijst Werkstroom na generatie weergegeven met alle werkstromen die in AEM zijn geconfigureerd. U moet een werkstroom selecteren die u wilt uitvoeren nadat de werkstroom van de outputgeneratie is voltooid.<br><br>**Opmerking**: Voor meer informatie over het creëren van een douane post-output generatiewerkschema, zie _Workflow voor het genereren na uitvoer aanpassen_ in de as a Cloud Service handleiding voor het installeren en configureren van Adobe Experience Manager-hulplijnen. |

**Bovenliggend onderwerp:**[ Uitvoervoorinstellingen](generate-output-understand-presets.md)

