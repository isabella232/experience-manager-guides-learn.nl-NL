---
title: Native PDF-publicatiefunctie | Aangepaste stijlen gebruiken in voetnoten
description: Leer hoe u stijl toepast op de getallen in voetnoten.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
source-git-commit: cb2aa028330c1e1b8b71e9e928d724cc0d87bf44
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%

---

# Voetnootstijlen toepassen


Voetnoten zijn notities die onder aan een pagina worden geplaatst en die een opmerking toevoegen aan of verwijzen naar een bepaald deel van de tekst.

Elke voetnoot heeft een voetnootmarkering aan de onderzijde van de pagina, die over het algemeen een getal of een symbool is zoals een sterretje. Binnen de hoofdinhoud wordt dezelfde voetnootmarkering weergegeven als een voetnootaanroep en wordt deze aangegeven met hetzelfde nummer of symbool als een superscript.




## De stijlen van voetnootaanroepen en -markeringen wijzigen

U kunt de stijlen van de voetnootaanroepen en -markeringen wijzigen en de weergave ervan in de PDF-uitvoer beheren. Met deze stijlen kunt u snel de voetnoten in het document identificeren.


**Voorbeeld 1**:

Gebruik het volgende voorbeeld om een haakje vóór en na de voetnootaanroep en markering toe te voegen:

* Voeg het voorvoegsel &quot;(&quot; en het achtervoegsel &quot;)&quot; toe met het inhoudskenmerk in het dialoogvenster `footnote-call` stijl, die de steunen rond het voetnootaantal in de onderwerpinhoud zal toevoegen.
* Voeg het voorvoegsel &quot;(&quot; en het achtervoegsel &quot;)&quot; toe met het inhoudskenmerk in het dialoogvenster `footnote-marker` stijl, waarmee de haakjes rond het voetnootnummer onder aan de pagina worden toegevoegd.

```css
...
.fn::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.fn::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```



<img src="./assets/pdf-output-footer-numbers.png" alt="Voettekst in PDF-uitvoer" width="500" border="2px">

*Voeg haakjes toe rond de voetnootaanroep en de voetnootmarkering.*

**Voorbeeld 2**:

U kunt de voetnootvraag en de teller met een asterisk of lager Grieks karakter in plaats van een aantal ook markeren.


```css
.fn::footnote-call {
 content: counter(footnote, asterisks);
}
.fn::footnote-marker {
 content: counter(footnote, asterisks) " ";
}
```

In de uitvoer kunt u iets weergeven als:

<img src="./assets/footnote-number-2.png" alt="Voettekst in PDF-uitvoer" width="500" border="2px">

*Voeg een sterretje toe aan een voetnootaanroep en -markering.*

## Een voetnootaanroep verbergen

U kunt ook een stijl toepassen op voetnootaanroepen met specifieke kenmerken. Gebruik bijvoorbeeld de volgende stijl om een voetnoot met de id&#39;s te verbergen: De aanroep van de voetnoot is verborgen in de hoofdinhoud, maar de voetnootmarkering wordt onder aan de pagina weergegeven.

```css
.fn[id]::footnote-call {
		display: none;
                        }
```

## Het voetnootgedeelte opmaken

In het voetnootgedeelte worden alle voetnoten geplaatst, meestal onder aan een pagina. U kunt het voetnootgedeelte opmaken met de paginalay-outs of CSS-stijlen.


### Paginalay-outs

U kunt de pagina-eigenschappen voor paginalay-outs gebruiken om het voetnootgedeelte in de verschillende secties in een PDF-document op te maken. U kunt bijvoorbeeld de eigenschappen voor marges en opvulling van het voetnootgedeelte in een hoofdstuk opgeven. U kunt ook de rand, stijl, kleur, breedte en straal wijzigen.

Meer informatie over [werken met de pagina-eigenschappen van een pagina-indeling](./design-page-layout.md#page-props-page-layout).

### CSS-stijlen

U kunt stijlen toepassen en het voetnootgedeelte in een PDF-document opmaken. U kunt bijvoorbeeld de lengte, stijl, kleur en breedte van de rand wijzigen.

```css
	@page {
	  @footnote {
   		border-top-style: solid;
   		border-top-color: #FF0000;
   		border-top-width: 3px;
 		        }
	      }
```

## De nummering van voetnoten opnieuw starten

Standaard worden de voetnoten doorlopend genummerd in een document. U kunt echter wel paginalay-outs of CSS-stijlen gebruiken om de nummering van voetnoten opnieuw te starten.


### Paginalay-outs

U kunt een nummer in de paginalay-outs opgeven om de voetnootnummering in de verschillende secties van een PDF-document opnieuw te starten. Selecteer bijvoorbeeld een getal in het menu **Nummering opnieuw beginnen vanaf** in het deelvenster Pagina-eigenschappen om de voetnootnummering voor elk hoofdstuk opnieuw te starten.

### CSS-stijlen

Gebruik de volgende stijl om de voetnootnummering op elke pagina van de PDF-uitvoer opnieuw in te stellen:

```css
@page
{
counter-reset: footnote
}
```

De voetnoten op elke pagina worden dus opnieuw gestart vanaf 1.

## Inline-voetnoten weergeven

Doorgaans wordt elke voetnoot als een blok weergegeven of begint deze op een nieuwe regel. Maar je kunt ze ook op één lijn of naast elkaar plaatsen.

```css
.fn{
  	display: inline;
              }
```

## Stijlen toepassen op voetnootkruisverwijzingen

U kunt ook meerdere keren naar een voetnoot verwijzen en in de PDF-uitvoer naar dezelfde voetnoot verwijzen. Hierdoor kunt u gemakkelijker meerdere keren naar hetzelfde citaat of gedetailleerde notitie in het document verwijzen zonder dat u er opnieuw een voetnoot voor hoeft te maken.

In de volgende schermafbeelding ziet u bijvoorbeeld hoe met dezelfde voetnoot wordt verwezen naar alle steden in de PDF-uitvoer.
<img width="550" alt="voetnootverwijzingen in een pdf" src="./assets/link-footnotes.png" border="2px">

*De kruisverwijzing invoegen in een voetnoot.*





Met CSS-stijlen kunt u ook de kruisverwijzingen naar voetnoten opmaken. U kunt bijvoorbeeld de achtergrondkleur van de kruisverwijzingen wijzigen.

```css
    .xref-fn{
	background-color: red;
	}
```



