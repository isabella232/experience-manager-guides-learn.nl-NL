---
title: Cloud Publishing Microservice-architectuur en -prestaties
description: Begrijp hoe de nieuwe microservice schaalbare publicatie op AEMaaCS mogelijk maakt.
source-git-commit: a8466a16cea7df7757d15005baaf73a39c7952ea
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---


# Cloud Publishing Microservice-architectuur en prestatieanalyse

In dit artikel wordt uitgelegd wat de architectuur en prestatienummers zijn van de nieuwe cloudpublicatiesmicroservice.

>[!NOTE]
>
> Momenteel ondersteunt het op microservices gebaseerde publiceren in AEMHulplijnen alleen PDF-uitvoer met behulp van het publiceren van de native PDF of via DITA-OT. AEM de Gidsen zullen op microservice-gebaseerde het publiceren steun voor meer outputtypes in de toekomstige versies toevoegen.

## Problemen met bestaande publicatieworkflows in de cloud

DITA Publishing is een hulpbronnenintensief proces dat voornamelijk afhankelijk is van het beschikbare systeemgeheugen en de CPU. De behoefte aan deze middelen neemt verder toe als de uitgevers grote kaarten met vele onderwerpen publiceren of als veelvoudige parallelle het publiceren verzoeken teweeggebracht worden.

Als u de nieuwe service niet gebruikt, gebeurt alle publicaties op dezelfde pod Kubernetes (k8) die ook de AEM cloudserver uitvoert. Een standaard k8-pod heeft een limiet voor de hoeveelheid geheugen en CPU die deze kan gebruiken. Als gebruikers van AEM hulplijnen grote of parallelle werklasten publiceren, kan deze limiet snel worden overschreden. K8 start pods opnieuw die meer bronnen proberen te gebruiken dan de geconfigureerde limiet en die ernstige gevolgen kunnen hebben voor de AEM cloudinstantie zelf.

Deze beperking van bronnen was de belangrijkste motivatie om een speciale service te ontwikkelen waarmee we meerdere gelijktijdige en grote publicatiewerklasten in de cloud kunnen uitvoeren.

## Inleiding tot de nieuwe architectuur

De service gebruikt Adobe edge-cloudoplossingen zoals App Builder, IO Event, IMS om een serverloos aanbod te maken. Deze diensten zijn zelf gebaseerd op de algemeen aanvaarde industriestandaarden zoals Kubernetes en docker.

Elk verzoek aan de nieuwe het publiceren microservice wordt uitgevoerd in een geïsoleerde docker container die slechts één het publiceren verzoek tegelijkertijd in werking stelt. Er worden automatisch meerdere nieuwe containers gemaakt voor het geval nieuwe publicatieverzoeken worden ontvangen. Deze enige container per verzoekconfiguratie staat microservice toe om de beste prestaties aan de klanten te leveren zonder enige veiligheidsrisico&#39;s te introduceren. Deze containers worden verwijderd zodra de publicatie is voltooid, waardoor alle gebruikte bronnen vrijkomen.

Al deze communicatie wordt beveiligd door Adobe IMS met behulp van JWT-verificatie en -autorisatie en wordt uitgevoerd via HTTPS.

<img src="assets/architecture.png" alt="tabblad Projecten" width="600">

>[!NOTE]
>
> Het publiceren proces voert sommige inhoud afhankelijke delen van het verzoek op de AEM server zelf uit, zoals de productie van de gebiedslijst. De meest uitgebreide onderdelen van het publicatieproces, zoals het uitvoeren van DITA-OT- of native engine, zijn echter naar de nieuwe service verschoven.


## Prestatieanalyse

In deze sectie worden de prestatienummers van de microservice weergegeven. Het vergelijkt de prestaties van de microservice met AEM Gidsen op prem aanbieden aangezien de oude wolkenarchitectuur problemen had bij het gelijktijdig publiceren of bij het publiceren van zeer grote kaarten.

Als u een grote kaart op prem publiceert, dan zou u de heap parameters van Java kunnen moeten aanpassen of anders kunt u uit-van-geheugenfouten ontmoeten. In de cloud wordt de microservice al geprofileerd en zijn de Java-heap en andere configuraties optimaal.

### Eén publicatie uitvoeren op cloud versus on-prem

* Wolk

   Als u één publicatie uitvoert op de cloud met de nieuwe service, kan het enige publiceren op de voorgrond wat meer tijd in beslag nemen. Deze lichte verhoogde tijd is toe te schrijven aan de gedistribueerde aard van de nieuwe wolkenarchitectuur.

   <img src="assets/cloud_single_publish.png" alt="tabblad Projecten" width="600">

* On-prem

   De resultaten van één publicatie zijn beter op de oude cloudarchitectuur of op de voorgrond, omdat de volledige publicatie plaatsvindt op dezelfde pod/computer waarop AEM wordt uitgevoerd.

   <img src="assets/onprem_single_publish.png" alt="tabblad Projecten" width="600">

### Meerdere publicaties uitvoeren op cloud versus on-prem

* Wolk

   De nieuwe het publiceren microdienst schijnt in dit scenario. Zoals u kunt zien in de onderstaande afbeelding, kan de cloud deze publiceren zonder dat de publicatietijd aanzienlijk toeneemt, gezien de toename van het aantal gelijktijdige publicatietaken.

   <img src="assets/cloud_bulk_publish.png" alt="tabblad Projecten" width="600">

* On-prem

   Als u tegelijkertijd publiceert op een on-prem-server, neemt de prestaties sterk af. Deze prestatievermindering is ernstiger als uitgevers nog meer kaarten tegelijk publiceren.

   <img src="assets/onprem_bulk_publish.png" alt="tabblad Projecten" width="600">

## Aanvullende voordelen

Een deel van elke publicatieaanvraag moet op de AEM worden uitgevoerd om de juiste publicatie-inhoud op te halen die naar de microservice moet worden verzonden. De nieuwe cloudarchitectuur gebruikt AEM taken in plaats van AEM workflows, zoals in de oude architectuur het geval was. Dankzij deze wijziging kunnen AEM beheerders van hulplijnen de instellingen van de wachtrij voor publicatie in de cloud afzonderlijk configureren zonder dat dit gevolgen heeft voor andere AEM taken of workflowconfiguraties.

Hier vindt u meer informatie over het configureren van de nieuwe publicatiemicroservice: [Microservice configureren](configure-microservices.md)