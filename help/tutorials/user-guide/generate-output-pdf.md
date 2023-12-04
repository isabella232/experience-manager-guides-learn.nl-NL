---
title: PDF genereren
description: Leer hoe u een PDF-voorinstelling maakt in de webeditor en het kaartdashboard. Configureer de PDF-uitvoervoorinstelling in AEM hulplijnen.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 0%

---

# PDF {#id205BE600HAH}

U kunt de voorinstelling PDF op twee manieren maken:

**Vanuit de webeditor:** Open in het deelvenster Opslagplaats het DITA-toewijzingsbestand in Kaartweergave en selecteer vervolgens op het tabblad Uitvoer het pictogram + om een uitvoervoorinstelling te maken. Selecteer vervolgens PDF in het keuzemenu Type in het dialoogvenster Voorinstelling toevoegen.

>[!NOTE]
>
> U kunt de methode kiezen om PDF te produceren gebruikend DITA-OT, Inheemse PDF, of FMPS \(als uw systeembeheerder het \) heeft gevormd.

In de redacteur van het Web zijn de configuraties georganiseerd onder Algemene en Geavanceerde lusjes:

**Algemeen**

De **Algemeen** bevat de volgende configuraties:

- Uitvoerpad
- Argumenten DITA-OT-opdrachtregel
- Transformatienaam
- Bestandsnaam PDF
- Voorwaarden toepassen met \(als de voorwaarden voor een kaart zijn gedefinieerd\)
- Basislijn gebruiken \(als een basislijn is gemaakt voor een kaart\)
- Workflow na generatie

**Geavanceerd**

Het tabblad Geavanceerd bevat de volgende configuraties:

- Versiering inschakelen
- Tijdelijke DITA-OT-bestanden opschonen

