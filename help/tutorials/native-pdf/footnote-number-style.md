---
title: Native PDF-publicatiefunctie | Aangepaste stijlen gebruiken in voetnoten
description: Leer hoe u stijl toepast op de getallen in voetnoten.
exl-id: f1068f2f-2ace-4bdb-b5a4-46b03d4e43d6
source-git-commit: 7b48633ef2418fa7c91842a8d2c2a4177017ef58
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---

# Aangepaste stijlen gebruiken in voetnoten

Voetnoten zijn notities die onder aan een pagina worden geplaatst en die een verwijzing naar een bepaald deel van de tekst aangeven of ernaar verwijzen.

U kunt de getallen opmaken in de voetnootaanroep in de onderwerpinhoud en in de voetnootmarkering onder aan de pagina. U kunt bijvoorbeeld vierkante haakjes toevoegen rond het getal of de kleur ervan wijzigen. Met deze stijlen kunt u gemakkelijk de voetnoten in het document herkennen.

```css
...
.footnote::footnote-call { 
content: "(" counter(footnote, decimal) ")"; 
} 

.footnote::footnote-marker { 
content: "(" counter(footnote, decimal) ")"; 
} 

...
```

In het gegeven voorbeeld wordt een haakje toegevoegd vóór en na de aanroep en markering van de voetnoot:

* Voeg het voorvoegsel &quot;(&quot; en het achtervoegsel &quot;)&quot; toe met het inhoudskenmerk in het dialoogvenster `footnote-call` stijl die de steunen rond het voetnootaantal in de onderwerpinhoud zal toevoegen.
* Voeg het voorvoegsel &quot;(&quot; en het achtervoegsel &quot;)&quot; toe met het inhoudskenmerk in het dialoogvenster `footnote-marker` stijl waarmee de haakjes rond het voetnootnummer onder aan de pagina worden toegevoegd.

<img src="./assets/pdf-output-footer-numbers.png" alt="Voettekst in PDF-uitvoer" width="500">
