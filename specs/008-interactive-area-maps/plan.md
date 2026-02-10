# Implementation Plan: Interactive Area Maps (GeoJSON)

**Branch**: `008-interactive-area-maps` | **Date**: 2026-02-10 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/008-interactive-area-maps/spec.md`

## Summary

Embed interactive GeoJSON maps throughout the repository's markdown documents so that climbing areas, trail systems, and town destinations are visually locatable on GitHub (web). Maps use GitHub's native GeoJSON rendering via fenced code blocks with the `geojson` language identifier, styled with the simplestyle-spec 1.1.0 (`marker-color`, `marker-size`, `title`, `description`). No external tools, build steps, or code required — this is pure content authoring.

## Technical Context

**Language/Version**: Markdown + GeoJSON (RFC 7946). No programming language.
**Primary Dependencies**: GitHub's native GeoJSON renderer (Leaflet.js + OpenStreetMap tiles). Simplestyle-spec 1.1.0 for marker styling.
**Storage**: Markdown files in the repository (no database, no external storage)
**Testing**: Manual visual verification on GitHub web after push. Coordinate spot-checks against Google Maps / Mountain Project.
**Target Platform**: GitHub web (primary). GitHub mobile app does NOT render GeoJSON — users must open in mobile browser for map views.
**Project Type**: Knowledge base — content authoring only
**Performance Goals**: Each map < 30 features (spec FR-010). All maps well under GitHub's 10 MB rendering limit.
**Constraints**: Maps only render on GitHub web (not mobile app, not local markdown editors). Offline use requires external apps (Gaia GPS, Mountain Project).
**Scale/Scope**: ~8-12 maps total across the repo. ~50-70 total map points to research and plot.

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Status | Notes |
|-----------|--------|-------|
| **I. Decision-Support First** | PASS | Maps directly answer "Where is this?" — the most fundamental spatial decision question. Skimmable in under 10 seconds. |
| **II. Bouldering Scope Boundary** | PASS | Maps show bouldering areas only (no sport/trad). Mountain biking and town destinations are separate categories per the vision doc. |
| **III. Ability-Aware, Hard-Climbing Priority** | PASS | Regional overview map covers all areas including those selected for V10 objectives. Maps don't alter area selection priorities. |
| **IV. Mountain Biking as First-Class Activity** | PASS | Trail systems get their own map pins with distinct visual markers, not buried under climbing content. |
| **V. Source Accuracy & Recency** | PASS | All coordinates sourced from Mountain Project, Google Maps, or Gaia GPS — verifiable and current. |

**Content Quality Gates**:
1. Skimmability: PASS — maps are visual, absorbed in seconds
2. Decision-orientation: PASS — answers "where to go?" directly
3. Scope: PASS — bouldering + biking boundaries respected
4. Ability coverage: N/A — maps show locations, not grade-specific content
5. Source: PASS — coordinates are verifiable against mapping services

**Gate result**: All clear. No violations.

## Project Structure

### Documentation (this feature)

```text
specs/008-interactive-area-maps/
├── plan.md              # This file
├── research.md          # Phase 0: GeoJSON capabilities + coordinate sourcing
├── data-model.md        # Phase 1: Map point schema and color conventions
├── quickstart.md        # Phase 1: How to add/edit maps
└── tasks.md             # Phase 2 output (/speckit.tasks command)
```

### Content Changes (repository root)

```text
# Maps embedded in existing documents (no new directories created)

areas/
├── README.md            # + Regional overview map (all Tier 1 + Tier 2 climbing areas)
├── stone-fort.md        # + Single-area parking/trailhead map
├── rocktown.md          # + Single-area parking/trailhead map
├── hp40.md              # + Single-area parking/trailhead map
├── waldens-ridge.md     # + Single-area parking/trailhead map
└── (Tier 2 profiles)    # Covered by regional overview map; no individual maps

trails/
└── README.md            # + Trail systems overview map (all 6 wishlist trails)

rest-days/
└── README.md            # + Town destinations map (food, breweries, gear shops)

sean-guide.md            # + Consolidated personal priority map
```

**Structure Decision**: No new directories or files created. All maps are GeoJSON code blocks embedded in existing markdown documents. This follows the repo's "edit existing files" convention and avoids file bloat.

## Map Placement Summary

| Document | Map Location | Pin Count (est.) | Category Colors |
|----------|-------------|-------------------|-----------------|
| `areas/README.md` | After area comparison table | 8-10 | Tier 1: red, Tier 2: blue |
| `areas/stone-fort.md` | After Overview section | 1-2 | Red (parking) |
| `areas/rocktown.md` | After Overview section | 1-2 | Red (parking) |
| `areas/hp40.md` | After Overview section | 1-2 | Red (parking) |
| `areas/waldens-ridge.md` | After Overview section | 1-2 | Red (parking) |
| `trails/README.md` | After comparison table | 6-8 | Green (trailheads) |
| `rest-days/README.md` | After Quick Decision table | 12-18 | Orange (food), Gold (breweries), Purple (gear) |
| `sean-guide.md` | After Table of Contents | 15-25 | Multi-category (red/green/orange/gold/purple/teal) |

## Color Convention

| Category | Marker Color | Hex | Marker Size |
|----------|-------------|-----|-------------|
| Climbing — Tier 1 | Red | `#e74c3c` | large |
| Climbing — Tier 2 | Blue | `#3498db` | medium |
| Mountain Biking | Green | `#2ecc71` | medium |
| Breweries | Gold | `#f39c12` | medium |
| Restaurants / Food | Orange | `#e67e22` | medium |
| Gear Shops | Purple | `#9b59b6` | medium |
| Sights & Experiences | Teal | `#1abc9c` | medium |
| Lodging (reference) | Gray | `#95a5a6` | small |
