---
sidebar_position: 1
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 0%

---


# Knop

Om een knoop te tonen gebruiken wij de component, knoop.
De knopcomponent in JUI vertegenwoordigt een HTML `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};
```

Hiermee wordt een knop gemaakt met een label van `Yes, login`. De andere eigenschappen omvatten maar zijn niet beperkt tot variant,label,klikken.
> **_OPMERKING:_**  De `on-<events>` is de syntaxis voor het aanroepen van de opdrachten in de controllers.

De weergegeven knop ziet er als volgt uit:

![knop](imgs/yes_login_button.png "Knop")
