---
title: Nieuwe aangepaste actieknop toevoegen op de werkbalk Webeditor
description: Leer hoe u een nieuwe aangepaste knop toevoegt op de werkbalk voor spetters en javascript aanroept om deze aan te passen.
exl-id: 118c4545-9eda-4e1e-a224-843767e49b5b
source-git-commit: ed3adf0cf8006c76461de34c6a2a4ba38d8b3406
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 0%

---

# Nieuwe aangepaste actieknop toevoegen op de werkbalk Webeditor

In dit artikel leren wij hoe een nieuwe douaneknoop in webeditor toolbar toevoegen en javascript roepen om gewenste douaneverrichting uit te voeren.

Het toevoegen van een actioneerbare knoop aan webeditor omvat het volgende stappen:
- De knop toevoegen in het dialoogvenster *ui_config.json* op de plaats waar dat nodig is
- De klikgebeurtenis van de knoop in webeditor registreren voor gebruiker om een actie uit te voeren wanneer zij het klikken


## Implementeren door een voorbeeld te nemen

Laten we dit begrijpen met een voorbeeld waarin een auteur een jira-verwijzing wil toevoegen aan een sectie met een onderwerpenproloog. De proloog sectie met ingebedde jira verwijzing-identiteitskaart kan als hieronder kijken:

![Prologsectie met verwijzing naar JIRA-id](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)

Het element &#39;change-request-id&#39; dat de JIRA-id bevat, moet worden opgehaald uit de API (laat bijvoorbeeld gebaseerd op een specifieke JIRA-query die door de toepassing wordt weergegeven). Wanneer de gebruiker de proloog sectie creeert, zou de gebruiker een knoop moeten kunnen klikken en jira verwijzings identiteitskaart van Web-redacteursttoolbar opnemen, iets als:

![Sectie Prolog - verwijzing JIRA toevoegen](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference.png)

En wanneer de gebruiker op de knop klikt, moet er een dialoogvenster worden weergegeven waarin de mogelijke opties worden weergegeven en de gebruiker de gewenste JIRA-id kan selecteren, bijvoorbeeld:

![Dialoogvenster JIRA-id toevoegen in het gedeelte Prolog](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference-dialog.png)

die vervolgens de &quot;change-request-id&quot; aan de blog moet toevoegen:

![Prologsectie met verwijzing naar JIRA-id](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)



## Dit implementeren


### Voeg de knoop in webeditor toe door het binnen te vormen *ui_config.json*

Gebruik de mapprofielen om de *ui_config.json* onder het tabblad &quot;XML Editor Configuration&quot; en voegt u de knopconfiguratie JSON toe aan het gewenste gedeelte van de groep &quot;toolbar&quot;

```
{
    "on-click":"insertJIRARef",
    "icon":"linkCheck",
    "variant":"quiet",
    "type":"button",
    "title":"Insert JIRA Reference"
}
```

[gebruik deze koppeling voor meer informatie over het mapprofiel en het configureren van ui_config.json](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en)


### De klikgebeurtenis voor de nieuwe knop afhandelen

    OPMERKING: De hieronder vermelde stappen zijn beschikbaar als pakket in dit bericht


- Nadat u het mapprofiel hebt opgeslagen, maakt u een &quot;cq:ClientLibraryFolder&quot; onder een projectmap (mogelijk onder */apps*) en voegt eigenschappen toe, zoals in de onderstaande schermafbeelding wordt getoond:
   ![Instellingen voor clientbibliotheek voor webeditor](../../../assets/authoring/webeditor-add-customtoolbarbutton-clientlibrarysettings.png)

```
This example uses "coralui3" library to show a dialog as it is used in the Javascript sample we presented.
You may use different library of your choice.
```

- Maak onder deze clientbibliotheekmap twee bestanden, zoals hieronder wordt vermeld:
   - *overrides.js*: die de javascript-code heeft voor het afhandelen van de klikgebeurtenis voor &quot;insertJIRARef&quot; (gebruik het bijgevoegde pakket om de inhoud van dit JavaScript op te halen).
   - *js.txt*: die de eigenschap &quot;overrides.js&quot; bevat om dit javascript in te schakelen

- Sla de wijzigingen op en u bent klaar om deze te testen.


### Testen

- Webeditor openen
- Kies uit gebruikersvoorkeuren het mapprofiel waarin u de aangepaste *ui_config.json*. Als u het aan het Globale profiel toevoegt, dan gebruikt u waarschijnlijk reeds dat.
- Open een onderwerp, u zult merken dat de toolbar een nieuwe knoop &quot;de Verwijzing van Jira van het Tussenvoegsel&quot;heeft
- Vervolgens kunt u de sectie Prolog toevoegen zoals hieronder aan het onderwerp wordt gegeven en vervolgens klikken in de knop &quot;Jira-verwijzing invoegen&quot; in het prologelement &quot;change-request-reference&quot;

```
<prolog>
    <change-historylist>
        <change-item>
            <change-request-reference>
            </change-request-reference>
            <change-completed></change-completed>
            <change-summary></change-summary>
        </change-item>
    </change-historylist>
</prolog>
```

Zie onderstaande screenshot voor een uitleg van hoe deze eruitziet:

![Nieuwe knop testen](../../../assets/authoring/webeditor-add-customtoolbarbutton-testing.png)


### Bijlagen

- Voorbeeldclientlibs-pakket waarmee de clientbibliotheek van de webeditor wordt geïnstalleerd met javascript-code voor knopactie op de werkbalk: [downloaden met deze koppeling](../../../assets/authoring/webeditor-addbuttonontoolbar-insertjira-clientlib.zip)
- Monster *ui_config.json* die u kunt uploaden naar een mapprofiel: [voorbeeldbestand ui_config.json downloaden](../../../assets/authoring/sample_ui_config_Guides4.2-InsertJiraReference.json)

```
Please note this is compatible to AEM 6.5 and AEM Guides version 4.2.
If you are using a different version please add the toolbar button to the ui_config.json manually.
```
