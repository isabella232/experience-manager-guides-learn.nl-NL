---
title: Bulkactivering voltooid, gebeurtenishandler
description: Meer informatie over de volledige gebeurtenishandler voor bulkactivering
source-git-commit: 4b0e3f7cf777d2b98eb394fd89235acddef4769a
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 2%

---

# Bulkactivering voltooid, gebeurtenishandler

Hulplijnen voor Experience Manager worden getoond `com/adobe/fmdita/replication/complete` gebeurtenis die wordt gebruikt om bewerkingen uit te voeren na voltooiing van een bulkactiveringsproces. Deze gebeurtenis wordt geactiveerd wanneer een bulkactiveringsproces wordt voltooid. Als u bijvoorbeeld de bulkactivering van een AEM sitevoorinstelling van een kaart uitvoert, wordt deze gebeurtenis aangeroepen nadat het activeringsproces is beëindigd.


U moet een AEM gebeurtenishandler maken om de eigenschappen te lezen die beschikbaar zijn in deze gebeurtenis en verdere verwerking uit te voeren.

De gebeurtenisdetails worden hieronder uitgelegd:

**Gebeurtenisnaam**:

```
com/adobe/fmdita/replication/complete 
```

**Parameters**: |Naam|Type|Omschrijving| |—|—|—| |`path`|String|Het pad van het bestand dat deze gebeurtenis heeft geactiveerd. <br> Bijvoorbeeld, `/content/output/sites/ditamap1-ditamap`. <br> Dit is een lijst met paden die als een JSON-array met serienummering zijn gecodeerd.| |`messageType`|String|Het type van een bericht. <br>Mogelijke optie: `REPLICATION`| |`action`|String|Dit is de uitgevoerde actie. <br>Mogelijke optie: `BulkReplicate`| |`user`|String|De gebruiker die de bewerking heeft gestart.| |`result`|String|Het resultaat van de activering van het opsommingsteken. Het is een geserialiseerd JSON-object: <br>`{"success":boolean,"code":integer,"message":"" }`| |`agentId`|String|The agentId used in the replication. Bijvoorbeeld, `"publish"`.| |`importMode`|Tekenreeks|Importmodus gebruikt in activering. De mogelijke opties zijn: <br>`REPLACE, MERGE, UPDATE`.|


**Voorbeeld van gebeurtenislistener**:

```XML
@Component(service = EventHandler.class,
        immediate = true,
        property = {
                EventConstants.EVENT_TOPIC + "=" + "com/adobe/fmdita/replication/complete",
        })
 
public class SampleEventHandler implements EventHandler {
 
    protected final Logger log = LoggerFactory.getLogger(this.getClass());
 
    @Override
    public void handleEvent(final Event event) {
        Map<String, String> properties = new HashMap<>();
        properties.put("paths", (String) event.getProperty("paths"));
        properties.put("messageType", (String) event.getProperty("messageType"));
        properties.put("action", (String) event.getProperty("action"));
        properties.put("result", (String) event.getProperty("result"));
        properties.put("user", (String) event.getProperty("user"));
        properties.put("agentId", (String) event.getProperty("agentId"));
        properties.put("importMode", (String) event.getProperty("importMode"));
 
        String eventTopic = event.getTopic();
        log.debug("eventTopic {}", eventTopic);
        for(Map.Entry entry:properties.entrySet()) {
            log.debug(entry.getKey() + " : " + entry.getValue());
        }
 
    }
}
```
