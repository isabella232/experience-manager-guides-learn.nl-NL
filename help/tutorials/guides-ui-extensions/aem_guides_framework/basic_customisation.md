---
sidebar_position: 3
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# De app aanpassen

Onze app volgt een MVC-structuur (Model, View, Controller)

## Model

Het model definieert de verschillende kenmerken en slaat de waarden ervan op. De waarden van de verschillende kenmerken die in het model zijn opgeslagen, zijn via de syntaxis toegankelijk via de controller

```typescript
this.model.attributeName
```

Voor aanpassing in de app worden alle nieuwe kenmerken toegevoegd onder een kaart in het model.
Om een nieuw attribuut in het model te plaatsen zullen wij de volgende syntaxis in het controlemechanisme gebruiken:

```typescript
this.model.extraProps.set("key", value)
```

Om tot een attribuut toegang te hebben dat aan het model wordt toegevoegd zullen wij de volgende syntaxis gebruiken:

```typescript
const value = this.model.extraProps.get("key")
```

## Weergave

De weergave definieert de gebruikersinterface van de app. We gebruiken JSON-bestanden om de weergave van onze bestanden te definiëren. Hier, bepalen wij de componenten, css (zoals die in de winningsklasse van componenten wordt gegeven) en geven de waarden terug die in het model worden opgeslagen.
In onze app wordt elke weergave gedefinieerd met behulp van een JSON. Naar de JSON&#39;s wordt verwezen met behulp van hun unieke id&#39;s, die een `id`.

## Controller

De controller wordt gebruikt om gebeurtenissen af te handelen en de gegevens te verwerken. Het controlemechanisme wordt gebruikt om gegevens van de server te halen en te verzenden, is het de interface tussen wat op UI wordt getoond en op het achtereind wordt opgeslagen.

- Als u waarden wilt instellen bij initialisatie, gebruiken we de `init` functie.
- Om een methode toe te voegen het controlemechanisme gebruiken wij de volgende syntaxis:

```typescript
methodName: function(args){
    // functionality
}
```

De `methodName` hier fungeert als `key` verwijzen naar de methode in de JSON-weergave of in andere functies

- Om een methode in het controlemechanisme te roepen gebruiken wij de syntaxis

```typescript
this.next('methodName', args)
```

## Voorbeeld

Laten we nu een eenvoudig voorbeeld gebruiken om te laten zien hoe deze drie componenten met elkaar communiceren.
Wij zullen een knoop toevoegen die zijn etiketwaarde op een klik schakelt

### Voorbeeld weergeven

Hieronder wordt de JSON gedefinieerd voor een knop met een dynamische tekst die in het model is opgeslagen onder de variabelenaam. `buttonLabel`.
In dit voorbeeld wordt het label gewijzigd wanneer u op de knop klikt.

```JSON
{
    "component": "button",
    "label": "@extraProps.buttonLabel",
    "variant": "cta",
    "on-click": "switchButtonLabel",
}
```

### Modelvoorbeeld

in dit geval `extraProps.buttonLabel` bevat het label van de knop

### Voorbeeld van controller

```typescript
  controller: {
    init: function () {
      this.model.extraProps.set("buttonLabel", "Submit")
    },

    switchButtonLabel(){
        const buttonLabel = this.model.extraProps.get("buttonLabel") === "Submit"? "Cancel" : "Submit"
        this.model.extraProps.set("buttonLabel", buttonLabel)
    }
  }
```

Onder GIF ziet u de bovenstaande code in actie
![basic_customization](imgs/basic_customisation.gif "Knop Basisaanpassing")
