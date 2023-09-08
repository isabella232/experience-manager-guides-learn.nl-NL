---
title: REST API om een gegevensbronschakelaar te registreren
description: Meer informatie over de REST API om een gegevensbronaansluiting te registreren
source-git-commit: 8707acf3ba01b7488eea6597c434da73a901d037
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 1%

---


# REST API om een gegevensbronschakelaar te registreren {#id236LG0Y0CXA}

Met de volgende REST API kunt u een gegevensbronaansluiting registreren.

## Een gegevensbronaansluiting registreren

Een methode van GET die een gegevensbronschakelaar registreert.

**Aanvraag-URL**:
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parameter**: |Naam|Type|Vereist|Beschrijving| |—|—|—|—| |`path`|String|Yes|A string which points to a path in the AEM repository. Het kan een pad zijn in de `/content/dam or /var/dxml`.|

**Voorbeeld**:\
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`

