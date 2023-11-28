---
sidebar_position: 2
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 0%

---


# Contextmenu&#39;s aanpassen

De volgende contextmenu&#39;s kunnen worden aangepast:

- `file_options`
controllers:
   - Kaartweergave: `ditamap_viewer_controller`
   - Deelvenster Opslagplaats: `repository_panel_controller`
   - Deelvenster Favorieten: `collection_tree_controller`
   - Referentiekoppelingen voor bestandseigenschappen: `file_references_links_controller`
   - Zoekdeelvenster voor opslagplaats: `repository_search_controller`
   - Deelvenster Onderwerp: `subject_scheme_tree_controller`

- `folder_options`
controllers:
   - Deelvenster Opslagplaats: `repository_panel_controller`
   - Deelvenster Favorieten: `collection_tree_controller`

- `collection_options`
controllers:
   - Deelvenster Favorieten: `collection_tree_controller`

- `map_view_options`
controllers:
   - Kaartweergave: `ditamap_viewer_controller`

- `baseline_panel_menu`
controllers:
   - Deelvenster Basislijn: `baseline_panel`

- `preset_item_menu`
controllers:
   - Deelvenster Voorinstellingen: `preset_panel`

U kunt ook uw eigen contextmenu maken door een nieuwe unieke id te definiëren.

Nu heeft elk contextmenu een `controller id` ermee geassocieerd. Deze controller handelt de `on-event` functionaliteit voor de verschillende contextmenuopties

Laten we een voorbeeld nemen om te begrijpen

```js title=customise_context_menu.js"
const fileOptions = {
    id: "file_options",
    contextMenuWidget: "repository_panel",
    view: {
            items: [
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Delete",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Edit",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    "displayName": "Download",
                    "data": {
                      "eventid": "downloadFile"
                    },
                    "icon": "downloadFromCloud",
                    "class": "menu-separator",         
                    target: {
                        key:"displayName",value: "Duplicate",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
            ]

    },

    controller: {
        downloadFile(){
            const path  = this.model.selectedItem.path
            this.loader.loadDitaFile(path).then((file) => {
              function download_file(name, contents) {
                const mime_type = "text/plain";
        
                const blob = new Blob([contents], {type: mime_type});
        
                const dlink = document.createElement('a');
                dlink.download = name;
                dlink.href = window.URL.createObjectURL(blob);
                dlink.onclick = function() {
                    // revokeObjectURL needs a delay to work properly
                    const that = this;
                    setTimeout(function() {
                        window.URL.revokeObjectURL(that.href);
                    }, 1500);
                };
        
                dlink.click();
                dlink.remove();
            }
            download_file(path,file.xml)
            });
          }
    }
}
```

Laten we nu begrijpen wat deze code doet.

1. `id` wordt gebruikt om het contextmenu te identificeren dat wij willen aanpassen.
2. `contextMenuWidget` wordt gebruikt om de `widget id` of de `component` dat het contextmenu aanroept en het `events`.

De rest blijft hetzelfde, waarbij `view` wordt gebruikt om de items te definiëren; `target` geeft aan waar de optie moet worden vervangen, waaraan de optie moet worden toegevoegd of waaraan de optie moet worden toegevoegd, en `contextMenuWidget` bedieningspaneel handelt de `on-click` gebeurtenissen.
