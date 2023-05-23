---
title: De Geavanceerde Kaarteditor instellen als standaard
description: Leer hoe u de Geavanceerde Kaarteditor instelt als standaard
source-git-commit: 801c306fa120e7889d4b9428fd5bee2849bf1956
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---


# De Geavanceerde Kaarteditor instellen als standaard {#id181AI0003PN}

AEM Hulplijnen worden geleverd met een Basic Map Editor en een Advanced Map Editor. De Basis Redacteur van de Kaart geeft u alle noodzakelijke eigenschappen om uw kaartdossier tot stand te brengen. De Geavanceerde Redacteur van de Kaart is veel eigenschaprijker en het is geïntegreerd binnen de Redacteur van het Web. Met de Geavanceerde Kaarteditor kunnen auteurs DITA-kaartbestanden maken en bewerken met een gebruiksvriendelijke interface.

Wanneer een nieuw kaartbestand wordt gemaakt, wordt dit standaard geopend in de Basic Map Editor. U kunt dit gedrag veranderen door het plaatsen toe te laten om de Geavanceerde Redacteur van de Kaart door gebrek te openen.

Voer de volgende stappen uit om van de Geavanceerde Redacteur van de Kaart als standaardredacteur voor de kaartdossiers te maken:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundel.

1. Selecteer **Basiskaarteditor verbergen** optie.

   Als deze optie is geselecteerd, zien gebruikers nergens in de gebruikersinterface de koppeling Basic Map Editor. Standaard worden kaartbestanden geopend in de Geavanceerde Kaarteditor.


