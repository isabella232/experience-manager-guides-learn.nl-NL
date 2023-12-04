---
title: Regx configureren voor geldige bestandsnaamtekens
description: Leer hoe u Regx kunt configureren voor geldige bestandsnaamtekens
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 0%

---

# Regx configureren voor geldige bestandsnaamtekens {#id214BD0550E8}

Vanaf AEM versie 3.8 van de Gidsen, als beheerder, kunt u een lijst van geldige speciale karakters bepalen die in dossiernamen worden toegestaan. In eerdere versies mochten gebruikers bestandsnamen definiëren die speciale tekens bevatten, zoals `@`, `$`, `>`en meer. Deze speciale karakters resulteerden in kwesties terwijl het openen van onderwerpen van DITA Kaart Dashboard of het klikken op de verbinding van onderwerp in TOC, die er vaak toe leidden dat de pagina niet wegens speciale karakters in URL werd geopend.

Gebruikend de configuratie die u toestaat om een regx voor geldige dossier te bepalen - noem karakters, hebt u volledige controle op hoe de dossiers intern in het systeem worden genoemd. U kunt een lijst met speciale tekens definiëren die zijn toegestaan in de bestandsnamen. Standaard bevat de geldige bestandsnaamconfiguratie &quot;`a-z A-Z 0-9 - _`&quot;. Tijdens het maken van een nieuw bestand kunt u elk speciaal teken in de bestandstitel opnemen, maar intern wordt het vervangen door &quot;`-`&quot; in de bestandsnaam. U kunt bijvoorbeeld de bestandstitel &quot;Introduction 1&quot; of &quot;Introduction@1&quot; hebben. De overeenkomstige bestandsnaam die voor beide gevallen wordt gegenereerd, is &quot;Introduction-1&quot;.

Wanneer u een lijst met geldige tekens definieert, moet u niet vergeten dat deze tekens &quot;`*/:[\]|#%{}?&<>"/+`&quot; wordt altijd vervangen door een &quot;`-`&quot;.

Als u de geldige lijst met speciale tekens niet configureert, kan het maken van bestanden onverwachte resultaten opleveren. Om dergelijke fouten te vermijden, wordt sterk geadviseerd om deze configuratieverandering onmiddellijk na de bevordering van uw bouwstijl aan versie 3.8 te maken.

Voer de volgende stappen uit om regx te configureren voor geldige \(of toegestane\) tekens in bestandsnamen:

1. Open de Adobe Experience Manager Web Console Configuration-pagina.

   De standaard-URL voor toegang tot de configuratiepagina is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Zoeken naar en klikken op de knop *com.adobe.fmdita.config.ConfigManager* bundel.

1. In de **Regex voor geldige tekens** eigenschap, controleer of de eigenschap is ingesteld op \[-a-zA-Z0-9\_\]. U kunt meer tekens aan deze lijst toevoegen. De lijst moet echter deze basistekens hebben en de lijst moet beginnen met een koppelteken &quot;-&quot;.

   >[!NOTE]
   >
   > Deze eigenschap is alleen van toepassing op bestandsnamen en niet op mapnamen.

1. Klikken **Opslaan**.


>[!NOTE]
>
> Net als in de lijst met geldige bestandsnaamtekens kunt u ook een lijst met geldige bestandsnaamtekens opgeven voor AEM site-uitvoer. Zie voor meer informatie [Geldige bestandsnamen voor AEM Site-uitvoer configureren](conf-file-names-valid-regx-aem-site-output.md#).

**Bovenliggend onderwerp:**[ Bestandsnamen configureren](conf-file-names.md)
