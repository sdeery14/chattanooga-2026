# Implementation Plan: Parallel Activity Mapping

**Branch**: `003-parallel-activity-mapping` | **Date**: 2026-02-08 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/003-parallel-activity-mapping/spec.md`

## Summary

Document mountain biking trail systems within the Chattanooga trip radius, organized as trail profiles with climbing-area pairings. Each trail system gets a structured profile (difficulty, distance, ride time, conditions, logistics) and is mapped to nearby climbing areas by drive time. A comparison table provides quick "where should I ride today?" answers. Trail documents are companion resources to the Feature 001 area profiles, linked but separate.

## Technical Context

**Format**: Markdown knowledge base (same as Features 001 and 002)
**Storage**: Flat `.md` files in `trails/` directory at repository root
**Testing**: Manual review against spec quality checklist — no automated tests
**Target Platform**: Offline-capable Markdown files readable on any device
**Project Type**: Knowledge base — no source code
**Scale/Scope**: Estimated 5–10 trail system profiles, each containing trail details, conditions notes, and climbing-area pairing information

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

### Principle I: Decision-Support First
- **Status**: PASS
- Trail profiles directly answer "Where can I ride today?" — one of the three core trip questions ("What else can I do nearby?")
- Comparison table and pairing matrix enable rapid in-the-moment decisions
- Trail profiles lead with actionable context (difficulty, distance, drive time) before background detail

### Principle II: Bouldering Scope Boundary (NON-NEGOTIABLE)
- **Status**: PASS
- Feature does not modify or dilute climbing content
- Trail documents are separate from area profiles (FR-009)
- Climbing references link to existing area profiles, not re-described

### Principle III: Ability-Aware, Hard-Climbing Priority
- **Status**: PASS (not directly applicable)
- Feature adds parallel activity support without affecting climbing priority
- Trail pairings reference climbing areas without altering their hard-climbing focus
- The biker is the V0 climber — biking is the appropriate parallel activity for this group member

### Principle IV: Mountain Biking as First-Class Activity
- **Status**: PASS — this is the primary feature implementing Principle IV
- Dedicated trail profiles with same research rigor as bouldering area profiles
- Covers: rest-day rides, half-day pairings, and parallel climbing+biking days (per constitution requirement)
- Trail information includes difficulty, distance, and access logistics (per constitution SHOULD)

### Principle V: Source Accuracy & Recency
- **Status**: PASS
- FR-004 requires source citation for every trail system
- FR-008 requires [UNVERIFIED] flags for unconfirmed information
- Research will use Trailforks, MTB Project, Singletracks, AllTrails, and park websites

## Project Structure

### Documentation (this feature)

```text
specs/003-parallel-activity-mapping/
├── plan.md              # This file
├── research.md          # Phase 0: Trail system research
├── data-model.md        # Phase 1: Trail profile document schema
├── quickstart.md        # Phase 1: How to use trail profiles
└── tasks.md             # Phase 2: Implementation tasks (/speckit.tasks)
```

### Content (repository root)

```text
trails/
├── README.md                    # Trail comparison table + climbing-area pairing matrix
├── enterprise-south.md          # ESNP — at lodging, zero drive
├── white-oak-mountain.md        # Best all-around near lodging, excellent drainage
├── raccoon-mountain.md          # Flagship Chattanooga MTB
├── waldens-ridge-park.md        # Gravity/DH — same location as Walden's Ridge bouldering
├── five-points.md               # Lookout Mountain — Rocktown/Zahnd pairing
├── stringers-ridge.md           # Urban, quick session + pump track
├── coldwater-mountain.md        # HP40 pairing — IMBA Bronze Ride Center in Anniston, AL
├── chickamauga-battlefield.md   # Always-rideable paved/gravel fallback
├── booker-t-washington.md       # Brief profile — close to ESNP, lakeside
├── lookout-mountain.md          # Brief profile — Moonshine/CCT, descent-oriented
├── pigeon-mountain.md           # Brief profile — near Rocktown, WMA access caveats
└── oak-mountain.md              # Brief profile — IMBA Epic near Birmingham, far from trip

areas/
├── stone-fort.md                # Existing — add "Nearby MTB" link
├── rocktown.md                  # Existing — add "Nearby MTB" link
├── hp40.md                      # Existing — add "Nearby MTB" link
├── dayton-pocket.md             # Existing — note "no nearby trails"
├── zahnd-tract.md               # Existing — add "Nearby MTB" link (same as Rocktown)
├── hospital-boulders.md         # Existing — add "Nearby MTB" link (Coldwater Mountain)
├── waldens-ridge.md             # Existing — add "Nearby MTB" link (same location!)
└── README.md                    # Existing — no changes needed (climbing-focused)
```

**Structure Decision**: Trail system profiles live in a new `trails/` directory at repository root, parallel to `areas/`. This keeps climbing and biking content cleanly separated while enabling cross-references. Each trail profile follows a consistent template. Area profiles gain a minimal "Nearby MTB" metadata line linking to relevant trail profiles. The `trails/README.md` serves as the quick-reference comparison table with a climbing-area pairing matrix.

**File Naming Convention**: `{trail-system-name}.md` (kebab-case, matching trail system name)

## Post-Design Constitution Re-Check

All five principles re-verified after Phase 1 design:

- **Principle I**: PASS — Data model enforces skimmability (comparison table, pairing matrix, structured profiles)
- **Principle II**: PASS — All content is mountain biking only; climbing references are links to existing area profiles
- **Principle III**: PASS — Feature adds parallel activity without affecting climbing priority
- **Principle IV**: PASS — 16 trail systems researched with same rigor as bouldering areas; covers rest-day, half-day, and parallel-day use cases
- **Principle V**: PASS — All trail systems cite sources; [UNVERIFIED] flags used for unconfirmed data; Black Creek February closure flagged

## Research Outcomes

Research resolved all unknowns. Key findings:

- **16 trail systems identified** (8 HIGH confidence, 3 MODERATE, 2 LOW-MODERATE, 1 LOW, plus 2 distant Alabama options)
- **Enterprise South Nature Park** (at lodging): ~15 mi singletrack, zero drive, good drainage — the default fallback
- **White Oak Mountain**: Best all-around option near lodging — 25 mi, excellent drainage, open until 10 PM
- **Raccoon Mountain**: Flagship Chattanooga MTB — 28-30 mi, but not rideable in wet conditions
- **Walden's Ridge Park**: Perfect pairing with Walden's Ridge bouldering (same location!) — gravity/DH focused
- **Coldwater Mountain** (Anniston, AL): **Critical HP40 pairing discovery** — 50+ mi IMBA Bronze Ride Center, ~55 min from HP40, free, open 365 days, excellent drainage
- **Black Creek February closure**: Noccalula Falls Park closed Jan 1–Feb 28, making the closest trail to HP40 effectively unusable
- **Every Tier 1 climbing area has at least 1 viable trail pairing** (Stone Fort→Raccoon Mountain, Rocktown→Five Points/Pigeon Mountain, HP40→Coldwater Mountain)
- **Wet-weather fallbacks**: White Oak Mountain (drains very well), ESNP (rock-lined), Chickamauga Battlefield (paved, always rideable)
- **Trail profiles planned for implementation**: 8 primary systems (ESNP, White Oak Mountain, Raccoon Mountain, Walden's Ridge Park, Five Points, Stringer's Ridge, Coldwater Mountain, Chickamauga Battlefield) + brief notes for 4-5 secondary systems

See `research.md` for full trail inventories, conditions data, pairing matrix, and source citations.
