# Café Radar

A real-time cafe finder which locates you, pulls nearby cafes (name, address,
hours where listed, distance) from the Geoapify Places API, and lets
anyone who visits star their own favorites. No backend, no build step,
just one HTML file.

- **Live data** - real cafe names, addresses and hours from Geoapify on
  every search.
- Map tiles from Geoapify too (same key as the places search)
- **Per-visitor favorites** - stored in each person's own browser
  (`localStorage`), so favorites are private to them.
- Radius filter, click-to-preview on the map.
- No server, no database, no build tooling - deploys as a static file.

## Running it locally

No build step - just open `index.html` in a browser (a "Live Server"-type
tool in your editor works well, since it serves over `http://localhost`,
which geolocation prefers).

## Using your own key instead

Forking this or reusing the code? Swap in your own free key:

1. Sign up at [myprojects.geoapify.com/register](https://myprojects.geoapify.com/register)
   (email only, no credit card) and copy the key from your dashboard.
2. Either paste it into `OWNER_API_KEY` near the top of the `<script>`
   block in `index.html` (same as this repo does), or clear that constant
   back to `"YOUR_API_KEY_HERE"` — then each visitor is prompted to enter
   their own key on first load, saved only in their browser.

## How favorites & keys stay private

Everything is stored in `localStorage`, which is scoped per browser per
site so visitors never see each other's favorites or API keys, and nothing
is sent anywhere except directly to Geoapify.

## Tech

Vanilla HTML/CSS/JS, [Leaflet](https://leafletjs.com/) for the map, and the
[Geoapify Places API](https://apidocs.geoapify.com/docs/places/) +
[Map Tiles API](https://apidocs.geoapify.com/docs/maps/map-tiles/) for cafe
data and the map background (both on one Geoapify key). No frameworks, no
dependencies to install.

## License

MIT — see `LICENSE`.
