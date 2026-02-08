# Tasks: Conditions, Timing & Reality Notes

**Input**: Design documents from `/specs/005-conditions-timing-notes/`
**Prerequisites**: plan.md, spec.md, research.md, data-model.md, quickstart.md

**Tests**: Not requested — no automated test tasks included.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing. This is a knowledge-base project (Markdown files only) — no source code, no build steps.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different sections, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

- **Content**: `conditions/README.md` (single guide document at repository root)
- **Cross-references**: `areas/*.md` (existing, Feature 001), `areas/*-problems.md` (existing, Feature 002)
- **Specs**: `specs/005-conditions-timing-notes/` (design documents)

---

## Phase 1: Setup

**Purpose**: Create directory structure and document skeleton

- [ ] T001 Create `conditions/` directory and `conditions/README.md` with document skeleton per data-model.md template (title, blockquote with cross-reference to area profiles and trip dates, empty Conditions Quick Reference table header, section headings for Southeastern Sandstone Primer, Area Conditions Synthesis, Crowds & Timing, Skin Management, February Seasonal Profile, Sources)

---

## Phase 2: Foundational — February Seasonal Profile & Sandstone Primer

**Purpose**: Build the seasonal context and sandstone primer that all user stories depend on for interpreting conditions advice

**⚠️ CRITICAL**: The February profile and sandstone primer provide the foundational knowledge for understanding all conditions, crowd, and skin guidance.

- [ ] T002 [P] Write "February Seasonal Profile" section in `conditions/README.md` using research.md section 1. Include: temperature range table (highs 51-59°F, lows ~35°F), precipitation stats (~4.1 inches, ~13-14 rain days), humidity/dew point patterns (average dew point 31-33°F, morning spike, afternoon drop), sunrise/sunset table for Feb 14-21, wind patterns (9-11 mph average), and a "February vs. Ideal Conditions" comparison table. Cite sources from research.md.
- [ ] T003 [P] Write "Southeastern Sandstone Primer" section in `conditions/README.md` using research.md section 6. Include: how sandstone friction works (friction coefficient ~0.74 vs granite/limestone), dew point vs. humidity explanation with threshold table (below 35°F = excellent, above 60°F = avoid), optimal temperature ranges (32-50°F = send temps), why "cold and dry" is the mantra, what "greasy rock" means mechanically, and a practical pre-departure checklist (check dew point, temp, recent rain, wind, cloud cover). Cite sources.

**Checkpoint**: Reader understands February Chattanooga conditions and sandstone friction fundamentals.

---

## Phase 3: User Story 1 — Know Today's Conditions Before Leaving Lodging (Priority: P1) 🎯 MVP

**Goal**: Provide a conditions quick-reference table and area-specific conditions synthesis so a reader can answer "Given today's weather, which area should we go to?" in under 60 seconds.

**Independent Test**: Given a February morning weather scenario (e.g., "45°F, 70% humidity, overnight rain"), use the conditions guide to identify which areas will climb well and which to avoid — in under 60 seconds.

### Implementation for User Story 1

