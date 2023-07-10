---
title: Native PDF | Steun voor taalvariabelen
description: Taalvariabelen gebruiken in de PDF-uitvoer en -uitvoersjablonen
source-git-commit: 3e922ef7ed9af200aa8fcfb0cbe4489cf059e335
workflow-type: tm+mt
source-wordcount: '1221'
ht-degree: 0%

---


# Ondersteuning voor taalvariabelen

AEM hulplijnen bieden de functie om taalvariabelen te gebruiken. U kunt taalvariabelen gebruiken om gelokaliseerde koorden in de output van PDF te bepalen of om het even welke statische tekst in de outputmalplaatjes te lokaliseren. U kunt CSS stijlen gebruiken om de koorden te lokaliseren die uit CSS komen.

## Taalvariabelen gebruiken in de PDF-uitvoer

U kunt taalvariabelen gebruiken om een gelokaliseerde versie van de uit-van-de-doos etiketten zoals Nota, Voorzichtigheid, en Waarschuwing of statische tekst in de output van PDF te bepalen. De variabelenaam is hetzelfde voor alle talen, maar kan verschillende waarden hebben voor de verschillende talen. U kunt de waarde voor deze variabelen bijwerken in een of meer talen en vervolgens wordt de gelokaliseerde waarde automatisch gekozen in de uitvoer van PDF.

U kunt het label bijvoorbeeld op de volgende manieren presenteren `Note` in de PDF-uitvoer:

- Engels: Opmerking

- Frans: Opmerking

- Duits: Hinweis

<img src="./assets/language-variable-output.png" width="550">

>[!NOTE]
>
> Als de waarde voor een variabele niet in een bepaalde taal is gedefinieerd, wordt de tekenreeks door AEM hulplijnen gekozen uit de taal van de gebruikersinterface (gebruikersinterface van de toepassing) als een fallback-mechanisme.
>
> Als u de waarde niet in de taal van UI hebt bepaald, zoekt het Engels (`en_us`), of anders kiest het Engels (`en`) en geeft hetzelfde weer in de uitvoer van PDF.

### Typen taalvariabelen

AEM hulplijnen ondersteunen twee typen variabelen: Toepassings- en gebruikersvariabelen.

#### Toepassingsvariabelen

AEM de Gidsen verstrekt een reeks vooraf bepaalde of uit-van-de-doos toepassingsvariabelen. U kunt deze vooraf gedefinieerde variabelen gebruiken om informatie toe te voegen over een document dat specifiek is voor AEM hulplijnen. De `chapter-number` Als de variabele in een pagina is opgenomen, wordt het hoofdstuknummer weergegeven waartoe de pagina behoort. De `author-label` met deze variabele wordt de naam van de auteur van het document weergegeven.

>[!NOTE]
>
> U kunt de waarde van een toepassingsvariabele overschrijven.


#### Gebruikersvariabelen

U kunt ook nieuwe taalvariabelen maken. U kunt bijvoorbeeld een gebruikersvariabele Publisher maken voor het label van de uitgever voor het document.

>[!NOTE]
>
>  U moet over beheerdersrechten beschikken om gebruikersvariabelen te maken en de toepassingsvariabelen te bewerken.

<img src="./assets/add-language-variables.png" width="550">

### Een nieuwe taalvariabele toevoegen

1. Ga in de webeditor naar het tabblad Uitvoer.
1. Selecteren **Taalvariabelen** <img src="./assets/language-variables.svg" width="25"> in het linkerdeelvenster.
1. Selecteren **Bewerken** om de **Taalvariabelen** venster. De toepassing en de gebruikersvariabelen in de geselecteerde taal worden in alfabetische volgorde weergegeven. De waarden worden weergegeven volgens de geselecteerde taal. Als u bijvoorbeeld de Franse taal selecteert, wordt Tip weergegeven als Conseil.
1. Van de **Taal** selecteert u de gewenste taal waarin u een variabele wilt bewerken.

   >[!NOTE]
   >
   > Als u de gewenste talen niet bekijkt, schakelt u de gewenste taal in via **Instellingen taalvariabele**. Instellingen selecteren <img src="./assets/settings-icon.svg" width="25">  om de **Instellingen taalvariabelen** .

