# Tasks: Area-Scoped Problem Clusters (V0–V3 / V4–V6 / V7–V10)

**Input**: Design documents from `/specs/002-problem-clusters/`
**Prerequisites**: plan.md (required), spec.md (required), research.md, data-model.md, quickstart.md

**Tests**: No tests requested. This is a knowledge base feature — validation is manual review against the spec quality checklist.

**Organization**: Tasks are grouped by user story to enable independent implementation and review of each story.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- All problem cluster files live in `areas/` at repository root
- File names use kebab-case: `{area-name}-problems.md`
- Area profiles (Feature 001) are in `areas/{area-name}.md`
- Research data is in `specs/002-problem-clusters/research.md`

---

## Phase 1: Setup

**Purpose**: Create the problem cluster template that all cluster documents will follow

- [ ] T001 Create problem cluster template based on data-model.md document structure. Save as `specs/002-problem-clusters/problem-cluster-template.md` with sections: header with area profile link, V7–V10 (Hard) with band summary and proximity groups, V4–V6 (Moderate) with band summary and proximity groups, V0–V3 (Easy) with band summary and proximity groups, Sources. Each problem entry format: `**Name** (VX) — Style notes. Body-type note. _Conditions flag._ [Source]`. Include proximity group headers with walk-from-parking times.

**Checkpoint**: Template ready. Cluster authoring can begin.

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: No blocking prerequisites — all problem clusters are independent files that reference existing area profiles. Proceed directly to user story phases.

---

## Phase 3: User Story 1 — Find What to Climb at Today's Area (Priority: P1) MVP

**Goal**: Create problem cluster documents for all 7 viable areas with curated V7–V10 problem lists as the primary content. V4–V6 and V0–V3 sections are included for completeness but the hard-climbing cluster is the MVP value.

**Independent Test**: Open any area's problem cluster and answer "What are the 5–15 best hard problems here?" with names, grades, proximity groupings, and enough context to walk to them.

### Tier 1 Clusters (Mandatory — Deepest Data)

