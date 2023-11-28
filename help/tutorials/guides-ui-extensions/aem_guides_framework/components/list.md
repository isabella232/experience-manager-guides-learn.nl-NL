---
sidebar_position: 5
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '57'
ht-degree: 0%

---


# Lijst

Om een lijst te tonen, gebruiken wij de componentenlijst.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@languages", // an array of list items
},
```

Hier is taal een eenvoudige array van tekenreeksen. `languages = ["English", "Hindi", "French"]`
Voor het geval dat wij een lijst van voorwerpen willen teruggeven, kunnen wij de structuur specificeren gebruikend punt config.

```js title="list.js"
const listJSON =  {
    "component": "list", //tells the component name
    "data": "@projects", // an array of list items
    "itemConfig": { // used to define the structure of the list items.
    "component": "widget",
    "id": "checkbox_label"
    }
},
```

ItemConfig is gewoonlijk een `widget`. Ga voor meer informatie over widgets naar [Widgets](../Widgets/basic_widget.md)

De gerenderde lijst ziet er als volgt uit:

![list](./imgs/list.png "Lijst")
