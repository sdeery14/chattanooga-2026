# Tasks: Interactive Area Maps (GeoJSON)

**Input**: Design documents from `/specs/008-interactive-area-maps/`
**Prerequisites**: plan.md (required), spec.md (required), research.md, data-model.md

**Tests**: Not requested — no test tasks included.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Phase 1: Setup

**Purpose**: Verify GeoJSON rendering works on GitHub before committing to full implementation

- [x] T001 Create a minimal test GeoJSON map with one Chattanooga-area pin in areas/README.md, push to GitHub, and verify it renders as an interactive map with clickable popup. Confirm `marker-color`, `marker-size`, `title`, and `description` properties all work. Remove or replace this test map once verified.

**Checkpoint**: GitHub GeoJSON rendering confirmed working. Color and popup conventions validated.

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: No shared blocking infrastructure needed. This feature is pure content authoring — each user story researches its own coordinates. Phase skipped.

---

## Phase 3: User Story 1 — Find Climbing Areas on the Map (Priority: P1) — MVP

**Goal**: Embed maps showing all climbing area locations — a regional overview in areas/README.md and individual parking/trailhead maps in each Tier 1 area profile.

**Independent Test**: Open areas/README.md on GitHub web and visually identify all Tier 1 and Tier 2 climbing areas on the map with labeled pins and correct colors. Click a pin to see area name, drive time, and context note.

### Coordinate Research

- [x] T002 [P] [US1] Research parking/trailhead coordinates for all 4 Tier 1 climbing areas: Stone Fort, Rocktown, HP40, Walden's Ridge. Source from Mountain Project area pages, verify each coordinate points to the parking lot (not boulderfield centroid) using Google Maps satellite view. Record as `[longitude, latitude]` with 3-4 decimal places. Document results in a comment or working notes for use in T004–T008.
- [x] T003 [P] [US1] Research parking/trailhead coordinates for all 6 Tier 2 climbing areas: Hospital Boulders, Dayton Pocket, Cumberland Boulders / Pep Boys, Zahnd Tract, Foster Falls, Suck Creek. Same sourcing and verification approach as T002. Record as `[longitude, latitude]`.

### Implementation

- [x] T004 [P] [US1] Embed single-area GeoJSON map in areas/stone-fort.md after the Overview section. One pin at parking coordinates with `title`: "Stone Fort Parking", `description`: drive time + problem count context, `marker-color`: `#e74c3c`, `marker-size`: `large`. Follow data-model.md property schema.
- [x] T005 [P] [US1] Embed single-area GeoJSON map in areas/rocktown.md after the Overview section. Same format as T004 with Rocktown parking coordinates.
- [x] T006 [P] [US1] Embed single-area GeoJSON map in areas/hp40.md after the Overview section. Same format as T004 with HP40 parking coordinates.
- [x] T007 [P] [US1] Embed single-area GeoJSON map in areas/waldens-ridge.md after the Overview section. Same format as T004 with Walden's Ridge parking coordinates.
- [x] T008 [US1] Embed regional overview GeoJSON map in areas/README.md after the area comparison table. Include all Tier 1 areas (4 pins, `marker-color`: `#e74c3c`, `marker-size`: `large`) and all Tier 2 areas (6 pins, `marker-color`: `#3498db`, `marker-size`: `medium`). Each pin needs `title` and `description` with area name, tier, and drive time from Chattanooga. Total: 8-10 pins. Must be under 30 pins per FR-010. Depends on T002 + T003 coordinates.

**Checkpoint**: All climbing areas are visually locatable on maps. Regional overview shows spatial relationships between all areas. Individual Tier 1 profiles show parking locations. User Story 1 is independently testable — push and verify on GitHub web.

---

## Phase 4: User Story 2 — Find Mountain Biking Trails on the Map (Priority: P2)

**Goal**: Embed a trail systems overview map in trails/README.md showing all 6 trail system trailheads from Sean's wishlist.

**Independent Test**: Open trails/README.md on GitHub web and visually identify all 6 trail systems. Confirm Coldwater Mountain appears closest to HP40 (validating the combo-day pairing). Click a pin to see trail name, miles, and character.

### Coordinate Research