- [ ] T004 [US1] Populate the Conditions Quick Reference table in `conditions/README.md` using research.md sections 1-2. Map at least 5 weather scenarios to area recommendations: (1) cold/dry ideal, (2) humid morning, (3) post-rain (day 1), (4) post-rain (day 2+), (5) warm/humid, (6) windy. Each row must include: Scenario, Best Areas, Avoid, Why (reasoning), and Alt Activity (non-climbing alternative with link to rest-days/ or trails/). Sort by most-likely-to-least-likely February scenarios.
- [ ] T005 [P] [US1] Write "Area Conditions Synthesis" section in `conditions/README.md` with entries for Stone Fort, Rocktown, and HP40 using research.md section 2. Each area entry (H3 heading linked to `../areas/{area}.md`) must include: rock type, humidity sensitivity (Low/Medium/High scale), sun/shade patterns (morning vs. afternoon), wind exposure (Sheltered/Moderate/Exposed), seepage after rain (drying time estimates for different sectors), best conditions, worst conditions, and best time of day. Cross-reference per-area profiles (FR-007) and problem cluster conditions flags (FR-007).
- [ ] T006 [P] [US1] Write Tier 2 area conditions entries in the "Area Conditions Synthesis" section of `conditions/README.md` for Dayton Pocket, Walden's Ridge, and other Tier 2 areas where conditions differ meaningfully from Tier 1. Use research.md section 2. Briefer format than Tier 1 — focus on what makes each area's conditions unique (e.g., Dayton Pocket gorge = sheltered/rain-resistant, Walden's Ridge = closest option). Link to existing area profiles.

**Checkpoint**: Conditions quick reference populated. Reader can map today's weather to an area recommendation. SC-001 and SC-002 testable.

---

## Phase 4: User Story 2 — Avoid Crowds and Timing Mistakes (Priority: P2)

**Goal**: Document crowd patterns, arrival timing, gate hours, and daylight constraints so the group can plan around other climbers and access restrictions.

**Independent Test**: Open the conditions guide and answer "It's Saturday — where can we go to avoid crowds?" with at least 2 recommendations and timing advice, in under 60 seconds.

### Implementation for User Story 2

- [ ] T007 [US2] Write "Crowds & Timing" section in `conditions/README.md` using research.md sections 3-4. Include: (1) February daylight & timing subsection with sunrise/sunset, practical climbing window (8:30am-5pm), and friction peak timing (10am-2pm on sunny days). (2) Per-area crowd profiles for Stone Fort, Rocktown, HP40, and Dayton Pocket — weekend vs. weekday crowds (Light/Moderate/Heavy), peak season status, recommended arrival time, gate hours where applicable, parking notes. (3) Crowd avoidance strategy — which areas to favor on weekends vs. weekdays, Triple Crown competition warning with check-date link. (4) HP40 Central Time zone note (gate opens 8am CT = 9am ET; leave ESNP by 7am ET). Cite sources.

**Checkpoint**: Crowds & timing section complete. SC-003 testable.

---

## Phase 5: User Story 3 — Manage Skin and Multi-Day Sustainability (Priority: P3)

**Goal**: Provide skin management guidance so climbers can sustain sendable skin across a 7-day sandstone trip.

**Independent Test**: Open the conditions guide, find skin management section, and identify a pacing strategy for a 7-day trip with at least 2 actionable strategies.

### Implementation for User Story 3

- [ ] T008 [US3] Write "Skin Management" section in `conditions/README.md` using research.md section 5. Include: (1) Rock abrasiveness comparison table (Rocktown = roughest, Stone Fort = moderate, HP40 = smoothest) with grip-style impact notes (slopers vs. crimps vs. huecos). (2) 7-day pacing strategy table (day-by-day: moderate → ramp → send → rest → moderate-hard → send → light). (3) Area rotation strategy — map skin condition to recommended area type. (4) Skin care tips (file calluses nightly, apply balm, avoid soaking hands) with product recommendations. (5) Skill-level notes for V0-V1, V5, and V10 climbers. Cite sources.

**Checkpoint**: Skin management section complete. SC-004 testable.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: Validate completeness, cross-links, sources, and quality gates

- [ ] T009 Write "Sources" section at the bottom of `conditions/README.md` consolidating all sources cited throughout the document in a table format (Source, Type, Used For). Include links from research.md source summary.
- [ ] T010 Validate all cross-reference links in `conditions/README.md` resolve to existing files: check every `../areas/*.md`, `../areas/*-problems.md`, `../trails/*.md`, and `../rest-days/*.md` link against actual files in the repository. Fix any broken links.
- [ ] T011 Validate success criteria SC-001 through SC-007 against `conditions/README.md`: (SC-001) area recommendation in <60s from quick reference, (SC-002) 3+ weather scenarios mapped, (SC-003) crowd/timing for all Tier 1 areas, (SC-004) 7-day pacing with 2+ strategies, (SC-005) all cross-references resolve, (SC-006) all claims sourced or [UNVERIFIED], (SC-007) 5 quality gates pass.
- [ ] T012 Run quickstart.md scenarios against `conditions/README.md`: (1) "It's 7am, where should we climb?" → find area recommendation from quick reference, (2) "It rained overnight" → find drying-time guidance, (3) "It's Saturday, where's less crowded?" → find crowd avoidance advice, (4) "My skin is wrecked" → find skin management strategy. Document any gaps and fix.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: No dependencies — can start immediately
- **Foundational (Phase 2)**: Depends on Phase 1 (T001) — skeleton must exist
- **User Story 1 (Phase 3)**: Depends on Phase 2 (T002-T003) — seasonal profile and primer provide context
- **User Story 2 (Phase 4)**: Depends on Phase 1 (T001) only — writes to its own section
- **User Story 3 (Phase 5)**: Depends on Phase 1 (T001) only — writes to its own section
- **Polish (Phase 6)**: Depends on all story phases complete (T004-T008)

### User Story Dependencies

- **User Story 1 (P1)**: Depends on Foundational (Phase 2). Core conditions content — MVP.
- **User Story 2 (P2)**: Depends on Phase 1 only. Writes to its own section — can proceed in parallel with US1.
- **User Story 3 (P3)**: Depends on Phase 1 only. Writes to its own section — can proceed in parallel with US1.

### Within Each User Story

- US1: T004 (quick reference table) should be written first, then T005 and T006 (area synthesis) can run in parallel
- US2: Single task (T007) covering all crowd/timing content
- US3: Single task (T008) covering all skin management content

### Parallel Opportunities

- **Phase 2**: T002 and T003 can run in parallel — independent sections
- **Phase 3 (US1)**: T005 and T006 can run in parallel after T004 — different area tiers
- **Phase 3-5**: T007 (US2) and T008 (US3) can run in parallel with each other and with T005/T006 (US1) — all write to different sections
- **Phase 6**: T009-T012 should run sequentially (each validates and may fix issues)

---

## Parallel Example: User Story 1 + US2 + US3

```text
# After T001 (setup) and T002-T003 (foundational), launch in parallel:
Task: "Populate Conditions Quick Reference table"                    (T004 - must be first for US1)

# Then launch all of these in parallel:
Task: "Write Tier 1 Area Conditions Synthesis"                      (T005)
Task: "Write Tier 2 Area Conditions entries"                        (T006)
Task: "Write Crowds & Timing section"                               (T007)
Task: "Write Skin Management section"                               (T008)
```

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete Phase 1: Setup (T001)
2. Complete Phase 2: February profile + sandstone primer (T002-T003)
3. Complete Phase 3: Conditions quick reference + area synthesis (T004-T006)
4. **STOP and VALIDATE**: Can a reader answer "where should we go today?" in <60s?
5. Guide is usable at this point for the core conditions decision

### Incremental Delivery

1. T001-T003 → Skeleton + seasonal context + primer ready
2. T004-T006 → Conditions quick reference + area synthesis → **MVP complete**
3. T007 → Crowds & timing added
4. T008 → Skin management added → Full guide
5. T009-T012 → Validation and polish → Production-ready

---

## Notes

- **Single file**: All content goes into `conditions/README.md` — no individual profile files
- **[P] tasks**: Write to independent sections of the same document; merge carefully if running in parallel agents
- **[UNVERIFIED] flags**: Carry through from research.md — do not remove during implementation (FR-008)
- **Cross-references**: Link to existing files only (FR-007, FR-009) — never duplicate content from areas/ or problem clusters
- **Sources**: Every conditions claim must cite a source or be flagged [UNVERIFIED] (FR-008)
- Total: **12 tasks** across 6 phases
