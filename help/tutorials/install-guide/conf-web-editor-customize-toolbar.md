---
title: Werkbalk Aanpassen
description: Leer hoe u de werkbalk kunt aanpassen
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 0%

---

# Werkbalk Aanpassen {#id172FB00L0V6}

Standaard wordt de webeditor geleverd met de meest voorkomende redactionele functies die door elke DITA-editor worden vereist. Functies zoals het invoegen van elementen van het type lijst \(genummerd of met opsommingstekens\), kruisverwijzing, inhoudsverwijzing, tabel, alinea en tekenopmaak zijn beschikbaar in de editor. Naast deze basiselementen, kunt u de Redacteur van het Web aanpassen om elementen op te nemen die in uw auteursmilieu worden gebruikt.

Er zijn twee manieren om de toolbar van de Redacteur van het Web aan te passen:

- Nieuwe functionaliteit toevoegen aan de werkbalk

- Bestaande functies van de werkbalk verwijderen


## Een functie toevoegen aan de werkbalk

Het toevoegen van een functionaliteit aan de Redacteur van het Web impliceert twee primaire taken - toevoegend een pictogram voor de eigenschap in *ui\_config.json* en de achtergrondfunctionaliteit in JavaScript toevoegen.

**Een pictogram toevoegen op de werkbalk**

Voer de volgende stappen uit om een eigenschap aan de toolbar van de Redacteur van het Web toe te voegen:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het standaardconfiguratiebestand dat beschikbaar is op de volgende locatie:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Maak een kopie van het standaardconfiguratiebestand op de volgende locatie:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigeer naar de `ui_config.json` in het `apps` knooppunt voor bewerken.

1. In de `ui_config.json` , voegt u de definitie van de nieuwe functie toe in de sectie Werkbalken. Doorgaans kunt u een nieuwe werkbalkknoopgroep maken en er een of meer werkbalkknoppen aan toevoegen. U kunt ook een nieuwe werkbalkknop toevoegen binnen een bestaande werkbalkgroep. U moet de volgende gegevens opgeven om een nieuwe werkbalkgroep te maken:

   - **type:**Specify `blockGroup` als de `type` waarde. Deze waarde geeft aan dat u een blokgroep maakt die een of meer werkbalkgroepen zou bevatten.

   - **extractiemas:** Naam van de klasse of klassen, gescheiden door spatie.

   - **objecten:** Geef de definitie van alle groepen op de werkbalk op. Elke groep kan een of meerdere werkbalkpictogrammen bevatten. Als u pictogrammen in een werkbalkgroep wilt definiëren, moet u opnieuw de `type` attribuut binnen `items`en stel de waarde in op `buttonGroup`. Geef een of meer klassenamen op in het dialoogvenster `extraclass` eigenschap. Geef de functienaam op in het dialoogvenster `label` eigenschap. Het volgende fragment uit het `ui_config.json` het bestand bevat de definitie van het hoofdwerkbalkblok, gevolgd door `buttonGroup` definitie:

     ```json
     "toolbar": {    
       "type": "blockGroup",    
       "extraclass": 
       "toolbar operations",    
         "items": [      
           {        
             "type": "buttonGroup",        
             "extraclass": "left-controls",        
             "label": "Left Controls",        
             "items": [
     ```

     Binnen de `items` verzameling, moet u de definitie voor een of meer werkbalkpictogrammen opgeven.
U moet de volgende eigenschappen definiëren om een werkbalkpictogram toe te voegen:

   - **type:** Opgeven `button` als de `type` waarde. Deze waarde geeft aan dat u een werkbalkknop toevoegt.

   - **pictogram:** Geef de naam op van het koraalpictogram dat u wilt gebruiken op de werkbalk.

   - **variant:** Opgeven `quiet` als de `variant` waarde.

   - **titel:** Geef de knopinfo voor het pictogram op.

   - **klikken:** Geef de opdrachtnaam op die voor de functie in het JavaScript-bestand is gedefinieerd. Als voor uw opdracht invoerparameters zijn vereist, geeft u de opdrachtnaam op als:

     ```JavaScript
     "on-click": {"name": "AUTHOR_INSERT_ELEMENT", "args": "simpletable"}
     ```

   - **tonen of verbergen:** Als u de `show` en geeft u vervolgens de modi op waarin het pictogram wordt weergegeven. Mogelijke waarden zijn: `@isAuthorMode`, `@isSourceMode`, `@isPreviewMode`, `true` \(weergeven in alle modi\), of `false` \(in alle modi verbergen\).

   In plaats van `show`kunt u ook de `hide` eigenschap. De mogelijke waarden zijn gelijk aan die in `show` eigenschap met het enige verschil dat het pictogram niet wordt weergegeven voor de opgegeven modus.

1. Een *clientlib* en voeg uw JavaScript toe aan deze map.

1. Werk het categoriebezit van bij *clientlib* door deze toe te wijzen aan de waarde van *apps.fmdita.xml\_editor.page\_overrides*.

1. Sla de *ui\_config.json* bestand en laad de webeditor opnieuw.


