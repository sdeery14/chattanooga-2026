# Feature Specification: Primary Bouldering Areas (Hard-First, Group-Aware)

**Feature Branch**: `001-primary-bouldering-areas`
**Created**: 2026-02-08
**Status**: Draft
**Input**: User description: "Primary Bouldering Areas (Hard-First, Group-Aware)"

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Pick Today's Area in Under 2 Minutes (Priority: P1)

A trip participant opens the repo at breakfast (or at the crag parking lot) and needs to decide which bouldering area to visit today. They scan the area profiles, compare tradeoffs (hard-climbing density, conditions sensitivity, drive time), and confidently choose a destination without pulling out phones or guidebooks.

**Why this priority**: This is the core purpose of the entire repository. If area selection is fast and informed, the trip succeeds. Everything else is additive.

**Independent Test**: Can be fully tested by reading the area profiles and answering "Where should we go today?" for at least three different scenarios (perfect weather, humid/warm day, short-session afternoon) without consulting external sources.

**Acceptance Scenarios**:

1. **Given** a morning with cool, dry conditions, **When** a V10 climber scans the area profiles, **Then** they can identify which area has the highest concentration of quality hard bouldering and why within 2 minutes.
2. **Given** a warm, humid afternoon, **When** the group checks the area profiles, **Then** they can identify which area handles poor conditions best (shade, elevation, wind exposure) within 2 minutes.
3. **Given** a day where the group wants a shorter session, **When** they check drive times and approach lengths, **Then** they can pick the area with the lowest total friction.

---

### User Story 2 - Understand Group Tradeoffs Per Area (Priority: P2)

A V5 or V0 climber wants to know whether a given area will have anything for them, or whether they should plan to spot, hike, or bring a book. They check the area profile and immediately see an honest summary of moderate and easy climbing density — not inflated to seem balanced, but clear enough to set expectations.

**Why this priority**: Group morale depends on honest expectation-setting. If lower-grade climbers feel informed rather than surprised, friction stays low even on hard-climbing-focused days.

**Independent Test**: Can be tested by reading any single area profile and answering "Will I have things to climb at V0–V3?" and "Will I have things to climb at V4–V6?" with a yes/no/limited answer and supporting context.

**Acceptance Scenarios**:

1. **Given** a V0 climber reading an area profile, **When** the area has very few easy problems, **Then** the profile states this honestly and suggests what else they could do (spot, hike, explore).
2. **Given** a V5 climber reading an area profile, **When** the area has moderate climbing scattered across sub-areas, **Then** the profile notes the density and proximity of V4–V6 problems relative to the hard-climbing zones.
3. **Given** any area profile, **When** a reader checks the ability breakdown, **Then** the framing does not enforce artificial parity — it reflects the area's actual strengths.

---

### User Story 3 - Compare Areas Side-by-Side (Priority: P3)

The group is debating between two areas. They want a quick way to compare key dimensions — hard-climbing quality, moderate density, conditions sensitivity, drive time, and vibe — without re-reading full profiles.

**Why this priority**: Comparison is a frequent decision pattern, but it's only useful once the individual profiles exist. A summary comparison layer adds speed but is not strictly required.

**Independent Test**: Can be tested by selecting any two areas and answering "Which is better for X?" across at least three dimensions using only the comparison reference.

**Acceptance Scenarios**:

1. **Given** the group is choosing between two areas, **When** they consult the comparison reference, **Then** they can see key dimensions side by side without flipping between separate profiles.
2. **Given** the comparison reference, **When** a reader looks at any dimension, **Then** the information is consistent with the detailed area profiles.

---

### Edge Cases

- What happens when an area has essentially zero easy climbing? The profile MUST still be included if it has high-quality hard bouldering, with an honest note about limited lower-grade options.
- What happens when conditions information is uncertain or seasonal? The profile MUST flag uncertainty and note the source/date of the conditions data.
- What if a well-known area exists but has very little hard climbing (e.g., primarily V0–V4)? The area MAY be omitted from this feature if it does not serve the primary V7–V10 focus, or included briefly as a "moderate-only" area if the group is likely to visit it.
- What if an area has access restrictions, seasonal closures, or permit requirements? The profile MUST note these prominently so the group doesn't drive there and get turned away.

