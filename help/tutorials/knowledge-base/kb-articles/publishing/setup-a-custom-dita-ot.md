---
title: Aangepaste DITA-OT instellen in [!DNL AEM Guides]
description: Leer hoe u aangepaste DITA-OT instelt [!DNL Adobe Experience Manager Guides]
role: Admin
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 0%

---

# Aangepaste DITA-OT instellen in [!DNL AEM Guides] voor AEM

De stappen om een douane DITA-OT toe te voegen worden gedocumenteerd in de sectie _Aangepaste DITA-OT-plug-ins gebruiken_ van de _Installatie- en configuratiehandleiding_.

Op hoog niveau zijn de volgende stappen:

+ Krijg de basisDITA-OT
   + Als u exemplaar van uit-van-de-doos DITA-OT van wilt verkrijgen [!DNL AEM Guides], download deze van het pad `/etc/fmdita/dita_resources/DITA-OT.zip`
   + Als u een andere versie wilt verkrijgen, kunt u downloaden van [dita-ot repo](https://www.dita-ot.org/download)
+ Wijzigingen aanbrengen in DITA-OT als [nieuwe insteekmodule toevoegen](https://www.dita-ot.org/dev/topics/plugins-installing.html)of bestaande plug-ins aanpassen (zie voorbeeld in de sectie Verwante koppelingen hieronder)
+ Uploaden `DITA-OT.zip` ontvangen aan `/apps/<project-folder>/dita_resources` (Aangepaste projectmappen maken wordt aanbevolen)
+ DITA-profiel toevoegen via **[!UICONTROL Tools]** > **[!UICONTROL Guides]** > **[!UICONTROL DITA Profiles]** (gebruik het DITA-OT-pad waar de aangepaste DITA-OT wordt geüpload, raadpleeg de onderstaande screenshot.)
  ![DITA-profielen](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [DITA-OT-insteekmodules aanpassen](https://www.dita-ot.org/dev/topics/pdf-customization.html)
