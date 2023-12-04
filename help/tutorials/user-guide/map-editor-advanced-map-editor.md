---
title: Werken met de Geavanceerde Kaarteditor
description: Leer hoe u met de geavanceerde kaarteditor in AEM hulplijnen werkt. Ken de eigenschappen van de geavanceerde Redacteur van de Kaart. Bewerk onderwerpen via een DITA-kaart en gebruik de layoutweergave, de auteurweergave en de voorvertoningsmodus.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '3695'
ht-degree: 0%

---

# Werken met de Geavanceerde Kaarteditor {#id1942D0S0IHS}

De Geavanceerde Redacteur van de Kaart komt met intuïtieve gebruikersinterface en het is gelijkaardig aan de Redacteur van het Web. Wanneer u een kaartdossier in de Redacteur van het Web opent, krijgt u een optie om het kaartdossier uit te geven gebruikend de Geavanceerde interface van de Redacteur van de Kaart. Met de Geavanceerde Kaarteditor kunt u onderwerpverwijzingen, zeer belangrijke verwijzingen, structuur uw inhoud en meer toevoegen.

Naast het uitgeven van kaartdossiers direct van de Redacteur van het Web, kunt u onderwerpdossiers in een kaart ook openen voor het uitgeven van de Redacteur van het Web. Dit onderwerp begeleidt u door de eigenschappen in de Geavanceerde Redacteur van de Kaart en hoe u dossiers in een kaart DITA in de Redacteur van het Web kunt openen en uitgeven.

## Onderwerpen toevoegen aan een kaartbestand

Voer de volgende stappen uit om uw kaartdossier te bouwen gebruikend de Geavanceerde Redacteur van de Kaart:

1. Navigeer in de interface Elementen naar het kaartbestand dat u wilt bewerken.

   >[!NOTE]
   >
   > Zorg ervoor dat de modus voor het selecteren van elementen niet is ingeschakeld.

1. Als u het kaartbestand exclusief wilt vergrendelen, selecteert u het kaartbestand en klikt u op **Uitchecken**.

   >[!NOTE]
   >
   > Als u eenmaal een exclusief kaartbestand hebt vergrendeld, kunnen andere gebruikers de kaart niet meer bewerken. Ze kunnen echter wel aan de onderwerpen in het kaartbestand werken. Als uw beheerder uw Redacteur van het Web aan controledossiers vóór het uitgeven heeft gevormd, dan zult u niet een dossier kunnen uitgeven tot u het controleert. Op dezelfde manier, als gevormd, zult u worden gevraagd om het even welk uitgecheckt dossier te controleren alvorens het te sluiten

1. Selecteer het kaartbestand en klik op **Onderwerpen bewerken**.

   ![](images/edit-map-main-menu.png){width="800" align="left"}

   U kunt ook de opdracht **Onderwerpen bewerken** optie in het menu Handeling in het kaartbestand:

   ![](images/edit-map-action-menu.png){width="800" align="left"}

   Het kaartdossier wordt geopend voor het uitgeven in in de Redacteur van het Web.

