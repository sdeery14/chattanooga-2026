# Implementation Plan: Rest Day & Low-Energy Decision Pack

**Branch**: `004-rest-day-pack` | **Date**: 2026-02-08 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/004-rest-day-pack/spec.md`

## Summary

Create a rest-day and low-energy decision guide for the Chattanooga climbing trip, organized by energy tier (zero/low/active) with weather-dependent alternatives. The guide provides pre-vetted options (food, breweries, hikes, sightseeing, indoor activities) so rest days don't devolve into phone-scrolling indecision. Cross-references existing trail profiles (Feature 003) and area profiles (Feature 001) by link — no content duplication.

## Technical Context

**Format**: Markdown knowledge base (same as Features 001, 002, and 003)
**Storage**: Flat `.md` files in `rest-days/` directory at repository root
**Testing**: Manual review against spec quality checklist — no automated tests
**Target Platform**: Offline-capable Markdown files readable on any device
**Project Type**: Knowledge base — no source code
**Scale/Scope**: 1 primary guide document with quick-decision table, energy-tier sections, and weather alternatives. Estimated 15-30 individual rest-day options across all tiers.

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

### Principle I: Decision-Support First
- **Status**: PASS
- Rest-day guide directly answers "What should we do today?" — one of the three core trip questions
- Quick-decision table enables rapid scanning under fatigue
- Energy-tier organization matches real decision patterns (how much energy does the group have?)

### Principle II: Bouldering Scope Boundary (NON-NEGOTIABLE)
- **Status**: PASS
- Feature does not modify or dilute climbing content
- Climbing references link to existing area profiles, not re-described
- Rest-day content is explicitly non-climbing (food, hikes, sightseeing, indoor activities)

### Principle III: Ability-Aware, Hard-Climbing Priority
- **Status**: PASS (not directly applicable)
- Feature adds rest-day support without affecting climbing priority
- Low-energy climbing session recommendations reference existing area profiles
- Rest days explicitly serve the whole group, not just climbers

### Principle IV: Mountain Biking as First-Class Activity
- **Status**: PASS
- Active-rest tier cross-references Feature 003 trail profiles for easy rides
- Mountain biking is presented as a peer option to hiking and other active-rest activities

### Principle V: Source Accuracy & Recency
- **Status**: PASS
- FR-006 requires source citation for every rest-day option
- FR-008 requires [UNVERIFIED] flags for unconfirmed information
- Research will use Google Maps, business websites, tourism sites, and community recommendations

## Project Structure

### Documentation (this feature)

```text
specs/004-rest-day-pack/
├── plan.md              # This file
├── research.md          # Phase 0: Rest-day options research
├── data-model.md        # Phase 1: Rest-day option schema
├── quickstart.md        # Phase 1: How to use the rest-day guide
└── tasks.md             # Phase 2: Implementation tasks (/speckit.tasks)
```

### Content (repository root)

```text
rest-days/
└── README.md            # The rest-day guide: quick-decision table,
                         # energy-tier sections (zero/low/active),
                         # weather alternatives, cross-references

areas/                   # Existing — no changes needed
trails/                  # Existing — no changes needed
```

**Structure Decision**: A single `rest-days/README.md` file serves as the complete rest-day guide. Unlike Features 001 and 003, which needed individual profiles per area/trail, rest-day options are brief enough to live in a single document organized by energy tier. This keeps the decision flow in one place — the reader opens one file and scans for their energy level. If the guide grows too large, individual options could be broken out, but the expected ~15-30 options fit comfortably in one document.

**File Naming Convention**: `rest-days/README.md` (single file)

## Research Outcomes

Research completed in [research.md](research.md). Key findings:

### Option Counts by Tier

| Tier | Count | Highlights |
|------|-------|-----------|
| Zero-Energy | 8 | 3 breweries (OddStory, Hutton & Smith, WanderLinger), 2 restaurants (Champy's, Niedlov's), 2 coffee shops (Rembrandt's, Mad Priest), 1 multi-use (Southside Social) |
| Low-Energy | 7 | 2 walks (Walnut St Bridge area, Bluff View Art District), 2 museums (Aquarium, Hunter), 1 scenic overlook (Point Park), 1 neighborhood (Southside District), 1 event (SeaLight Festival) |
| Active-Rest | 7 | 4 hikes (Stringer's Ridge, Glen Falls, Lookout Creek, Sunset Rock), 1 pool (Brainerd Complex), 1 disc golf (The Sinks), 1 indoor climbing (Synergy) |
| Day Trips | 2 | Sewanee (~60 min), Fort Mountain State Park (~55 min) |
| Low-Energy Climbing | 2 recommended | Walden's Ridge (~25-35 min, free), Stone Fort (~35-45 min, $10-12) |

**Total: ~26 options** — well within the 15-30 estimate from the plan.

### Weather Alternatives

6 rain-proof options identified: Tennessee Aquarium, Hunter Museum, Southside Social, Synergy Climbing, IMAX Theater, plus a structured Rainy-Day Food & Drink Crawl itinerary. Spare Time Entertainment also noted but heavily [UNVERIFIED].

### Cross-References Confirmed

- **Feature 003 (Trails)**: Active-rest section references `trails/README.md#rest-day-rides-top-3-near-lodging` for MTB options. No duplication.
- **Feature 001 (Areas)**: Low-energy climbing references `areas/waldens-ridge.md` and `areas/stone-fort.md`. No content duplicated — links only.

### Unverified Items

12 items flagged [UNVERIFIED] in research.md — mostly pricing, specific 2026 event dates, and a few drive times. These are appropriately flagged per FR-008 and will carry through to the final guide.

### February-Specific Insights

- Tennessee Aquarium may have College Days pricing (~50% off) and Valentine's events
- Glen Falls waterfall is at peak flow Nov-Mar (February = ideal timing)
- SeaLight Festival (Chinese lanterns) may be running through April
- Sewanee: 5-10°F cooler than Chattanooga at 2,000 ft elevation
- Valentine's Day (Feb 14) = trip start date; restaurants will be busier Feb 13-15

## Post-Design Constitution Re-Check

*Re-checking all 5 principles after Phase 0 research and Phase 1 design.*

### Principle I: Decision-Support First — PASS
- Quick-decision table covers all 26 options in scannable format
- Energy-tier sections enable the "How much energy does the group have?" decision flow
- Weather section provides rapid pivot capability
- 60-second decision target is achievable with the table + tier structure

### Principle II: Bouldering Scope Boundary — PASS
- No climbing content duplicated — all climbing references are links to existing area profiles
- Rest-day content is clearly non-climbing (food, hikes, museums, breweries, etc.)
- Indoor climbing gym (Synergy) is an option, not a replacement for outdoor climbing content

### Principle III: Ability-Aware, Hard-Climbing Priority — PASS
- Low-energy climbing section recommends Walden's Ridge (V4-V6 sweet spot) and Stone Fort (all grades)
- Decision shortcut includes V10 climber guidance ("Stone Fort — worth the fee and the drive")
- Rest-day options serve the whole group regardless of climbing ability

### Principle IV: Mountain Biking as First-Class Activity — PASS
- Active-rest section explicitly cross-references Feature 003 trail profiles
- Walden's Ridge highlighted as dual-use spot (MTB + bouldering at same location)
- MTB presented as a peer option to hiking, not an afterthought

### Principle V: Source Accuracy & Recency — PASS
- 12+ external sources cited across research (tourism boards, official sites, Yelp, AllTrails, NPS)
- 12 [UNVERIFIED] items properly flagged for follow-up closer to trip
- Existing repository content (areas/, trails/) cross-referenced by link, not re-researched
