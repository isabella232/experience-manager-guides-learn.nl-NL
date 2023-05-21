---
title: Native PDF-publicatiefunctie | Werken met aangepaste wijzigingsbalken
description: Leer hoe u stijlen toepast op wijzigingsbalken.
exl-id: a81ec56c-ccbb-4599-a696-8edef7a73cdd
source-git-commit: 7b48633ef2418fa7c91842a8d2c2a4177017ef58
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---

# Werken met aangepaste wijzigingsbalken

Een wijzigingsbalk is een verticale lijn die nieuwe of herziene inhoud visueel identificeert. AEM Gidsen staat u toe om een veranderingsbar op de linkerzijde van de veranderde inhoud binnen onderwerpen en ook de veranderde onderwerpen in TOC van de output van de PDF te tonen.

Ga voor meer informatie over het weergeven van de wijzigingsbalk naar *PDF maken met wijzigingsbalk tussen gepubliceerde versies* instellen in [PDF-uitvoer publiceren](../web-editor/native-pdf-web-editor.md).

## Gewijzigde inhoud binnen onderwerpen

De veranderingsbar verschijnt op de linkerzijde van de inhoud in de onderwerpen die zijn opgenomen, veranderd of geschrapt.

U kunt de volgende stijlen wijzigen om de gewijzigde inhoud weer te geven en onder de wijzigingsbalken.


>[!NOTE]
>
>Deze stijlen maken deel uit van `layout.css` en kunt u deze naar wens bewerken.

U kunt bijvoorbeeld het kenmerk color in het dialoogvenster `.inserted-block` stijl om te bepalen hoe uw opgenomen inhoud in de gepubliceerde uitvoer van PDF verschijnt.


```css
...
.inserted-block { 
  color: #2ECC40; 
  display: inline; 
  -ro-comment-content: " "; 
  -ro-comment-style: underline; 
  -ro-comment-title: "Inserted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

U kunt ook de opdracht `.deleted-block` stijl om te definiëren hoe uw verwijderde inhoud wordt weergegeven in de gepubliceerde PDF-uitvoer.

```css
...
.deleted-block { 
  display: inline; 
  color: #FF6961; 
  text-decoration: line-through; 
  -ro-comment-content: " "; 
  -ro-comment-style: strikeout; 
  -ro-comment-title: "Deleted"; 
  -ro-comment-date: attr(data-time); 
  -ro-comment-dateformat: "yyyy/dd/MM HH:mm:ss"; 
} 
...
```

U kunt `.inserted-change-bar` en `.deleted-change-bar` stijl om de weergave te wijzigen van de wijzigingsbalken die links van de bijgewerkte inhoud worden weergegeven.

U kunt bijvoorbeeld `-ro-change-bar-color` kenmerk in `.inserted-change-bar` stijl om de ingevoegde wijzigingsbalk in groene kleur weer te geven. U kunt ook `-ro-change-bar-color` kenmerk in `.deleted-change-bar` stijl om de verwijderde wijzigingsbalk in rode kleur weer te geven.

```css
...
.inserted-change-bar { 
  -ro-change-bar-color: #2ECC40; 
} 

.deleted-change-bar { 
  -ro-change-bar-color: #FF6961; 
  } 
...
```

<img src="./assets/changed-bar-content.png" alt="Inhoud van gewijzigd onderwerp van balk" width="500">

## Gewijzigd onderwerp in de Inhoudsopgave (TOC)

U kunt een veranderingsbar op de linkerzijde van de veranderde onderwerpen in TOC van de output van de PDF ook toevoegen. U kunt `-ro-change-bar-color` in het dialoogvenster `.changed-topic` stijl om een veranderingsbar in de kleur van uw keus voor de bijgewerkte onderwerpen in de lijst van TOC toe te voegen.

U kunt bijvoorbeeld een wijzigingsbalk met een groene kleur toevoegen.

```css
...
.changed-topic { 
 -ro-change-bar-color: #2ECC40; 
}  
...
```


Dit toont een groene veranderingsbar tegen alle onderwerpen in TOC waar sommige bijgewerkt zijn gedaan. U kunt op het gewijzigde onderwerp in de inhoudsopgave klikken en de gedetailleerde wijzigingen bekijken.

<img src="./assets/changed-bar-TOC.png" alt="Gewijzigde balk" width="500">
