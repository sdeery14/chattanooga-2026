# Tasks: Rest Day & Low-Energy Decision Pack

**Input**: Design documents from `/specs/004-rest-day-pack/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, quickstart.md

**Tests**: Not requested — no automated test tasks included.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story. This is a knowledge-base project (Markdown files only) — no source code, no build steps.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files or independent sections, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Content**: `rest-days/README.md` (single guide document at repository root)
- **Cross-references**: `areas/*.md` (existing, Feature 001), `trails/*.md` (existing, Feature 003)
- **Specs**: `specs/004-rest-day-pack/` (design documents)

---

## Phase 1: Setup

**Purpose**: Create directory structure and document skeleton

- [ ] T001 Create `rest-days/` directory and `rest-days/README.md` with document skeleton per data-model.md template (title, blockquote with reference point and trip dates, empty Quick Decision Table header, section headings for When It Rains, Zero-Energy, Low-Energy, Active-Rest, Low-Energy Climbing Sessions, Day Trips)

---

## Phase 2: Foundational — Quick Decision Table

**Purpose**: Build the quick-decision summary table that all user stories depend on for rapid scanning (FR-007, SC-001, SC-006)

**⚠️ CRITICAL**: The Quick Decision Table is the entry point for all three user stories. It must be populated before story-specific sections can be validated.

- [ ] T002 Populate the Quick Decision Table in `rest-days/README.md` with all ~26 options from research.md. Each row must include: Option name, Energy tier (Zero/Low/Active), Type (food/brewery/hike/museum/etc.), Drive time from ESNP, Cost (Free/$/$$/$$$), Rain-OK (Yes/No/Partial), and 1-line Notes. Sort by energy tier (zero first, then low, then active), then by drive time within each tier. Include day trip options at the bottom as a separate group.

**Checkpoint**: A reader can scan the table and identify options by energy level — the core decision-support mechanism.

---

## Phase 3: User Story 1 — Decide What to Do on a Rest Day (Priority: P1) 🎯 MVP

**Goal**: Populate all three energy-tier sections with pre-vetted options so a reader can answer "What should we do today?" within 60 seconds.

**Independent Test**: Open `rest-days/README.md`, ask "Nobody wants to climb — what should we do?", and find at least 2 options per energy tier (zero, low, active) with name, type, location, drive time, description, hours, cost, and source link.

### Implementation for User Story 1

- [ ] T003 [P] [US1] Write Zero-Energy Options section in `rest-days/README.md` with all 8 options from research.md sections 1a-1h (OddStory Brewing, Hutton & Smith, WanderLinger, Champy's, Niedlov's, Rembrandt's, Mad Priest, Southside Social). Each option follows data-model.md format: H3 heading with name, type/location/drive inline, 1-2 sentence description, bullet list with Hours, Cost, and Source link. Flag [UNVERIFIED] items per research.md.
- [ ] T004 [P] [US1] Write Low-Energy Options section in `rest-days/README.md` with all 7 options from research.md sections 2a-2g (Walnut St Bridge + Coolidge Park + North Shore, Bluff View Art District, Tennessee Aquarium, Hunter Museum, Point Park, Southside District, SeaLight Festival). Same per-option format. Include February-specific notes (FR-010): Aquarium extended hours, Hunter Museum closed Tuesdays, Valentine's Day crowd warning.
- [ ] T005 [P] [US1] Write Active-Rest Options section in `rest-days/README.md` with all 7 options from research.md sections 3a-3g (Stringer's Ridge, Glen Falls, Lookout Creek, Sunset Rock, Brainerd Complex pool, The Sinks disc golf, Synergy Climbing). Same per-option format. Add MTB cross-reference note at end of section linking to `../trails/README.md#rest-day-rides-top-3-near-lodging` per FR-004. Include February note for Glen Falls (peak waterfall flow Nov-Mar).
- [ ] T006 [P] [US1] Write Day Trips section in `rest-days/README.md` with 2 options from research.md sections 5a-5b (Sewanee, Fort Mountain State Park). Include drive time, what makes it worth the drive, what to do there, February considerations.

**Checkpoint**: All energy-tier sections populated. Reader can find 2+ options per tier with complete logistics. SC-001 testable.

---

## Phase 4: User Story 2 — Salvage a Weather-Ruined Day (Priority: P2)

**Goal**: Populate the "When It Rains" section so a reader can find weather-appropriate alternatives within 60 seconds of a weather pivot.

**Independent Test**: Open `rest-days/README.md`, jump to "When It Rains" section, and find at least 2 rain-proof options within 30 min of lodging with complete logistics (drive time, hours, cost).

### Implementation for User Story 2

- [ ] T007 [US2] Write "When It Rains" section in `rest-days/README.md` using research.md section 4 weather alternatives. Include: (1) Quick bullet list of all rain-proof options with cross-references to their full entries in the energy-tier sections below (Tennessee Aquarium, Hunter Museum, Southside Social, Synergy Climbing, IMAX Theater). (2) The Rainy-Day Food & Drink Crawl itinerary from research.md section 4 (Niedlov's → Mad Priest/Rembrandt's → Champy's → OddStory/Hutton & Smith → WanderLinger/Southside Social) with note that all spots are within a 5-10 min walk of each other in Southside. (3) Note about partial weather days — morning indoor activity + afternoon climbing/riding if weather clears. Tag each option with Rain-OK status matching the Quick Decision Table.

**Checkpoint**: "When It Rains" section complete. SC-002 and SC-006 testable.

---

## Phase 5: User Story 3 — Find a Low-Energy Climbing or Riding Session (Priority: P3)

**Goal**: Add cross-references to existing climbing and trail profiles for short, close-to-lodging sessions that pair with afternoon rest.

**Independent Test**: Open `rest-days/README.md`, find "Low-Energy Climbing Sessions" section, and identify at least 2 close-to-lodging options (climbing or riding) within 20 min of lodging with session length estimate.

### Implementation for User Story 3

- [ ] T008 [US3] Write "Low-Energy Climbing Sessions" section in `rest-days/README.md` using research.md section 6. Include: (1) Summary table of recommended areas (Walden's Ridge, Stone Fort) with drive time, approach, fee, and "best for" notes. (2) Brief write-up for each recommended area explaining why it works for a casual half-day session — link to existing area profiles via `../areas/waldens-ridge.md` and `../areas/stone-fort.md` per FR-005. (3) "Not Recommended for Casual Sessions" list (Rocktown, HP40, Dayton Pocket, Hospital Boulders) with reason (too far). (4) Decision Shortcut box from research.md. (5) Cross-reference to `../areas/README.md` for full area details. (6) Note about Walden's Ridge as dual-use spot (MTB + bouldering at same location) with link to `../trails/waldens-ridge-park.md`.

**Checkpoint**: Low-energy climbing and riding sessions documented with working cross-references. SC-004 testable.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Validate completeness, cross-links, and quality gates

- [ ] T009 Validate all cross-reference links in `rest-days/README.md` resolve to existing files: check every `../areas/*.md` and `../trails/*.md` link against actual files in the repository. Fix any broken links.
- [ ] T010 Validate Quick Decision Table completeness: confirm every option in the energy-tier sections has a corresponding row in the table, and every table row has a matching section entry. Fix any mismatches.
- [ ] T011 Validate success criteria SC-001 through SC-006 against `rest-days/README.md`: (SC-001) 2+ options per energy tier findable in <60s, (SC-002) 2+ rain-proof options within 30 min documented, (SC-003) all mandatory fields present per data-model.md, (SC-004) all cross-references resolve, (SC-005) 5 quality gates pass (skimmability, decision-orientation, scope, ability coverage, source citation), (SC-006) weather alternative findable in <60s.
- [ ] T012 Run quickstart.md scenarios against `rest-days/README.md`: (1) "Nobody wants to climb" → find 2+ options per tier in <60s, (2) "It's raining" → find rain-proof options in <60s, (3) "Short morning session then chill" → find low-energy climbing + afternoon rest pairing, (4) "Someone wants to ride" → find link to trails/README.md. Document any gaps and fix.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — can start immediately
- **Foundational (Phase 2)**: Depends on Phase 1 (T001) — document skeleton must exist
- **User Story 1 (Phase 3)**: Depends on Phase 2 (T002) — table must be populated before sections
- **User Story 2 (Phase 4)**: Depends on Phase 3 (T003-T005) — "When It Rains" cross-references energy-tier sections
- **User Story 3 (Phase 5)**: Depends on Phase 1 (T001) only — can run in parallel with US1/US2 since it writes to its own section
- **Polish (Phase 6)**: Depends on all story phases complete (T003-T008)

### User Story Dependencies

- **User Story 1 (P1)**: Depends on Foundational (Phase 2). Core content — MVP.
- **User Story 2 (P2)**: Depends on US1 (Phase 3) because rain section cross-references energy-tier entries.
- **User Story 3 (P3)**: Depends on Phase 1 only. Writes to its own section — can proceed in parallel with US1.

### Within Each User Story

- US1: All 4 tasks (T003-T006) write to different sections of the same file but are independent content blocks → marked [P] for parallel content generation
- US2: Single task (T007) that cross-references US1 content
- US3: Single task (T008) that writes to its own section

### Parallel Opportunities

- **Phase 3 (US1)**: T003, T004, T005, T006 can all run in parallel — they write to independent sections
- **Phase 3 + Phase 5**: T008 (US3) can run in parallel with T003-T006 (US1) since they target different sections
- **Phase 6**: T009, T010, T011, T012 should run sequentially (each validates and may fix issues that affect subsequent checks)

---

## Parallel Example: User Story 1

```text
# Launch all 4 energy-tier content tasks together:
Task: "Write Zero-Energy Options section in rest-days/README.md"         (T003)
Task: "Write Low-Energy Options section in rest-days/README.md"          (T004)
Task: "Write Active-Rest Options section in rest-days/README.md"         (T005)
Task: "Write Day Trips section in rest-days/README.md"                   (T006)

# Can also run US3 in parallel with US1:
Task: "Write Low-Energy Climbing Sessions section in rest-days/README.md" (T008)
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (T001)
2. Complete Phase 2: Quick Decision Table (T002)
3. Complete Phase 3: User Story 1 — all energy-tier sections (T003-T006)
4. **STOP and VALIDATE**: Test SC-001 — can a reader answer "What should we do?" with 2+ options per tier in <60s?
5. Guide is usable at this point even without weather and climbing sections

### Incremental Delivery

1. T001-T002 → Skeleton + table ready
2. T003-T006 → Energy-tier sections populated → **MVP complete**
3. T007 → Weather alternatives added → Rain-day coverage
4. T008 → Low-energy climbing/riding sessions → Full guide
5. T009-T012 → Validation and polish → Production-ready

---

## Notes

- **Single file**: All content goes into `rest-days/README.md` — no individual profile files for this feature
- **[P] tasks**: Write to independent sections of the same document; merge carefully if running in parallel agents
- **[UNVERIFIED] flags**: Carry through from research.md — do not remove during implementation (FR-008)
- **Cross-references**: Link to existing files only (FR-009) — never duplicate content from areas/ or trails/
- **February specifics**: Include winter hours, seasonal closures, Valentine's Day notes where relevant (FR-010)
- Total: **12 tasks** across 6 phases