- [ ] T002 [P] [US1] Write problem cluster for Stone Fort in `areas/stone-fort-problems.md` using the template. Research data source: research.md Stone Fort section. Must include: header with link to `stone-fort.md`, V7–V10 section (~12 problems: Tennessee Thong V7, Spyro Gyro V7, Poison Ivy V7, Celestial Mechanics V7, A Face in the Crowd V7, Sherman Photo Roof V7, Now and Zen V7, Red House Extension V7–V8, Jerry's Kids V7, Grimace V8, The Orb V8, Cleopatra V8, Ace of Spades V9, Bedwetters V9, Instinct V9/V10, White Face V10), V4–V6 section (~12 problems including The Wave V6, Crack of Doom V5, Super Mario V4, Sternum V5, Tristar V4), V0–V3 section (~9 problems including Spare V0, Ribcage V3, Storming the Castle V1). Group by proximity: Front Area, Main Area/Sternum, Super Mario/Jungle Gym, Deep Areas. Include style notes, body-type notes, and conditions flags from research. Add conditions quick reference table. Sources: Stone Fort Bouldering 3rd Ed., KAYA, Mountain Project.
- [ ] T003 [P] [US1] Write problem cluster for Rocktown in `areas/rocktown-problems.md` using the template. Research data source: research.md Rocktown section. Must include: header with link to `rocktown.md`, V7–V10 section (~13 problems: Sherman Photo Roof V7, The Comet V7, Iron Claw V7, The Orb V8, The Vagina V8, Brown Hole V8, Tractor Traylor V8, Burst of Joy V9, B-Cubed V9, Blackout V9, Sherman Roof Traverse V9, Iron Claw Sit V9, Golden Harvest V10), V4–V6 section (~10 problems including Standard Deviation V6, Golden Shower V5, Soap on a Rope V4), V0–V3 section (~10 problems including Goforia V0, The Standard V3). Group by proximity: Orb Area/Front, Sherman Roof, Hueco Simulator, The Maze, Comet Area, The Valley. Note Golden Harvest/Golden Shower mixed-ability boulder. Note Comet Boulder as always-shaded fallback. Sources: Rocktown guidebook, KAYA, Mountain Project.
- [ ] T004 [P] [US1] Write problem cluster for HP40 in `areas/hp40-problems.md` using the template. Research data source: research.md HP40 section. Must include: header with link to `hp40.md`, V7–V10 section (~12 problems: The Thief V7, Don't Rock My Boat V7, Great White V7, The Flow V7, Litz Pocket Problem V7, Skywalker V8, Ghetto Superstar V8, Lawdog V8, Slider V9, Cadillac Thrills V9, No Tranquility V9, Hot 'N Tot V10, God Module V11 as area classic), V4–V6 section (~12 problems including Hammerhead V5, Popeye V5, Millipede V5, Redneck V6), V0–V3 section (~10 problems including Silky V0, Merlin V1, Bumboy V3 with stiff-grade warning, Genesis V3). Group by proximity: Upper Boulders, Lower Boulders. Note stiff grading culture. Include proximity circuits for mixed-ability groups (Skywalker Area, Cadillac Thrills Boulder, Millipede/Great White cluster). Note Bumboy as friction canary. Sources: HP40 guidebook, KAYA, Mountain Project.

### Tier 2 Clusters (Conditional — Where Data Supports)

- [ ] T005 [P] [US1] Write problem cluster for Dayton Pocket in `areas/dayton-pocket-problems.md` using the template. Research data source: research.md Dayton Pocket section. Must include: header with link to `dayton-pocket.md`, V7–V10 section (~10 problems concentrated on Vapor Lock Cave: Torpedo V7, White Noise V7, Tavalin Shaft V7, 300 V9, Dune Blasting V9, Riverdance V9, Peace Love and Smile V9, Creation of Adam V9, Honeycomb V10, Wild Wild West V10), V4–V6 section (~3 problems: Bedrocker V4, Seduction V4, Reconciliation V5 — note thin data honestly), V0–V3 section (~2 problems: Head Smacking Sound V0, Tollbooth ~V3 — note critically thin data, suggest consulting ChattBloc 2nd Ed.). Note Vapor Roof is overhung/sheltered. Sources: Mountain Project, 27crags, KAYA, ChattBloc 2nd Ed.
- [ ] T006 [P] [US1] Write problem cluster for Zahnd Tract in `areas/zahnd-tract-problems.md` using the template. Research data source: research.md Zahnd Tract section. Must include: header with link to `zahnd-tract.md`, V7–V10 section (~8 problems: Rhino V7, Castle in the Sky V7, Harvest Moon V8, Pray Like a Mantis V9, Harvest Moon Sit V9/V10, Rhino Low V10, Storm Crow V10, Ode to Austria V10), V4–V6 section (~2 problems: Razors Edge V6, Razorback V6 — note thin web data, recommend Caffeine and Climbing guide), V0–V3 section (note no named problems from web sources — honestly state data gap, recommend guidebook). Sources: Mountain Project, KAYA, 8a.nu, Caffeine and Climbing guide (referenced).
- [ ] T007 [P] [US1] Write problem cluster for Hospital Boulders in `areas/hospital-boulders-problems.md` using the template. Research data source: research.md Hospital Boulders section. Must include: header with link to `hospital-boulders.md`, V7–V10 section (3 problems: Eddie V7, Smash Alley V8, Hustle and Flow V10 — note thin hard data [UNVERIFIED above V7]), V4–V6 section (~8 problems: Get Low V4, Low & Slow V4, Madness V5, Savage Problem V5, Angina V5, Mystified V5, Aggravated Assault I ~V5, Deadhead V6), V0–V3 section (~8 problems: Nosey V1, Slippery When Wet V2, Saddle V2, Ballast V3, Scales V3, Gadfly V3, Hero V3). Group by sub-areas: Barn Area, Eddie Area, Lower Area, Middle Area, Water Tower Area. Sources: KAYA, Mountain Project, SCC, RV Project.
- [ ] T008 [P] [US1] Write problem cluster for Walden's Ridge in `areas/waldens-ridge-problems.md` using the template. Research data source: research.md Walden's Ridge section. Must include: header with link to `waldens-ridge.md`, V7–V10 section (1 problem: God's Gas V7 — honestly note minimal hard climbing), V4–V6 section (~10 problems: Meathook V4, Handicap Parking V4, Epitaph V4, Isosceles V4, Circumference V4, Compact Car V5, Jet-Puffed V5, Eulogy V5, Stranger Danger V5, The Last Spot V5, The Upside-Down V6, Double Parked Dually V6), V0–V3 section (1 problem: Ok Joe V0 — note thin data, unnamed moderate slab at parking). Note this is primarily a moderate-climbing destination. Group by: Upper Parking Area, Falls Connector, Boy Scout Trail. Sources: KAYA, Mountain Project.

### Integration

- [ ] T009 [US1] Add problem cluster links to each area profile in `areas/*.md`. For each of the 7 areas with clusters, add a link from the area profile to its companion problem cluster document (e.g., "See [Problem Clusters](stone-fort-problems.md) for curated problem lists by grade band"). Place the link in the Overview section or as a new "Problem Clusters" line in the header metadata. Do NOT modify Dogwood, Sunset Rock, or Hell's Kitchen profiles (no clusters for those areas).
- [ ] T010 [US1] Update `areas/README.md` comparison table to note which areas have problem cluster documents. Add a "Problems" column or a note below the table indicating which areas have companion cluster files with links.

**Checkpoint**: All 7 problem clusters written with curated lists across all three grade bands. A climber can now answer "What should I climb here?" at any area. US1 acceptance scenarios should be testable.

---

## Phase 4: User Story 2 — Find Moderate and Easy Climbing Nearby (Priority: P2)

**Goal**: Ensure every problem cluster honestly communicates moderate and easy options with proximity context, so lower-grade climbers can find things to do near where the group is climbing.

**Independent Test**: Open any area's problem cluster and answer "What can a V5 climber do within a short walk of where the V10 climber is working?" with at least 3 specific suggestions.

- [ ] T011 [US2] Review and enhance V4–V6 and V0–V3 sections across all 7 problem clusters in `areas/*-problems.md`. For each cluster: verify proximity notes relate moderate/easy problems to the hard-climbing zones (e.g., "near Sternum V5 and White Face V10, so all ability levels can share the same area"). Where an area has limited or nearly nonexistent easy climbing (Zahnd, Walden's Ridge V0–V3), add a brief note suggesting alternatives (spot, hike, explore). Ensure no cluster enforces artificial parity — reflect actual data honestly.
- [ ] T012 [US2] Review and enhance body-type notes across all 7 problem clusters in `areas/*-problems.md` where data exists. Flag reachy problems (Celestial Mechanics V7, Genesis V3, Redneck V6, Hot 'N Tot V10), compression-heavy areas (HP40 generally, Millipede V5), and short-friendly options where known. Omit body-type notes where no data exists rather than guessing.

**Checkpoint**: All clusters now honestly communicate group tradeoffs with proximity context. US2 acceptance scenarios should be testable.

---

## Phase 5: User Story 3 — Adapt the Session to Current Conditions (Priority: P3)

**Goal**: Add conditions flags and quick-reference information to problem clusters so climbers can adapt mid-session when conditions change.

**Independent Test**: At any Tier 1 area, identify at least 3 problems that remain viable when conditions deteriorate using only the problem cluster.

- [ ] T013 [US3] Review and enhance conditions flags across all Tier 1 problem clusters in `areas/stone-fort-problems.md`, `areas/rocktown-problems.md`, `areas/hp40-problems.md`. For each cluster: tag problems with conditions flags where known from research (shaded, sheltered/overhung, seepage-prone, friction-dependent, sun-exposed, afternoon sun). Add a "Conditions Quick Reference" section at the end of each Tier 1 cluster summarizing: best zones after rain, best zones when humid/warm, sheltered problems for marginal conditions. Use data from research.md conditions tables. Only tag when sourced — omit rather than guess per FR-008 and spec edge cases.
- [ ] T014 [US3] Review conditions flags for Tier 2 clusters in `areas/dayton-pocket-problems.md`, `areas/zahnd-tract-problems.md`, `areas/hospital-boulders-problems.md`, `areas/waldens-ridge-problems.md`. Add conditions notes where known from research (e.g., Vapor Roof at Dayton Pocket is overhung/sheltered, Walden's Ridge is forested). Tier 2 clusters do not need full conditions quick reference tables — simple inline flags are sufficient.

**Checkpoint**: Conditions flags added where data supports. US3 acceptance scenarios should be testable. All three user stories are now independently functional.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Validation and consistency across all problem clusters

- [ ] T015 Validate all problem clusters against FR-001 through FR-014 in `areas/*-problems.md`. Verify every mandatory field is present (name, V-grade, location, source per FR-005/FR-013). Check that no cluster exceeds 40 problems total (SC-006). Verify all clusters link back to parent area profiles (FR-011). Confirm proximity grouping is used, not alphabetical ordering (FR-012). Document any gaps found and fix them.
- [ ] T016 Validate problem cluster consistency with area profiles. Cross-check grade density descriptors in cluster band headers against area profile density sections (e.g., if area profile says "V7–V10: Limited" for Walden's Ridge, the cluster header must reflect this). Fix any contradictions per SC-003 and SC-005 from Feature 001.
- [ ] T017 Run quickstart.md scenarios against the completed `areas/` directory. Walk through each "During the Trip" scenario in `specs/002-problem-clusters/quickstart.md` and verify the file layout, section order, and navigation paths work as described. Note any quickstart instructions that need updating.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — start immediately
- **User Story 1 (Phase 3)**: Depends on Phase 1 (template)
- **User Story 2 (Phase 4)**: Depends on Phase 3 (clusters must exist to review)
- **User Story 3 (Phase 5)**: Depends on Phase 3 (clusters must exist to add conditions flags)
- **Polish (Phase 6)**: Depends on Phases 3, 4, and 5

### User Story Dependencies

- **US1 (P1)**: Can start after Setup. No dependencies on other stories.
- **US2 (P2)**: Depends on US1 (clusters must exist before proximity/body-type review).
- **US3 (P3)**: Depends on US1 (clusters must exist before conditions enhancement). Can run in parallel with US2.

### Parallel Opportunities

- All Tier 1 clusters (T002, T003, T004) can run in parallel
- All Tier 2 clusters (T005, T006, T007, T008) can run in parallel
- All 7 clusters (T002–T008) can run in parallel with each other
- US2 (T011–T012) and US3 (T013–T014) can run in parallel after US1 completes
- Polish tasks T015 and T016 can run in parallel

---

## Parallel Example: User Story 1

```text
# Launch all Tier 1 clusters together:
Task: "Write Stone Fort problem cluster in areas/stone-fort-problems.md"
Task: "Write Rocktown problem cluster in areas/rocktown-problems.md"
Task: "Write HP40 problem cluster in areas/hp40-problems.md"

# Launch all Tier 2 clusters together:
Task: "Write Dayton Pocket problem cluster in areas/dayton-pocket-problems.md"
Task: "Write Zahnd Tract problem cluster in areas/zahnd-tract-problems.md"
Task: "Write Hospital Boulders problem cluster in areas/hospital-boulders-problems.md"
Task: "Write Walden's Ridge problem cluster in areas/waldens-ridge-problems.md"
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (template)
2. Complete Phase 3: Write all 7 problem clusters
3. **STOP and VALIDATE**: Can you answer "What should I climb here?" at any area within 60 seconds?
4. This alone delivers massive trip value

### Incremental Delivery

1. Setup → Cluster template ready
2. US1 → All 7 clusters written → Validate independently (MVP!)
3. US2 → Proximity context and body-type review → Validate independently
4. US3 → Conditions flags and quick reference → Validate independently
5. Polish → Cross-cutting validation pass

---

## Notes

- [P] tasks = different files, no dependencies
- [Story] label maps task to specific user story for traceability
- Each user story is independently completable and testable
- Commit after each phase or logical group of clusters
- All problem data comes from `specs/002-problem-clusters/research.md`
- Cluster format must follow `specs/002-problem-clusters/problem-cluster-template.md`
- [UNVERIFIED] flags must be preserved from research.md — do not remove them
- Areas without clusters: Dogwood (insufficient data), Sunset Rock (Tier 3), Hell's Kitchen (Tier 3)
