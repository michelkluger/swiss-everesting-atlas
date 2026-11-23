# Data

These are the stages of the compile pipeline, from raw data to dashboard. Each file is the output of the step before it.

| File | Stage | Rows |
|---|---|---|
| `01_osm_lifts_overpass.json` | Raw Overpass result for Switzerland | 1,461 lifts |
| `02_lifts_with_heights.json` | Plus station heights (swisstopo) and rise | 630 |
| `03_candidates_routed.json` | Plus BRouter hiking trail length and ascent | 375 |
| `04_ranked.json` | Plus DIN 33466 climb time, laps and total time | 345 |
| `../lifts.json` | The rows embedded in the dashboard | 336 + 2 manual |
| `05_verified_timetables.json` | Hand-checked hours, fares and seasons | 26 |

Coordinates `A`/`B` are Swiss LV95 (EPSG:2056); `a`/`b` are WGS84. Heights are in metres, lengths in metres (`len`) or km (`km`), and times in minutes.

The format of the `../lifts.json` rows: `[name, type, persons per cabin, rise m, trail km, ride min, wait min, E km, N km, travel min from Zürich HB, class, GA validity, base height]`.

## Sources and licences

- **Lifts:** © OpenStreetMap contributors, [ODbL](https://opendatacommons.org/licenses/odbl/). Files 01 to 04 and `lifts.json` are derived databases under ODbL.
- **Heights:** © swisstopo, via `api3.geo.admin.ch`
- **Trails:** [BRouter](https://brouter.de) on OSM data
- **Travel times:** transport.opendata.ch
- **Border in the map:** Natural Earth (public domain)
- **Timetables and fares:** operator websites, checked 2026-11-24