## Clarifications

### Session 2026-02-08

- Q: Should area profiles follow a uniform structure or free-form prose? → A: Structured template — each profile follows a fixed section order (overview, hard appeal, grade density, conditions, logistics, access, style, sources) with brief bullet points.
- Q: Which band does V7 belong to? → A: Hard band. Ability bands are V0–V3 (easy), V4–V6 (moderate), V7–V10 (hard).
- Q: What is the drive-time reference point for logistics? → A: Enterprise South Nature Park area (near Airbnb lodging, 2/14–2/21/2026).

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: Each area profile MUST include an overview paragraph explaining what makes the area notable for bouldering and who it best serves.
- **FR-002**: Each area profile MUST identify the primary appeal for V7–V10 climbers (concentration of hard problems, classic lines, style of climbing).
- **FR-003**: Each area profile MUST include an honest assessment of moderate (V4–V6) and easy (V0–V3) climbing density, using terms like "abundant," "scattered," "limited," or "nearly nonexistent."
- **FR-004**: Each area profile MUST note conditions sensitivity: shade/sun exposure, humidity tolerance, elevation, wind, and best seasons or times of day.
- **FR-005**: Each area profile MUST include logistics basics: approximate drive time from the Enterprise South Nature Park area (lodging reference point), parking situation, and approach length to primary bouldering.
- **FR-006**: Each area profile MUST note access considerations: land ownership, permit requirements, seasonal closures, or etiquette expectations.
- **FR-007**: Each area profile SHOULD include style and body-type notes where known (e.g., reachy, compression-heavy, slab-dominant, technical).
- **FR-008**: Each area profile MUST cite primary sources (guidebook edition, online database, or local knowledge) and flag any unverified claims.
- **FR-009**: A comparison reference SHOULD exist that summarizes all profiled areas across key dimensions in a scannable format.
- **FR-011**: Each area profile MUST follow a structured template with a fixed section order: Overview, Hard Appeal (V7–V10), Grade Density (V0–V3 / V4–V6), Conditions, Logistics, Access, Style & Body-Type Notes, Sources. Each section uses brief bullet points rather than long prose.
- **FR-010**: The feature MUST survey all known bouldering areas within reasonable driving distance (~2 hours) of the Enterprise South Nature Park area, including but not limited to: Stone Fort (LRC), Rocktown, HP40 (Horse Pens 40), Little Rock City (Montague), and Sunset Park. Additional areas (e.g., Dayton Pocket, Pendergrass, Zahnd Tract, Denny Cove) MUST be included if they offer bouldering. This is a comprehensive lay-of-the-land survey — each area receives a profile, but depth is kept consistent and concise rather than exhaustive.

### Key Entities

- **Bouldering Area**: A distinct geographic zone with its own access, approach, and character. Key attributes: name, location relative to Chattanooga, primary grade range appeal, conditions profile, logistics summary, source citations.
- **Ability Band**: A grade grouping used to frame climbing density per area: V0–V3 (easy), V4–V6 (moderate), V7–V10 (hard). These are not rigid cutoffs but communication shorthand.
- **Comparison Reference**: A scannable summary that presents all areas along shared dimensions for rapid side-by-side decisions.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A trip participant can identify the best area for a given day's conditions and goals within 2 minutes of opening the repo.
- **SC-002**: Every profiled area includes all mandatory fields (FR-001 through FR-008) with no blank or placeholder sections.
- **SC-003**: A V0 climber reading any area profile can determine within 30 seconds whether the area has easy climbing for them, and if not, what alternatives exist.
- **SC-004**: 100% of conditions and access claims are either sourced or explicitly flagged as unverified.
- **SC-005**: The comparison reference (if included) is consistent with the detailed profiles — no contradictions in grade density, conditions, or logistics data.