Zie voor meer informatie [PDF-configuratie](#id231KIM004X1).

**Van het kaartdashboard**

Als u uitvoervoorinstellingen voor PDF wilt openen, klikt u op een DITA-toewijzingsbestand in de interface Middelen, klikt u op Uitvoervoorinstellingen en klikt u vervolgens op de optie PDF. Klik in het dashboard Kaart op **Bewerken** bovenaan om de verschillende configuraties bij te werken, en klik dan **Opslaan**.

**PDF-configuratie**

De volgende opties zijn beschikbaar voor de Uitvoer van PDF:

| PDF-opties | Beschrijving |
| --- | --- |
| Uitvoertype | Het type uitvoer dat u wilt genereren. Als u PDF-uitvoer wilt genereren, kiest u de optie PDF. |
| Naam instellen | Geef een beschrijvende naam voor de PDF-uitvoerinstellingen die u maakt. U kunt bijvoorbeeld _Uitvoer van interne klanten_ of _eindgebruikeruitvoer_. |
| Argumenten DITA-OT-opdrachtregel | Geef de aanvullende argumenten op die u tijdens het genereren van uitvoer wilt laten verwerken door DITA-OT. Zie voor meer informatie over de opdrachtregelargumenten die worden ondersteund in DITA-OT [DITA-OT-documentatie](https://www.dita-ot.org/). |
| Voorwaarden toepassen met | Selecteer een van de volgende opties:<br><br>* **Niets toegepast**: Selecteer deze optie als u geen voorwaarde wilt toepassen op de gepubliceerde uitvoer.<br>* **DITAVal-bestand**: Selecteer DITAVal-bestand(en) om gepersonaliseerde inhoud te genereren. U kunt meerdere DITAVal-bestanden selecteren via het dialoogvenster Bladeren of door een bestandspad te typen. Gebruik het kruispictogram bij de bestandsnaam om het te verwijderen. DITAVal-bestanden worden in de opgegeven volgorde geëvalueerd, zodat de voorwaarden die in het eerste bestand zijn opgegeven voorrang hebben op de voorwaarden die in latere bestanden worden vermeld. U kunt de bestandsvolgorde behouden door bestanden toe te voegen of te verwijderen. Als het DITAVal-bestand naar een andere locatie wordt verplaatst of wordt verwijderd, wordt het niet automatisch verwijderd van het kaartdashboard. U moet de locatie bijwerken als bestanden worden verplaatst of verwijderd. U kunt de muisaanwijzer boven de bestandsnaam plaatsen om het pad te zien in de AEM opslagplaats waar het bestand is opgeslagen. U kunt alleen DITAVal-bestanden selecteren en er wordt een fout weergegeven als u een ander bestandstype hebt geselecteerd. FrameMaker Publishing Server ondersteunt geen meerdere DITAVAL-bestanden.<br>* **Voorinstelling voorwaarde**: Selecteer een voorinstelling voor de voorwaarde in het keuzemenu om een voorwaarde toe te passen tijdens het publiceren van de uitvoer. De optie is zichtbaar als u een voorwaarde hebt toegevoegd op het tabblad Voorinstellingen voorwaarde van de DITA-kaartconsole. Zie voor meer informatie over voorinstellingen voor voorwaarden [Voorinstellingen voor voorwaarden gebruiken](generate-output-use-condition-presets.md#id1825FL004PN). |
| PDF genereren met | Selecteer DITA-OT om de PDF te genereren. |
| Workflow na generatie uitvoeren | Wanneer u deze optie kiest, wordt een nieuwe vervolgkeuzelijst Werkstroom na generatie weergegeven met alle werkstromen die in AEM zijn geconfigureerd. U moet een werkstroom selecteren die u wilt uitvoeren nadat de werkstroom van de outputgeneratie is voltooid.<br><br>**Opmerking**: Voor meer informatie over het creëren van een douanewerkschema van de post-output generatie, zie de werkschema&#39;s van de post-output van de generatie in installeer en vorm as a Cloud Service de Gidsen van Adobe Experience Manager. |
| Transformatienaam | Geef het type uitvoer op dat u wilt genereren. Dit is vereist als u uitvoer wilt genereren met uw eigen aangepaste plug-in, die is geïntegreerd in de DITA-OT-plug-in. Als u bijvoorbeeld XHTML-uitvoer wilt genereren, geeft u `xhtml`. Voor een lijst van transformaties beschikbaar in DITA-OT, zie [DITA-OT-transformaties (uitvoerindelingen)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) in OASIS DITA-OT User Guide. |
| Bestandsnaam | Geef de bestandsnaam op waarmee u de PDF wilt opslaan.<br><br>U kunt ook variabelen gebruiken wanneer u de bestandsnaam PDF instelt. Voor meer informatie over het gebruik van variabelen raadpleegt u [Variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Opmerking**: Als u geen bestandsnaam opgeeft, wordt de titel van de DITA-kaart gebruikt om de uiteindelijke naam van het PDF te genereren. Als de kaart geen titel heeft, dan wordt de het dossiernaam van de kaart DITA gebruikt aan naam de definitieve PDF. De bestandsnaam wordt ontsmet volgens de regels die in het systeem zijn geconfigureerd voor het verwerken van elk ongeldig teken. |
| Doelpad | Het pad in uw AEM opslagplaats waar de PDF is opgeslagen.<br><br>U kunt ook variabelen gebruiken bij het instellen van het bestemmingspad. Voor meer informatie over het gebruik van variabelen raadpleegt u [Variabelen gebruiken voor het instellen van de opties Doelpad, Sitenaam of Bestandsnaam](generate-output-use-variables.md#id18BUG70K05Z). |
| Tijdelijke DITA-OT-bestanden opschonen | Selecteer deze optie als u de tijdelijke bestanden die door DITA-OT worden gegenereerd, wilt opschonen. De plaats waar DITA-OT tijdelijke dossiers opslaat kan in het logboek van de outputgeneratie worden gevonden.<br><br>Als er fouten optreden bij het genereren van uitvoer via DITA-OT, kunt u deze optie uitschakelen om de tijdelijke bestanden te behouden. Vervolgens kunt u deze bestanden gebruiken om fouten met uitvoergeneratie op te lossen. |
| Basislijn gebruiken | Als u een basislijn voor de geselecteerde kaart hebt gecreeerd DITA, selecteer deze optie om de versie te specificeren die u wilt publiceren.<br><br>Zie [Werken met basislijn](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) voor meer details. |
| Eigenschappen | Selecteer de eigenschappen die u als metagegevens wilt verwerken. Deze eigenschappen worden ingesteld op de pagina Eigenschappen van de DITA-kaart of het bladwijzerbestand. De eigenschappen die u in de vervolgkeuzelijst selecteert, worden onder de **Eigenschappen** en worden verwijderd uit de vervolgkeuzelijst. Zodra reeks, worden deze eigenschappen ook gekopieerd in de onderwerpen binnen de kaart.<br><br>Opmerking: u kunt de metagegevens ook doorgeven aan de uitvoer met DITA-OT-publicatie. Zie voor meer informatie [Geef de metagegevens door aan de uitvoer met DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Bovenliggend onderwerp:**[ Uitvoervoorinstellingen](generate-output-understand-presets.md)
