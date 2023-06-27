---
title: Versiebeheer
description: Leer hoe u versies beheert
source-git-commit: 4f15166b1b250578f07e223b0260aacf402224be
workflow-type: tm+mt
source-wordcount: '1498'
ht-degree: 0%

---


# Versiebeheer {#id181GB000XY4}

Versioning is een belangrijk aspect van elk contentbeheersysteem. Hiermee kunt u een momentopname van uw digitale middel op een bepaald tijdstip maken. Met een versie van een digitaal middel op zijn plaats, kunt u de vereiste versie van het middel herstellen en het bijwerken. Doorgaans kunt u voor het maken van een versie van een element het vereiste element uitchecken en inchecken.

Als beheerder kunt u regels afdwingen die gebruikers beperken om een bestand te bewerken zonder het uit te checken. Op dezelfde manier kunt u ervoor zorgen dat alle uitgecheckte bestanden worden ingecheckt om gegevensverlies te voorkomen.

In een omgeving voor meerdere toepassingen is het ook belangrijk ervoor te zorgen dat gebruikers geen bestanden van het systeem verwijderen. Deze vereiste is belangrijker voor bestanden die door andere gebruikers zijn uitgecheckt. Als u wilt voorkomen dat uitgecheckte bestanden per ongeluk door gebruikers worden verwijderd uit het systeem, biedt AEM hulplijnen een configuratie die u kunt gebruiken. Naast uitgecheckte bestanden kunt u ook het verwijderen van bestanden besturen die verwijzingen bevatten of waarnaar wordt verwezen vanuit andere bestanden.

## Nieuwe versie maken voor geüploade bestand

>[!NOTE]
>
> Deze configuratie is alleen van toepassing tijdens het uploaden van bestanden.

Om het **Nieuwe versie maken voor geüploade bestand** voert u de volgende stappen uit:

1. Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken.
1. Geef in het configuratiebestand de volgende \(eigenschap\) details op om het **Nieuwe versie maken voor geüploade bestand** optie:


   | PID | Eigenschappensleutel | Waarde van eigenschap |
   |---|------------|--------------|
   | `com.adobe.fmdita.confi g.ConfigManager` | `create.ver.new.content` | Booleaanse waarde \(true/false\).<br> **Standaardwaarde**: `true` |

>[!NOTE]
>
> Als de optie is geselecteerd, wordt er een nieuw versiebeheermechanisme toegepast dat het standaarduploadgedrag overschrijft dat bij elke volgende upload wordt toegepast, wordt de inhoud van het geüploade bestand als een nieuwe versie opgeslagen. Als deze optie is uitgeschakeld, gebruikt AEM hulplijnen het AEM standaardmechanisme voor versiebeheer.

## Instellingen configureren om het bewerken van uitgecheckte bestanden toe te staan

De redacteur van het Web van Hulplijnen van de AEM staat u toe om onderwerpen te creëren en bij te werken DITA. U kunt de Redacteur van het Web vormen om het uitgeven van slechts die documenten toe te staan die uit de bewaarplaats zijn gecontroleerd. Dit zorgt ervoor dat geen andere schrijver per ongeluk een onderwerp overschrijft dat voor het uitgeven door een andere schrijver wordt geopend. Als een onderwerp eenmaal is geopend voor bewerking, kan een auteur het bestand inchecken op het moment dat het bestand wordt gesloten.

Een andere belangrijke regel is ervoor te zorgen dat de dossiers die zijn gecontroleerd terug in het systeem worden gecontroleerd. Zo voorkomt u dat gebruikers per ongeluk de bestanden sluiten zonder ze weer in te checken.

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\) gegevens op om het bewerken van uitgecheckte bestanden te configureren:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.autocheckout` | Booleaanse waarde \(true/false\).<br> **Standaardwaarde**: `false` |

Bovendien kunt u configureren om een waarschuwingsbericht weer te geven wanneer een uitgecheckt bestand wordt gesloten zonder het op te slaan of terug te controleren in de opslagplaats.

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.checkin` | Booleaanse waarde \(true/false\).<br> **Standaardwaarde**: `false` |

