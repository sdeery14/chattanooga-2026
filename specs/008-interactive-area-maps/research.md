# Research: Interactive Area Maps (GeoJSON)

**Feature**: 008-interactive-area-maps
**Date**: 2026-02-10

## GitHub GeoJSON Rendering Capabilities

### Decision: Use fenced `geojson` code blocks in markdown

**Rationale**: GitHub natively renders GeoJSON embedded in markdown files using Leaflet.js + OpenStreetMap tiles. No build step, no external tools, no JavaScript. Works in READMEs, issues, PRs, wikis, and any `.md` file.

**Syntax**:
````
```geojson
{
  "type": "FeatureCollection",
  "features": [...]
}
```
````

**Alternatives considered**:
- Standalone `.geojson` files: GitHub renders these too, but requires navigating to a separate file. Embedding inline keeps maps in context with the content they support.
- Static map images (PNG/SVG): No interactivity (can't zoom, pan, click). Would need regeneration if coordinates change. Rejected.
- Links to geojson.io or Google Maps: Requires leaving GitHub. Adds friction. Rejected as primary approach (could be a fallback for mobile app users).

## Styling: simplestyle-spec 1.1.0

### Decision: Use simplestyle-spec properties for visual differentiation

**Rationale**: GitHub officially supports Mapbox simplestyle-spec 1.1.0. This provides marker colors, sizes, and symbols plus stroke/fill for lines and polygons.

**Supported marker properties**:

| Property | Type | Default | Values |
|----------|------|---------|--------|
| `marker-color` | hex color | `#7e7e7e` | `#e74c3c`, `#3498db`, etc. |
| `marker-size` | string | `medium` | `small`, `medium`, `large` |
| `marker-symbol` | string | `""` | Maki icon IDs, `0`-`9`, `a`-`z` |
| `title` | string | `""` | Popup title on click |
| `description` | string | `""` | Popup description on click |

**Color format**: Only hex colors (`#RGB` or `#RRGGBB`). Named CSS colors (e.g., `red`) are not supported.

**Popup behavior**: The simplestyle-spec defines `title` and `description` for click/hover interaction. GitHub's implementation should wire these to Leaflet popups, though documentation is not 100% explicit. Include both properties regardless — they're harmless if not rendered and provide metadata value in raw JSON.

**Alternatives considered**:
- Custom CSS/JS styling: Not possible on GitHub. GitHub renders maps in a sandboxed iframe.
- TopoJSON: Supported by GitHub but adds complexity without benefit for point-only maps.

## Mobile App Support

### Decision: Design for GitHub web; document mobile browser workaround

**Rationale**: GitHub's native mobile apps (iOS/Android) do NOT render GeoJSON maps. Users see raw JSON or a loading spinner. This is a confirmed, acknowledged limitation with no short-term fix planned by GitHub (as of March 2025 community discussion).

**Workaround**: Opening the same URL in a mobile browser (Safari/Chrome) renders maps correctly. This should be documented in the repo so users know to use their browser instead of the app.

**Alternatives considered**:
- Dual-format (GeoJSON + static images): Would work on mobile app but doubles maintenance burden for every coordinate change. Rejected — the workaround (use mobile browser) is simpler.
- Link to geojson.io viewer: Could include as a secondary fallback alongside the embedded maps.

## Rendering Limits

### Decision: Keep maps under 30 features each (per spec FR-010)

**Rationale**: GitHub can handle up to 10 MB GeoJSON files and auto-clusters at ~750 markers. Our maps will have 1-25 pins each — well within all limits. The 30-pin cap is a readability constraint, not a technical one.

| Limit | Value | Our Usage |
|-------|-------|-----------|
| Max file size for rendering | 10 MB | ~2-5 KB per map block |
| Marker clustering threshold | ~750 markers | Max ~25 per map |
| Projection | CRS84 (WGS84 lon/lat) | Standard — all sources use this |

## Coordinate Sourcing Strategy

### Decision: Use parking/trailhead coordinates from Mountain Project + Google Maps

**Rationale**: FR-008 requires navigable locations (where you actually drive to), not abstract area centroids. Mountain Project provides area-level coordinates that typically point to parking or main boulderfield access. Google Maps provides precise parking lot and business address coordinates.

**Sourcing approach by category**:

| Category | Primary Source | Fallback | Notes |
|----------|---------------|----------|-------|
| Climbing areas (Tier 1) | Mountain Project area page | Google Maps satellite | Verify coordinate points to parking, not mid-boulderfield |
| Climbing areas (Tier 2) | Mountain Project area page | Google Maps | Same verification |
| Trail systems | Google Maps (trailhead parking) | Trail system website | Trailheads are well-marked on Google Maps |
| Restaurants / Breweries | Google Maps (business address) | Business website | Street addresses convert to coordinates via Google Maps |
| Gear shops | Google Maps (business address) | Business website | Same as restaurants |
| Sights & Experiences | Google Maps | Attraction website | Use visitor entrance, not center of property |

**Coordinate format**: GeoJSON uses `[longitude, latitude]` — note the reversed order from the common `lat, lng` convention. Double-check all coordinates for order correctness.

## Map Organization Strategy

### Decision: Category-scoped maps in existing documents, one consolidated personal map

**Rationale**: Rather than creating new standalone map files, embed maps directly in the documents where users are already reading about those destinations. This follows the repo's decision-support philosophy: maps appear in context, not in a separate location that requires navigation.

**Map inventory**:

| Map | Document | Purpose | Est. Pins |
|-----|----------|---------|-----------|
| Regional climbing overview | `areas/README.md` | All climbing areas at a glance | 8-10 |
| Stone Fort detail | `areas/stone-fort.md` | Parking/trailhead for this area | 1-2 |
| Rocktown detail | `areas/rocktown.md` | Parking/trailhead for this area | 1-2 |
| HP40 detail | `areas/hp40.md` | Parking/trailhead for this area | 1-2 |
| Walden's Ridge detail | `areas/waldens-ridge.md` | Parking/trailhead for this area | 1-2 |
| Trail systems overview | `trails/README.md` | All trail system trailheads | 6-8 |
| Town destinations | `rest-days/README.md` | Food, breweries, gear shops | 12-18 |
| Sean's priority map | `sean-guide.md` | Consolidated personal favorites | 15-25 |

**Total**: 8 maps, ~50-65 pins to research

**Alternatives considered**:
- Single mega-map with all destinations: Exceeds 30-pin readability limit. Different audiences need different maps (climbers don't need brewery pins when choosing an area).
- Separate `maps/` directory with standalone files: Breaks context — user has to navigate away from the area profile to see its map. Rejected.
- Maps in every trail profile: Overkill — trail systems are adequately served by the overview map in `trails/README.md`. Individual trail profile maps would duplicate the overview with less context.
