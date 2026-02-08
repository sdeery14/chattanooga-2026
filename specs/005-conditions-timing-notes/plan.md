# Implementation Plan: Conditions, Timing & Reality Notes

**Branch**: `005-conditions-timing-notes` | **Date**: 2026-02-08 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/005-conditions-timing-notes/spec.md`

## Summary

Create a cross-cutting conditions, timing, and reality guide for the Chattanooga climbing trip. The guide synthesizes conditions wisdom *across* all bouldering areas — mapping weather scenarios to area recommendations, documenting crowd patterns and timing, and providing skin management strategies for a 7-day sandstone trip. It sits above the per-area conditions sections in Feature 001 profiles, adding the "meta" decision layer: "given today's weather, where should we go?"

## Technical Context

**Format**: Markdown knowledge base (same as Features 001-004)
**Storage**: Flat `.md` files in `conditions/` directory at repository root
**Testing**: Manual review against spec quality checklist — no automated tests
**Target Platform**: Offline-capable Markdown files readable on any device
**Project Type**: Knowledge base — no source code
**Scale/Scope**: 1 primary conditions guide document with quick-reference table, area-specific conditions synthesis, crowd/timing profiles, skin management guide, and February seasonal notes. Cross-references Features 001 and 002.

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

### Principle I: Decision-Support First
- **Status**: PASS
- Conditions guide directly answers "Given today's weather, which area should we go to?" — the most time-sensitive of the core trip questions
- Quick-reference table maps weather scenarios to area recommendations for sub-60-second decisions
- Crowd and timing sections prevent the "arrive late, fight for parking" mistake

### Principle II: Bouldering Scope Boundary (NON-NEGOTIABLE)
- **Status**: PASS
- All conditions content is specific to bouldering (friction, humidity, seepage on rock)
- Trail conditions are out of scope (covered by Feature 003)
- No sport/trad climbing content

### Principle III: Ability-Aware, Hard-Climbing Priority
- **Status**: PASS
- Conditions guide helps prioritize areas for hard climbing (friction-dependent V10 problems)
- Humidity and temperature guidance is most critical for hard slopers and crimps
- Skin management is especially relevant for multi-day projecting on sandstone

### Principle IV: Mountain Biking as First-Class Activity
- **Status**: PASS (peripherally applicable)
- When climbing conditions are bad, the guide references Feature 003 trail profiles and Feature 004 rest-day options as alternatives
- Trail conditions are not duplicated — link only

### Principle V: Source Accuracy & Recency
- **Status**: PASS
- FR-008 requires source citation for every conditions claim
- [UNVERIFIED] flags required for unconfirmed information
- Research will use weather data, guidebooks, community forums, and climbing beta sources

## Project Structure

### Documentation (this feature)

```text
specs/005-conditions-timing-notes/
├── plan.md              # This file
├── research.md          # Phase 0: Conditions research
├── data-model.md        # Phase 1: Conditions guide schema
├── quickstart.md        # Phase 1: How to use the conditions guide
└── tasks.md             # Phase 2: Implementation tasks (/speckit.tasks)
```

### Content (repository root)

```text
conditions/
└── README.md            # The conditions guide: quick reference,
                         # area conditions synthesis, crowd/timing,
                         # skin management, February seasonal notes

