# Tasks: Primary Bouldering Areas (Hard-First, Group-Aware)

**Input**: Design documents from `/specs/001-primary-bouldering-areas/`
**Prerequisites**: plan.md (required), spec.md (required), research.md, data-model.md, quickstart.md

**Tests**: No tests requested. This is a knowledge base feature — validation is manual review against the spec quality checklist.

**Organization**: Tasks are grouped by user story to enable independent implementation and review of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- All area profiles live in `areas/` at repository root
- File names use kebab-case: `{area-name}.md`
- Comparison reference is `areas/README.md`

---

## Phase 1: Setup

**Purpose**: Create directory structure and profile template

- [x] T001 Create `areas/` directory at repository root
- [x] T002 Create area profile template based on FR-011 and data-model.md, to be used as the structural reference for all profiles. Save as `specs/001-primary-bouldering-areas/area-profile-template.md` with sections: Overview, Hard Appeal (V7–V10), Grade Density (V0–V3 / V4–V6), Conditions, Logistics, Access, Style & Body-Type Notes, Sources. Use density descriptors from data-model.md. Include February conditions framing per research decision 4.

**Checkpoint**: Directory and template ready. Profile authoring can begin.

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: No blocking prerequisites for this feature — all profiles are independent files. Proceed directly to user story phases.

---

## Phase 3: User Story 1 — Pick Today's Area in Under 2 Minutes (Priority: P1) MVP

**Goal**: Create structured profiles for all 10 areas so a trip participant can scan them and choose a destination within 2 minutes.

**Independent Test**: Read the profiles and answer "Where should we go today?" for three scenarios (cool/dry morning, warm/humid afternoon, short session) without consulting external sources.

### Tier 1 Profiles (Primary Destinations)

- [x] T003 [P] [US1] Write area profile for Stone Fort (LRC) in `areas/stone-fort.md` using the profile template. Research data source: research.md Stone Fort section. Must include: overview, V7–V10 hard appeal (strong — Now and Zen V7, Grimace V8, Bedwetters V9), grade density (V0–V3 abundant, V4–V6 abundant), conditions (forested shade, peak Feb friction, bullet-hard sandstone), logistics (~35–45 min from ESNP, $10–12 day fee, park at clubhouse), access (private — Montlake Golf Course, waiver required, closes at dark), style (diverse — slopers, compression, mantles, iron rail features), sources (Stone Fort Bouldering 3rd Ed., Mountain Project, SCC).
- [x] T004 [P] [US1] Write area profile for Rocktown in `areas/rocktown.md` using the profile template. Research data source: research.md Rocktown section. Must include: overview, V7–V10 hard appeal (excellent — The Orb V8, Golden Harvest V10, Burst of Joy V9), grade density (V0–V3 abundant, V4–V6 abundant), conditions (~2,200 ft elevation, coarse sandstone, good shade, peak Feb), logistics (~50–70 min from ESNP, 5–20 min approach), access (GA WMA — license required ~$5–10, verify Feb 2026 hunting dates, no camping), style (extremely diverse — slopers, huecos, compression, committing topouts), sources (Rocktown guidebook, KAYA, Mountain Project, SCC).
- [x] T005 [P] [US1] Write area profile for Horse Pens 40 (HP40) in `areas/hp40.md` using the profile template. Research data source: research.md HP40 section. Must include: overview, V7–V10 hard appeal (outstanding — 60+ at V8+, Slider V9, Ghetto Superstar V8, stiff grades), grade density (V0–V3 moderate, V4–V6 strong), conditions (~1,500 ft, peak Feb, smooth grippy sandstone in cold), logistics (~2 hrs from ESNP, $15 day/$25 camping), access (private park, reservations for camping, open year-round), style (compression, slopers, water grooves, body tension — NOT a crimp area), sources (HP40 guidebook, KAYA, Mountain Project, SCC).

### Tier 2 Profiles (Supplementary Areas)

