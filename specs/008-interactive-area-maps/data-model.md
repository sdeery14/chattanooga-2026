# Data Model: Interactive Area Maps (GeoJSON)

**Feature**: 008-interactive-area-maps
**Date**: 2026-02-10

## Overview

This feature uses GeoJSON (RFC 7946) embedded in markdown. There is no database or application state. The "data model" is the GeoJSON structure and the property conventions used across all maps in the repo.

## GeoJSON Structure

Every map is a GeoJSON `FeatureCollection` containing one or more `Feature` objects with `Point` geometries.

```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "title": "Stone Fort (LRC)",
        "description": "Tier 1. ~1 hr 15 min from Chattanooga. 700+ problems V0-V14.",
        "marker-color": "#e74c3c",
        "marker-size": "large",
        "category": "climbing",
        "tier": 1
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-85.681, 35.172]
      }
    }
  ]
}
```

## Property Schema

### Required Properties (all features)

| Property | Type | Description | Example |
|----------|------|-------------|---------|
| `title` | string | Display name shown in popup | `"Stone Fort (LRC)"` |
| `description` | string | One-line context (drive time, grade range, specialty) | `"Tier 1. ~1 hr 15 min. 700+ problems V0-V14."` |
| `marker-color` | string (hex) | Color per category convention (see below) | `"#e74c3c"` |
| `marker-size` | string | `"small"`, `"medium"`, or `"large"` | `"large"` |

### Optional Properties (for internal organization — not rendered by GitHub)

| Property | Type | Description | Example |
|----------|------|-------------|---------|
| `category` | string | Destination type | `"climbing"`, `"biking"`, `"brewery"`, `"food"`, `"gear"`, `"sights"` |
| `tier` | number | Climbing area tier (1 or 2) | `1` |

These optional properties are not part of simplestyle-spec and won't affect rendering, but they make the raw JSON self-documenting and easier to maintain.

## Color Convention

| Category | Hex Code | Marker Size | Usage |
|----------|----------|-------------|-------|
| Climbing — Tier 1 | `#e74c3c` | `large` | Stone Fort, Rocktown, HP40, Walden's Ridge |
| Climbing — Tier 2 | `#3498db` | `medium` | Hospital Boulders, Dayton Pocket, Cumberland/Pep Boys, Zahnd Tract, Foster Falls, Suck Creek |
| Mountain Biking | `#2ecc71` | `medium` | White Oak, Enterprise South, Coldwater, Raccoon Mountain, Stringer's Ridge, Five Points |
| Breweries | `#f39c12` | `medium` | Hutton & Smith, Five Wits, Chattanooga Brewing, OddStory, WanderLinger |
| Restaurants / Food | `#e67e22` | `medium` | Sugar's Ribs, Edley's, Tremont Tavern, Champy's, etc. |
| Gear Shops | `#9b59b6` | `medium` | Suck Creek Cycle, Rock/Creek, Gear Closet, REI |
| Sights & Experiences | `#1abc9c` | `medium` | Sunset Rock, Ruby Falls, Rock City, Raccoon Mountain Caverns |
| Lodging (reference) | `#95a5a6` | `small` | Enterprise South Nature Park area (assumed lodging zone) |

## Coordinate Convention

- **Format**: `[longitude, latitude]` (GeoJSON standard — note reversed order from common lat/lng)
- **Precision**: 3-4 decimal places (sufficient for ~10m accuracy)
- **Target**: Parking lots or trailheads (navigable locations), NOT boulder-field centroids
- **Projection**: CRS84 / WGS84 (standard for all web mapping)

## Map Inventory

| Map ID | Document | Features (est.) | Categories Present |
|--------|----------|-----------------|-------------------|
| `climbing-overview` | `areas/README.md` | 8-10 | Climbing Tier 1, Climbing Tier 2 |
| `stone-fort-detail` | `areas/stone-fort.md` | 1-2 | Climbing Tier 1 |
| `rocktown-detail` | `areas/rocktown.md` | 1-2 | Climbing Tier 1 |
| `hp40-detail` | `areas/hp40.md` | 1-2 | Climbing Tier 1 |
| `waldens-ridge-detail` | `areas/waldens-ridge.md` | 1-2 | Climbing Tier 1 |
| `trails-overview` | `trails/README.md` | 6-8 | Mountain Biking |
| `town-destinations` | `rest-days/README.md` | 12-18 | Breweries, Food, Gear, Sights |
| `sean-priority` | `sean-guide.md` | 15-25 | All categories |

## Validation Rules

- Every feature MUST have `title`, `description`, `marker-color`, and `marker-size` properties
- Every `marker-color` MUST use hex format (`#RRGGBB`) from the color convention table
- Coordinates MUST be `[longitude, latitude]` with longitude in the range [-90, -80] and latitude in the range [33, 36] (Chattanooga / North Alabama / North Georgia region)
- No single FeatureCollection may exceed 30 features
- `title` should be concise (under 40 characters)
- `description` should be one line of context (under 80 characters)
