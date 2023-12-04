---
title: Native PDF-publicatiefunctie | Een aangepaste bladwijzer toevoegen in PDF-uitvoer
description: Leer hoe u gebruiksstijlen maakt en stijlen voor uw inhoud maakt.
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---

# Een aangepaste bladwijzer toevoegen in PDF-uitvoer

Over het algemeen wordt de inhoudsopgave in een DITA-kaart gerepliceerd als bladwijzers in de uiteindelijke PDF-uitvoer. Deze TOC wordt gecreeerd van de onderwerp of sectietitels in uw kaart DITA. Soms wilt u een aangepaste bladwijzer toevoegen aan een bepaalde inhoud in uw PDF-uitvoer, zodat u gemakkelijk kunt navigeren. Dit kan worden bereikt door een `outputclass` kenmerk op het element en het volgende kenmerk hierop toepassen:

`bookmark-level: 3`

Hier, `bookmark-level` is een kenmerk en een getal `3` is de waarde die het niveau in de bladwijzerhiërarchie aangeeft waar de bladwijzer wordt toegevoegd. In het volgende voorbeeld, heeft het eerste niveauonderwerp &quot;Contacten&quot;een lijst, &quot;Lijst van het Contact&quot;waarop wij een `outputclass` kenmerk met de waarde van `custom-bookmark`.


<img src="./assets/custom-bookmark-attribute.png" width="500">

De volgende definitie van de `custom-bookmark` -klasse wordt toegevoegd aan het CSS-bestand:

```css
…
/*Adding a custom bookmark*/
.custom-bookmark{
    bookmark-level: 2
}
…
```

In de uitvoer van de PDF worden de *Lijst met contactpersonen* tabel wordt toegevoegd op het tweede niveau in de bladwijzerlijst PDF, zoals hieronder wordt getoond:

<img src="./assets/custom-bookmark-in-pdf-output.png" width="500">

>[!NOTE]
>
>U moet het juiste niveau kiezen waar de aangepaste bladwijzer wordt toegevoegd. Als u een getal opgeeft dat kleiner is dan de bladwijzer van het bovenliggende onderwerp, neemt de aangepaste bladwijzer de positie van de bovenliggende bladwijzer en worden alle andere bladwijzers als onderliggende bladwijzers weergegeven. Dit kan tot onverwachte bladwijzerstructuur leiden.
