---
title: Een gegevensbronaansluiting configureren
description: Leer hoe te om een gegevensbronschakelaar te vormen
source-git-commit: bb04590ccb08cde0826dcb60c664f47d7305c9d1
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 0%

---


# Een gegevensbronaansluiting configureren

AEM de Gidsen verstrekt uit-van-de-doos schakelaars voor JIRA en SQL (MySQL, PostgreSQL, SQL Server, SQLite) gegevensbestanden. U kunt andere schakelaars ook toevoegen door de standaardinterfaces uit te breiden. De volgende configuratie helpt u om de diverse gegevensbronnen gemakkelijk toe te voegen. Zodra toegevoegd, kunt u de gegevensbronnen in de Redacteur van het Web bekijken.

Voer de volgende stappen uit om een gegevensbronschakelaar te vormen en dan het van de Redacteur van het Web te gebruiken:

## Een connector configureren

U kunt een out-of-the-box schakelaar vormen door een JSON dossier te uploaden. U kunt de volgende dossiers van de steekproefopstelling aan opstellingsschakelaars voor Jira en SQL (MySQL, PostgreSQL, SQL Server, SQLite) gegevensbestanden gebruiken.

Een voorbeeldinstellingenbestand voor de basisverificatie van Jira met gebruikersnaam en wachtwoord:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"username": "jirausername",
			"password": "jirapassword",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Bijvoorbeeld, sparen als `jira.json`.

Een voorbeeldinstellingenbestand voor de basisverificatie van Jira met token:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Bijvoorbeeld, sparen als `jira.json`.

Een voorbeeldinstellingenbestand voor de basisverificatie van Jira met het token dat het trefwoord &quot;Basic&quot; bevat:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.rest.JiraConnector",
	"configName": "Jira",
	"templateFolders": ["/content/dam/dita-templates/konnect/jira"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.rest.BasicAuthRestConfig",
		"configData": {
			"token": "Basic jiraauthtoken",
			"url": "https://jira.corp.adobe.com/rest/api/latest/search"
		}
	}
}
```

Bijvoorbeeld, sparen als `jira.json`.

Een voorbeeldinstellingenbestand voor de basisverificatie van MySql:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MySqlConnector",
	"configName": "MySQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.mysql.jdbc.Driver",
			"connectionString": "jdbc:mysql://host.corp.adobe.com:3306/plm"
		}
	}
}
```

Bijvoorbeeld, sparen als `mysql.json`.

Een voorbeeldinstellingenbestand voor de basisverificatie van PostgreSQL:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.PostgreSqlConnector",
	"configName": "PostgreSQL",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.postgresql.Driver",
			"connectionString": "jdbc:postgresql://host:port/database"
		}
	}
}
```

Bijvoorbeeld, sparen als `postgres.json`.

Een voorbeeld van een installatiebestand voor de basisverificatie van MS SQL Server:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.MsSqlServerConnector",
	"configName": "MSSQLServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
			"connectionString": "jdbc:sqlserver://10.10.10.10\\SQLEXPRESS01:1433;database=TutorialDB;encrypt=false;trustServerCertificate=true"
		}
	}
}
```

Bijvoorbeeld, sparen als `mssqlserver.json`.

Een voorbeeldinstellingenbestand voor de basisverificatie van SQLite:

```
{
	"connectorClazz": "com.adobe.guides.konnect.definitions.ootb.connector.sql.SqliteConnector",
	"configName": "SQLiteServer",
	"templateFolders": ["/content/dam/dita-templates/konnect/sql"],
	"connectionConfig": {
		"configClazz": "com.adobe.guides.konnect.definitions.ootb.config.sql.UserPassSqlConfig",
		"configData": {
			"username": "admin",
			"password": "admin",
			"driver": "org.sqlite.JDBC",
			"connectionString": "jdbc:sqlite:sample.db"
		}
	}
}
```

Bijvoorbeeld, sparen als `sqqlite.json`.

### Een verbindingsconfiguratie aanpassen

Met AEM hulplijnen kunt u bepaalde waarden in het configuratiebestand aanpassen aan de behoeften van de gebruiker.

| Eigenschapnaam | Beschrijving |
|---|---|
| configName | De gebruiker kan een configuratienaam specificeren helpen de schakelaar identificeren |
| templateFolders | Lijst met mappen waaruit sjablonen worden opgehaald |

Andere gebieden worden aangepast gebaseerd op de config klasse die wordt geselecteerd om de Schakelaar in werking te stellen.

## Het bestand uploaden naar een locatie in AEM

Upload het bestand naar een locatie in AEM Assets.

Bijvoorbeeld,  `/var/dxml/konnect/jira.json`

## Configuratie maken met REST API

U kunt de configuratie registreren met REST API. Voor meer informatie bekijkt u de *REST API om een gegevensbronschakelaar te registreren* in de API-naslag voor Adobe Experience Manager-hulplijnen.

Zodra u de gegevensbron hebt gevormd, is de schakelaar vermeld onder het paneel van Gegevensbronnen in de Redacteur van het Web. U kunt dan met de gegevensbron verbinden en een inhoudsfragment opnemen in uw onderwerpen. Voor meer informatie, bekijkt u [Een inhoudsfragment uit uw gegevensbron invoegen](../user-guide/web-editor-content-snippet.md).