1. Voer de naam van de variabele in het dialoogvenster **Naam** en de waarde ervan in het dialoogvenster **Waarde** kolom.

   >[!NOTE]
   >
   >U kunt elke HTML-inhoud als een variabelewaarde gebruiken om de variabelewaarde in specifieke opmaak weer te geven. U kunt bijvoorbeeld `<b>` label toe aan de waarde van de variabele om de Publisher vet weer te geven.

1. Selecteren **Taalvariabele toevoegen** <img src="./assets/add-language-variable.svg" width="25"> om een nieuwe taalvariabele aan de geselecteerde taal toe te voegen. Als u een variabele aan één taal toevoegt, wordt deze automatisch aan alle talen toegevoegd. U kunt geen variabele maken met dezelfde naam als een bestaande variabele. Er wordt een fout weergegeven.

>[!NOTE]
>
> Als u deze optie niet selecteert **Taalvariabele toevoegen**, wordt de variabele niet gemaakt en toegevoegd aan de lijst

### Opties voor een taalvariabele

Houd de muisaanwijzer boven de variabele om de **Opties** menu.

<img width="550" src="./assets/language-variable-user-options.png">

U kunt zowel toepassings- als gebruikersvariabelen voorvertonen. Selecteer **Voorvertoning** van de **Opties** menu van de geselecteerde variabele.
U kunt ook **Verwijderen** of **Dupliceren** de gebruikersvariabelen. Als u een variabele uit één taal verwijdert, wordt deze automatisch uit alle talen verwijderd.

### Toepassingsvariabelen bewerken of herstellen

U kunt ook de waarden voor een toepassingsvariabele bewerken. Later kunt u de oorspronkelijke waarde van een toepassingsvariabele herstellen. **Variabele herstellen** <img src="./assets/application-variable-revert.svg" width="25">  wordt weergegeven voor een toepassingsvariabele met een gewijzigde waarde.

## Taalvariabelen gebruiken in de uitvoersjablonen

Voeg taalvariabelen toe aan gelokaliseerde documenten. U kunt deze taalvariabelen invoegen in de paginalay-out die op verschillende pagina&#39;s in uw gelokaliseerde documenten wordt weergegeven. U kunt bijvoorbeeld de taalvariabele voor de `author-name` die wordt weergegeven in het koptekstgebied van de paginalay-out (of in een ander deel, zoals de voettekst of tekst).

<img src="./assets/language-variable-page-layout.png" width="550">

In de volgende screenshot ziet u de auteur en de merknaam die zijn gelokaliseerd in de PDF-uitvoer die voor de Franse taal is gegenereerd.


Om een taalvariabele zoals uw in te voegen `copyright-label` Voer in het koptekstgebied de volgende stappen uit:

1. Open de vereiste pagina-indeling voor bewerking.

   >[!NOTE]
   >
   > Weergave [Een pagina-indeling aanpassen](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) voor het openen van een pagina-indeling voor aanpassen of bewerken.

1. Selecteer de koptekst om deze actief te maken en een variabele in te voegen.
1. Selecteren **Variabele invoegen**  <img src="./assets/insert-language-variable.svg" width="25"> in de werkbalk.
1. In de **Variabele invoegen** selecteert u de naam van de taalvariabele die u wilt invoegen en klikt u op **Invoegen** om het in het koptekstgebied op te nemen.

   >[!NOTE]
   >
   > U kunt ook de zoektekenreeks in het tekstvak invoeren. De namen van variabelen die de opgegeven tekenreeks bevatten, worden gefilterd en in de lijst weergegeven.
   > De geselecteerde taalvariabele wordt ingevoegd in het koptekstgebied.

