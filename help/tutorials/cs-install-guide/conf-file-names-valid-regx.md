---
title: Regx configureren voor geldige bestandsnaamtekens
description: Leer hoe u Regx kunt configureren voor geldige bestandsnaamtekens
source-git-commit: 880cd344ceb65ea339be699ebcad41c0d62e168a
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Regx configureren voor geldige bestandsnaamtekens {#id214BD0550E8}

Vanaf AEM versie 3.8 van de Gidsen, als beheerder, kunt u een lijst van geldige speciale karakters bepalen die in dossiernamen worden toegestaan. In eerdere versies mochten gebruikers bestandsnamen definiëren die speciale tekens bevatten, zoals `@`, `$`, `>`en meer. Deze speciale karakters resulteerden in kwesties terwijl het openen van onderwerpen van het dashboard van de kaart DITA of het klikken op de verbinding van onderwerp in TOC, die vaak in resulteerden dat de pagina niet wegens speciale karakters in URL werd geopend.

Gebruikend de configuratie die u toestaat om een regx voor geldige dossier te bepalen - noem karakters, hebt u volledige controle op hoe de dossiers intern in het systeem worden genoemd. U kunt een lijst met speciale tekens definiëren die zijn toegestaan in de bestandsnamen. Standaard bevat de geldige bestandsnaamconfiguratie &quot;`a-z A-Z 0-9 - _`&quot;. Tijdens het maken van een nieuw bestand kunt u elk speciaal teken in de bestandstitel opnemen, maar intern wordt het vervangen door &quot;`-`&quot; in de bestandsnaam. U kunt bijvoorbeeld de bestandstitel &quot;Introduction 1&quot; of &quot;Introduction@1&quot; hebben. De overeenkomstige bestandsnaam die voor beide gevallen wordt gegenereerd, is &quot;Introduction-1&quot;.

Wanneer u een lijst met geldige tekens definieert, moet u niet vergeten dat deze tekens &quot;`*/:[\]|#%{}?&<>"/+`&quot; wordt altijd vervangen door een &quot;`-`&quot;.

Als u de geldige lijst met speciale tekens niet configureert, kan het maken van bestanden onverwachte resultaten opleveren. Om dergelijke fouten te vermijden, wordt sterk geadviseerd om deze configuratieverandering aan te brengen.

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\) gegevens op om regex te configureren voor geldige bestandsnaamtekens:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `valid.characters` | De waarde is een regex-patroon. Deze moet drie basistekens hebben en de lijst moet beginnen met een koppelteken \(-\).<br> **Standaardwaarde**: \[-a-zA-Z0-9\_\] |

>[!NOTE]
>
> Net als in de lijst met geldige bestandsnaamtekens kunt u ook een lijst met geldige bestandsnaamtekens opgeven voor AEM site-uitvoer. Zie voor meer informatie [Geldige bestandsnamen voor AEM Site-uitvoer configureren](conf-file-names-valid-regx-aem-site-output.md#).

**Bovenliggend onderwerp:**[ Bestandsnamen configureren](conf-file-names.md)
