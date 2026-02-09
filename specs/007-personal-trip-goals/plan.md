# Implementation Plan: Personal Trip Goals & Preferences (Sean)

**Branch**: `007-personal-trip-goals` | **Date**: 2026-02-09 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `specs/007-personal-trip-goals/spec.md`

## Summary

Create a single personal guide document (`sean-guide.md`) at the repository root that serves as Sean's decision-support layer on top of the existing group research. The guide consolidates: mountain bike trail rankings (filtered for his Jamis Faultline A2 and athletic-beginner skill level), climbing problem picks (curated for his 6'2"/200lb/V1-outdoor profile with reach advantages and knee/hip constraints), IPA-focused brewery targets and hearty casual food spots, sights and experiences, and a cross-category priority stack. All content cross-references existing documents by link — no duplication.

## Technical Context

**Language/Version**: Markdown (CommonMark)
**Primary Dependencies**: Existing Features 001–006 documents (area profiles, problem clusters, trail profiles, rest-day guide, conditions guide, logistics guide)
**Storage**: Single markdown file at repository root (`sean-guide.md`)
**Testing**: Manual validation against spec success criteria (SC-001 through SC-008)
**Target Platform**: GitHub-rendered markdown, readable on mobile
**Project Type**: Knowledge base document
**Performance Goals**: Key decisions accessible within 15–60 seconds (per spec success criteria)
**Constraints**: Must not duplicate content from existing documents. Must flag [UNVERIFIED] information. Must cite sources.
**Scale/Scope**: Single document, ~300–500 lines estimated

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Status | Notes |
|-----------|--------|-------|
| I. Decision-Support First | **PASS** | Every section answers "What should Sean do right now?" Format optimized for fatigue/time pressure |
| II. Bouldering Scope Boundary | **PASS** | All climbing content is V-scale bouldering on pads. No rope disciplines |
| III. Ability-Aware, Hard-Climbing Priority | **PASS** | This is a personal guide for the V0–V1 climber. It references area profiles that already cover V10 objectives. The guide surfaces lower-grade options personalized for Sean's strengths |
| IV. Mountain Biking as First-Class | **PASS** | Mountain biking is P1 priority in this feature. Trail wishlist is the lead section |
| V. Source Accuracy & Recency | **PASS** | All food/drink/sights research cites web sources. [UNVERIFIED] flags used where applicable. February 2026 window assumed |

**Content Quality Gates**:
1. ✅ **Skimmability**: Tables, ranked lists, emoji flags — all designed for 15–60 second access
2. ✅ **Decision-orientation**: Every section answers a core question (what to ride, what to climb, where to eat, what to see)
3. ✅ **Scope**: Bouldering + mountain biking + personal lifestyle targets
4. ✅ **Ability coverage**: Personalized for V0–V3 with reach/power filter. V10 objectives live in referenced area profiles
5. ✅ **Source**: Research cites URLs and guidebook references. [UNVERIFIED] flags applied

No gate violations. No complexity tracking needed.

## Project Structure

### Documentation (this feature)

```text
specs/007-personal-trip-goals/
├── spec.md              # Feature specification
├── plan.md              # This file
├── research.md          # Phase 0 output — climbing, biking, food, sights research
├── data-model.md        # Phase 1 output — entity definitions and document structure
├── checklists/
│   └── requirements.md  # Spec quality checklist
└── tasks.md             # Phase 2 output (created by /speckit.tasks)
```

### Source Content (repository root)

```text
sean-guide.md            # The single output document (this feature's deliverable)
```

**Structure Decision**: Single markdown file at repository root, parallel to existing hub documents (`areas/README.md`, `trails/README.md`, etc.). No subdirectory — Sean's guide is a personal overlay, not a new content category.

## Implementation Approach

### Phase 1: Document Skeleton + Profile Section

Create `sean-guide.md` with the full heading structure from the data model, populate the Quick Profile section with Sean's physical attributes, climbing level, bike specs, and constraint summary. This section serves as a quick reference for anyone helping Sean pick problems or rides.

### Phase 2: Mountain Biking Section (P1)

Write the trail wishlist as a ranked table using research findings. Include:
- Top 6 ranked trails with all required fields (character, drainage, pairing, skill-dev notes)
- Climbing-area pairing matrix (what to ride when the group climbs where)
- Wet-weather fallback hierarchy
- Links to all referenced trail profiles

### Phase 3: Climbing Projects Section (P2)

Write per-area climbing pick tables for Tier 1 areas (Stone Fort, Rocktown, HP40) plus Hospital Boulders and Tier 2 honest assessments. Each entry includes:
- Problem name, grade, sub-area, walk time
- Category (send list / stretch goal / moonshot)
- Why it suits Sean (reach, power, good feet)
- Landing quality flag and body-constraint flags
- Links to area profiles and problem clusters

### Phase 4: Food & Drink Section (P3)

Write tiered food/drink lists using research findings:
- "Don't miss" tier: Hutton & Smith, Five Wits, Chattanooga Brewing Co. (breweries); Sugar's Ribs, Tremont Tavern, Edley's, Champy's (food); Mean Mug (coffee)
- "If nearby" tier: Chatt Smoke House, Urban Stack, Little Coyote, Nic & Norman's, Velo, Public House
- IPA crawl route map (walkable Southside)
- Tactical notes (hours, closures, Valentine's Day, half-price ribs timing)

### Phase 5: Sights & Experiences Section (P4)

Write categorized sights lists:
- Quick hits (free, under 1 hour): Sunset Rock, Walnut Street Bridge, The Passage, sculpture garden
- Worth the time (1–3 hours): Point Park, Bessie Smith Center (BHM!), Gate 11 Distillery
- Half-day experiences: Rock City, Ruby Falls, Raccoon Mountain wild cave, North Shore walk
- Gear shops: Suck Creek Cycle, Rock/Creek, The Gear Closet

### Phase 6: Priority Stack + Personal Logistics (P5)

Write the cross-category priority stack (top 10 ranked items) and personal logistics section:
- Priority stack as a numbered list with emoji category tags and checkbox format
- Bike transport notes, gear checklist, knee/body management notes

### Phase 7: Validation

Validate against all success criteria:
- SC-001 through SC-008 manual checks
- Verify all cross-reference links resolve
- Verify no content duplication
- Run constitution quality gates
- Update checklist

## Post-Phase 1 Constitution Re-Check

| Principle | Status |
|-----------|--------|
| I. Decision-Support First | **PASS** — Tables, ranked lists, 15–60 second targets maintained |
| II. Bouldering Scope Boundary | **PASS** — No rope climbing content |
| III. Ability-Aware, Hard-Climbing Priority | **PASS** — Personal V0–V3 guide references V10 area profiles |
| IV. Mountain Biking as First-Class | **PASS** — P1 section, detailed trail ranking |
| V. Source Accuracy & Recency | **PASS** — Research cites sources, [UNVERIFIED] flags applied |