**JavaScript-codevoorbeelden**

Deze sectie bevat twee voorbeelden van JavaScript-code die u helpen om aangepaste functionaliteit toe te voegen. In het volgende voorbeeld ziet u AEM het versienummer van hulplijnen wanneer een gebruiker op het pictogram Versie tonen op de werkbalk klikt.

Voeg de volgende code toe aan een JavaScript-bestand:

```JavaScript
/**
* This file contains an example to show AEM Guides version 
* number when a user clicks on the Show Version icon in the toolbar. 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  window.addEventListener('DOMContentLoaded', function () {
    fmxml.ready(function () {
      fmxml.eventHandler.subscribe({
        key: 'user.alert',
        next: function next() {
          alert("AEM Guides version x.x");
        }
      });
    });
  });
})(window);
```

Voeg de functie in het bestand ui\_config.json toe als:

```json
 {
      "type": "button",
      "icon": "alert",
      "title": "About AEM Guides",
      "variant": "quiet",

  "show": "true",
      "on-click": "user.alert"
  } 
```

In het volgende voorbeeld ziet u hoe u de status van een actief bestand in een document kunt wijzigen in &quot;In-Review&quot;.

```JavaScript
/**
* This file contains an example to set the document state of an active *open documen to "In-Review". 
* Step 1. Create a clientlib folder and add save a file with your *JavaScript code into this folder. A code sample is shared below.
* Step 2: Update the categories property of the clientlib folder by *assigning it the value of 
* "apps.fmdita.xml_editor.page_overrides".
* Step 3: Add the feature in the ui_config.json file as shown after the *sample code. Save the ui_config.json file and reload the Web Editor
 */

(function (window) {
  "use strict";

  //Wait for the page has been completely loaded 

  window.addEventListener('DOMContentLoaded', function () {

    //Wait for the xml editor to start
    fmxml.ready(function () {

      //Subscribe to 'user.docstate.to.in-review' event
      fmxml.eventHandler.subscribe({
        key: 'user.docstate.to.in-review',
        next: function next() {
          var docstate = "In-Review"; // New docstate name
          var filePath = fmxml.curEditor.filePath; 
// Get the file path of active open file
          if (filePath) {
            //Call API to change the doc state
            $.ajax({
              type: 'POST',
              url: '/bin/fmdita/states',
              data: {
                paths: filePath,
                operation: "setdocstates",
                docstate: docstate
              }
            }).fail(function (xhr, textStatus, errorThrown) {
              console.error("Cannot update docstate to " + docstate);
            }).success(function (data) {
              console.log('docstate updated to ' + docstate);
            });
          }
        }
      });
    });
  });
})(window);
```

Voeg de functie in het bestand ui\_config.json toe als:

```json
 {
      "type": "button",
      "icon": "actions",
      "title": "Change document state to In-Review",
      "variant": "quiet",
      "show": "true",
      "on-click": "user.docstate.to.in-review"
    } 
```

## Een functie verwijderen uit de werkbalk

Soms wilt u wellicht niet alle functies weergeven die momenteel beschikbaar zijn in de webeditor. In dat geval kunt u de ongewenste functie verwijderen van de werkbalk van de webeditor.

Voer de volgende stappen uit om ongewenste functies van de werkbalk te verwijderen:

1. Meld u aan bij AEM en open de modus CRXDE Lite.

1. Navigeer naar het standaardconfiguratiebestand dat beschikbaar is op de volgende locatie:

   `/libs/fmdita/clientlibs/clientlibs/xmleditor/ui_config.json`

1. Maak een kopie van het standaardconfiguratiebestand op de volgende locatie:

   `/apps/fmdita/xmleditor/ui_config.json`

1. Navigeer naar de `ui_config.json` in het `apps` knooppunt voor bewerken.
De `ui_config.json` bestand heeft drie secties:

- **werkbalken:**   Deze sectie bevat de definitie van alle functies die beschikbaar zijn op de werkbalk van de editor, zoals Genummerde lijst invoegen/verwijderen, \(bestand\) Sluiten, Opslaan, Opmerkingen en meer.

- **sneltoetsen:**   Deze sectie bevat de definitie van toetsenbordkortere weg die aan een bepaalde eigenschap in de redacteur wordt toegewezen.

- **sjablonen:**   Deze sectie bevat de vooraf gedefinieerde structuur van DITA-elementen die u in uw document kunt gebruiken. Standaard bevat de sjabloonsectie sjabloondefinities voor een alinea, eenvoudige tabel, tabel en tekstelementen. U kunt een sjabloondefinitie maken voor elk element door een geldige XML-structuur toe te voegen voor het gewenste element. Als u bijvoorbeeld een `p` element met elke nieuwe `li` in een lijst kunt u de volgende code toevoegen aan het einde van de sjabloonsectie om dit te bereiken:

```HTML
"li": "<li><p></p></li>"
```

1. Verwijder in de sectie Werkbalken het item van de functie die u niet aan uw gebruikers wilt tonen.

1. Sla de *ui\_config.json* bestand en laad de webeditor opnieuw.


**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