1. Klik op de knop **Bewerken** pictogram.

   ![](images/edit-map-icon.png){width="550" align="left"}

   De kaart wordt geopend in de Geavanceerde interface van de Redacteur van de Kaart. Als u een nieuw kaartdossier hebt geopend, dan slechts wordt de titel van de kaart getoond in de redacteur.

   ![](images/new-map-file-in-editor.png){width="800" align="left"}

   - **A** - \(*Hoofdwerkbalk*\): Dit is vergelijkbaar met de hoofdwerkbalk van de webeditor. Zie [Hoofdwerkbalk](web-editor-features.md#id2051EA0G05Z) in de Redacteur van het Web voor meer details.

   - **B** - \(*Secundaire werkbalk*\) Dit is de secundaire werkbalk waarmee u kunt werken met kaartbestanden. Zie voor meer informatie over de functies die beschikbaar zijn via de secundaire werkbalk [Functies beschikbaar op de werkbalk van de Geavanceerde Kaarteditor](#id205DEC0005Z).

   - **C** - \(*Weergaven toewijzen*\): Hiermee kunt u in de Kaarteditor schakelen tussen Indeling, Auteur, Bron en Voorvertoning. De **Layout** staat u toe om de onderwerpen in een kaart te organiseren DITA. Dit geeft de boom of de hiërarchische mening van de kaart. De **Auteur** de mening staat u toe om de onderwerpen in de Redacteur van de Kaart uit te geven. Dit geeft ook de WYSIWYG mening van het kaartdossier. De **Bron** kunt u met de onderliggende XML van het kaartbestand werken. De Voorproef geeft u een geconsolideerde mening van al onderwerp en submaps binnen het kaartdossier. De **Sluiten** Hiermee sluit u het kaartbestand.

   - **D** - \(*Linkerdeelvenster*\): Geeft toegang tot het linkerpaneel dat u toegang tot Favorieten, Bewaarplaats, Kaart, Overzicht en andere eigenschappen verleent. U kunt het uit- of samenvouwen door te klikken op het pictogram Zijbalk uitvouwen \(![](images/sidebar-expand-icon.svg)\). Ga voor meer informatie over de functies in het linkerdeelvenster naar [Deelvenster Links](web-editor-features.md#id2051EA0M0HS) in de webeditor.

   - **E** - \(*Midden gebied*\): gebied voor het bewerken van inhoud toewijzen.

   - **F** - \(*Rechterdeelvenster*\): geeft toegang tot het deelvenster Eigenschappen. U kunt de inhoudseigenschappen en de kaarteigenschappen van het geselecteerde onderwerp of de kaart zien. Zie voor meer informatie over de functies in dit deelvenster [Rechterdeelvenster](web-editor-features.md#id2051EB003YK) in de webeditor.

1. Schakel in het linkerdeelvenster over naar het **Weergave opslagplaats**.

1. Navigeer in de AEM naar de map die de onderwerpen of submaps bevat die u wilt toevoegen.

1. Selecteer het onderwerp- of kaartbestand in het dialoogvenster **Weergave opslagplaats** en sleep deze naar het bewerkingsgebied van de \(middelste\) kaart-inhoud.

   Het onderwerp wordt toegevoegd in de kaart.

   ![add-onderwerp kaarteditor](images/map-editor-add-topic.png){width="800" align="left"}

1. Als u volgende onderwerpen of een submap wilt toevoegen, sleept u het onderwerp of de submap naar de gewenste locatie in de kaart en zet u deze neer.

   Houd rekening met de volgende punten bij het samenstellen van uw kaartbestand:

   - Het bestand wordt toegevoegd op een locatie waar de horizontale balk wordt weergegeven in het kaartbewerkingsgebied. In de volgende screenshot *Overzicht* onderwerp wordt toegevoegd tussen *Algemene beschrijving* en *Starten en aanlanden* onderwerpen.

     ![](images/horizontal-line-in-adv-map-editor.png){width="350" align="left"}

   - Als u een onderwerp wilt vervangen, plaatst u het onderwerp boven, links of rechts van het onderwerp dat u wilt vervangen. Een verticale bar links of rechts van een onderwerp wijst erop dat het met het onderwerp zal worden vervangen dat op het wordt gelaten vallen.

     ![](images/vertical-bar-left-right.png){width="550" align="left"}

     Nochtans, alvorens een onderwerp te vervangen, krijgt u een bevestigingsherinnering. Het onderwerp wordt pas vervangen nadat u de bevestiging hebt gegeven.

     ![](images/replace-topic-confirm.png){width="300" align="left"}

   - Als u een sub-kaart aan uw kaart DITA toevoegt, wordt submap getoond als verbinding in de kaart DITA. Als u alle onderwerpen van de submap wilt weergeven, houdt u Ctrl ingedrukt en klikt u op de koppeling voor de submap. De inhoud van de submap wordt weergegeven op een nieuw tabblad. Op dezelfde manier om een onderwerp van de kaart te openen DITA, Crtl+Klik de onderwerpverbinding en het opent omhoog in het nieuwe lusje.

   - U kunt de sneltoetsen CTRL+Z en CTRL+Y of de respectieve pictogrammen in de werkbalk gebruiken om wijzigingen in de kaart ongedaan te maken of opnieuw uit te voeren.

   - Om de positie van een onderwerp te veranderen, selecteer het onderwerp \ (door op het onderwerppictogram te klikken \), dan belemmering-en-daling het bij de gewenste plaats in het kaartdossier. Zorg ervoor dat de horizontale bar bij de plaats zichtbaar is waar u het onderwerp wilt plaatsen. In het volgende schermafbeelding, het onderwerp *Starten en aanlanden* wordt verplaatst na de *Overzicht* onderwerp.

     ![](images/move-topic-adv-map-editor.png){width="350" align="left"}

   - Als u de eigenschappen van het kaartbestand wilt controleren, klikt u met de rechtermuisknop ergens in het kaartbewerkingsgebied en kiest u **Eigenschappen** in het contextmenu. Op basis van uw AEM kunt u eigenschappen zien zoals metagegevens, het plannen van \(de\)activering, verwijzingen, documentstatus en meer.

1. Klikken **Opslaan**.


## Functies beschikbaar op de werkbalk van de Geavanceerde Kaarteditor {#id205DEC0005Z}

De toolbar in de Geavanceerde Redacteur van de Kaart is gelijkaardig aan de Redacteur van het onderwerpWeb. De basisbewerkingen zoals het in- en uitschakelen van het linkerdeelvenster, het opslaan van een kaart, het maken van een nieuwe versie van de kaart, het ongedaan maken/opnieuw uitvoeren van de laatste bewerking en het verwijderen van de geselecteerde elementen komen in beide editors veel voor. Zie voor meer informatie over hoe deze bewerkingen werken [De functies van de webeditor kennen](web-editor-features.md#) sectie.

De volgende kaartspecifieke bewerkingen zijn ook beschikbaar op de werkbalk in de layoutweergave en de weergave Auteur:

## Layoutweergave {#id205DEC0005Z_layout_view}

Wanneer u een kaart opent om te bewerken, wordt de layoutweergave van de Kaarteditor geopend. In de layoutweergave wordt de kaarthiërarchie in een boomstructuurweergave weergegeven en kunt u de onderwerpen in een kaart ordenen.

>[!NOTE]
>
> In de layoutweergave worden alleen de verwijzingen weergegeven die zich in een kaart bevinden. Als verwijzingen worden verbroken, wordt links van de verwijzing een klein kruissymbool weergegeven

U kunt de volgende taken uitvoeren in de layoutweergave:

**Onderwerpverwijzing invoegen** - ![](images/insert-topic-reference.png)

Toont de dialoog van het onderwerponderzoek. Navigeer naar het onderwerp-/kaartbestand dat u wilt invoegen en klik op Selecteren om het toe te voegen aan de kaart.
![](images/insert-topic-reference-dialog.png){width="800" align="left"}


**Onderwerpgroep invoegen** - ![](images/insert-topic-group.png)

Voeg de `topicgroup` element. Voor meer informatie over het groeperen van onderwerpen, zie [onderwerpgroep](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) documentatie in OASIS DITA Language Specification.

**Toetsdefinitie invoegen** - ![](images/Key_icon.svg)

Hiermee wordt het dialoogvenster Keydef invoegen weergegeven. In dit dialoogvenster kunt u een sleuteldefinitie definiëren die u wilt gebruiken in de kaart.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Voor/Invoegen na** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Hiermee geeft u het dialoogvenster Element invoegen weer. Selecteer het element dat u op de kaart wilt invoegen. Afhankelijk van de bewerking wordt het nieuwe element ingevoegd voor of na het huidige element op de kaart.

**Voorste rand invoegen** - ![](images/frontmatter.svg)

Dit pictogram wordt weergegeven wanneer u een bladwijzer opent voor bewerking. U kunt componenten aan het begin van het boek invoegen, zoals een inhoudsopgave, een index en een lijst met tabellen.

**Achterste item invoegen** - ![](images/backmatter.svg)

Dit pictogram wordt weergegeven wanneer u een bladwijzer opent voor bewerking. U kunt componenten voor een eind van het boek als een Index, een Verklarende woordenlijst, en een Lijst van Cijfers opnemen.

**Geselecteerd item naar links/rechts verplaatsen** - ![](images/left-arrow-icon.png) / ![](images/right-arrow-icon.png)

Klik op de pijl naar links om het onderwerp naar links in de hiërarchie te verplaatsen. Dit bevordert hoofdzakelijk het respectieve onderwerp één niveau omhoog in de hiërarchie. Als u bijvoorbeeld op de pijl naar links klikt terwijl een onderliggend onderwerp is geselecteerd, wordt dit het onderwerp erboven op hetzelfde niveau. Op dezelfde manier als u de juiste pijl klikt, wordt het onderwerp geduwd in de richting van de juiste kant die het het kind van het onderwerp boven het maken.

**Geselecteerd item omhoog/omlaag verplaatsen![](images/arrowup.svg)** - / ![](images/arrowdown.svg)

Klik op de pictogrammen voor pijl-omhoog of pijl-omlaag om het onderwerp omhoog of omlaag te verplaatsen in de hiërarchie.

>[!NOTE]
>
> U kunt de verwijzingen ook slepen en neerzetten om ze in een kaart te verplaatsen.

**Vergrendelen/Ontgrendelen** - ![](images/LockClosed_icon.svg) / ![](images/LockOpen_icon.svg)

Hiermee wordt een vergrendeling op het kaartbestand opgehaald en wordt de vergrendeling opgeheven. Als uw kaartbestand niet-opgeslagen wijzigingen bevat en u het vergrendelingsbestand vervolgens loslaat, wordt u gevraagd het kaartbestand op te slaan. De wijzigingen worden opgeslagen in de huidige versie van het kaartbestand.

**Samenvoegen** - ![](images/merge-icon.svg)

Ga voor meer informatie over het samenvoegen van inhoud uit een andere versie van hetzelfde of een ander bestand naar [Samenvoegen](web-editor-features.md#id205DF04E0HS) in de webeditor.

**Versiehistorie** - ![](images/version-history-web-editor-ico.svg)

Controleer de beschikbare versies en de etiketten op uw actieve onderwerp, en keer aan om het even welke versie van de redacteur zelf terug.

**Versielabel** - ![](images/version-label-icon.svg)

Hiermee geeft u het dialoogvenster voor versielabel weer. Selecteer een versie in de vervolgkeuzelijst. Kies het label dat u op de geselecteerde versie wilt toepassen en klik op **Label toevoegen** toevoegen.

**Weergaveopties** - ![](images/view-options.svg)

Hiermee wordt een vervolgkeuzelijst weergegeven waarin u de optie Regelnummers weergeven, Selectievakje tonen en Bestandsnaam tonen kunt kiezen.

- **Regelnummers tonen**

Hiermee toont of verbergt u het regelnummer voor elk onderwerp. De regelnummers worden weergegeven, afhankelijk van het niveau in de hiërarchie.

- **Selectievakje tonen**

Toont of verbergt checkbox voor elk onderwerp. U kunt het selectievakje gebruiken om het onderwerp te selecteren en verschillende taken uit te voeren via het menu Opties. Zie voor meer informatie de [Opties](#id228ID8006H8) -menu.

- **Bestandsnaam tonen**

Toont filename van de titels van de onderwerpen.

>[!NOTE]
>
> Wanneer u de aanwijzer boven de titel van een onderwerp plaatst, wordt het bestandspad weergegeven.


**Onderwerpen weergeven op basis van voorwaardelijke filters** Als u om het even welke voorwaarden op een onderwerp hebt toegepast, wordt een filterpictogram getoond op het recht van het onderwerp. Wanneer u de aanwijzer boven een filterpictogram houdt, ziet u de toegepaste voorwaarde en de kenmerkwaarde.

**Het menu Opties in de layoutweergave**

Naast het organiseren van onderwerpen in het kaartdossier, kunt u de volgende acties ook uitvoeren gebruikend het menu van Opties beschikbaar voor een element in de mening van de Lay-out:

![](images/map-editor-options-menu.png){width="650" align="left"}

- **Toevoegen**: U kunt een nieuw onderwerp of een lege verwijzing toevoegen in de Kaarteditor:
   - **Lege referentie**: Met deze optie kunt u een lege verwijzing toevoegen aan uw DITA-kaart. U kunt de opgenomen lege verwijzing later tweemaal klikken en de details van het Onderwerp toevoegen. Zie voor meer informatie de [Een onderwerp maken](web-editor-features.md#id228ICI0105U) in de webeditor.
   - **Nieuw onderwerp**: Wanneer u een nieuw onderwerp maakt in het menu, wordt het dialoogvenster Nieuw onderwerp maken weergegeven. Geef in het dialoogvenster Nieuw onderwerp maken de vereiste gegevens op en klik op Maken. Zie voor meer informatie de [Een onderwerp maken](web-editor-features.md#id228ICI0105U) in de webeditor.
- **Verplaatsen**: U kunt ervoor kiezen een onderwerp omhoog/omlaag/naar rechts/naar links in de hiërarchie te verplaatsen.U kunt ook een onderwerp of een kaart van het paneel van de bewaarplaats naar de kaart slepen die in de Redacteur van de Kaart wordt geopend.
- **Ongedaan maken**: Maak de laatste bewerking in de layoutweergave ongedaan.
- **Opnieuw**: De laatste bewerking in de layoutweergave wordt opnieuw uitgevoerd.
- **Kopiëren**: Kopieer de geselecteerde verwijzing uit het kaartbestand.

  >[!NOTE]
  >
  > U kunt de selectievakjes weergeven en vervolgens selecteren om meerdere verwijzingen te kopiëren.

- **Plakken**: Plak de gekopieerde verwijzingen op de huidige locatie in de hiërarchie.
- **Verwijderen**: Verwijder de geselecteerde verwijzingen uit het kaartbestand.

  >[!NOTE]
  >
  > U kunt de selectievakjes weergeven en vervolgens selecteren om meerdere verwijzingen te verwijderen.


## Rechterdeelvenster in de Kaarteditor

In het rechterdeelvenster worden de eigenschappen Inhoud en Kaart weergegeven in de layoutweergave van de Kaarteditor.

**Eigenschappen van inhoud**

Het deelvenster Eigenschappen voor inhoud bevat informatie over het type onderwerp dat momenteel is geselecteerd in de kaart, de koppeling-URL en de kenmerken van het onderwerp. Zie voor meer informatie [Eigenschappen van inhoud](web-editor-features.md#id228IDB00HMM) in de webeditor.

- **Overige kenmerken** Als uw beheerder een profiel voor attributen heeft gecreeerd, dan zult u die attributen samen met hun gevormde waarden krijgen. Gebruikend het paneel van inhoudseigenschappen, kunt u die attributen kiezen en hen toewijzen aan relevante inhoud in uw onderwerp. U kunt ook attributen toewijzen die door uw beheerder onder **Weergavekenmerken** in de editorinstellingen. De kenmerken die voor een element zijn gedefinieerd, worden weergegeven in de layoutweergave en in de contourweergave. Dit helpt u om een snelle blik bij alle onderwerpen in een kaart te hebben waarvoor een bepaald attribuut wordt bepaald. Bijvoorbeeld alle onderwerpen waarvoor het platformkenmerk is gedefinieerd als &#39;Android&#39;.

  ![layoutweergave](images/layout-inline-attributes.png){width="650" align="left"}


  Zie voor meer informatie de *Weergavekenmerken* binnen de *Editor-instellingen* functiebeschrijving in het dialoogvenster [Linkerdeelvenster](web-editor-features.md#id2051EA0M0HS) sectie.

- **Metagegevens** Met de metagegevens kunt u de metagegevens instellen. U kunt de NAV-titel, Tekst koppelen, Korte beschrijving en Trefwoorden definiëren.

Voor meer informatie over de standaardonderwerpattributen en meta-gegevens, zie [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) documentatie in OASIS DITA Language Specification.

**Eigenschappen van kaart**

Hiermee geeft u het dialoogvenster Kaarteigenschappen weer waarin u de kenmerken en metagegevens voor de kaart kunt instellen.

## Auteursweergave {#id205DEC0005Z_author_view}

De **Auteur** de mening staat u toe om uw kaart DITA in de Redacteur van het Web uit te geven. Dit toont de WYSIWYG mening van de Redacteur van de Kaart en sommige pictogrammen die in de mening van de Auteur worden getoond zijn het zelfde als de mening van de Lay-out. Zie voor meer informatie [Layoutweergave](#id205DEC0005Z_layout_view). Bovendien kunt u de volgende pictogrammen zien en de verwante taken uitvoeren van de mening van de Auteur:

**Voor/Invoegen na** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Hiermee geeft u het dialoogvenster Element invoegen weer. Selecteer het element dat u op de kaart wilt invoegen. Afhankelijk van de bewerking wordt het nieuwe element ingevoegd voor of na het huidige element op de kaart.

**Element invoegen** - ![](images/Add_icon.svg)

Hiermee geeft u het dialoogvenster Element invoegen weer. Selecteer het element dat u wilt invoegen. U kunt het toetsenbord gebruiken om door de lijst van elementen te scrollen en te drukken binnengaan om het vereiste element op te nemen. U kunt ook rechtstreeks op het element klikken om het in de kaart in te voegen.

**Relatietabel invoegen** - ![](images/relationship_table_icon.svg)

Voegt een relatietabel in de kaart in. Aangezien het concept werken met de relatietabel gelijk is aan de beschrijving in de sectie Basic Map Editor, raadpleegt u [Werken met relatietabellen in de Basic Map Editor](map-editor-basic-map-editor.md#id1944B0I0COB) voor meer informatie .

**Herbruikbare inhoud invoegen** - ![](images/content-reuse-icon.png)

Hiermee geeft u het dialoogvenster Inhoud opnieuw gebruiken weer. In dit dialoogvenster kunt u de inhoud invoegen die u opnieuw wilt gebruiken op de kaart.

**Kenmerk navigatitel vernieuwen** - ![](images/navtitle-refresh-icon.svg)

Hiermee synchroniseert u de `title` element van een referenced dossier in een kaart met de waarde die in zijn wordt gespecificeerd `@navtitle` kenmerk. U kunt verschillende soorten verwijzingsdossiers in een kaart toevoegen, bijvoorbeeld onderwerp, verwijzing, taak, \(sub\) kaarten, etc. De meeste van deze bestanden ondersteunen de `@navtitle` kenmerk. Als een bestand de `@navtitle` kenmerk, dan de `@navtitle` wordt het kenmerk voor hetzelfde bestand op de kaart bijgewerkt. In het geval van `@navtitle` Het kenmerk is niet aanwezig, dan wordt het `@navtitle` wordt toegevoegd aan dat referentiebestand en de bijbehorende `title` wordt ook bijgewerkt om de `@navtitle`.

>[!NOTE]
>
> Uw beheerder kan automatisch toevoegen vormen `@navtitle` aan elk verwijzingsdossier dat u aan een kaart toevoegt. Voor meer details over het vormen auto-toevoegt `@navtitle` kenmerk, zie *@navtitle-kenmerk standaard opnemen* in Adobe Experience Manager-hulplijnen installeren en configureren as a Cloud Service.

Klik op het pictogram Kenmerk navigatitel vernieuwen om het dialoogvenster `title` elementen en `@navtitle` de waarden van het kenmerk.

**Tagweergave in-/uitschakelen** - ![](images/Label_icon.svg)

Hiermee toont of verbergt u de XML-labels. De tags dienen als visuele aanwijzingen die de grens van een element aangeven. Als u in deze modus een onderwerp-/kaartverwijzing wilt invoegen, sleept u het gewenste bestand voor of na de tag. De horizontale balk wordt niet weergegeven in de modus Codes weergeven.

**Wijzigingen bijhouden inschakelen/uitschakelen** - ![](images/track-change-icon.svg)

U kunt alle in het kaartbestand aangebrachte updates bijhouden door de modus Wijzigingen bijhouden in te schakelen. Nadat u wijzigingen in de track hebt ingeschakeld, worden alle invoegingen en verwijderingen vastgelegd in het document. Zie voor meer informatie [Wijzigingen bijhouden inschakelen/uitschakelen](web-editor-features.md#id205DF0203Y4) in de webeditor.

**Revisietaak maken** - ![](images/create-review-task-icon.svg)

U kunt een overzichtstaak van het huidige onderwerp of kaartdossier direct van de Redacteur van het Web tot stand brengen. Open het bestand waarvoor u de revisietaak wilt maken en klik op Revisietaak maken om het proces voor het maken van de revisie te starten. Volg de instructies in de [Onderwerpen of kaarten controleren](review.md#) voor meer informatie .

## Onderwerpen bewerken via de DITA-kaart {#id17ACJ0F0FHS}

Het uitgeven van een individueel onderwerp geeft niet de volledige context aan de auteur. Een auteur zou geen informatie over waar een onderwerp in een kaart DITA wordt geplaatst hebben. Zonder deze contextuele informatie wordt het voor auteurs een beetje moeilijk om inhoud te creëren.

AEM Gidsen staat auteurs toe om een kaart DITA in de Redacteur van het Web te openen en de plaatsing van onderwerpen binnen de kaart te zien. Dit helpt auteurs te weten waar precies het onderwerp binnen de kaart wordt geplaatst en relevantere inhoud tot stand te brengen. Ook, als er veelvoudige auteurs zijn die aan een project werken, kunnen zij weten welke alle onderwerpen in de kaart beschikbaar zijn en inhoud hergebruiken, waar nodig.

Ga als volgt te werk om onderwerpen te bewerken via een DITA-kaart:

1. In Elementen UI, navigeer aan de kaart DITA die de onderwerpen bevat die u wilt uitgeven.
1. Klik op de kaart DITA om het in DITA kaartconsole te openen.
1. Selecteer de **Onderwerpen** om een lijst van onderwerpen te zien beschikbaar in de kaart DITA.

   >[!TIP]
   >
   > Het lusje van Onderwerpen geeft u een optie om het kaartdossier met zijn gebiedsdelen te downloaden. Zie voor meer informatie [Een DITA-toewijzingsbestand exporteren](authoring-download-assets.md#id218UBA00IXA).

1. Klik in de hoofdwerkbalk op **Onderwerpen bewerken**.

   De kaart DITA opent in de Redacteur van het Web.

   >[!NOTE]
   >
   > U kunt ook het DITA-kaartbestand selecteren in de interface Middelen en op **Onderwerpen bewerken** in de hoofdwerkbalk om de webeditor te starten.

   ![](images/web-editor-map-view_cs.png){width="350" align="left"}

1. \(*Optioneel*\) U kunt ook een onderwerp op de kaart selecteren en het bestand uitchecken voordat u het gaat bewerken. Als u het bestand wilt uitchecken, selecteert u een of meer bestanden in het linkerdeelvenster en klikt u op **Afhandeling**. U kunt de vergrendeling ook op elk bestand loslaten door het uitgecheckte bestand te selecteren en op de knop **Afhandeling annuleren en ontgrendelen** in de Kaartweergave.

   >[!IMPORTANT]
   >
   > Als uw beheerder het **Bewerken uitschakelen zonder afhandeling** selecteert, moet u het bestand uitchecken voordat u het kunt bewerken. Als u het bestand niet uitcheckt, wordt het document in de editor geopend in de modus Alleen-lezen.

   In de volgende schermafbeelding worden de pictogrammen voor Uitchecken en vergrendelen \(A\), Uitchecken annuleren en ontgrendelen \(B\), Opslaan als nieuwe versie en Ontgrendelen \(C\), Bewerken \(D\), Voorvertoning \(E\), verschillende pictogrammen met verschillende DITA-bestandstypen \(F\) en bestanden die zijn uitgecheckt \(G\) gemarkeerd.

   ![](images/file-checkout-map-editor.png){width="550" align="left"}

1. Klik op om het even welke onderwerpverbinding om het in de Redacteur van het Web voor het uitgeven te openen.

   U kunt veelvoudige onderwerpen in de redacteur openen en elk onderwerp wordt geopend in een nieuw lusje in de redacteur. Zelfs als uw kaart DITA submaps bevat, worden de onderwerpen van sub-maps ook geopend in een nieuw lusje voor het uitgeven. Als u de onderwerpen onder een sub-kaart wilt bekijken, kunt u klikken en sub-kaart uitbreiden.

   ![](images/web-editor-multiple-topics.png){width="800" align="left"}

   Als u op een kaartbestand klikt, wordt de kaart geopend in een nieuw tabblad van de webbrowser.

1. Als u klaar bent met het bewerken van de onderwerpen, kunt u het volgende doen:

   - U kunt deze afzonderlijk opslaan. Als u op **Sluiten zonder opslaan** in uw onderwerpen wordt een dialoogvenster weergegeven waarin u wordt gevraagd de niet-opgeslagen onderwerpen op te slaan:

     ![](images/save-multiple-topics.PNG){width="550" align="left"}

     U kunt alle geselecteerde onderwerpen opslaan of de onderwerpen deselecteren die u niet wilt opslaan.

   - U kunt het onderwerp inchecken met de **Opslaan als nieuwe versie en ontgrendelen** knop. Wanneer u sparen een revisie van het onderwerp, wordt een nieuwe revisie gecreeerd en het slot is ook versie.
   - Als uw beheerder de optie heeft ingeschakeld om bestanden bij het sluiten in te checken, wordt u gevraagd om bestanden op te slaan wanneer de uitgecheckte bestanden worden gesloten. Als deze optie is ingeschakeld en u de editor sluit met gewijzigde bestanden, wordt een lijst weergegeven met uitgecheckte bestanden die moeten worden opgeslagen. De uitgecheckte bestanden worden weergegeven met een vergrendelingspictogram:

     ![](images/save-on-close.PNG){width="550" align="left"}

      - Klikken op **Sluiten zonder opslaan** sluit de bestanden zonder wijzigingen op te slaan.

      - Klik op de knop **Opslaan** slaat de wijzigingen op, maar checkt de bestanden niet in.

      - De **Bestanden controleren** en vervolgens op de knop **Opslaan** controleert de bestanden \(maakt een andere versie\) en slaat de bestanden ook op.


## Een kaart voorvertonen

Naast de positie van elk onderwerpdossier binnen een kaart kunnen zien, is het wenselijk om de kaartinhoud in één opeenvolgende stroom te zien. Met de functie Kaart voorvertonen kunt u de volledige inhoud van het kaartbestand met één klik bekijken. U hoeft geen uitvoer van het kaartbestand te genereren om te zien hoe de hele kaart er na publicatie uitziet. U hebt eenvoudig toegang tot de voorvertoning van de kaart en alle onderwerpen en submaps worden weergegeven in de vorm van een boek.

U kunt de voorvertoning van een kaart openen via:

- **UI Middelen**: Navigeer in de interface Elementen naar de kaartlocatie, selecteer het kaartbestand en kies **Voorvertoning toewijzen** in de werkbalk. De voorvertoning van de kaart wordt weergegeven op een nieuw tabblad. U kunt de inhoud van alle onderwerpen bekijken in de voorvertoningsmodus. In deze weergave kunt u geen onderwerp bewerken.

  >[!NOTE]
  >
  > Als de *Voorvertoning toewijzen* Deze optie is niet zichtbaar in de hoofdwerkbalk en is mogelijk onder de **Meer** werkbalkmenu.

- **Geavanceerde kaarteditor**: Klik in de Geavanceerde Kaarteditor op het pictogram Voorvertoning om de voorvertoning van de huidige kaart weer te geven.

  ![](images/map-preview-icon.png){width="350" align="left"}

  In de voorvertoningsmodus kunt u de volgende aanvullende taken uitvoeren:

   - Klik met de rechtermuisknop op een onderwerp en selecteer **Bewerken** om het onderwerp voor het uitgeven in een nieuw lusje te openen.

     >[!NOTE]
     >
     > Als u geen bewerkingsrechten hebt, wordt het onderwerp geopend in de modus Alleen-lezen.

   - Springen naar het gewenste onderwerp door op de onderwerptitel in de boomstructuur \(in linkerpaneel \) te klikken.

   - Het huidige onderwerp in kaartvoorproef wordt ook benadrukt in de kaartboom.


**Bovenliggend onderwerp:**[ Werken met de Kaarteditor](map-editor.md)
