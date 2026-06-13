# Face Blurring 😎

Een browsergebaseerde tool die gezichten op foto's automatisch onherkenbaar maakt. Geen installatie, geen account, geen server — open het bestand en het werkt direct in de browser.

## Wat doet de app

1. Je kiest of sleept een foto naar de app.
2. De app zoekt automatisch gezichten op de foto met een gezichtsherkenningsmodel.
3. Elk gevonden gezicht wordt gepixeleerd (vervaagd).
4. Je kunt de sterkte van de vervaging en de grootte van het vervaagde gebied aanpassen.
5. Gezichten die niet automatisch herkend zijn (bijv. profiel, klein, ver weg) kun je zelf aanwijzen door een rechthoek te slepen.
6. Met "Download resultaat" sla je de bewerkte foto op.

## Gebruikte technologie

| Onderdeel | Wat het doet | Bron |
|---|---|---|
| **face-api.js** (TinyFaceDetector-model) | Detecteert gezichten op de foto | Open-source JavaScript-library, gebaseerd op TensorFlow.js, geladen vanaf jsDelivr CDN |
| **HTML5 Canvas API** | Tekent de foto, past de pixelatie toe en maakt de download mogelijk | Ingebouwd in elke moderne browser |
| **File / Drag-and-drop API** | Foto inladen via klik of slepen | Ingebouwd in elke moderne browser |
| **Google Fonts** (Space Grotesk, IBM Plex Sans) | Lettertypen van de interface | Geladen vanaf Google Fonts CDN |

Er wordt geen eigen server, database of API-key gebruikt. Het enige externe verkeer is het eenmalig downloaden van het detectiemodel en de lettertypen bij het openen van de pagina.

## Privacy

- De foto verlaat je apparaat **niet**. Alle herkenning en bewerking gebeurt lokaal in de browser.
- Er wordt niets opgeslagen, gelogd of verzonden.
- Bij het laden van de pagina worden eenmalig kleine bestanden (detectiemodel + lettertypen) gedownload vanaf externe CDN's. Dit gebeurt voordat je een foto inlaadt en bevat geen foto-data.

## Beperkingen — lees dit voor gebruik

- Dit is **geen officiële privacy- of beveiligingstool**. Gebruik je eigen beoordeling bij gevoelig of vertrouwelijk materiaal.
- Automatische gezichtsherkenning is niet perfect: gezichten in profiel, deels verborgen, klein, ver weg, of onder ongunstig licht worden soms gemist.
- **Controleer het resultaat altijd zelf** voordat je een foto deelt of publiceert. Gebruik "Zelf gezicht aanwijzen" om gemiste gezichten alsnog te markeren.
- Zeer grote afbeeldingen worden voor de bewerking automatisch verkleind tot maximaal 1600 pixels (langste zijde), zodat de app ook op mobiele apparaten goed presteert.
- Een werkende internetverbinding is nodig bij het **eerste** gebruik (voor het laden van het model en de lettertypen). Daarna werkt de app zonder internet, zolang de pagina openblijft.

## Gebruik

Open `face-blurring.html` in een moderne browser (Chrome, Edge, Firefox, Safari). Geen installatie of build-stap vereist.

## Licentie / credits

- Gezichtsherkenning: [face-api.js](https://github.com/justadudewhohacks/face-api.js) (MIT-licentie), gebaseerd op TensorFlow.js-modellen.
- Overige code: zelfgeschreven HTML/CSS/JavaScript, vrij te gebruiken en aan te passen binnen de AI app store.
