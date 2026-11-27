# Pagliaroom

Website for **Pagliaroom**, a Sicilian barn for a dreamy retreat in Santo Stefano Quisquina (AG), Sicily.

Visitors explore the house as an interactive 3D model, open real photos of each room, see what is nearby on a map, and send a booking request by email.

## What's on the site

- **The house**: 3D model of the house (three.js), opening on the street view.
  - Guided tour (button): in through the front door, through each room with its photos, and out through the skylight onto the roof.
  - "See inside" cutaway view.
  - Day / Evening switch. Evening also turns the whole site dark, with fireflies and crickets.
  - Swallows with birdsong in the street view.
  - Record player in the living-room niche: plays the Pagliaroom clip, then a 3½-minute instrumental.
- **Photo carousel**: 22 photos in assets/photos/gallery-01..22.jpg, auto-advancing every 4.5 s with a pause button; it pauses on hover, touch or when off-screen.
- **Booking request**:
  - Date picker that only allows dates from today onwards.
  - Prepares an email to `info@pagliaroom.com` with the guest's details.
- **Around Pagliaroom**: minimal map from OpenStreetMap data with five nearby places, their descriptions and distances. It shows only the area of the house, never the exact address.
- **The project**: before-the-renovation photo and survey, architect drawings, and credits.
- **Your Pagliaroom**: guidance and project management for people who want their own little house in Sicily, with an enquiry form that prepares an email.
- **English / Italian**: the site opens in Italian for Italian browsers and remembers the visitor's choice.

## Files

```
index.html              the whole site (HTML, CSS, JavaScript, 3D model, map data)
assets/photos/          room and facade photos (EXIF metadata removed)
assets/drawings/        A-01…A-05 drawings (SVG) and survey drawings (PNG)
assets/audio/           pagliaroom-clip.mp3, paglia-groove.mp3
.nojekyll               tells GitHub Pages to serve files as they are
```

External libraries are loaded from a CDN: three.js r128 and OrbitControls (jsDelivr). Fonts come from Google Fonts (Hanken Grotesk).

## Publish with GitHub Pages

1. Create a repository, e.g. `pagliaroom`, and upload the contents of this folder to its root.
2. Open **Settings → Pages** and choose **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. The site appears at `https://<your-user>.github.io/pagliaroom/` after a minute or two.
4. Optional custom domain, e.g. `www.pagliaroom.com`: add it under **Settings → Pages → Custom domain**, then point a DNS `CNAME` record to `<your-user>.github.io`.

## Run it locally

The music is loaded with `fetch`, which browsers block for pages opened straight from disk (`file://`). Serve the folder instead:

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Things to edit

Search `index.html` for `const HOST=`:

```js
const HOST={pricePerNight:null,currency:"€",contact:"info@pagliaroom.com",location:null};
```

- `pricePerNight`: a number, e.g. `85`. The booking box then shows the price per night and the total for the stay.
- `contact`: the address booking requests are sent to.
- `location`: an optional line for the "Good to know" box.

## Credits and licences

- **Map data**: © OpenStreetMap contributors, available under the Open Database Licence (ODbL), https://www.openstreetmap.org/copyright. The credit line on the map must stay.
- **three.js**: MIT licence.
- **Photos, drawings, the Pagliaroom clip**: © Pagliaroom. All rights reserved unless stated otherwise.
- **"Paglia groove"** (`paglia-groove.mp3`): an original instrumental composed and synthesised for this site.
- **Place descriptions**: written from the FAI "Luoghi del Cuore" pages and the Comune's information.

No licence file is included, so by default all rights are reserved. Add a `LICENSE` file if you want others to reuse the code.
