---
title: Tekstfilters configureren
description: Leer hoe u tekstfilters kunt configureren
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Tekstfilters configureren {#id21BPD0FK0XA}

Met AEM hulplijnen kunt u zoeken naar tekst in de bestanden die zich op het geselecteerde pad van de AEM bevinden. Met filterzoekopdrachten kunt u bestanden zoeken in het paneel van de gegevensopslagruimte of door bestanden bladeren. Wanneer u werkt in de webeditor, moet u het bladerdialoogvenster voor bestanden gebruiken om elementen in te voegen, zoals een afbeelding, verwijzing of een toetsverwijzing.

Standaard kunt u bepaalde verbeterde filters gebruiken om de bestanden in de AEM te doorzoeken. U kunt alle DITA-bestanden of niet-DITA-bestanden op het geselecteerde pad filteren. U kunt ook zoeken naar specifieke waarden in de kenmerken van DITA-elementen. U kunt ook zoeken naar bestanden die door de opgegeven gebruiker zijn uitgecheckt.

>[!NOTE]
>
> U kunt ook het algemene profiel configureren en meer filters voor zoeken toevoegen.

Voer de volgende stappen uit om de tekstfilters te configureren:

1. Meld u als beheerder aan bij Adobe Experience Manager.
1. Klik op de Adobe Experience Manager-koppeling bovenaan en kies **Gereedschappen**.
1. Selecteren **Hulplijnen** in de lijst met gereedschappen en klik op de knop **Mapprofielen**.
1. Klik op de knop **Globaal profiel** tegel.
1. Klikken op **XML Editor-configuratie**.
1. Klikken op **Bewerken** bovenaan.
1. Klik op de knop **Downloaden** pictogram om het bestand ui\_config.json op uw lokale systeem te downloaden. Vervolgens kunt u wijzigingen in het bestand aanbrengen en het bestand vervolgens uploaden.
   1. Configureer de filters in het bestand. U kunt ook aangepaste filters toevoegen, zoals in het onderstaande voorbeeld wordt getoond:

      In het volgende codefragment wordt getoond hoe u filteropties DITA-bestanden, niet-DITA-bestanden, DITA-elementen en uitgecheckt door bestanden kunt toevoegen. Het bevat ook een aangepast filter - Markeringen.

      ```
       "operation":"like"
                                      },
                                      {
                                      "title":"Checked out by",
                                      "property":"jcr:content/cq:drivelock",
                                      "operation":"like",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Checked out by"
                                      },
                                      "children":[
                                      {
                                      "title":"Check out"
                                      }
                                      ]
                                      },
                                      {
                                      "title":"Tags",
                                      "property":"jcr:content/metadata/cq:tags",
                                      "itemConfig":{
                                      "component":"textfield",
                                      "placeholder":"Enter Tag"
                                      },
                                      "children":[
                                      {
                                      "title":"Tags"
                                      }
                                      ]
                                      }
                                      ]
      ```

      In het bovenstaande codefragment is het eerste filter voor DITA-bestanden. De filterdefinitie heeft de volgende parameters:

      ****Titel****: De weergavenaam van het filter. Deze titel wordt weergegeven als filteroptie in het bladerdialoogvenster van het bestand.

      ****Eigenschap****: De eigenschap die moet overeenkomen met de metagegevens van het bestand. Als u bijvoorbeeld alleen bestanden wilt toestaan die de metagegevens van de klasse dita\_in hun eigenschap hebben, neemt het eigenschapsfilter &quot;jcr:content/metadata/dita\_class&quot; als waarde.

      ****Bewerking **:**&quot;exists&quot; opgeven die overeenkomt met het bestaan van de waarde die in de parameter property is opgegeven

1. Upload het bijgewerkte bestand ui\_config.json dat de toegevoegde filters bevat.

De geconfigureerde filters zijn beschikbaar in het deelvenster Filters.

**Bovenliggend onderwerp:**[ Webeditor aanpassen](conf-web-editor.md)