In de volgende schermafbeelding wordt de waarde voor de `copyright-label` toegevoegd in het koptekstgebied.

<img src="./assets/language-variable-header.png" width="550">

### Inhoudsstijl toepassen op taalvariabelen

Naast de waarde die u toewijst aan een taalvariabele, kunt u ook HTML-tags gebruiken om de waarde van de variabele in een specifieke opmaak weer te geven. U kunt bijvoorbeeld de waarde van de optie `publisher-label` vetgedrukt.

- U kunt de stijlen van de waarden ook opmaken met <span> tag. Met de taalvariabele voor het paginanummer kunt u bijvoorbeeld het paginanummer in Romeinse getalnotatie in het Engels weergeven en de notatie voor andere talen opgeven.

  Waarde voor Engels:
  `<span data-field="page-number" data-format="upper-roman">1</span>`

  Waarde voor Tamil:
  `<span data-field="page-number" data-format="tamil">1</span>`

U kunt ook taalvariabelen toevoegen en andere velden opmaken die worden vermeld in de functie Velden invoegen van de paginalay-outs. Voor meer informatie over het toevoegen van velden, bekijkt u [Velden en metagegevens toevoegen](../native-pdf/design-page-layout.md#add-fields-metadata).

- U kunt ook gelokaliseerde afbeeldingen aan de waarden toevoegen. U kunt bijvoorbeeld een afbeeldingspictogram toevoegen in de taal met hoofdstuknummers en gelokaliseerde afbeeldingen van het pictogram ophalen in de uitvoer van PDF.

  In het Engels kan de variabelewaarde voor een afbeelding er als volgt uitzien `<img src="banner-en.jpg">`en voor dezelfde variabele in het Duits `<img src="banner-de.jpg">`. Het neemt de beelden op afhankelijk van de taal.

## De tekenreeksen lokaliseren met CSS-stijlen

Met CSS-stijlen kunt u ook de tekenreeksen lokaliseren die in Herfst worden gebruikt, zoals Hoofdstuk, Sectie, Figuur en Tabel. Aangezien deze tekenreeksen uit CSS-bestanden komen, kunt u ze niet lokaliseren met behulp van taalvariabelen. Als u deze tekenreeksen wilt lokaliseren, kunt u CSS-stijlen maken voor elke taal waarin u ze wilt lokaliseren.
U kunt bijvoorbeeld de volgende CSS gebruiken om het hoofdstukvoorvoegsel en de bijbehorende getalnotatie in verschillende talen weer te geven.
Bijvoorbeeld, kunt u volgende CSS gebruiken om Hoofdstuk als Hoofdstuk in het Duits en het hoofdstukaantal in decimaal formaat te tonen. Bij Japans kunt u de getalnotatie voor Japans gebruiken om de hoofdstuknummers weer te geven in de inhoudsopgave.

```
// for English
h1:before {
  counter-increment: h11;
  content: "Chapter " counter(h11, decimal)".";
}

// for German
:root:lang(de) h1:before {
  content: "Hoofdstuk " counter(h11, decimal)".";
}

// for Japanese
:root:lang(ja) h1:before {
  content: "章 " counter(h11, japanese-formal)".";
}
```

In de volgende schermafbeeldingen worden de tekenreeksen weergegeven die zijn gelokaliseerd in Duitse en Japanse PDF-uitvoer.

<img src="./assets/localize-chapter-german.png" width="550">

<img src="./assets/localize-chapter-japanese.png" width="550">

### De voorvoegsels opmaken

Met CSS-stijlen kunt u ook de voorvoegsels opmaken. U kunt bijvoorbeeld het label opmaken `Note` in rode kleur in de PDF-uitvoer van verschillende talen.

```
.note .prefix-content 
{
color: red;
} 
```