>[!NOTE]
>
> Ongeacht of u deze functie in- of uitschakelt, zijn de opties voor het uitchecken en inchecken van bestanden altijd beschikbaar in een voorvertoning van een onderwerp.

## Uitgecheckt bestand tijdens uploaden overschrijven

>[!NOTE]
>
> *Deze configuratie is alleen van toepassing wanneer u bestanden maakt via de interface Middelen en niet wanneer u bestanden uploadt met het WebDAV-hulpprogramma.*

Voer de volgende stappen uit om gebruikers toe te staan het uploadbestand te overschrijven dat door hen of een andere gebruiker is uitgecheckt:

1. Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken.
1. Geef in het configuratiebestand de volgende \(eigenschap\) details op om het **Uitgecheckt bestand tijdens uploaden overschrijven** optie:


| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.confi g.ConfigManager` | `overwrite.checkout.onupload` | Booleaanse waarde \(true/false\).<br> **Standaardwaarde**: `false` |

>[!NOTE]
>
> Deze optie is standaard uitgeschakeld. Als deze optie is geselecteerd, kunnen gebruikers uitgecheckte bestanden overschrijven. Als de optie niet is geselecteerd, kan het bestand niet worden overschreven als het door de gebruiker of een andere gebruiker is uitgecheckt.

## Verwijderen van uitgecheckte bestanden voorkomen

Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\) gegevens op om te voorkomen dat gebruikers per ongeluk uitgecheckte bestanden verwijderen:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.preventcheckedoutcontentdeletion` | Booleaanse waarde \(true/false\). <br> **Standaardwaarde**: `true` |

## Verwijderen van bestanden waarnaar wordt verwezen voorkomen

Als beheerder kunt u bepalen wie bestanden uit de AEM kan verwijderen. Als een bestand verwijzingen bevat of door een ander bestand wordt genoemd, kunt u met name bepalen wie dergelijke bestanden kan verwijderen.

Met deze configuratie kunt u toestaan of weigeren dat alle gebruikers bestanden verwijderen of alleen een bepaalde gebruikersgroep bestanden laten verwijderen. Als het verwijderen van een bestand is toegestaan, wordt het volgende proces uitgevoerd:

- Als u een map verwijdert, die alle bestanden bevat waarnaar wordt verwezen en waarnaar wordt verwezen, worden alle bestanden verwijderd. Het proces verwijdert eerst alle bestanden die geen verwijzingen bevatten, gevolgd door de bestanden die verwijzingen bevatten of waarnaar wordt verwezen.

- Als u een map verwijdert en naar een bestand in de map wordt verwezen door een bestand buiten die map, wordt u gevraagd de verwijzing te verwijderen voordat u het bestand verwijdert.


