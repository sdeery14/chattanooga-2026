# Tasks: Logistics & Access Cheat Sheets

**Input**: Design documents from `/specs/006-logistics-access-cheat-sheets/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, quickstart.md

**Tests**: Not requested — no automated test tasks included.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing. This is a knowledge-base project (Markdown files only) — no source code, no build steps.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different sections, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Content**: `logistics/README.md` (single guide document at repository root)
- **Cross-references**: `areas/*.md` (existing, Feature 001), `conditions/README.md` (existing, Feature 005)
- **Specs**: `specs/006-logistics-access-cheat-sheets/` (design documents)

---

## Phase 1: Setup

**Purpose**: Create directory structure and document skeleton

- [ ] T001 Create `logistics/` directory and `logistics/README.md` with document skeleton per data-model.md template (title, blockquote with cross-references to conditions guide, area profiles, and trip dates, empty Drive-Time Comparison table header, section headings for Don't Screw This Up, Area Access Cheat Sheets, Multi-Area Day Pairings, Sources)

---

## Phase 2: User Story 1 — Drive-Time Comparison & Daily Departure Planning (Priority: P1) 🎯 MVP

**Goal**: Provide a drive-time comparison table so the group can answer "how far is each area?" in under 15 seconds.

**Independent Test**: Open the logistics guide and determine drive time from ESNP to any area in under 15 seconds using the comparison table.

### Implementation for User Story 1

- [ ] T002 [US1] Populate the Drive-Time Comparison table in `logistics/README.md` using research.md section 1. Include all Tier 1 areas (Stone Fort, Rocktown, HP40) and Tier 2 areas (Dayton Pocket, Walden's Ridge, Hospital Boulders, Dogwood, Zahnd Tract) sorted by drive time. Each row must include: Area (linked to area profile), Drive Time, Distance, Route description, Time Zone (flag ET/CT crossings), and Road Notes for February. Add a brief note below the table about mountain road concerns in February (ice, unpaved sections). Cite sources from research.md.

**Checkpoint**: Drive-time table populated. Reader can determine drive time to any area in under 15 seconds. SC-001 testable.

---

## Phase 3: User Story 2 — Access Requirements & "Don't Screw This Up" Warnings (Priority: P2)

**Goal**: Document all access requirements per area and consolidate critical warnings so the group never makes a preventable access mistake.

**Independent Test**: Open the logistics guide and identify all access requirements (fee, gate hours, registration) for any area in under 30 seconds. The "Don't Screw This Up" section contains at least 5 critical warnings.

### Implementation for User Story 2

- [ ] T003 [US2] Write the "Don't Screw This Up" section in `logistics/README.md` using research.md section 5. Split into two subsections: (1) Pre-Trip Action Items (7 items: purchase GA WMA license, request Hospital Boulders gate code, register for Dayton Pocket, register for Dogwood, check Triple Crown dates, confirm Stone Fort hours, check HP40 hours) and (2) Day-Of Warnings (5 items: HP40 time zone trap, Dayton Pocket lock-in, Stone Fort clubhouse check-in, Hospital Boulders property boundary, Rocktown road after rain). Each warning must include severity indicator. Cite sources.
- [ ] T004 [P] [US2] Write Tier 1 Area Access Cheat Sheets in `logistics/README.md` using research.md sections 2-3. Create H3 entries for Stone Fort, Rocktown, and HP40. Each entry must include: fee, gate hours, check-in/registration, critical rules, parking location, approach (distance/time/terrain/pad-carry), and contact info/verification link. Link area name to area profile. Flag HP40 and Hospital Boulders time zones. Cite sources.
- [ ] T005 [P] [US2] Write Tier 2 Area Access Cheat Sheets in `logistics/README.md` using research.md sections 2-3. Create H3 entries for Dayton Pocket, Walden's Ridge, Hospital Boulders, Dogwood, and Zahnd Tract. Briefer format than Tier 1 — focus on what's unique about each area's access (Dayton Pocket lock-in, Hospital Boulders gate code, Dogwood registration, Zahnd WMA license). Link to area profiles. Cite sources.

**Checkpoint**: Access cheat sheets complete for all areas. "Don't Screw This Up" has 12 items (7 pre-trip + 5 day-of). SC-002, SC-003, SC-004 testable.

---

## Phase 4: User Story 3 — Parking & Approach Information (Priority: P3)

**Goal**: Document parking and approach details so first-time visitors don't waste time on arrival.

**Independent Test**: Open the logistics guide and find parking and approach info for any area in under 30 seconds.

### Implementation for User Story 3

- [ ] T006 [US3] Verify that parking and approach details are included in each Area Access Cheat Sheet entry (T004-T005). If any area is missing parking location, approach distance/time, or pad-carry notes, add them. Ensure Stone Fort includes Montlake clubhouse address, Rocktown includes unpaved road warning, HP40 includes "boulders scattered throughout park" note, and Dayton Pocket includes the significant elevation change (~1,000 ft) warning.

**Checkpoint**: All area entries include complete parking and approach information. SC-002 (extended) testable.

---

## Phase 5: Multi-Area Pairings & Polish

**Purpose**: Add multi-area day pairings, consolidate sources, validate quality

- [ ] T007 Write "Multi-Area Day Pairings" section in `logistics/README.md` using research.md section 4. Include at least 4 pairings: (1) Alabama Corridor: HP40 + Hospital Boulders, (2) Georgia Ridge: Rocktown + Zahnd Tract, (3) Cumberland Plateau: Stone Fort + Dogwood, (4) Quick Local: Walden's Ridge + Sunset Rock viewpoint. Each pairing must include: areas (linked), total drive time from ESNP and between areas, why it works logistically, and timing tips. Cite sources.
- [ ] T008 Write "Sources" section at the bottom of `logistics/README.md` consolidating all sources cited throughout the document in a table format (Source, Type, Used For). Include links from research.md source summary.
- [ ] T009 Validate all cross-reference links in `logistics/README.md` resolve to existing files: check every `../areas/*.md`, `../conditions/README.md`, `../trails/README.md`, and `../rest-days/README.md` link against actual files in the repository. Fix any broken links.
- [ ] T010 Validate success criteria SC-001 through SC-007 against `logistics/README.md`: (SC-001) drive time lookup in <15s, (SC-002) access requirements in <30s, (SC-003) at least 5 critical warnings, (SC-004) contact info for all gated/fee areas, (SC-005) all cross-references resolve, (SC-006) all claims sourced or [UNVERIFIED], (SC-007) at least 3 multi-area pairings with drive-time totals.
- [ ] T011 Run quickstart.md scenarios against `logistics/README.md`: (1) "How long to get to HP40?" → find in drive-time table, (2) "We're heading to Dayton Pocket — what do we need to know?" → find access cheat sheet, (3) "We want to visit two areas today" → find multi-area pairings, (4) "Do we need to pay?" → find in Don't Screw This Up or access sheet. Document any gaps and fix.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — can start immediately
- **User Story 1 (Phase 2)**: Depends on Phase 1 (T001) — skeleton must exist
- **User Story 2 (Phase 3)**: Depends on Phase 1 (T001) — writes to its own sections
- **User Story 3 (Phase 4)**: Depends on Phase 3 (T004-T005) — verifies/extends access entries
- **Polish (Phase 5)**: Depends on all story phases complete (T002-T006)

### User Story Dependencies

- **User Story 1 (P1)**: Depends on Phase 1 only. Writes to drive-time table section.
- **User Story 2 (P2)**: Depends on Phase 1 only. Writes to its own sections — can proceed in parallel with US1.
- **User Story 3 (P3)**: Depends on US2 (T004-T005) — verifies parking/approach in access entries.

### Within Each User Story

- US1: Single task (T002) covering the drive-time table
- US2: T003 (Don't Screw This Up) should be written first, then T004 and T005 (area access sheets) can run in parallel
- US3: Single task (T006) that verifies/extends US2 entries

### Parallel Opportunities

- **Phase 2-3**: T002 (US1 drive-time table) can run in parallel with T003 (US2 warnings) — different sections
- **Phase 3**: T004 and T005 can run in parallel after T003 — different area tiers in same section
- **Phase 5**: T007-T008 can run in parallel (different sections), then T009-T011 should run sequentially (each validates and may fix issues)

---

## Parallel Example: US1 + US2

```text
# After T001 (setup), launch in parallel:
Task: "Populate Drive-Time Comparison table"                          (T002 - US1)
Task: "Write Don't Screw This Up section"                            (T003 - US2)

# Then launch in parallel:
Task: "Write Tier 1 Area Access Cheat Sheets"                        (T004 - US2)
Task: "Write Tier 2 Area Access Cheat Sheets"                        (T005 - US2)
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (T001)
2. Complete Phase 2: Drive-time table (T002)
3. **STOP and VALIDATE**: Can a reader find drive time to any area in <15s?
4. Guide is usable at this point for the core logistics question

### Incremental Delivery

1. T001 → Skeleton ready
2. T002 → Drive-time table → **MVP complete**
3. T003-T005 → Access cheat sheets + warnings added
4. T006 → Parking/approach verified
5. T007 → Multi-area pairings added → Full guide
6. T008-T011 → Validation and polish → Production-ready

---

## Notes

- **Single file**: All content goes into `logistics/README.md` — no individual profile files
- **[P] tasks**: Write to independent sections of the same document; merge carefully if running in parallel agents
- **[UNVERIFIED] flags**: Carry through from research.md — do not remove during implementation (FR-008)
- **Cross-references**: Link to existing files only (FR-006) — never duplicate content from areas/ or conditions/
- **Sources**: Every logistics claim must cite a source or be flagged [UNVERIFIED] (FR-008)
- Total: **11 tasks** across 5 phases