- [x] T009 [US2] Research trailhead parking coordinates for all 6 trail systems from Sean's wishlist: White Oak Mountain, Enterprise South, Coldwater Mountain, Raccoon Mountain, Stringer's Ridge, Five Points. Source from Google Maps (search trailhead parking lot name). Record as `[longitude, latitude]`.

### Implementation

- [x] T010 [US2] Embed trail systems overview GeoJSON map in trails/README.md after the trail comparison table. Include all 6 trail systems as pins with `marker-color`: `#2ecc71`, `marker-size`: `medium`. Each pin needs `title` (trail system name) and `description` (total miles + character summary, e.g., "25 mi machine-built flow"). Total: 6 pins. Follow data-model.md property schema.

**Checkpoint**: All 6 trail systems are visually locatable. Spatial relationships to climbing areas are immediately apparent from the map. Push and verify on GitHub web.

---

## Phase 5: User Story 3 — Find Town Destinations on the Map (Priority: P3)

**Goal**: Embed a town destinations map in rest-days/README.md showing all curated restaurants, breweries, gear shops, and sights in the Chattanooga area.

**Independent Test**: Open rest-days/README.md on GitHub web and identify all three IPA crawl breweries clustered on the Southside. Confirm they appear within walking distance. Click a pin to see name and specialty/context.

### Coordinate Research

- [x] T011 [US3] Research coordinates for all town destinations from sean-guide.md Food & Drink and Gear Shops sections. Include: breweries (Hutton & Smith, Five Wits, Chattanooga Brewing Co., OddStory, WanderLinger), restaurants (Sugar's Ribs, Edley's, Tremont Tavern, Champy's, Niedlov's, Mean Mug, Chatt Smoke House, Little Coyote, Urban Stack), gear shops (Suck Creek Cycle, Rock/Creek, The Gear Closet, REI), and key sights (Sunset Rock, Ruby Falls, Rock City, Raccoon Mountain Caverns). Source from Google Maps business addresses. Record as `[longitude, latitude]`.

### Implementation

- [x] T012 [US3] Embed town destinations GeoJSON map in rest-days/README.md after the Quick Decision table. Use category-specific colors: breweries `#f39c12`, restaurants/food `#e67e22`, gear shops `#9b59b6`, sights `#1abc9c`. Each pin needs `title` (business name) and `description` (one-line context: specialty, neighborhood, or key note). Include `category` property for self-documentation. Total: 12-20 pins (verify under 30 per FR-010). Follow data-model.md property schema.

**Checkpoint**: All curated town destinations are visually locatable. Southside brewery cluster is clearly visible. Category colors distinguish breweries from restaurants from gear shops. Push and verify on GitHub web.

---

## Phase 6: User Story 4 — Sean's Personal Priority Map (Priority: P4)

**Goal**: Embed a single consolidated map in sean-guide.md showing Sean's priority destinations across all categories.

**Independent Test**: Open sean-guide.md on GitHub web and see a single map with climbing areas, trail systems, breweries, food spots, and sights — all visually distinguishable by category color.

### Implementation

- [x] T013 [US4] Assemble Sean's consolidated priority map by selecting coordinates from T002, T003, T009, and T011. Include: top climbing areas (Stone Fort, HP40, Rocktown, Walden's Ridge), top trail systems (White Oak, Enterprise South, Coldwater), IPA crawl breweries (Hutton & Smith, Five Wits, Chattanooga Brewing), key food (Sugar's Ribs, Tremont Tavern, Edley's), key sights (Sunset Rock, Ruby Falls, Raccoon Mountain Caverns), and lodging reference pin. Use all category colors per data-model.md convention. Total: 15-25 pins (verify under 30 per FR-010).
- [x] T014 [US4] Embed the consolidated GeoJSON map in sean-guide.md after the Table of Contents section (before Quick Profile). Add a brief intro line explaining the map categories and color legend. Follow data-model.md property schema.

**Checkpoint**: Sean's personal guide has a single visual overview of all his priority destinations. All categories are visually distinguishable. Push and verify on GitHub web.

---

## Phase 7: Polish & Cross-Cutting Concerns

**Purpose**: Documentation, validation, and cleanup across all maps.

