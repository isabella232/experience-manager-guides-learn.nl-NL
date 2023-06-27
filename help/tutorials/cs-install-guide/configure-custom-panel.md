---
title: Een aangepast deelvenster configureren in het linkerdeelvenster
description: Leer hoe u een aangepast deelvenster kunt configureren in het linkerdeelvenster
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '87'
ht-degree: 0%

---


# Een aangepast deelvenster configureren in het linkerdeelvenster {#id224JI200Y6F}

Voer de volgende stappen uit om een aangepast paneel binnen het linkerpaneel van de Redacteur van het Web toe te voegen:

1. Een *clientlib* en voeg uw JavaScript- en CSS-bestand toe aan deze map.
1. Werk het categoriebezit van bij *clientlib* door deze toe te wijzen aan de waarde van *apps.fmdita.xml\_editor.page\_overrides*.

Voorbeeldcode voor het configureren van een aangepast deelvenster:

```
tcx.ready(function () { //Ready will call the callback after editor code is set for events and global variable excess
 
 
    // APP_ADD_AUTHOR_LEFT_TAB event will add a new left tab in the left panel, user can show hide it using editor settings
    tcx.eventHandler.next(tcx.eventHandler.KEYS.APP_ADD_AUTHOR_LEFT_TAB, {
            id: 'my_panel',
            class: 'my-panel-tab',
            icon: 'file', //Any valid Adobe Spectrum icon name https://spectrum.adobe.com/page/icons/
            label: 'My Tab',
            prevTabID: 'repository_panel' //Existing tab ids are 'collection_panel', 'repository_panel', 'map_panel', 'outline_panel', 'conref_panel', 'glossary_panel', 'condition_panel', 'subject_scheme_panel', 'snippet_panel', 'template_panel', 'search_panel'
    })
 
    // APP_PANEL_DID_MOUNT event will be called after user has selected the panel and panel is rendered in the DOM
    tcx.eventHandler.subscribe({
        key: tcx.eventHandler.KEYS.APP_PANEL_DID_MOUNT,
        next: function(opts) {
            // TODO create panel ui inside $el
            let $el = opts.$el //$el is Tab panel content html node
            let id = opts.id //id is tab panel id (my_panel)
            console.log("mounted", opts)
        }
    })
 
  // APP_PANEL_WILL_UNMOUNT will be called before destorying the new left panel
  tcx.eventHandler.subscribe({
        key: tcx.eventHandler.KEYS.APP_PANEL_WILL_UNMOUNT,
        next: function(opts) {
            //TODO do some cleanup
            let id = opts.id //id is tab panel id (my_panel)
            console.log("unmounted", opts)
        }
    })
 
});
```

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)