- [x] T006 [P] [US1] Write area profile for Dayton Pocket in `areas/dayton-pocket.md` using the profile template. Research data source: research.md Dayton Pocket section. Must include: overview (Vapor Roof is signature feature), V7–V10 hard appeal (moderate — concentrated on Vapor Roof, White Noise V7, Riverdance V9), grade density (V0–V3 moderate, V4–V6 moderate), conditions (river gorge, shade in morning, humidity/seepage risk, Feb should offset [UNVERIFIED]), logistics (~50–65 min from ESNP, Laurel Snow State Natural Area parking), access (TN State Park — free with daily online registration, gate closes 30 min after sunset), style (horizontal roof on pockets/pinches/flakes, extremely overhung), sources (Mountain Project, theCrag, 27crags, ChattBloc).
- [x] T007 [P] [US1] Write area profile for Zahnd Tract in `areas/zahnd-tract.md` using the profile template. Research data source: research.md Zahnd section. Must include: overview (uncrowded moderate area near Rocktown), V7–V10 hard appeal (limited — Harvest Moon V8, The Wave V11/12, few hard gems), grade density (V0–V3 moderate, V4–V6 strong), conditions (Lookout Mtn ~1,800–2,100 ft, fine-grained sandstone, good shade), logistics (~50–60 min from ESNP, 15 min from Rocktown), access (GA WMA — license required, Feb fully open, April–May morning closure), style (vertical slabs, textured slopers, cavernous overhangs, pebbly rock), sources (ChattBloc, SCC, Mountain Project, Every Last Rock).
- [x] T008 [P] [US1] Write area profile for Dogwood in `areas/dogwood.md` using the profile template. Research data source: research.md Dogwood section. Must include: overview (developing area, V3–V7 sweet spot), V7–V10 hard appeal (limited — problems to V9 exist, FA potential), grade density (V0–V3 moderate, V4–V6 strong), conditions (Cumberland Plateau, bullet sandstone, forested), logistics (~45–55 min from ESNP [UNVERIFIED]), access (TN State Park — registration at dogwoodclimbing.com, no bolting, no camping), style (patina incuts, technical slab, bulbous slopers), sources (SCC, ChattBloc, Dogwood guidebook on Rakkup).
- [x] T009 [P] [US1] Write area profile for Hospital Boulders in `areas/hospital-boulders.md` using the profile template. Research data source: research.md Hospital Boulders section. Must include: overview (easy-access moderate bouldering near HP40 corridor), V7–V10 hard appeal (limited [UNVERIFIED] — V7, V9, V11 confirmed but count unknown), grade density (V0–V3 abundant, V4–V6 strong), conditions (west brow Lookout Mtn, sandstone), logistics (~1.5–2 hrs from ESNP [UNVERIFIED], few hundred feet from parking), access (SCC-owned — gate code required via SCC website, dawn to dusk, do not pass "End SCC Property" signs), style ([UNVERIFIED]), sources (SCC, Mountain Project).
- [x] T010 [P] [US1] Write area profile for Walden's Ridge Park in `areas/waldens-ridge.md` using the profile template. Research data source: research.md Walden's Ridge section. Must include: overview (convenient close-to-town option, opened 2023), V7–V10 hard appeal (minimal [UNVERIFIED] — V8 Juice boulder suggests V8 exists), grade density (V0–V3 present, V4–V6 present), conditions (Signal Mountain eastern slope, 200 acres forested, easy approaches), logistics (~25–35 min from ESNP, multiple areas within 1 mile of parking), access (free public park — Hamilton County, no fees/permits, no camping), style (varied Pennsylvanian sandstone), sources (SCC, Mountain Project, waldensridgepark.com).

### Tier 3 Profiles (Brief — Not Primary Bouldering Destinations)

- [x] T011 [P] [US1] Write brief area profile for Sunset Rock in `areas/sunset-rock.md` using the profile template. Research data source: research.md Sunset section. This is a brief profile — note prominently that this is primarily a trad climbing area with minimal documented bouldering. V7–V10: negligible for bouldering. Include what is known about base-of-cliff bouldering, Constellation Chaos V8 on Lookout Mountain. Access: free, Chickamauga National Military Park, Cravens House parking. Flag as NOT a meaningful bouldering destination for this trip.
- [x] T012 [P] [US1] Write brief area profile for Hell's Kitchen in `areas/hells-kitchen.md` using the profile template. Research data source: research.md Hell's Kitchen section. This is a brief profile — note that information is thin and the area is developing. V7–V10: [UNVERIFIED]. Include 2-mile approach note, Cumberland Trail State Park, no bolting allowed, Access Fund/SCC purchase history. Flag as promising but not confirmed for this trip's scope.

**Checkpoint**: All 10 area profiles written. A trip participant can now scan individual profiles to choose a destination. US1 acceptance scenarios should be testable.

---

## Phase 4: User Story 2 — Understand Group Tradeoffs Per Area (Priority: P2)

**Goal**: Ensure every profile honestly communicates what each ability band can expect, so lower-grade climbers can set expectations before arriving.

**Independent Test**: Read any single area profile and answer "Will I have things to climb at V0–V3?" and "Will I have things to climb at V4–V6?" with a yes/no/limited answer and supporting context.

- [x] T013 [US2] Review and enhance Grade Density sections across all 10 profiles in `areas/*.md`. For each profile: verify V0–V3 and V4–V6 sections use canonical density descriptors (abundant/strong/moderate/limited/nearly nonexistent). Where an area has limited or nearly nonexistent easy climbing, add a brief note suggesting what else a V0 climber could do (spot, hike nearby, explore). Ensure no profile enforces artificial parity — reflect each area's actual strengths honestly. Cross-reference research.md for accuracy.
- [x] T014 [US2] Review and enhance Style & Body-Type Notes across all profiles in `areas/*.md` where data exists. Flag reachy problems, compression-heavy areas, and technical vs power styles. These notes are informational per FR-007 — omit the section entirely if no data is available rather than guessing.

