# Implementation Plan: Area-Scoped Problem Clusters

**Branch**: `002-problem-clusters` | **Date**: 2026-02-08 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/002-problem-clusters/spec.md`

## Summary

Create curated problem cluster documents for each bouldering area, organized by ability band (V0–V3, V4–V6, V7–V10). Each cluster provides area-scoped "what can I climb here?" answers with proximity groupings, style notes, body-type hints, and conditions flags. Clusters are companion documents to the Feature 001 area profiles, linked but separate.

## Technical Context

**Format**: Markdown knowledge base (same as Feature 001)
**Storage**: Flat `.md` files in `areas/` directory alongside area profiles
**Testing**: Manual review against spec quality checklist — no automated tests
**Target Platform**: Offline-capable Markdown files readable on any device
**Project Type**: Knowledge base — no source code
**Scale/Scope**: Up to 8 problem cluster documents (3 Tier 1 mandatory, 5 Tier 2 conditional on data availability), each containing 15–40 curated problems across 3 ability bands

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

### Principle I: Decision-Support First
- **Status**: PASS
- Problem clusters directly answer "What can I climb here?" — the second core trip question
- Proximity groupings and conditions flags enable rapid in-the-moment decisions
- Curated lists (5–15 per band, 40 max total) keep content skimmable

### Principle II: Bouldering Scope Boundary (NON-NEGOTIABLE)
- **Status**: PASS
- All content is bouldering-only; V-scale grades; pad-based access assumed
- No rope climbing, sport, or trad content

### Principle III: Ability-Aware, Hard-Climbing Priority
- **Status**: PASS
- V7–V10 cluster is US1 (P1 priority) — hard climbing first
- V4–V6 and V0–V3 clusters serve US2 (P2) — moderate/easy options noted where they exist
- No artificial parity — areas with limited easy climbing state this honestly
- Body-type notes included where known (FR-007)

### Principle IV: Mountain Biking as First-Class Activity
- **Status**: DEFERRED (Feature 003)
- Problem clusters are bouldering-specific content
- Mountain biking will be addressed in Feature 003: Parallel Activity Mapping

### Principle V: Source Accuracy & Recency
- **Status**: PASS
- FR-013 requires source citation for every problem listing
- Unverified claims flagged per established convention
- Guidebook editions cited with publication date

## Project Structure

### Documentation (this feature)

```text
specs/002-problem-clusters/
├── plan.md              # This file
├── research.md          # Phase 0: Problem data research per area
├── data-model.md        # Phase 1: Problem cluster document schema
├── quickstart.md        # Phase 1: How to use problem clusters
└── tasks.md             # Phase 2: Implementation tasks (/speckit.tasks)
```

### Content (repository root)

```text
areas/
├── stone-fort.md                 # Existing area profile (Feature 001)
├── stone-fort-problems.md        # NEW: Problem cluster for Stone Fort
├── rocktown.md                   # Existing area profile
├── rocktown-problems.md          # NEW: Problem cluster for Rocktown
├── hp40.md                       # Existing area profile
├── hp40-problems.md              # NEW: Problem cluster for HP40
├── dayton-pocket.md              # Existing area profile
├── dayton-pocket-problems.md     # NEW: Problem cluster (if data supports)
├── zahnd-tract.md                # Existing area profile
├── zahnd-tract-problems.md       # NEW: Problem cluster (if data supports)
├── dogwood.md                    # Existing area profile — NO cluster (insufficient data)
├── hospital-boulders.md          # Existing area profile
├── hospital-boulders-problems.md # NEW: Problem cluster (if data supports)
├── waldens-ridge.md              # Existing area profile
├── waldens-ridge-problems.md     # NEW: Problem cluster (if data supports)
├── sunset-rock.md                # Existing Tier 3 — NO cluster (FR-003)
├── hells-kitchen.md              # Existing Tier 3 — NO cluster (FR-003)
└── README.md                     # Update with problem cluster links
```

**Structure Decision**: Problem cluster files live alongside area profiles in `areas/`, using the naming convention `{area-name}-problems.md`. This keeps related content co-located and maintains a flat, navigable directory. Each area profile gains a link to its companion cluster document.

**File Naming Convention**: `{area-name}-problems.md` (kebab-case, matching area profile name)

## Post-Design Constitution Re-Check

All five principles re-verified after Phase 1 design:

- **Principle I**: PASS — Data model enforces skimmability (curated caps, proximity groups, band headers)
- **Principle II**: PASS — All content is V-scale bouldering only
- **Principle III**: PASS — V7–V10 section listed first in template; honest density framing at all bands; research confirmed varying depths across areas (abundant at Stone Fort, thin at Walden's Ridge) — no artificial parity
- **Principle IV**: DEFERRED — Feature 003
- **Principle V**: PASS — Source field is MUST on every problem entry; research.md documents all sources with confidence levels

## Research Outcomes

Research resolved all unknowns. Key findings:

- **7 areas viable for clusters** (3 Tier 1 + 4 Tier 2). Dogwood excluded — all problem data locked behind Rakkup guidebook.
- **Stone Fort**: Deepest data (39 problems across all bands). Strongest moderate pool (V4–V6).
- **Rocktown**: Strong across all bands (35 problems). Golden Harvest/Golden Shower boulder is ideal mixed-ability spot.
- **HP40**: Deepest hard climbing (40 problems). Stiff grading culture noted. Bumboy V3 = friction canary.
- **Dayton Pocket**: Strong V7–V10 (11 problems, mostly on Vapor Roof). V0–V3 data thin (2 named).
- **Zahnd Tract**: V7–V10 viable (8 problems). Lower bands critically thin from web sources.
- **Hospital Boulders**: Best Tier 2 data overall (19 problems). KAYA guidebook is comprehensive.
- **Walden's Ridge**: Strongest moderate data of any Tier 2 (13 V4–V6 problems). Minimal hard climbing.

See `research.md` for full problem inventories, sub-area maps, conditions notes, and source citations.
