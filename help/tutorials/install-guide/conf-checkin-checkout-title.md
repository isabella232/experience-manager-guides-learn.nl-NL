---
title: Titel configureren voor inchecken en uitchecken van pictogrammen
description: Leer hoe u de titel voor de pictogrammen Inchecken en Uitchecken configureert
source-git-commit: bb4b875864b31197437a944ded5862bbf937bc29
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# De titel configureren voor de pictogrammen Inchecken en Uitchecken

Met AEM hulplijnen kunt u de titel configureren voor de pictogrammen Inchecken en Uitchecken in de webeditor. Voer de volgende stappen uit om de titel voor de pictogrammen Inchecken en Uitchecken te configureren:

1. Download het UI-configuratiebestand door u als beheerder aan te melden bij Adobe Experience Manager.
1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen en klik op de knop **Mapprofielen**.
1. Klik op de knop **Globaal profiel** tegel.
1. Selecteer de **XML Editor-configuratie** en klik op de knop **Bewerken** bovenaan.
1. In de **UI-configuratie XML-editor** klikt u op de **Downloaden** pictogram om het `ui_config.json` op uw lokale systeem.
1. In de `ui_config.json` , wijzigt u de titel in de sectie &quot;bovenste balk&quot;. U kunt de volgende waarden wijzigen:

   ```json
   //Change title to "Check out" instead of "Lock"
           "title": "Check out"
   
   //Change title to "Check in" instead of "@checkOutBy
            "title": "Check in"
   ```

1. Sla het bestand op en upload het.

