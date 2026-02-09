# Tasks: Personal Trip Goals & Preferences (Sean)

**Input**: Design documents from `/specs/007-personal-trip-goals/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md

**Organization**: Tasks are grouped by user story to enable independent implementation. All tasks write to a single file (`sean-guide.md`) at the repository root, so tasks within each phase run sequentially. Phases are also sequential since later sections may reference earlier ones.

## Format: `[ID] [Story] Description`

- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- All tasks write to `sean-guide.md` at the repository root

---

## Phase 1: Setup (Document Skeleton + Profile)

**Purpose**: Create the output file with full heading structure and Quick Profile section

- [ ] T001 [Setup] Create `sean-guide.md` at repository root with full heading structure from data-model.md: Quick Profile, Priority Stack, Mountain Biking (Trail Wishlist, Climbing-Area Pairings, Wet-Weather Fallbacks), Climbing Projects (Stone Fort, Rocktown, HP40, Tier 2 Quick Notes), Food & Drink (Don't Miss, If Nearby, IPA Crawl Route, Tactical Notes), Sights & Experiences (Quick Hits, Worth the Time, Half-Day Experiences, Gear Shops), Personal Logistics (Bike Transport, Gear Checklist, Knee/Body Notes)
- [ ] T002 [Setup] Write the Quick Profile section with Sean's physical attributes (6'2", 200 lbs, 34), climbing level (V1 outdoor / V4 gym), bike specs (Jamis Faultline A2, 120/130mm FS 29er), strengths summary (reach, power, developing finger strength), constraints summary (tight hips, bilateral ACL history, 200 lb weight on sustained overhangs), and preference summary (IPA, BBQ/burgers/Southern, flow+skill-dev riding). Include links to spec.md for full profile detail.

**Checkpoint**: `sean-guide.md` exists with all headings and a populated Quick Profile. Every section below has a heading placeholder.

---

## Phase 2: User Story 1 — Pick a Mountain Bike Ride (Priority: P1)

**Goal**: Sean can pick a ride matching his energy, skill goal, and group plans within 60 seconds (SC-001)

**Independent Test**: Open the Mountain Biking section and identify top 3 rides with character, skill-dev value, and day-pairing in under 60 seconds

### Implementation for User Story 1

- [ ] T003 [US1] Write the Trail Wishlist ranked table (6 trails) in `sean-guide.md` § Mountain Biking → Trail Wishlist. Each row per data-model.md Trail Target entity: Trail Name, Personal Rank (1–6), Drive from Lodging, Total Miles, Ride Character, Ride Purpose, Bike Suitability, February Drainage, Climbing Pairing, Key Trails for Sean, Skill Dev Note, Link to Trail Profile. Source: research.md § 2 (Top Tier: White Oak #1, Enterprise South #2, Coldwater #3; Second Tier: Raccoon Mountain #4, Stringer's Ridge #5, Five Points #6). Include "Skip for This Trip" list with one-line reasons below the table.
- [ ] T004 [US1] Write the Climbing-Area Pairings subsection in `sean-guide.md` § Mountain Biking → Climbing-Area Pairings. Matrix format: "Group is climbing at [area] → Sean's best ride option, drive time, notes." Source: research.md § 2 pairing matrix. Cover all 6 areas (Stone Fort, Rocktown, HP40, Walden's Ridge, Dayton Pocket, Hospital Boulders).
- [ ] T005 [US1] Write the Wet-Weather Fallbacks subsection in `sean-guide.md` § Mountain Biking → Wet-Weather Fallbacks. Tiered list: "Ride anytime" (White Oak, Coldwater), "Generally reliable" (Enterprise South, Raccoon Mountain), "Check conditions" (Stringer's Ridge, Five Points), "Avoid in wet" (list with reasons). Source: research.md § 2 drainage table. Add cross-reference link to conditions guide (`conditions/README.md`).

**Checkpoint**: Mountain Biking section is complete. Sean can scan the ranked table, check pairings, and assess wet-weather options. All trail profile links resolve. SC-001 testable.

---

## Phase 3: User Story 2 — Find Climbing Problems That Suit Me (Priority: P2)

**Goal**: Sean can identify 3+ suited problems at any Tier 1 area within 30 seconds (SC-002). Every pick has landing-quality + body-constraint flags (SC-005).

**Independent Test**: Open any Tier 1 area subsection and find 3+ problems with why-it-suits-Sean notes and safety flags in under 30 seconds

### Implementation for User Story 2

- [ ] T006 [US2] Write the Stone Fort climbing picks table in `sean-guide.md` § Climbing Projects → Stone Fort. Each row per data-model.md Climbing Pick entity: Problem Name, Grade, Sub-Area, Walk from Parking, Category (send list / stretch goal), Why It Suits Sean, Body/Safety Flags, Landing Quality. Source: research.md § 1 Stone Fort section (9 problems: 6 send list, 2 stretch goals, 1 caution). Include send list / stretch goal / caution groupings. Add links to area profile and problem cluster files.
- [ ] T007 [US2] Write the Rocktown climbing picks table in `sean-guide.md` § Climbing Projects → Rocktown. Same entity format. Source: research.md § 1 Rocktown section (10 problems: 5 send list, 2 stretch goals, 1 caution). Highlight The Scoop (V2) reach advantage. Add links to area profile and problem cluster files.
- [ ] T008 [US2] Write the HP40 climbing picks table in `sean-guide.md` § Climbing Projects → HP40. Same entity format. Source: research.md § 1 HP40 section (11+ problems: 5 send list, 3 stretch goals, 1 moonshot V4, 2 caution). Highlight Genesis (V3) as best reach-advantage problem. Note Red Arrow shares boulder with group V9/V10 objectives. Add links to area profile and problem cluster files.
- [ ] T009 [US2] Write the Tier 2 Quick Notes subsection in `sean-guide.md` § Climbing Projects → Tier 2 Quick Notes. Honest assessment table: Hospital Boulders ("Worth climbing — 7 problems, good rest-day destination"), Dayton Pocket ("Ride or spot — only 2 V0–V3"), Walden's Ridge ("Ride or spot — only 1 V0–V3"), Zahnd Tract ("Ride or spot — 1 borderline V3/V4"). Source: research.md § 1 Tier 2 table. Add a "Tall/Powerful-Friendly Picks" callout box listing Genesis, The Scoop, Mystery Groove, Redneck (moonshot) from research.md § 1 explicitly-friendly table.

**Checkpoint**: Climbing Projects section is complete. All 3 Tier 1 areas have curated pick tables. Every entry has landing quality + body flags (SC-005). Tier 2 areas have honest verdicts. All area profile and problem cluster links resolve (SC-006). SC-002 testable.

---

## Phase 4: User Story 3 — Find a Brewery or Restaurant (Priority: P3)

**Goal**: Sean can name his top 3 "don't miss" spots without opening any other document (SC-003)

**Independent Test**: Open the Food & Drink section and identify top 3 "don't miss" spots with location, vibe, and IPA notes in under 30 seconds

### Implementation for User Story 3

- [ ] T010 [US3] Write the Don't Miss tier in `sean-guide.md` § Food & Drink → Don't Miss. Each entry per data-model.md Food/Drink Target entity: Name, Type, Location, Standout Item, Vibe, Hours, Sean Note, Source. Source: research.md § 3. Include: Hutton & Smith (Igneous IPA), Five Wits (Sunblaze), Chattanooga Brewing Co. (Hill City IPA, Hazy Rider), Sugar's Ribs (half-price ribs Tue-Thu), Tremont Tavern (Best Burger, patty melt), Edley's (ribs, brisket, hot chicken), Champy's (fried chicken), Mean Mug (6am coffee), Niedlov's (sourdough). Organize by sub-type (Breweries, BBQ, Burgers, Southern, Coffee).
- [ ] T011 [US3] Write the If Nearby tier in `sean-guide.md` § Food & Drink → If Nearby. Same entity format. Source: research.md § 3. Include: OddStory, WanderLinger, Chatt Smoke House (CLOSED Sun-Mon), Little Coyote (Michelin Bib Gourmand), Urban Stack, Nic & Norman's (bison burgers), Public House, Velo Coffee, Rembrandt's, Mad Priest.
- [ ] T012 [US3] Write the IPA Crawl Route in `sean-guide.md` § Food & Drink → IPA Crawl Route. Walking route map: Hutton & Smith → Five Wits → Chattanooga Brewing Co. (all Southside, walkable). Note: pair with Chatt Smoke House for BBQ + brewery night (same block as Hutton & Smith). Include approximate walk times between stops.
- [ ] T013 [US3] Write the Tactical Notes in `sean-guide.md` § Food & Drink → Tactical Notes. Bullet list of timing/logistics intelligence from research.md § 3: Sugar's half-price ribs (Tue-Thu 5pm-close), Chatt Smoke House (CLOSED Sun-Mon), Valentine's Day impact (Feb 13-15 busier), late-night options (Urban Stack until 10pm, Whataburger 24hr), Mean Mug 6am opens, Little Coyote walk-in only. Add cross-reference link to rest-day guide (`rest-days/README.md`) for already-documented spots.

**Checkpoint**: Food & Drink section is complete. Don't Miss and If Nearby tiers populated. IPA crawl route mapped. Tactical notes cover timing/closures. SC-003 testable.

---

## Phase 5: User Story 4 — Sights, Experiences & Side-Trips (Priority: P4)

**Goal**: Sean can find 2+ specific experiences with enough detail to act on

**Independent Test**: Open the Sights section and find 2+ experiences with location, time needed, and why

### Implementation for User Story 4

- [ ] T014 [US4] Write the Quick Hits subsection in `sean-guide.md` § Sights & Experiences → Quick Hits. Each entry per data-model.md Sight/Experience entity: Name, Location, Time Needed, Cost, Why, February Note. Include: Sunset Rock (free, sunset ~6pm), Walnut Street Bridge + Coolidge Park, The Passage at Ross's Landing (Cherokee sculpture + Trail of Tears art), Bluff View Sculpture Garden (free, Smithsonian-listed). Source: research.md § 4.
- [ ] T015 [US4] Write the Worth the Time subsection in `sean-guide.md` § Sights & Experiences → Worth the Time. Same entity format. Include: Point Park ($10, Civil War memorial + river view), Bessie Smith Cultural Center (Black History Month programming during trip!), North Shore walking tour (Frazier Ave shops, Clumpie's, Good Dog), Gate 11 Distillery (tour + tasting $18). Source: research.md § 4.
- [ ] T016 [US4] Write the Half-Day Experiences subsection in `sean-guide.md` § Sights & Experiences → Half-Day Experiences. Same entity format. Include: Rock City ($25-35, seven-state view, Valentine's package), Ruby Falls ($30-41, strongest flow + smallest crowds in February, tickets online only), Raccoon Mountain Caverns ($25-55, wild cave expeditions — crawling/scrambling), Southside walkabout (breweries + murals + Choo Choo). Note Incline Railway CLOSED during trip dates. Source: research.md § 4.
- [ ] T017 [US4] Write the Gear Shops subsection in `sean-guide.md` § Sights & Experiences → Gear Shops. Table format: Suck Creek Cycle (MTB shop — local trail intel, closed Sundays), Rock/Creek (climbing gear, local institution since 1987), The Gear Closet (used gear, nonprofit), REI (standard, bike tune-ups). Source: research.md § 4.

**Checkpoint**: Sights & Experiences section is complete. Quick hits, longer experiences, and gear shops all populated with February-specific notes.

---

## Phase 6: User Story 5 — Priority Stack + Personal Logistics (Priority: P5)

**Goal**: Sean can make a "last day" decision in under 15 seconds (SC-004)

**Independent Test**: Open the Priority Stack and identify top 5 cross-category priorities in order in under 15 seconds

### Implementation for User Story 5

- [ ] T018 [US5] Write the Priority Stack in `sean-guide.md` § Priority Stack. 10+ ranked entries per data-model.md Priority Stack Entry entity: Rank, Category (emoji tag), Name, One-Line Context, Status checkbox (☐). Cross all categories: biking, climbing, food, sights. Draw from top picks across all sections. Format as numbered list with checkboxes for trip-time use. Must include at least: White Oak Mountain ride, Enterprise South sessions, Genesis (HP40), Stone Fort day, Hutton & Smith IPA crawl, Sugar's Ribs half-price night, Sunset Rock sunset, and 3+ more from research highlights.
- [ ] T019 [US5] Write the Personal Logistics section in `sean-guide.md` § Personal Logistics. Three subsections: (1) Bike Transport — rack/vehicle notes, pre-trip checklist (tire pressure, brake pads, dropper post, chain lube, thru-axle torque); (2) Gear Checklist — bike gear (helmet, gloves, pedals, shoes, spare tube, pump, multi-tool, chain quick-link) + climbing gear (shoes, chalk, brush, crash pad contribution, tape) + personal (knee braces/sleeves, hip stretching bands, foam roller); (3) Knee/Body Notes — pre-session warmup protocol, landing assessment protocol for highballs, hip mobility routine, when to call it (fatigue → bad landings → knee risk), ATG knees-over-toes exercises for trip maintenance. Cross-reference group logistics (`logistics/README.md`) for shared gear.

**Checkpoint**: Priority Stack enables instant "last day" decisions. Personal Logistics covers bike transport, gear, and body management. SC-004 testable.

---

## Phase 7: Validation

**Purpose**: Verify all success criteria and quality gates

- [ ] T020 [Val] Validate SC-001: Open Mountain Biking section and confirm top 3 rides identifiable with character, skill-dev value, and pairing info within 60 seconds
- [ ] T021 [Val] Validate SC-002: Open each Tier 1 area climbing section and confirm 3+ suited problems identifiable within 30 seconds
- [ ] T022 [Val] Validate SC-003: Confirm top 3 "don't miss" food/drink spots identifiable without opening any other document
- [ ] T023 [Val] Validate SC-004: Confirm priority stack enables "last day" decision in under 15 seconds
- [ ] T024 [Val] Validate SC-005: Audit every climbing pick for landing-quality flag AND body-constraint flag (where applicable). Fix any missing flags
- [ ] T025 [Val] Validate SC-006: Test every cross-reference link in `sean-guide.md` — all must resolve to existing files. Fix any broken links
- [ ] T026 [Val] Validate SC-007: Run content quality gates — skimmability (tables, ranked lists, emoji flags), decision-orientation (each section answers a core question), scope (bouldering + biking + lifestyle, no rope climbing), source citation
- [ ] T027 [Val] Validate SC-008: Confirm no content is duplicated from area profiles, problem clusters, trail profiles, or rest-day options. All shared data referenced by link only
- [ ] T028 [Val] Verify all [UNVERIFIED] flags are applied where needed (unconfirmed hours, seasonal closures, pricing). Add any missing flags
- [ ] T029 [Val] Run quickstart.md validation checklist (every cross-ref resolves, every climbing pick has flags, every trail has drainage + bike suitability, priority stack has 10+ items)

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — creates file and profile
- **US1 Mountain Biking (Phase 2)**: Depends on Phase 1 — file must exist
- **US2 Climbing Projects (Phase 3)**: Depends on Phase 1 — file must exist. No dependency on Phase 2
- **US3 Food & Drink (Phase 4)**: Depends on Phase 1 — file must exist. No dependency on Phases 2–3
- **US4 Sights (Phase 5)**: Depends on Phase 1 — file must exist. No dependency on Phases 2–4
- **US5 Priority Stack (Phase 6)**: Depends on Phases 2–5 — draws top picks from all sections
- **Validation (Phase 7)**: Depends on all previous phases

### Recommended Execution Order

Since all content writes to a single file, execute sequentially by priority:

```
Phase 1 (Setup) → Phase 2 (US1: Biking) → Phase 3 (US2: Climbing) → Phase 4 (US3: Food) → Phase 5 (US4: Sights) → Phase 6 (US5: Priority Stack + Logistics) → Phase 7 (Validation)
```

### Within Each Phase

- Tasks are sequential (all write to the same file section)
- Complete all tasks in a phase before moving to the next
- Validation tasks (Phase 7) can run in any order after content is complete

---

## Notes

- All 29 tasks write to a single file: `sean-guide.md` at repository root
- No parallel execution within phases — single-file writes must be sequential
- Research data is fully populated in `research.md` — tasks reference specific sections
- Data model entities are defined in `data-model.md` — each content task follows entity field requirements
- Cross-references use relative markdown links from repository root (e.g., `areas/hp40.md`, `trails/white-oak-mountain.md`)
- [UNVERIFIED] flags required for: unconfirmed business hours, seasonal pricing, closure dates sourced from web only
