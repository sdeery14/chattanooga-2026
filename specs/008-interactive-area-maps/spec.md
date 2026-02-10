# Feature Specification: Interactive Area Maps (GeoJSON)

**Feature Branch**: `008-interactive-area-maps`
**Created**: 2026-02-10
**Status**: Draft
**Input**: User description: "Feature 008: Interactive Area Maps (GeoJSON) from the vision.md doc"

## User Scenarios & Testing

### User Story 1 — Find a Climbing Area on the Map (Priority: P1)

Sean is reviewing area profiles on GitHub (web or mobile app) before or during the trip and wants to see where each climbing area is relative to lodging and other destinations. He scrolls to a map embedded in the repo and sees labeled pins for each Tier 1 climbing area — Stone Fort, Rocktown, HP40, Walden's Ridge — plus parking/trailhead locations. He taps a pin to see the area name and key context (drive time from lodging, number of problems at his level).

**Why this priority**: The entire feature exists to answer "where is this?" visually. Climbing areas are the primary destinations on the trip, and spatial orientation between them is the highest-value use of maps. Without this, users rely on separate apps or mental models built from text-only drive-time tables.

**Independent Test**: Open the repo on GitHub web or mobile, navigate to a map, and visually identify all Tier 1 climbing area locations with labels — in under 10 seconds.

**Acceptance Scenarios**:

