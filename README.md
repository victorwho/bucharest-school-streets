# School Streets

Cycling-risk bands for the street outside every school and highschool, city by city.

| City | Page | Institutions | Streets |
|---|---|---|---|
| Bucharest | `/` | 303 | 279 |
| Iași | `/iasi/` | 50 | 44 |

K-12 institutions from OpenStreetMap, each matched by spatial lookup to the
nearest named street, with that street's risk band from the Defensive Pedal
cycling-safety routing model, plus the factors that push its risk up or down.

**Live page:** see the repository's GitHub Pages deployment.

## What's shown

- **Risk bands** (Safer / Typical / High / Extreme), not raw model scores.
- **Factors by direction only** (▲ raises risk, ▼ lowers it) — never by weight.
  The model's numeric outputs and factor weights are not published here.
- A vector map of the city drawn entirely from OpenStreetMap data and baked into
  the page — no external tile server is contacted.

## Method

A street's band comes from the length-weighted average across every road segment
carrying that street name inside the city's administrative boundary (OSM
relation 377733 for Bucharest, 1207838 for Iași), restricted to drivable street classes. Each school is matched
to its geometrically nearest such street (median distance 43 m in Bucharest,
42 m in Iași). `amenity=school` entries that are not K-12 -- driving schools,
after-school programs, kindergartens, post-secondary vocational schools --
are excluded (30 in Bucharest, 2 in Iași).

## Attribution

Street geometry, school locations, water and parks © OpenStreetMap contributors,
licensed under the [Open Database License](https://www.openstreetmap.org/copyright).

Each page is a single self-contained `index.html` with no runtime dependencies;
both are generated from one template so a copy edit lands on both.
