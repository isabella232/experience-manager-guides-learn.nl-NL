---
title: Voorinstelling ePub
description: Leer hoe u een voorinstelling voor EPUB maakt via het kaartdashboard. Configureer de uitvoervoorinstelling EPUB in AEM hulplijnen.
exl-id: 19425ed2-fd7e-49c2-8f84-fc559a1db81b
source-git-commit: 8504a0a52d381044bf1f0d6e7de3585ebecf3a7b
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 0%

---

# EPUB {#id205BED020YT}

U kunt de voorinstelling EPUB maken via het kaartdashboard.

>[!NOTE]
>
> U kunt de methode kiezen om HTML5 te produceren gebruikend DITA-OT of FMPS \(als uw systeembeheerder het \) heeft gevormd.

Als u uitvoervoorinstellingen voor EPUB wilt openen, klikt u op een DITA-toewijzingsbestand. Klik vervolgens op Voorinstellingen uitvoer en klik vervolgens op de optie EPUB. De volgende opties zijn beschikbaar voor de Output van EPUBS:

| Opties voor ePub | Beschrijving |
| --- | --- |
| Uitvoertype | Het type uitvoer dat u wilt genereren. Kies de optie EPUB om uitvoer van EPUBS te genereren. |
| Naam instellen | Geef een beschrijvende naam voor de uitvoerinstellingen voor EPUB die u maakt. U kunt bijvoorbeeld _Uitvoer van interne klanten_ of _eindgebruikeruitvoer_. |
| Argumenten DITA-OT-opdrachtregel | Geef de aanvullende argumenten op die u tijdens het genereren van uitvoer wilt laten verwerken door DITA-OT. Zie voor meer informatie over de opdrachtregelargumenten die worden ondersteund in DITA-OT [DITA-OT-documentatie](https://www.dita-ot.org/). |
| EPubs genereren met | Selecteer DITA-OT om de uitvoer van het EPUB te genereren. |
| Voorwaarden toepassen met | Selecteer een van de volgende opties:<br><br>* **Niets toegepast**: Selecteer deze optie als u geen voorwaarde wilt toepassen op de gepubliceerde uitvoer.<br>* **DITAVal-bestand**: Selecteer DITAVal-bestand(en) om gepersonaliseerde inhoud te genereren. U kunt meerdere DITAVal-bestanden selecteren via het dialoogvenster Bladeren of door een bestandspad te typen. Gebruik het kruispictogram bij de bestandsnaam om het te verwijderen. DITAVal-bestanden worden in de opgegeven volgorde geëvalueerd, zodat de voorwaarden die in het eerste bestand zijn opgegeven voorrang hebben op de voorwaarden die in latere bestanden worden vermeld. U kunt de bestandsvolgorde behouden door bestanden toe te voegen of te verwijderen. Als het DITAVal-bestand naar een andere locatie wordt verplaatst of wordt verwijderd, wordt het niet automatisch verwijderd van het kaartdashboard. U moet de locatie bijwerken als bestanden worden verplaatst of verwijderd. U kunt de muisaanwijzer boven de bestandsnaam plaatsen om het pad te zien in de AEM opslagplaats waar het bestand is opgeslagen. U kunt alleen DITAVal-bestanden selecteren en er wordt een fout weergegeven als u een ander bestandstype hebt geselecteerd. FrameMaker Publishing Server ondersteunt geen meerdere DITAVAL-bestanden.<br>* **Voorinstelling voorwaarde**: Selecteer een voorinstelling voor de voorwaarde in het keuzemenu om een voorwaarde toe te passen tijdens het publiceren van de uitvoer. De optie is zichtbaar als u een voorwaarde hebt toegevoegd op het tabblad Voorinstellingen voorwaarde van de DITA-kaartconsole. Zie voor meer informatie over voorinstellingen voor voorwaarden [Voorinstellingen voor voorwaarden gebruiken](generate-output-use-condition-presets.md#id1825FL004PN). |
| Doelpad | Het pad in uw AEM opslagplaats waar de uitvoer van het EPUB wordt opgeslagen. |
| Bestandsnaam | Geef de bestandsnaam op waarmee u de uitvoer van de EPUBS wilt opslaan.<br><br>**Opmerking**: Als u geen bestandsnaam opgeeft, wordt de titel van de DITA-kaart gebruikt om de uiteindelijke naam van het uitvoerbestand voor EPUBS te genereren. Als de kaart geen titel heeft, dan wordt de het dossiernaam van de kaart DITA gebruikt om de definitieve output van de EPUB te noemen. De bestandsnaam wordt ontsmet volgens de regels die in het systeem zijn geconfigureerd voor het verwerken van elk ongeldig teken. |
| Transformatienaam | Geef het type uitvoer op dat u wilt genereren. Dit is vereist als u uitvoer wilt genereren met uw eigen aangepaste plug-in, die is geïntegreerd in de DITA-OT-plug-in. Als u bijvoorbeeld XHTML-uitvoer wilt genereren, geeft u `xhtml`. Voor een lijst van transformaties beschikbaar in DITA-OT, zie [DITA-OT-transformaties (uitvoerindelingen)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.md) in OASIS DITA-OT User Guide. |
| Tijdelijke DITA-OT-bestanden opschonen | Selecteer deze optie als u de tijdelijke bestanden die door DITA-OT worden gegenereerd, wilt opschonen. De plaats waar DITA-OT tijdelijke dossiers opslaat kan in het logboek van de outputgeneratie worden gevonden.<br><br>Als er fouten optreden bij het genereren van uitvoer via DITA-OT, kunt u deze optie uitschakelen om de tijdelijke bestanden te behouden. Vervolgens kunt u deze bestanden gebruiken om fouten met uitvoergeneratie op te lossen. |
| Workflow na generatie uitvoeren | Wanneer u deze optie kiest, wordt een nieuwe vervolgkeuzelijst Werkstroom na generatie weergegeven met alle werkstromen die in AEM zijn geconfigureerd. U moet een werkstroom selecteren die u wilt uitvoeren nadat de werkstroom van de outputgeneratie is voltooid.<br><br>**Opmerking**: Zie voor meer informatie over het maken van een aangepaste workflow voor het genereren van na de uitvoer _Workflow voor het genereren na uitvoer aanpassen_ in Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service. |
| Basislijn gebruiken | Als u een basislijn voor de geselecteerde kaart hebt gecreeerd DITA, selecteer deze optie om de versie te specificeren die u wilt publiceren.<br><br>Zie [Werken met basislijn](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) voor meer details. |
| Eigenschappen | Selecteer de eigenschappen die u als metagegevens wilt verwerken. Deze eigenschappen worden ingesteld op de pagina Eigenschappen van de DITA-kaart of het bladwijzerbestand. De eigenschappen die u in de vervolgkeuzelijst selecteert, worden onder het veld Eigenschappen weergegeven en uit de vervolgkeuzelijst verwijderd. Zodra reeks, worden deze eigenschappen ook gekopieerd in de onderwerpen binnen de kaart.<br><br>**Opmerking**: U kunt de metagegevens ook doorgeven aan de uitvoer met DITA-OT-publicatie. Zie voor meer informatie [Geef de metagegevens door aan de uitvoer met DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Bovenliggend onderwerp:**[ Uitvoervoorinstellingen](generate-output-understand-presets.md)