areas/                   # Existing — no changes needed (cross-referenced)
areas/*-problems.md      # Existing — no changes needed (cross-referenced)
trails/                  # Existing — no changes needed (cross-referenced)
rest-days/               # Existing — no changes needed (cross-referenced)
```

**Structure Decision**: A single `conditions/README.md` file serves as the complete conditions guide. Like Feature 004 (rest-days), this is a cross-cutting reference document — the reader opens one file to understand conditions for all areas. The content synthesizes and compares across areas rather than profiling each one individually (that's Feature 001's job). If the guide grows beyond comfortable single-file size, area-specific conditions could be broken out, but the expected scope fits well in one document.

**File Naming Convention**: `conditions/README.md` (single file)

## Research Outcomes

Research completed in [research.md](research.md) — 783 lines, 45 sources. Key findings:

### February Weather Profile

| Metric | Value |
|--------|-------|
| Temperature | Highs 51-59°F, lows ~35°F. Sweet spot for friction: 40-55°F (mid-morning to early afternoon) |
| Precipitation | ~4.1 inches total, ~13-14 rain days. Expect 2-3 rain events during the trip |
| Dew point | 31-33°F average — excellent for friction (greasy threshold is 55-60°F+) |
| Humidity pattern | Spikes 80%+ before sunrise, drops to 50-65% by afternoon |
| Daylight | Feb 14: sunrise 7:20am, sunset 6:29pm (~11h 9min). Feb 21: sunrise 7:13am, sunset 6:36pm |

### Area Conditions Summary

| Area | Humidity Sensitivity | Seepage After Rain | Crowd Level (Weekend) |
|------|---------------------|-------------------|----------------------|
| Stone Fort | HIGH (slopers); moderate (crimps) | 24-48 hrs shaded; 2-4 hrs sunny | Heavy |
| Rocktown | Moderate (larger holds, less affected) | 24-48 hrs (sandstone caprock) | Moderate |
| HP40 | VERY HIGH (sloper-dominant) | Variable (some sheltered areas) | Moderate-Heavy |
| Dayton Pocket | Low-Moderate (sheltered gorge) | Roof climbing largely rain-proof | Light |
| Walden's Ridge | Moderate | [UNVERIFIED] | Light |

### Key Decision Insights

1. **"Cold and dry" is the mantra** — February dew points (low 30s°F) make it peak friction season for sandstone
2. **Morning humidity trap** — Rock may have condensation before sunrise; east-facing boulders clear first
3. **Rain needs 24-48 hours** to fully dry on sandstone; sunny sectors dry faster; shaded boulders may seep
4. **February IS peak season** — Stone Fort will be busy on weekends; consider weekday visits or early arrival (before 9am)
5. **HP40 slopers are weather-dependent** — practically impossible above 65% humidity; go cold and dry
6. **Rocktown sits 500-1000 ft higher** than Chattanooga valley — 5-10°F cooler, different conditions

### Skin Management Research

- Southeastern sandstone is significantly more abrasive than granite or limestone (friction coefficient ~0.7 vs 0.55-0.65)
- HP40 is the most skin-friendly of the big three (smoother); Stone Fort is moderate; Rocktown is roughest
- Community consensus: don't climb more than 3-4 consecutive days on sandstone without a rest day
- Area rotation strategy: alternate rough (Rocktown) with smooth (HP40) days
- Skin care: sand/file calluses nightly, apply climbing balm, avoid soaking hands

### Unverified Items

12 items flagged [UNVERIFIED] — mostly hourly humidity patterns, specific area elevations, Rocktown temperature differentials, and 2026 competition dates. All properly flagged per FR-008.

## Post-Design Constitution Re-Check

*Re-checking all 5 principles after Phase 0 research and Phase 1 design.*

### Principle I: Decision-Support First — PASS
- Conditions Quick Reference table maps 5+ weather scenarios to area recommendations
- "Morning humidity trap" and dew point guidance enable smart morning decisions
- Crowd timing helps avoid the Stone Fort Saturday crunch

### Principle II: Bouldering Scope Boundary — PASS
- All conditions content is bouldering-specific (rock friction, seepage, sandstone behavior)
- Trail conditions explicitly out of scope

### Principle III: Ability-Aware, Hard-Climbing Priority — PASS
- Humidity/friction guidance is most critical for V10 slopers and crimps
- HP40 conditions section specifically addresses friction-dependent hard problems
- Skin management helps V10 climbers preserve projecting capacity across the week

### Principle IV: Mountain Biking as First-Class Activity — PASS
- Bad-conditions alternatives reference Feature 003 trail profiles and Feature 004 rest-day options
- No trail conditions duplicated

### Principle V: Source Accuracy & Recency — PASS
- 45 sources cited across research (weather data, climbing magazines, guidebooks, community forums, conservation orgs)
- 12 [UNVERIFIED] items properly flagged
- Weather data from multiple cross-referenced sources