1. **Given** a user opens a document containing a GeoJSON map on GitHub, **When** the page renders, **Then** an interactive map displays with labeled pins for all Tier 1 climbing areas (Stone Fort, Rocktown, HP40, Walden's Ridge).
2. **Given** the map is rendered, **When** the user clicks/taps a pin, **Then** a popup shows the area name, approximate drive time from Chattanooga lodging, and a brief context note.
3. **Given** Tier 2 areas exist in the repo (Hospital Boulders, Dayton Pocket, Cumberland/Pep Boys, etc.), **When** viewing the map, **Then** Tier 2 areas are visually distinguishable from Tier 1 (e.g., different pin color or style).

---

### User Story 2 — Find Mountain Biking Trails on the Map (Priority: P2)

Sean wants to see where trail systems are relative to climbing areas so he can plan combo days (climb in the morning, ride in the afternoon). He views a map showing both climbing areas and trail systems with distinct visual markers, letting him quickly assess which rides pair with which climbing areas based on proximity.

**Why this priority**: Sean is the only mountain biker and frequently needs to split from the group. The climbing-area pairing table in his guide is useful but lacks spatial intuition — a map makes drive-time relationships immediately obvious.

**Independent Test**: Open a map and visually identify which trail system is closest to HP40 — confirming the Coldwater Mountain pairing — in under 10 seconds.

**Acceptance Scenarios**:

1. **Given** a map displays both climbing areas and trail systems, **When** the user views it, **Then** trail systems are visually distinct from climbing areas (different color or marker style).
2. **Given** the map renders, **When** the user taps a trail system pin, **Then** a popup shows the trail name, total miles, and character summary (e.g., "25 mi machine-built flow").

---

### User Story 3 — Find Town Destinations (Food, Breweries, Gear Shops) (Priority: P3)

The group finishes climbing and wants to grab dinner and hit a brewery. Sean opens a town-focused map and sees pins for his "don't miss" restaurants, the IPA crawl breweries, and gear shops — all plotted in Chattanooga. He can see which spots are walkable from each other (the Southside brewery cluster) vs. which require a drive (Tremont Tavern on North Shore).

**Why this priority**: Town navigation is lower stakes than area-finding (Google Maps works fine for addresses), but a consolidated map of curated spots adds convenience — especially for the IPA crawl walkability and clustering food stops near breweries.

**Independent Test**: Open the town map and identify all three IPA crawl breweries and confirm they cluster within walking distance — in under 10 seconds.

**Acceptance Scenarios**:

1. **Given** a town map renders on GitHub, **When** the user views it, **Then** pins appear for all "don't miss" restaurants, breweries, and gear shops from the personal guide.
2. **Given** the map shows breweries, **When** the user views the Southside area, **Then** the three IPA crawl breweries (Hutton & Smith, Five Wits, Chattanooga Brewing) are visibly clustered, confirming walkability.
3. **Given** multiple destination categories exist, **When** viewing the map, **Then** each category (breweries, restaurants, gear shops) uses a distinct visual marker or color.

---

### User Story 4 — Sean's Personal Priority Map (Priority: P4)

Sean wants a single consolidated map in his personal guide showing all his priority destinations across categories — his top climbing areas, preferred trail systems, must-hit breweries, and key food spots. This is a personal "everything I care about" overview map.

**Why this priority**: This consolidates the spatial picture for Sean's personal decision-making. Lower priority because it overlaps with the category-specific maps, but adds value as a one-stop overview in his personal guide.

**Independent Test**: Open Sean's personal guide on GitHub and see a single map with his top-priority destinations across all categories, visually distinguishable by type.

**Acceptance Scenarios**:

1. **Given** Sean opens his personal guide on GitHub, **When** the map renders, **Then** it shows pins for his priority stack items across climbing, biking, food, and sights.
2. **Given** the consolidated map is displayed, **When** viewing it, **Then** each category is visually distinguishable (climbing vs. biking vs. food vs. sights).

---

### Edge Cases

- **GeoJSON not rendering**: GitHub occasionally has rendering issues with large GeoJSON blocks. If a map fails to render, the raw JSON is still visible — coordinates can be copied into Google Maps or Gaia GPS manually.
- **Mobile app rendering**: GitHub mobile app may render GeoJSON differently than web. Maps should be tested on both GitHub web and the GitHub mobile app to confirm pin visibility and popup functionality.
- **Coordinate accuracy**: Climbing area coordinates sourced from Mountain Project or Gaia may point to parking lots, trailheads, or boulder fields — these are different locations. The map should consistently use parking/trailhead coordinates (where you actually navigate to), not boulder-field centroids.
- **Too many pins on one map**: A map with 30+ pins becomes cluttered. Category-specific maps should contain only relevant pins (not everything on every map).
- **Offline use**: GeoJSON maps require GitHub rendering and do not work offline. Users who need offline maps should use Gaia GPS or Mountain Project with pre-downloaded areas.

## Requirements

### Functional Requirements

- **FR-001**: Each Tier 1 climbing area profile document MUST contain an embedded GeoJSON map showing that area's parking/trailhead location.
- **FR-002**: A regional overview map MUST exist showing all climbing areas (Tier 1 and Tier 2) with visual distinction between tiers.
- **FR-003**: Trail systems from the mountain biking section MUST be represented on at least one map with pins at primary trailhead locations.
- **FR-004**: A town destinations map MUST show all curated restaurants, breweries, and gear shops from the Food & Drink and Gear Shops sections.
- **FR-005**: Each map pin MUST include a popup with at minimum: name and one line of context (e.g., drive time, trail miles, or food specialty).
- **FR-006**: Different destination categories (climbing, biking, food/drink, gear, sights) MUST use visually distinct markers or colors.
- **FR-007**: Sean's personal guide MUST include a consolidated map showing his priority destinations across all categories.
- **FR-008**: All coordinates MUST represent navigable locations (parking lots or trailheads), not abstract area centroids.
- **FR-009**: Maps MUST render correctly as interactive GeoJSON on GitHub web. GitHub mobile app rendering SHOULD be verified but is not a blocking requirement.
- **FR-010**: Each map MUST contain fewer than 30 pins to maintain readability and rendering performance.

### Key Entities

- **Map Point**: A geographic location with coordinates (longitude, latitude), name, category (climbing/biking/food/gear/sights), tier (for climbing areas), and a context note for the popup label.
- **Map**: A GeoJSON FeatureCollection embedded in a markdown document. Contains multiple Map Points. Scoped to a specific purpose (area overview, town destinations, personal consolidated, or single-area detail).

## Success Criteria

### Measurable Outcomes

- **SC-001**: A user viewing the repo on GitHub can visually locate any Tier 1 climbing area on a map within 10 seconds of opening the relevant document.
- **SC-002**: All Tier 1 climbing areas (Stone Fort, Rocktown, HP40, Walden's Ridge) and Tier 2 areas (Hospital Boulders, Dayton Pocket, Cumberland/Pep Boys, Zahnd Tract) appear on the regional overview map with correct pin placement (within 0.5 miles of actual parking).
- **SC-003**: All 6 trail systems from Sean's trail wishlist appear on at least one map with trailhead pins.
- **SC-004**: The town destinations map contains all "don't miss" food, brewery, and gear shop locations from the personal guide.
- **SC-005**: Sean's personal guide contains a consolidated map covering his priority destinations across all categories.
- **SC-006**: Every map pin displays a name and context note when clicked/tapped on GitHub web.
- **SC-007**: No single map contains more than 30 pins.

## Assumptions

- GitHub's GeoJSON rendering in fenced code blocks (```geojson) remains stable and available. This is a documented GitHub feature.
- The GitHub mobile app supports GeoJSON rendering at a basic level (pins visible, popups functional). If mobile rendering is degraded, maps still provide value on web.
- Coordinates for major climbing areas (Stone Fort, Rocktown, HP40) are readily available from Mountain Project. Coordinates for smaller areas (Walden's Ridge, Cumberland/Pep Boys) and town destinations can be sourced from Google Maps.
- GeoJSON `properties` fields like `marker-color` are supported by GitHub's renderer for visual differentiation. If not fully supported, category distinction will rely on name prefixes in popup labels.
- The repo is primarily viewed on GitHub (web or app), not in local markdown editors. Maps are a GitHub-specific enhancement; the underlying text content remains fully functional without map rendering.

## Scope Boundaries

### In Scope

- GeoJSON maps embedded in existing markdown documents (area profiles, personal guide)
- A standalone regional overview map (new document or section)
- A town destinations map
- Parking/trailhead coordinate research for all mapped locations
- Pin popups with name and brief context

### Out of Scope

- Turn-by-turn directions or routing between locations
- Trail route traces (line geometries showing actual trail paths)
- Individual boulder-level mapping (pins for specific problems)
- Offline map generation or export to Gaia/Mountain Project
- Custom map styling beyond GitHub's built-in GeoJSON renderer
- Elevation profiles or topographic overlays
