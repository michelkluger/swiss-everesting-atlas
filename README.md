# Swiss Everesting Atlas

**Live dashboard: https://michelkluger.github.io/swiss-everesting-atlas/**

Where in Switzerland can you do an *hiking Everesting*: climb 8,848 m on foot, ride the lift down after each lap?

The dashboard ranks 1,461 Swiss cable cars, gondolas, chairlifts and funiculars. For most of them, what limits you is the lift's operating hours, not your legs.

## Method

- **Lifts:** OpenStreetMap via Overpass (`aerialway`, `railway=funicular`)
- **Station heights:** swisstopo height API
- **Trail length and climb:** BRouter, `hiking-mountain` profile
- **Travel time from Zürich HB:** transport.opendata.ch
- **Climb time:** DIN 33466. By default 900 m/h vertical and 5 km/h horizontal; both are adjustable in the page.
- **Laps:** `ceil(8848 / rise)`. Total time adds the lift ride and the wait for each descent.
- **Verified lifts:** the top 26 have opening hours, seasons and Halbtax / GA prices checked by hand against the 2026 timetables, used as a proxy for summer 2027.

## Files

- `index.html`: the whole dashboard, a single file with the data embedded
- `lifts.json`: the per-lift rows behind it

Check timetables before you go. Lift operators change their hours every season.
