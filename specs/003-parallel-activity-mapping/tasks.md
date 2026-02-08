# Tasks: Parallel Activity Mapping

**Input**: Design documents from `/specs/003-parallel-activity-mapping/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, quickstart.md

**Tests**: Not requested — no test tasks included.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Trail profiles**: `trails/` at repository root
- **Area profiles**: `areas/` at repository root (existing, modifications only)
- **Research source**: `specs/003-parallel-activity-mapping/research.md`
- **Template**: `specs/003-parallel-activity-mapping/data-model.md` (Trail System Profile Template section)

---

## Phase 1: Setup

**Purpose**: Create directory structure and template foundation

- [ ] T001 Create `trails/` directory at repository root
- [ ] T002 Create `trails/README.md` with header, comparison table skeleton, and pairing matrix skeleton per data-model.md schema

**Checkpoint**: Directory and README shell exist — ready for content

---

## Phase 2: Foundational (Trail Profile Content)

**Purpose**: Write all 12 trail profiles that ALL user stories depend on. Each profile follows the template in data-model.md and uses research.md as the data source. No user story can be validated until profiles exist.

**CRITICAL**: No user story work can begin until this phase is complete.

### Full Profiles (8) — Primary Trail Systems

- [ ] T003 [P] Write full trail profile for Enterprise South Nature Park in `trails/enterprise-south.md` using research.md Trail #1 data and data-model.md template (name, location, drive time, nearby climbing links to `../areas/`, overview, trails & difficulty table, conditions, access & logistics, sources)
- [ ] T004 [P] Write full trail profile for Raccoon Mountain in `trails/raccoon-mountain.md` using research.md Trail #2 data and data-model.md template
- [ ] T005 [P] Write full trail profile for Stringer's Ridge in `trails/stringers-ridge.md` using research.md Trail #3 data and data-model.md template
- [ ] T006 [P] Write full trail profile for Walden's Ridge Park in `trails/waldens-ridge-park.md` using research.md Trail #4 data and data-model.md template
- [ ] T007 [P] Write full trail profile for White Oak Mountain in `trails/white-oak-mountain.md` using research.md Trail #5 data and data-model.md template
- [ ] T008 [P] Write full trail profile for Five Points Recreation Area in `trails/five-points.md` using research.md Trail #6 data and data-model.md template
- [ ] T009 [P] Write full trail profile for Chickamauga Battlefield in `trails/chickamauga-battlefield.md` using research.md Trail #11 data and data-model.md template (note: gravel/road riding, not MTB singletrack — flag clearly)
- [ ] T010 [P] Write full trail profile for Coldwater Mountain in `trails/coldwater-mountain.md` using research.md Trail #16 data and data-model.md template (note: HP40 pairing, include drive time from HP40)

### Brief Profiles (4) — Secondary Trail Systems

- [ ] T011 [P] Write brief trail profile for Booker T. Washington State Park in `trails/booker-t-washington.md` using research.md Trail #7 data (abbreviated: header metadata, 2-3 sentence overview, key logistics, sources — no full trail breakdown table)
- [ ] T012 [P] Write brief trail profile for Lookout Mountain (Moonshine/CCT) in `trails/lookout-mountain.md` using research.md Trail #8 data (abbreviated format)
- [ ] T013 [P] Write brief trail profile for Pigeon Mountain in `trails/pigeon-mountain.md` using research.md Trail #12 data (abbreviated format; flag WMA access restrictions and hunting season closures prominently)
- [ ] T014 [P] Write brief trail profile for Oak Mountain State Park in `trails/oak-mountain.md` using research.md Trail #14 data (abbreviated format; note too far for climbing pairing, standalone only)

**Checkpoint**: All 12 trail profiles exist — ready for README tables and cross-references

---

## Phase 3: User Story 1 — Find Where to Ride Near Today's Climbing Area (Priority: P1)

**Goal**: The biker can open any Tier 1 climbing area's trail pairing information and answer "Where can I ride while they climb here?" with at least 1 specific trail system, its difficulty range, ride length, and drive time — in under 60 seconds.

**Independent Test**: Open trails/README.md, find Stone Fort in the pairing matrix, and locate at least 1 trail system within 30 min with difficulty, distance, and drive time. Repeat for Rocktown and HP40.

### Implementation for User Story 1

- [ ] T015 [US1] Populate the Climbing Area Pairing Matrix in `trails/README.md` per data-model.md schema and research.md pairing matrix: one row per climbing area (Stone Fort, Rocktown, HP40, Dayton Pocket, Zahnd Tract, Hospital Boulders, Walden's Ridge) with linked trail names, drive times from climbing area to trail, and notes. Links point to trail profiles in `trails/` and area profiles in `../areas/`. Honestly state when no nearby trails exist (Dayton Pocket).
- [ ] T016 [P] [US1] Add "Nearby MTB" metadata line to `areas/stone-fort.md` blockquote: `> **Nearby MTB**: [Raccoon Mountain](../trails/raccoon-mountain.md) (~20-30 min), [Stringer's Ridge](../trails/stringers-ridge.md) (~15-20 min)`
- [ ] T017 [P] [US1] Add "Nearby MTB" metadata line to `areas/rocktown.md` blockquote: `> **Nearby MTB**: [Five Points](../trails/five-points.md) (~25-40 min), [Pigeon Mountain](../trails/pigeon-mountain.md) (~10-15 min)`
- [ ] T018 [P] [US1] Add "Nearby MTB" metadata line to `areas/hp40.md` blockquote: `> **Nearby MTB**: [Coldwater Mountain](../trails/coldwater-mountain.md) (~50-55 min from HP40)`
- [ ] T019 [P] [US1] Add "Nearby MTB" metadata line to `areas/dayton-pocket.md` blockquote: `> **Nearby MTB**: None nearby — closest is [ESNP](../trails/enterprise-south.md) (~50-65 min back to lodging)`
- [ ] T020 [P] [US1] Add "Nearby MTB" metadata line to `areas/zahnd-tract.md` blockquote: `> **Nearby MTB**: [Five Points](../trails/five-points.md) (~25-40 min), [Pigeon Mountain](../trails/pigeon-mountain.md) (~10-20 min)`
- [ ] T021 [P] [US1] Add "Nearby MTB" metadata line to `areas/hospital-boulders.md` blockquote: `> **Nearby MTB**: [Coldwater Mountain](../trails/coldwater-mountain.md) (~1 hr)`
- [ ] T022 [P] [US1] Add "Nearby MTB" metadata line to `areas/waldens-ridge.md` blockquote: `> **Nearby MTB**: [Walden's Ridge Park](../trails/waldens-ridge-park.md) (same location!), [Raccoon Mountain](../trails/raccoon-mountain.md) (~15-20 min)`

**Checkpoint**: Pairing matrix complete. Every climbing area links to nearby trails (or honestly says none). Area profiles link back to trail profiles. User Story 1 is independently testable.

---

## Phase 4: User Story 2 — Plan a Dedicated Biking Day (Priority: P2)

**Goal**: The biker can open trails/README.md and answer "What are the best full-day rides near the Airbnb?" with at least 2 options including difficulty, total ride time, and logistics.

**Independent Test**: Open trails/README.md comparison table and identify at least 2 trail systems within 30 min of ESNP with miles, difficulty, and fees visible. Verify ESNP (0 min) and White Oak Mountain (~15-25 min) are prominent.

### Implementation for User Story 2

- [ ] T023 [US2] Populate the Trail Comparison Table in `trails/README.md` per data-model.md schema: all 12 trail systems with columns for Trail System (linked), Drive from Lodging, Miles, Difficulty, Style, Feb Status, Fees, Best Pairing. Sort by drive time from lodging (shortest first). Include a "Rest-Day Rides" callout section below the table highlighting the top 3 options near lodging (ESNP, White Oak Mountain, Raccoon Mountain).

**Checkpoint**: Comparison table complete. Full-day and rest-day riding options are scannable. User Story 2 is independently testable.

---

## Phase 5: User Story 3 — Understand Trail Conditions and Logistics (Priority: P3)

**Goal**: For any documented trail system, the biker can find: parking location, fees, February access status, and conditions notes — all sourced.

**Independent Test**: Open any trail profile and verify presence of: Conditions section (drainage, February notes), Access & Logistics section (parking, fees, February status, hours), and Sources section with at least 1 verifiable link.

### Implementation for User Story 3

- [ ] T024 [US3] Add February Riding Conditions summary section to `trails/README.md` between the header and comparison table: freeze/thaw guidance from research.md, SORBA trail status link, wet-weather fallback list (White Oak Mountain, ESNP, Chickamauga Battlefield), and the "if your tires leave ruts deeper than 1/2 inch, turn around" rule.
- [ ] T025 [US3] Review all 12 trail profiles for conditions completeness: verify every profile has Conditions section with drainage rating and February notes, Access section with parking/fees/February status, and Sources with at least 1 link. Add [UNVERIFIED] flags where data is uncertain (per FR-008). Fix any gaps found.

**Checkpoint**: All conditions and logistics data present and sourced. User Story 3 is independently testable.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Quality validation and final integration

- [ ] T026 Validate all trail profile cross-links: verify every `../areas/` link in trail profiles resolves to an existing file, every `../trails/` link in area profiles resolves to an existing file, and all internal links in `trails/README.md` resolve correctly
- [ ] T027 Validate against spec success criteria SC-001 through SC-006: (1) each Tier 1 area has 1+ trail pairing findable in <60s, (2) 2+ full-day rides from lodging documented, (3) all mandatory fields present in every profile, (4) all 7 areas covered in pairing matrix, (5) profiles pass 5 content quality gates, (6) comparison table answers "where should I ride?" in <60s
- [ ] T028 Run quickstart.md scenarios: walk through all 4 "During the Trip" scenarios in quickstart.md and verify each can be answered using the created documents

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — can start immediately
- **Foundational (Phase 2)**: Depends on Phase 1 (directory exists) — BLOCKS all user stories
- **User Story 1 (Phase 3)**: Depends on Phase 2 (trail profiles exist for linking)
- **User Story 2 (Phase 4)**: Depends on Phase 2 (trail profiles exist for table data)
- **User Story 3 (Phase 5)**: Depends on Phase 2 (trail profiles exist for conditions review)
- **Polish (Phase 6)**: Depends on all user story phases being complete

### User Story Dependencies

- **User Story 1 (P1)**: Can start after Phase 2 — No dependencies on other stories
- **User Story 2 (P2)**: Can start after Phase 2 — No dependencies on other stories (but shares `trails/README.md` with US1, so T023 should not run in parallel with T015)
- **User Story 3 (P3)**: Can start after Phase 2 — No dependencies on other stories

### Within Each Phase

- Phase 2: All 12 trail profiles (T003-T014) can run in **parallel** — each is a separate file
- Phase 3: T015 first (README pairing matrix), then T016-T022 in **parallel** (separate area profile files)
- Phase 4: T023 after T015 (both modify `trails/README.md`)
- Phase 5: T024 after T023 (both modify `trails/README.md`), T025 after Phase 2

### Parallel Opportunities

- **12 trail profiles in parallel** (T003-T014) — each is an independent file
- **7 area profile updates in parallel** (T016-T022) — each is a separate existing file
- **US1 area updates in parallel with US2/US3** after T015 completes

---

## Parallel Example: Phase 2 (Trail Profiles)

```bash
# Launch all 8 full profiles in parallel:
Task: "Write ESNP trail profile in trails/enterprise-south.md"
Task: "Write Raccoon Mountain trail profile in trails/raccoon-mountain.md"
Task: "Write Stringer's Ridge trail profile in trails/stringers-ridge.md"
Task: "Write Walden's Ridge Park trail profile in trails/waldens-ridge-park.md"
Task: "Write White Oak Mountain trail profile in trails/white-oak-mountain.md"
Task: "Write Five Points trail profile in trails/five-points.md"
Task: "Write Chickamauga Battlefield trail profile in trails/chickamauga-battlefield.md"
Task: "Write Coldwater Mountain trail profile in trails/coldwater-mountain.md"

# Then launch 4 brief profiles in parallel:
Task: "Write Booker T Washington brief profile in trails/booker-t-washington.md"
Task: "Write Lookout Mountain brief profile in trails/lookout-mountain.md"
Task: "Write Pigeon Mountain brief profile in trails/pigeon-mountain.md"
Task: "Write Oak Mountain brief profile in trails/oak-mountain.md"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (T001-T002)
2. Complete Phase 2: Trail Profiles (T003-T014) — **12 profiles, all parallel**
3. Complete Phase 3: Climbing Area Pairings (T015-T022) — pairing matrix + area links
4. **STOP and VALIDATE**: Can you answer "Where can I ride near Stone Fort?" from trails/README.md in under 60 seconds?
5. Commit as working MVP

### Incremental Delivery

1. Setup + Trail Profiles → Content foundation ready
2. Add US1 (pairing matrix + area links) → "Where do I ride near X?" works → Commit
3. Add US2 (comparison table + rest-day callout) → "Best rides near lodging?" works → Commit
4. Add US3 (conditions summary + profile review) → "Can I ride today?" works → Commit
5. Polish → All cross-links validated, success criteria verified → Final commit

---

## Notes

- All content is authored Markdown — no code, no build tools, no automated tests
- Source data for every trail profile is in `specs/003-parallel-activity-mapping/research.md`
- Template structure for every trail profile is in `specs/003-parallel-activity-mapping/data-model.md`
- [UNVERIFIED] flags MUST be preserved from research.md — do not remove uncertainty markers
- Climbing area links use relative paths: `../areas/{area}.md` from trail profiles
- Trail profile links use relative paths: `../trails/{trail}.md` from area profiles
- `trails/README.md` links use same-directory paths: `{trail}.md`