Gebruik de instructies die worden gegeven in [Configuratieoverschrijvingen](download-install-additional-config-override.md#) om het configuratiebestand te maken. Geef in het configuratiebestand de volgende \(eigenschap\)-details op om te bepalen wie een bestand kan verwijderen dat verwijzingen bevat of waarnaar wordt verwezen door andere bestanden:

| PID | Eigenschappensleutel | Waarde van eigenschap |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `block.unsafe.delete` | Mogelijke waarden zijn: <br> - allow\_unsafe\_delete\_for\_all <br> - allow\_unsafe\_delete\_for\_delete\_assets\_group <br> - block\_unsafe\_delete\_for\_all <br> **Standaardwaarde**: `allow_unsafe_delete_for_delete_assets_group` <br> De details van deze constanten worden hieronder gegeven. |

Afhankelijk van wie u toegang voor verwijdering wilt geven, geeft u een van de volgende constanten op:

- allow\_unsafe\_delete\_for\_all: Alle gebruikers toestemming geven om bestanden te verwijderen. In dit geval kunt u dergelijke bestanden ook met kracht verwijderen als het bestand\(en\) verwijzingen bevat of door andere bestanden wordt genoemd. Voordat u het bestand verwijdert, verschijnt er een bericht met de referenties waarin u wordt gevraagd of u de verwijderbewerking wilt annuleren, de verwijzingen wilt verwijderen en vervolgens het bestand wilt verwijderen. U kunt ook het bestand of de bestanden zonder geweld verwijderen zonder de referenties te verwijderen.

  ![](assets/allow_unsafe_delete-force-delete.PNG)

- allow\_unsafe\_delete\_for\_delete\_assets\_group: Een beheerder of een gebruiker die bij de *delete-assets* groep mag bestanden verwijderen. Als een andere gebruiker bestanden met verwijzingen probeert te verwijderen, is het hem niet toegestaan deze bestanden te verwijderen totdat alle referenties zijn verwijderd. De volgende schermafbeelding wordt weergegeven wanneer een gebruiker die geen machtigingen heeft, bestanden probeert te verwijderen.

  ![](assets/allow_unsafe_delete_for_delete_assets_group.PNG)

- block\_unsafe\_delete\_for\_all: Alle gebruikers \(inclusief beheerders\) niet toestaan bestanden te verwijderen totdat de verwijzingen naar en van het bestand\(en\) zijn verwijderd.


## Oudere versies van DITA-bestanden wissen

Wanneer u inhoud bijwerkt en nieuwe versies maakt, blijven de vorige versies van DITA-bestanden behouden in de opslagplaats. Veel versies worden gedurende een periode gemaakt voor uw DITA-bestanden en kunnen samen een grote hoeveelheid ruimte innemen in uw opslagplaats. AEM Met hulplijnen kunt u de oudere versies configureren die uit de opslagplaats moeten worden verwijderd.

U hebt toegang tot dit hulpprogramma via de opgegeven URL als u beheerdersrechten hebt:

`<server folder path> /libs/fmdita/clientlibs/xmleditor_version_purge/page.html`

De versie van een DITA-bestand die aan een van de opgegeven criteria voldoet, blijft behouden en wordt niet gewist:

- Is de eerste versie van een bestand
- Is opgenomen in een basislijn
- Is inbegrepen in om het even welke vertaling of revisiewerkschema
- Er is een label op toegepast
- Voldoet aan de gedefinieerde leeftijd of het gedefinieerde aantal versiecriteria

Voer de volgende stappen uit om de oudere versies leeg te maken:

1. Voer de volgende gegevens in over de bestanden die u wilt leegmaken:

   ![](assets/preview-purge-report.png)

1. 
   - **Aantal versies dat moet worden behouden vanaf de nieuwste versie**: Voer het aantal versies in dat u wilt behouden en dat u niet wilt leegmaken. Als we bijvoorbeeld 5 invoeren, blijven de laatste 5 versies behouden en worden de versies vóór die versies gekwalificeerd om te worden gewist als aan andere zuiveringsvoorwaarden wordt voldaan.
- **Versies behouden die zijn gemaakt binnen tijdspan \(in dagen\)**: Voer de maximumleeftijd van een versie in dagen in. De versies ouder dan het opgegeven aantal dagen zijn gekwalificeerd om te worden gezuiverd als aan andere zuiveringsvoorwaarden wordt voldaan. Als we bijvoorbeeld 100 invoeren, kunnen alle versies die vóór 100 dagen zijn gemaakt, worden gewist als aan andere zuiveringsvoorwaarden wordt voldaan.
- **Pad**: Selecteer het pad van het bestand of de map waarvan u de bestanden wilt wissen.

  >[!NOTE]
  >
  > U kunt alleen DITA-bestanden leegmaken.

1. Klikken **Voorvertoning rapport voor wissen**.

   >[!NOTE]
   >
   > Er kan slechts één zuiveringstaak tegelijk zijn. U kunt geen andere versiezuivering in werking stellen als één bezig is.

   Het rapport voor het verwijderen van de versie wordt gegenereerd.

1. Rapport voor het opschonen van versies downloaden en de bestanden en versies controleren die worden gewist.
1. U kunt ervoor kiezen **Wissen annuleren** of **Opschonen starten**.

   ![](assets/download-purge-report.png)

   De status van leegmaken wordt weergegeven.

   Klikken **Rapport voor opschonen van versie downloaden** om de gezuiverde versies weer te geven. Dit rapport bevat de opschonende status voor alle versies, samen met de redenen waarom een bepaalde versie is behouden of waarom deze is gewist.


>[!NOTE]
>
> Het rapport wordt gedownload op de volgende locatie: `/var/dxml/versionpurge`