**Checkpoint**: All profiles now honestly communicate group tradeoffs. US2 acceptance scenarios should be testable.

---

## Phase 5: User Story 3 — Compare Areas Side-by-Side (Priority: P3)

**Goal**: Create a comparison reference table so the group can quickly compare areas across key dimensions without reading individual profiles.

**Independent Test**: Select any two areas and answer "Which is better for X?" across at least three dimensions using only the comparison reference.

- [x] T015 [US3] Create comparison reference table in `areas/README.md`. Include: heading with feature context, Markdown table with columns per data-model.md (Area with link to profile, Drive time from ESNP, V7–V10 density, V4–V6 density, V0–V3 density, Feb Conditions summary, Access/Fees summary, Style summary). One row per area, ordered by V7–V10 density (strongest first). All data must be consistent with individual profiles — cross-reference each profile during creation.
- [x] T016 [US3] Add tier grouping and index to `areas/README.md` above the comparison table. Group areas into Tier 1 (Primary Destinations), Tier 2 (Supplementary Areas), Tier 3 (Brief Profiles) with linked file names. Include a 1-sentence description of what each tier means.

**Checkpoint**: Comparison reference complete. US3 acceptance scenarios should be testable. All three user stories are now independently functional.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Validation and consistency across all profiles

- [x] T017 Validate all profiles against FR-001 through FR-008 and FR-011 in `areas/*.md`. Verify every mandatory section is present and non-empty for all 10 profiles. Check that every conditions/access claim is either sourced or flagged [UNVERIFIED] per FR-008 and SC-004. Document any gaps found and fix them.
- [x] T018 Validate comparison reference consistency in `areas/README.md`. Cross-check every cell in the comparison table against the corresponding profile. Fix any contradictions in grade density, conditions, or logistics data per SC-005.
- [x] T019 Run quickstart.md scenarios against the completed `areas/` directory. Walk through each "During the Trip" scenario in `specs/001-primary-bouldering-areas/quickstart.md` and verify the file layout, section order, and navigation paths work as described. Note any quickstart instructions that need updating.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — start immediately
- **User Story 1 (Phase 3)**: Depends on Phase 1 (template + directory)
- **User Story 2 (Phase 4)**: Depends on Phase 3 (profiles must exist to review)
- **User Story 3 (Phase 5)**: Depends on Phase 3 (profiles must exist to summarize)
- **Polish (Phase 6)**: Depends on Phases 3, 4, and 5

### User Story Dependencies

- **US1 (P1)**: Can start after Setup. No dependencies on other stories.
- **US2 (P2)**: Depends on US1 (profiles must exist before grade density review).
- **US3 (P3)**: Depends on US1 (profiles must exist before comparison table). Can run in parallel with US2.

### Parallel Opportunities

- All Tier 1 profiles (T003, T004, T005) can run in parallel
- All Tier 2 profiles (T006–T010) can run in parallel
- All Tier 3 profiles (T011, T012) can run in parallel
- All 10 profiles (T003–T012) can run in parallel with each other
- US2 (T013–T014) and US3 (T015–T016) can run in parallel after US1 completes
- Polish tasks T017 and T018 can run in parallel

---

## Parallel Example: User Story 1

```text
# Launch all Tier 1 profiles together:
Task: "Write Stone Fort profile in areas/stone-fort.md"
Task: "Write Rocktown profile in areas/rocktown.md"
Task: "Write HP40 profile in areas/hp40.md"

# Launch all Tier 2 profiles together:
Task: "Write Dayton Pocket profile in areas/dayton-pocket.md"
Task: "Write Zahnd Tract profile in areas/zahnd-tract.md"
Task: "Write Dogwood profile in areas/dogwood.md"
Task: "Write Hospital Boulders profile in areas/hospital-boulders.md"
Task: "Write Walden's Ridge profile in areas/waldens-ridge.md"

# Launch Tier 3 profiles together:
Task: "Write Sunset Rock brief profile in areas/sunset-rock.md"
Task: "Write Hell's Kitchen brief profile in areas/hells-kitchen.md"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (template + directory)
2. Complete Phase 3: Write all 10 area profiles
3. **STOP and VALIDATE**: Can you pick today's area in under 2 minutes?
4. This alone delivers massive trip value

### Incremental Delivery

1. Setup → Profile template ready
2. US1 → All 10 profiles written → Validate independently (MVP!)
3. US2 → Grade density and body-type review → Validate independently
4. US3 → Comparison table → Validate independently
5. Polish → Cross-cutting validation pass

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- Each user story is independently completable and testable
- Commit after each phase or logical group of profiles
- All research data comes from `specs/001-primary-bouldering-areas/research.md`
- Density descriptors must use canonical terms from data-model.md
- [UNVERIFIED] flags must be preserved from research.md — do not remove them
