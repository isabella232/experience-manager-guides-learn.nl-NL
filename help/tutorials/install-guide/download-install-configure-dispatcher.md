---
title: Dispatcher configureren
description: Leer hoe u Dispatcher configureert
source-git-commit: 9fe396dcfd2e3570ec386c958d7d4efdb4d608e5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 3%

---


# Dispatcher configureren {#id213BCM0M05U}

Als u een Dispatcher op AEM Author-instantie samen met AEM Gidsen wilt gebruiken, dan moet u de volgende extra configuraties uitvoeren om de opstelling te voltooien:

>[!NOTE]
>
> Dispatcher is de Adobe Experience Manager-tool voor cache- en taakverdelingsbewerkingen. Voor meer informatie over het gebruik van Dispatcher raadpleegt u [Overzicht van verzending](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=en).

## EnableEncodedSlashes in URLs inschakelen

URL&#39;s met gecodeerde schuine strepen zijn standaard niet ingeschakeld in AEM installatie van de verzender, maar als u werkt in AEM hulplijnen, moet u deze optie inschakelen. Hiervoor moet u de parameter AllowEncodedSlashes instellen op Aan in Apache-configuratie, zoals in het volgende fragment wordt getoond:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Het bestand mime.types configureren voor DITA

Wanneer u een Dispatcher met AEM hulplijnen gebruikt, moet u ervoor zorgen dat de DITA-kaart en onderwerpbestanden worden gerenderd als HTML zodat auteurs de inhoud kunnen bekijken zoals ze \(in plaats van onbewerkte tekstindeling\) verwachten.

Voer de volgende stappen uit om het bestand mime.types bij te werken:

1. Maak verbinding met de Dispatcher-server met SSH en blader naar het bestand httpd.conf.

1. Controleer het pad van het bestand &quot; mime.types&quot;.

1. Open het bestand mime.types en zoek naar &quot; text/html&quot;. De standaardtoewijzing voor &quot; text/html&quot; is:

   `text/html html htm`

1. Werk de afbeelding bij door ditamap- en dita-extensies toe te voegen als:

   `text/html html htm ditamap dita`

1. Sla het bestand op en sluit het.


Deze configuratieupdate zorgt ervoor dat de kaart DITA en onderwerpdossiers die door de Verzender worden teruggegeven als HTML in Elementen UI worden getoond.

## Aanvraag-URL voor gebruikersvoorkeuren toestaan

Als u een Dispatcher met AEM hulplijnen gebruikt en uw instantie Auteur een verzender vooraan heeft, brengt u de volgende twee wijzigingen aan:

- Whitelist de POST verzoek URL. Een voorbeeld &quot; `/filters`De regel wordt hieronder gegeven - voeg deze regel aan het configuratiedossier van de verzender toe:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Controleer of het URL-patroon &quot; /libs/cq/security/userinfo.json&quot; niet in de cache is opgeslagen bij de auteur-dispatcher. Voeg daarom een regel \(zoals hieronder\) toe in de auteur\_dispatcher.any

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Bovenliggend onderwerp:**[ Downloaden en installeren](download-install.md)

