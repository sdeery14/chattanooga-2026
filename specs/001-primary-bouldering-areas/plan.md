# Implementation Plan: Primary Bouldering Areas (Hard-First, Group-Aware)

**Branch**: `001-primary-bouldering-areas` | **Date**: 2026-02-08 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/001-primary-bouldering-areas/spec.md`

## Summary

Research and document all known bouldering areas within ~2 hours of the Enterprise South Nature Park area (Chattanooga lodging). Each area receives a structured profile prioritizing V7–V10 appeal with honest group-aware grade density assessments. A comparison reference table ties all profiles together for rapid side-by-side decisions. Trip dates: February 14–21, 2026.

## Technical Context

**Format**: Markdown documents (`.md`)
**Storage**: Git repository — flat files in `areas/` directory at repo root
**Tooling**: No build tools, no dependencies — plain Markdown readable offline
**Target Platform**: Any Markdown viewer (GitHub, VS Code, phone browser)
**Project Type**: Knowledge base (static documents)
**Performance Goals**: Each profile skimmable in under 60 seconds per constitution gate
**Constraints**: All content must work offline once cloned; no external service dependencies
**Scale/Scope**: Estimated 8–15 area profiles + 1 comparison reference document

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Status | Evidence |
|-----------|--------|----------|
| I. Decision-Support First | ✅ PASS | Structured profiles with bullet points; comparison table for rapid decisions; 2-minute selection target in SC-001 |
| II. Bouldering Scope Boundary | ✅ PASS | All profiles limited to bouldering; V-scale grades only; no rope-climbing content |
| III. Ability-Aware, Hard-Climbing Priority | ✅ PASS | V7–V10 appeal is the first substantive section in each profile; grade density uses honest descriptors; no artificial parity |
| IV. Mountain Biking as First-Class Activity | ⚠️ DEFERRED | Mountain biking is Feature 003 scope. Area profiles in this feature will NOT include biking trails — this is intentional per the roadmap dependency chain |
| V. Source Accuracy & Recency | ✅ PASS | FR-008 requires source citations; unverified claims must be flagged; conditions data must include date/season context |

**Gate result**: PASS. Principle IV is intentionally deferred to Feature 003, not violated — the constitution requires biking coverage "in each area or rest-day document," and the area profiles will be updated when Feature 003 is implemented.

## Project Structure

### Documentation (this feature)

```text
specs/001-primary-bouldering-areas/
├── plan.md              # This file
├── research.md          # Phase 0: area inventory and source research
├── data-model.md        # Phase 1: area profile schema
├── quickstart.md        # Phase 1: how to use the area profiles
└── tasks.md             # Phase 2: /speckit.tasks output
```

### Content (repository root)

```text
areas/
├── README.md                    # Comparison reference table (FR-009)
├── stone-fort.md                # Individual area profiles (FR-001–FR-011)
├── rocktown.md
├── hp40.md
├── little-rock-city.md
├── sunset-park.md
├── dayton-pocket.md
├── pendergrass.md
├── zahnd-tract.md
├── denny-cove.md
└── [additional areas as discovered in research]
```

**Structure Decision**: Each area gets its own Markdown file in `areas/` at the repo root. The `areas/README.md` serves as both the index and the comparison reference table (US3 / FR-009). This flat structure keeps navigation simple — one file per area, no nesting.

## Complexity Tracking

No constitution violations requiring justification.
