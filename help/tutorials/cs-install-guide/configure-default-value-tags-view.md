---
title: Standaardwaarde voor de weergave Codes configureren
description: Leer hoe te om standaardwaarde voor de Mening van Markeringen te vormen
source-git-commit: 6051181e243cf71919901093c1b5590f21832545
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---


# Standaardwaarde voor de weergave Codes configureren {#id223GN0M0NDC}

AEM de Gidsen staat u toe om de standaardstaat voor de Mening van Markeringen in de Redacteur van het Web te vormen, die u helpt om de Mening van Markeringen voor de zitting van een nieuwe gebruiker te houden of weg door gebrek. Voer de volgende stappen uit om de standaardwaarde voor de Mening van Markeringen te vormen:

1. Download het UI-configuratiebestand door u als beheerder aan te melden bij Adobe Experience Manager.
1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen en klik op de knop **Mapprofielen**.
1. Klik op de knop **Globaal profiel** tegel.
1. Selecteer **XML Editor-configuratie** en klik op de knop **Bewerken** bovenaan.
1. In de **UI-configuratie XML-editor** klikt u op de **Downloaden** pictogram om het `ui_config.json` op uw lokale systeem.
1. In de `ui_config.json` bestand, wijzigt u de weergavestatus van de standaardlabels door de sectie defaultValues als volgt te wijzigen:

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Sla het bestand op en upload het.

>[!NOTE]
>
> De voorkeur van de gebruiker in de Redacteur van het Web om de Mening van Markeringen toe te laten/onbruikbaar te maken heeft belangrijkheid over deze standaardwaarde. Zo, als een gebruiker de Mening van Markeringen van de Redacteur van het Web toelaat, blijft het toegelaten zelfs over de zittingen.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)

