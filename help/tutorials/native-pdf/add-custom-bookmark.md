---
title: Native PDF-publicatiefunctie | Aangepaste stijl toepassen op inhoudsopgave-items en onderwerpinhoud
description: Leer hoe u gebruiksstijlen maakt en stijlen voor uw inhoud maakt.
source-git-commit: fbb81704ea8d9d2793b066fa159b405460fa1dcf
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---


# Een aangepaste bladwijzer toevoegen in PDF-uitvoer

Over het algemeen wordt de inhoudsopgave in een DITA-kaart gerepliceerd als bladwijzers in de uiteindelijke PDF-uitvoer. Deze TOC wordt gecreeerd van de onderwerp of sectietitels in uw kaart DITA. Soms wilt u een aangepaste bladwijzer toevoegen aan een bepaalde inhoud in uw PDF-uitvoer, zodat u gemakkelijk kunt navigeren. Dit kan worden bereikt door een `outputclass` attribuut op het element en het toepassen van het volgende attribuut op het:

`bookmark-level: 3`

Hier, de `bookmark-level` is een kenmerk en een getal `3` is de waarde die het niveau in de bladwijzerhiërarchie aangeeft waar de bladwijzer wordt toegevoegd. In het volgende voorbeeld, heeft het eerste niveauonderwerp &quot;Contacten&quot;een lijst, &quot;Lijst van het Contact&quot;waarop wij een `outputclass` kenmerk met de waarde van `custom-bookmark`.

<img src="./assets/custom-bookmark-attribute.png" width="500">

De volgende definitie van de `custom-bookmark` wordt toegevoegd aan het CSS-bestand:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

In de uitvoer van de PDF, *Lijst met contactpersonen* tabel wordt toegevoegd op het tweede niveau in de bladwijzerlijst PDF, zoals hieronder wordt getoond:

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">