- [x] T015 [P] Add a mobile viewing note near the top of areas/README.md and sean-guide.md explaining that GeoJSON maps render on GitHub web but not the GitHub mobile app — users should open in mobile browser (Safari/Chrome) for map views.
- [x] T016 Push all changes to GitHub and visually verify every map renders correctly on GitHub web: areas/README.md, areas/stone-fort.md, areas/rocktown.md, areas/hp40.md, areas/waldens-ridge.md, trails/README.md, rest-days/README.md, sean-guide.md. Confirm pins appear at correct locations, popups display title + description, and category colors are visually distinct.
- [x] T017 Spot-check coordinate accuracy for at least 5 map points by comparing pin positions against Google Maps satellite view. Verify pins land within 0.5 miles of actual parking lots per SC-002. Fix any coordinates that are off.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — start immediately
- **US1 (Phase 3)**: Depends on Setup (T001 confirms GeoJSON works)
- **US2 (Phase 4)**: Can start after Setup. Independent of US1.
- **US3 (Phase 5)**: Can start after Setup. Independent of US1 and US2.
- **US4 (Phase 6)**: Depends on US1 + US2 + US3 (reuses their coordinates)
- **Polish (Phase 7)**: Depends on all user stories being complete

### User Story Dependencies

- **User Story 1 (P1)**: Can start after T001. No dependencies on other stories.
- **User Story 2 (P2)**: Can start after T001. No dependencies on other stories.
- **User Story 3 (P3)**: Can start after T001. No dependencies on other stories.
- **User Story 4 (P4)**: Depends on US1 + US2 + US3 completion (assembles coordinates from all three).

### Within User Story 1

- T002 and T003 are parallel (researching different area tiers)
- T004, T005, T006, T007 are parallel (different files) — depend on T002
- T008 depends on both T002 and T003

### Parallel Opportunities

- T002 + T003 can run in parallel (different coordinate sets)
- T004 + T005 + T006 + T007 can run in parallel (different area profile files)
- US1, US2, and US3 can run in parallel after Setup (independent coordinate research and different target files)
- T015 tasks can run in parallel (different files)

---

## Parallel Example: User Story 1

```text
# Research phase (parallel):
Task T002: "Research Tier 1 coordinates (Stone Fort, Rocktown, HP40, Walden's Ridge)"
Task T003: "Research Tier 2 coordinates (Hospital Boulders, Dayton Pocket, Cumberland, Zahnd, Foster Falls, Suck Creek)"

# After T002 completes — individual maps (parallel):
Task T004: "Embed map in areas/stone-fort.md"
Task T005: "Embed map in areas/rocktown.md"
Task T006: "Embed map in areas/hp40.md"
Task T007: "Embed map in areas/waldens-ridge.md"

# After T002 + T003 complete:
Task T008: "Embed regional overview in areas/README.md"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (verify GeoJSON rendering)
2. Complete Phase 3: User Story 1 (climbing area maps)
3. **STOP and VALIDATE**: Push to GitHub web. Verify all climbing area maps render correctly.
4. This alone delivers the highest-value maps — all climbing areas visually locatable.

### Incremental Delivery

1. Setup → Verify rendering works
2. Add US1 (climbing maps) → Validate → Push (MVP!)
3. Add US2 (trails map) → Validate → Push
4. Add US3 (town map) → Validate → Push
5. Add US4 (personal consolidated map) → Validate → Push
6. Polish → Final verification → Done

### Sequential Execution (Single Author)

Recommended order for one person working through tasks:

1. T001 (setup spike)
2. T002, T003 (research all climbing coordinates)
3. T004–T008 (build all climbing maps)
4. T009, T010 (trails)
5. T011, T012 (town destinations)
6. T013, T014 (personal map — reuses all previous coordinates)
7. T015–T017 (polish and verify)

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- All coordinates must be `[longitude, latitude]` — the reverse of common `lat, lng` convention
- All marker colors must use hex format (`#RRGGBB`) from data-model.md color convention
- Each map must contain fewer than 30 pins (FR-010)
- Commit after each phase or logical group
- Stop at any checkpoint to validate that story independently on GitHub web
