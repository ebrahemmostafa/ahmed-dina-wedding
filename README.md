# Inviteness Template Source Code — t-5dfd657ef056fc64

This is the static source bundle for the **Ahmed & Dina** wedding invitation template
hosted at `https://inviteness.com/invite-template/t-5dfd657ef056fc64`.

## Architecture

This site is a **React SPA** built with Vite. The application is **fully data-driven**:
the invitation content (couple names, date, photos, sections, fonts, music, videos) is
fetched at runtime from the Inviteness API:

- API base: `https://api.inviteness.com/api`
- Storage base: `https://api.inviteness.com/storage`

When the page loads, the JS bundle fetches the template data from
`GET /api/public/invite-template/t-5dfd657ef056fc64` and renders all sections
dynamically based on that JSON.

## Files Included

### `index.html`
Clean entry HTML pointing to local beautified JS/CSS.

### `js/`
- `index-Bww_-tMg.beautified.js` — Main Vite bundle (beautified, readable)
- `index-Bww_-tMg.js` — Original minified bundle

### `css/`
- `index-CLaaNNlE.css` — Main stylesheet (minified, original asset hash paths)
- `index-CLaaNNlE.beautified.css` — Beautified version
- `font-face-custom.css` — Custom @font-face declarations (4 fonts) with local TTF paths

### `assets/fonts/` (4 custom TTF fonts from Inviteness)
- `diwani-letter.ttf` — Diwani Letter (Arabic calligraphy)
- `edwardian.ttf` — Edwardian Script
- `product-sans.ttf` — Product Sans
- `thuluth.ttf` — Thuluth (Arabic calligraphy)

### `assets/images/` (3 background images)
- `background-1.jpg` — Section background
- `background-2.png` — Section background (transparent PNG)
- `background-3.jpg` — Section background

### `assets/videos/` (3 videos)
- `hero-video.mp4` — Hero section video
- `background-video.mp4` — Section background video
- `package-video.mp4` — Package media asset video

### `assets/audio/`
- `background-music.mp3` — Background music track

### `template-data.json`
Full API response containing all invitation content (875 KB). This includes:
- Couple names (Ahmed & Dina)
- Event date, venue, countdown
- Pre-wedding events, day program, activities
- RSVP form, gift registry, dress code, menu
- Photo gallery references, transport, accommodation
- Special notes, thank-you message

### `favicon.svg` / `vite.svg`
Site icons.

## Google Fonts (loaded via CDN)

The site uses **44 Google Fonts** loaded via `<link>` tags. These are NOT bundled locally
because Google Fonts CDN serves them efficiently with proper unicode-range subsetting.
The fonts used include:

- Playfair Display, Cormorant Garamond, Great Vibes, Dancing Script
- Lora, Cinzel, Alex Brush, Libre Baskerville, Merriweather, Raleway
- Abril Fatface, Bebas Neue, Oswald, Righteous, Passion One
- Bodoni Moda, Cinzel Decorative, Yeseva One
- Inter, Roboto, Open Sans, Lato
- Arabic fonts: Noto Sans Arabic, Noto Naskh Arabic, Noto Kufi Arabic
- IBM Plex Sans Arabic, Cairo, Tajawal, Almarai, Amiri, Changa
- El Messiri, Lateef, Reem Kufi, Scheherazade New, Markazi Text
- Mirza, Harmattan, Katibeh, Lemonada, Lalezar, Mada, Rakkas, Vibes

## Running Locally

Since this is a data-driven SPA, running it locally requires the API to be reachable.
To view the template exactly as it appears online, open `index.html` via a local web
server (e.g. `python3 -m http.server 8000`) — the JS will fetch the live API.

For a fully offline copy of the invitation content, see `template-data.json`.

## External Services Used

- **Stripe** (`js.stripe.com/v3`) — Payment processing for invitation purchases
- **Facebook Pixel** (`connect.facebook.net`) — Analytics
- **Google Fonts** — Font delivery
- **Inviteness API** — All invitation data and media storage
