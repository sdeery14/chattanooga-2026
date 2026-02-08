# Implementation Plan: Logistics & Access Cheat Sheets

**Branch**: `006-logistics-access-cheat-sheets` | **Date**: 2026-02-08 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/006-logistics-access-cheat-sheets/spec.md`

## Summary

Create a logistics and access cheat sheet that consolidates drive times, access requirements, parking/approach details, and critical access warnings for all climbing areas into a single reference document. The guide sits alongside the conditions guide (Feature 005) as the second cross-cutting reference layer — conditions answers "where should we go today?" while logistics answers "how do we get there and what do we need to know before arriving?" It synthesizes access information from per-area profiles (Feature 001) into a comparison format optimized for rapid daily planning.

## Technical Context

**Format**: Markdown knowledge base (same as Features 001-005)
**Storage**: Flat `.md` files in `logistics/` directory at repository root
**Testing**: Manual review against spec quality checklist — no automated tests
**Target Platform**: Offline-capable Markdown files readable on any device
**Project Type**: Knowledge base — no source code
**Scale/Scope**: 1 primary logistics guide document with drive-time comparison table, per-area access cheat sheets, parking/approach details, "don't screw this up" checklist, and multi-area day pairings. Cross-references Features 001 and 005.

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

### Principle I: Decision-Support First
- **Status**: PASS
- Logistics guide directly answers "how do we get there?" and "what do we need to know before arriving?" — critical daily decisions
- Drive-time comparison table enables sub-15-second area logistics lookup
- "Don't Screw This Up" checklist prevents the most costly trip mistakes (missed gates, missing codes, wrong time zone)

### Principle II: Bouldering Scope Boundary (NON-NEGOTIABLE)
- **Status**: PASS
- All logistics content is specific to bouldering areas (parking at climbing trailheads, approach to boulder fields, climbing area fees)
- Trail logistics for biking are out of scope (covered by Feature 003)
- No sport/trad climbing content

### Principle III: Ability-Aware, Hard-Climbing Priority
- **Status**: PASS (peripherally applicable)
- Logistics are ability-neutral — drive times and access rules apply equally to all climbers
- Multi-area day pairings can help optimize time at hard-climbing destinations (e.g., HP40 + Hospital Boulders corridor)

### Principle IV: Mountain Biking as First-Class Activity
- **Status**: PASS (peripherally applicable)
- When group splits, the guide cross-references Feature 003 trail profiles for nearby trailhead locations
- Biking-specific logistics not duplicated — link only

### Principle V: Source Accuracy & Recency
- **Status**: PASS
- FR-008 requires source citation for every logistics claim
- FR-007 requires contact info/verification links for each area
- [UNVERIFIED] flags required for unconfirmed information

## Project Structure

### Documentation (this feature)

```text
specs/006-logistics-access-cheat-sheets/
├── plan.md              # This file
├── research.md          # Phase 0: Logistics research
├── data-model.md        # Phase 1: Logistics guide schema
├── quickstart.md        # Phase 1: How to use the logistics guide
└── tasks.md             # Phase 2: Implementation tasks (/speckit.tasks)
```

### Content (repository root)

```text
logistics/
└── README.md            # The logistics guide: drive-time table,
                         # per-area access cheat sheets, parking/approach,
                         # "don't screw this up" checklist, multi-area pairings

areas/                   # Existing — no changes needed (cross-referenced)
conditions/              # Existing — no changes needed (cross-referenced)
trails/                  # Existing — no changes needed (cross-referenced)
rest-days/               # Existing — no changes needed (cross-referenced)
```

**Structure Decision**: A single `logistics/README.md` file serves as the complete logistics guide. Like Features 004 (rest-days) and 005 (conditions), this is a cross-cutting reference document — the reader opens one file to see logistics for all areas. The content synthesizes and compares across areas rather than profiling each one individually (that's Feature 001's job).

**File Naming Convention**: `logistics/README.md` (single file)

## Research Outcomes

Research completed in [research.md](research.md) — 18 sources, 12 unverified items. Key findings:

### Drive-Time Summary

| Area | Drive Time | Time Zone | Key Concern |
|------|-----------|-----------|-------------|
| Walden's Ridge | ~25–35 min | ET | Closest option; no access hurdles |
| Stone Fort | ~35–45 min | ET | Must check in at clubhouse |
| Dogwood | ~45–55 min | ET | Registration required |
| Dayton Pocket | ~50–65 min | ET | Gate locks at 7 PM — lock-in risk |
| Rocktown | ~50–70 min | ET | Last 3 mi unpaved; WMA license |
| Zahnd Tract | ~50–60 min | ET | Same WMA license as Rocktown |
| Hospital Boulders | ~1.5–2 hrs | CT | Gate code required from SCC |
| HP40 | ~2 hrs | CT | Time zone crossing; gate 8AM–6PM CT |

### Critical Access Findings

1. **7 pre-trip action items** identified: WMA license, Hospital Boulders gate code, Dayton Pocket registration, Dogwood registration, Triple Crown date check, Stone Fort hours confirmation, HP40 hours check
2. **5 day-of warnings**: HP40 time zone, Dayton Pocket lock-in, Stone Fort clubhouse check-in, Hospital Boulders property boundary, Rocktown road conditions
3. **4 multi-area pairings** identified: HP40 + Hospital Boulders (Alabama corridor), Rocktown + Zahnd (Georgia ridge), Stone Fort + Dogwood (Cumberland Plateau), Walden's Ridge + Sunset Rock (quick local)

### Unverified Items

12 items flagged [UNVERIFIED] — mostly payment methods, specific phone numbers, road conditions, and approach time estimates. All properly flagged per FR-008.

## Post-Design Constitution Re-Check

*Re-checking all 5 principles after Phase 0 research and Phase 1 design.*

### Principle I: Decision-Support First — PASS
- Drive-time comparison table enables sub-15-second lookup (SC-001)
- "Don't Screw This Up" section has 7 pre-trip + 5 day-of items (exceeds SC-003 target of 5)
- Per-area access cheat sheets enable sub-30-second requirement lookup (SC-002)

### Principle II: Bouldering Scope Boundary — PASS
- All logistics content is for bouldering area access only
- Sunset Rock noted as "not a meaningful bouldering destination" — included only for scenic pairing

### Principle III: Ability-Aware, Hard-Climbing Priority — PASS
- Logistics are ability-neutral; multi-area pairings optimize time at HP40 (hard-climbing destination)

### Principle IV: Mountain Biking as First-Class Activity — PASS
- Cross-references to Feature 003 trail profiles maintained in area profiles (linked, not duplicated)

### Principle V: Source Accuracy & Recency — PASS
- 18 sources cited; 12 [UNVERIFIED] items properly flagged
- Contact info and verification links provided for all gated/fee areas (FR-007)
