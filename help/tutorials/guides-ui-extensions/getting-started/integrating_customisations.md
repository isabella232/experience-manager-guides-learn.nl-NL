---
sidebar_position: 2
source-git-commit: 42052b37724f97e34ab007db4cc3d9f9524ad3a2
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 0%

---


# Het extensiepakket voor hulplijnen AEM installeren en gebruiken

Met extensies kunt u de app Hulplijnen voor AEM aanpassen aan uw wensen. Dit extensieframework wordt ondersteund door AEM hulplijnen v4.3 en hoger (on-prem) en 2310 (cloud).

## Vereisten

Dit pakket vereist [git bash](https://github.com/git-guides/install-git) en npm

## Installatie

De gemakkelijkste manier om AEM het kaderinstallatie van Gidsen op te starten is door middel van cli

```bash
npx @adobe/create-guides-extension
```

## Aanpassingscode toevoegen

1. Voeg codebestanden toe voor elke component die u wilt uitbreiden in het dialoogvenster `src/` directory. Sommige voorbeeldbestanden zijn al voor u toegevoegd.
2. Nu in de `index.ts` bestand in het dialoogvenster `src/` directory:
   - Het dialoogvenster Importeren `.ts` bestanden met de aanpassingen die u in uw build wilt toevoegen.
   - De import toevoegen aan `window.extension`
   - De aangepaste componenten registreren `id` en corresponderende invoer `tcx extensions`
   - Verwijs naar de steekproef [index.ts](../../../src/index.ts)

## De aangepaste code maken

- Uitvoeren `npm run build` in de hoofdmap. U krijgt 3 bestanden in de map, `dist/`:
   - `build.css`
   - `guides-extension.js`
   - `guides-extension.umd.cjs`

![Uitvoer samenstellen](./../imgs/build_output.png)

## De aanpassing toevoegen aan AEM

- Ga naar `CRXDE` `crx/de/index.jsp#/`
- Onder de `apps` map, maak een nieuw knooppunt van het type `cq:ClientLibraryFolder`

![Mapstructuur](./../imgs/crxde_folder_structure.png)

- In de `properties` van het knooppunt selecteert u `Multi` voeg de volgende bezitsnaam toe: `categories`
Type: `String []`
Waarde: `apps.fmdita.review_overrides`, `apps.fmdita.xml_editor.page_overrides`

![Eigenschappen van map](./../imgs/crxde_folder_properties.png)

- Als u de gebouwde js wilt toevoegen, maakt u een nieuw bestand, bijvoorbeeld: `tcx1.js` in het hierboven gemaakte knooppunt. Voeg hier de code van toe `dist/guides-extension.umd.cjs` of `dist/guides-extension.js`. Maak nu een nieuw bestand `js.txt`Hier voegen we de naam van ons JS-bestand toe, die in dit geval:

```t
#base=.
tcx1.js
```

- Als u de ingebouwde css wilt toevoegen, maakt u een nieuw bestand, bijvoorbeeld `tcx1.css` in het hierboven gemaakte knooppunt. Voeg hier de code van toe `dist/build.css`. Maak nu een nieuw bestand `css.txt`Hier voegen we de naam van ons CSS-bestand toe, die in dit geval:

```t
#base=.
tcx1.css
```

- Doe een `shift + refresh` om de app met de aanpassingen te laden!

## Problemen oplossen

Controleer of alle bovenstaande stappen correct zijn uitgevoerd.
Nadat u de code aan tcx.js hebt toegevoegd, moet u de code hard vernieuwen (shift+refresh).
Open nu AEM, klik met de rechtermuisknop en klik op `Inspect`
Ga naar Bronnen en zoek naar uw `[node_name].js` (bijvoorbeeld: extensions.js) file. Voer een Besturing / Cmd + D uit om naar het bestand te zoeken. Als de `.js` bestand bestaat met de JS-code waaruit u het bestand hebt geplakt `dist/guides-extension.umd.cjs` of `dist/guides-extension.js`, is de installatie voltooid
