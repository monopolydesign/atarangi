# Ātārangi

3D terrain and building shadow viewer for Aotearoa New Zealand.

- CesiumJS globe on LINZ Basemaps imagery and LINZ elevation (DEM/DSM terrain-rgb)
- Real-time sun position and cast shadows from terrain and 3D buildings (LINZ NZ Building Outlines, heights from DSM − DEM)
- Shadow probe: horizon trace, sun/shade status and direct-sun hours for any point
- NZ-only place search (Photon / Nominatim, © OpenStreetMap contributors)
- Local haze, 3D compass, quality presets, phone and tablet layouts

Everything runs in the browser. Open `index.html` directly or serve the folder with any static host.

Data © Toitū Te Whenua LINZ, CC BY 4.0. Search data © OpenStreetMap contributors, ODbL.

## ArcGIS Maps SDK version (`arcgis/`)

`arcgis/index.html` is the same app rebuilt on the ArcGIS Maps SDK for JavaScript 5.1, loaded from Esri's CDN.

- LINZ aerial / Topo50 / hillshade basemaps as web tile layers; LINZ DEM/DSM terrain-rgb as a custom elevation layer
- ArcGIS sun lighting, plus a custom render pass for cast shadows: a height grid of LINZ terrain and building tops is traced towards the sun for every pixel, so terrain and buildings cast dark shadows like the Cesium build (Range and Darkness sliders included)
- 3D buildings from Esri's Esri3D_Buildings_v1 scene service, falling back to LINZ NZ Building Outlines with LiDAR (DSM − DEM) heights if it can't load; an optional ArcGIS API key can be entered in the panel
- Haze uses ArcGIS foggy weather; the shadow probe, search, compass and layout are shared with the Cesium build

Serve it over http(s) (GitHub Pages or `python3 -m http.server`); opening it straight from disk is not supported.
