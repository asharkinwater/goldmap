# Gold Prospecting Map — Groveland, CA

Interactive web map for metal detecting and sluicing sites in Tuolumne County / Sierra Nevada foothills.

## How to use
Open `index.html` in any browser. No server needed — it runs locally.

## Folder structure
- `index.html` — interactive Leaflet map
- `data/locations.geojson` — all point-of-interest data (edit this to add/remove locations)
- `layers/` — drop in custom GeoJSON layers here (BLM claim shapefiles, USGS geology, etc.)

## Adding new locations
Edit `data/locations.geojson` — each feature follows this schema:
- `name` — display name
- `category` — placer_river | placer_hike | blm_designated | lode_tailings | base
- `owner` — USFS / BLM / private
- `drive_min` — minutes from Groveland
- `claim_density` — low | low-medium | medium | high
- `panning` / `sluicing` / `metal_detecting` / `suction_dredge` — true/false
- `gold_type` — description of expected gold character
- `why_promising` — geological / historical rationale
- `notes` — access warnings, contacts, seasonal info
- `verify_claims` — true if you need to check BLM MLRS before going

## Adding BLM claim layers
1. Download Tuolumne County claim shapefile from BLM MLRS or thediggings.com
2. Convert to GeoJSON (use QGIS or mapshaper.org)
3. Save to `layers/` folder
4. Add a `fetch('layers/your-file.geojson')` block in index.html to render it

## Data sources
- BLM MLRS: https://mlrs.blm.gov
- The Diggings (claim map): https://thediggings.com/usa/california/tuolumne-ca109/map
- USGS MRDS: https://mrdata.usgs.gov/mrds/
- Stanislaus NF: https://www.fs.usda.gov/stanislaus
