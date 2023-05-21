---
title: Native PDF-publicatiefunctie | Aangepaste stijl toepassen op inhoudsopgave-items en onderwerpinhoud
description: Leer hoe u gebruiksstijlen maakt en stijlen voor uw inhoud maakt.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
source-git-commit: e2349fc14143e5e49f8672ef1bfa48984df3b1c7
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 0%

---

# Aangepaste stijl toepassen op inhoudsopgave-items en onderwerpinhoud

Mogelijk wilt u soms aangepaste opmaak toepassen op de inhoudsopgave-items of een bepaald onderwerp. Dit kan worden bereikt door een `outputclass` kenmerk met de `<topicref>` -element in uw DITA-kaart. Ook, voor het geval u een douaneformaat op een volledig onderwerp wilt toepassen, dan kan dat ook worden bereikt door de de stijldefinitie van de attributen in CSS uit te breiden.

Neem een voorbeeld van een nieuw onderwerp dat u voor overzicht wilt verzenden. Voor gemakkelijke identificatie van het bijgewerkte onderwerp, moet u toevoegen `outputclass` aan de `<topicref>` in uw DITA-kaart en definieert vervolgens een aangepaste opmaak voor dezelfde opmaak in de CSS.

In het volgende voorbeeld wordt *Geschiedenis van de vluchten* onderwerp is toegewezen en `outputclass` kenmerk met de waarde van `new-topic`.

<img src="./assets/new-topic-attribute-in-map.png" width="500">

De klassedefinitie van de klasse `new-topic` in een CSS kunt u de stijl definiëren voor de volgende items:
* De belangrijkste vermelding in de inhoudsopgave of de miniinhoudsopgave
* De titel van het onderwerp in de hoofdinhoud
* De volledige inhoud van het onderwerp, inclusief de titel

Zie hoe elk van deze scenario&#39;s in CSS kan worden bepaald. In de volgende CSS-definitie van de `new-topic` is de tekstkleur gewijzigd.

```css
…
.new-topic {
  color: #CC5309
}
…
```

Deze definitie controleert de kleur van de tekst in TOC en de titel van het onderwerp. In de volgende PDF-uitvoer ziet u de andere kleur die op het inhoudsopgave-item wordt toegepast:

<img src="./assets/pdf-output-toc-entry.jpg" width="500">

De titel van het onderwerp wordt ook opgemaakt met dezelfde kleur.

<img src="./assets/pdf-output-topic-title.jpg" width="500">

Als u de ingang van TOC en de titel van het onderwerp verschillende stijlen wilt hebben, dan kunt u hen afzonderlijk bepalen zoals hieronder getoond:

```css
...
/*for styling TOC entry */
.new-topic {
  color: #CC3509
}

/* for styling topic's title */
.new-topic.title {
  color: #092ACC
}
...
```

Tot slot kunt u stijlen op de volledige inhoud binnen het onderwerp ook toepassen. Hiervoor moet u een achtervoegsel toevoegen &quot;`-content`&quot; aan de klassenaam. In het volgende voorbeeld, is een veranderingsbar toegevoegd op de volledige inhoud van het onderwerp:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color: #A609CC;
}
...
```

Met de bovenstaande opmaakkenmerken wordt links van het dialoogvenster een wijzigingsbalk toegevoegd *Geschiedenis van de vlucht* onderwerp, zoals hieronder getoond:

<img src="./assets/pdf-output-topic-content.jpg" width="500">
