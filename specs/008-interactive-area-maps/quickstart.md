# Quickstart: Adding & Editing Maps

**Feature**: 008-interactive-area-maps
**Date**: 2026-02-10

## Adding a Map to a Markdown File

1. Find the coordinates for your location:
   - **Climbing areas**: Search on [Mountain Project](https://www.mountainproject.com/) — coordinates are on each area page
   - **Businesses/addresses**: Search on [Google Maps](https://maps.google.com/) — right-click a location → "What's here?" to get coordinates
   - **Trail systems**: Search Google Maps for the trailhead parking lot name

2. Convert coordinates to GeoJSON format:
   - GeoJSON uses `[longitude, latitude]` — **longitude first** (the opposite of Google Maps' display which shows lat, lng)
   - Example: Google Maps shows `35.172, -85.681` → GeoJSON is `[-85.681, 35.172]`

3. Choose the marker color from the convention:

   | Category | Color | Hex |
   |----------|-------|-----|
   | Climbing Tier 1 | Red | `#e74c3c` |
   | Climbing Tier 2 | Blue | `#3498db` |
   | Biking | Green | `#2ecc71` |
   | Breweries | Gold | `#f39c12` |
   | Food | Orange | `#e67e22` |
   | Gear | Purple | `#9b59b6` |
   | Sights | Teal | `#1abc9c` |
   | Lodging | Gray | `#95a5a6` |

4. Add the GeoJSON block to your markdown file:

````markdown
```geojson
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "title": "Your Location Name",
        "description": "One line of context.",
        "marker-color": "#e74c3c",
        "marker-size": "medium"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [-85.681, 35.172]
      }
    }
  ]
}
```
````

5. Push to GitHub and view the file on the web to verify the map renders correctly.

## Adding a Pin to an Existing Map

1. Find the `geojson` code block in the markdown file
2. Add a new Feature object inside the `features` array (after the last `}` and before `]`):

```json
,
{
  "type": "Feature",
  "properties": {
    "title": "New Location",
    "description": "Context note.",
    "marker-color": "#3498db",
    "marker-size": "medium"
  },
  "geometry": {
    "type": "Point",
    "coordinates": [-85.123, 35.456]
  }
}
```

3. Make sure the JSON is valid (matching braces, commas between features but not after the last one).

## Common Mistakes

- **Coordinates reversed**: GeoJSON is `[longitude, latitude]`, NOT `[latitude, longitude]`. If your pin appears in the wrong hemisphere or ocean, you swapped them.
- **Missing comma**: Each feature in the array needs a comma separator. The last feature should NOT have a trailing comma.
- **Wrong hex format**: Use `#RRGGBB` (e.g., `#e74c3c`). Named colors like `"red"` won't work.
- **Map not rendering**: GitHub mobile app doesn't render GeoJSON. Open the URL in a mobile browser instead.

## Viewing Maps

- **GitHub web**: Maps render automatically. Click/tap pins for popups.
- **GitHub mobile app**: Maps do NOT render. Open the same URL in your phone's browser (Safari/Chrome) instead.
- **Local editor (VS Code, etc.)**: Maps won't render locally. Push and view on GitHub.
