# Feature Specification: Area-Scoped Problem Clusters (V0–V3 / V4–V6 / V7–V10)

**Feature Branch**: `002-problem-clusters`
**Created**: 2026-02-08
**Status**: Draft
**Input**: User description: "Area-Scoped Problem Clusters (V0-V3 / V4-V6 / V7-V10)"

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Find What to Climb at Today's Area (Priority: P1)

The group has arrived at an area (chosen using Feature 001's profiles). A V10 climber wants to know "What should I try here?" without scrolling Mountain Project or flipping through a guidebook in the parking lot. They open the area's problem cluster and immediately see a curated shortlist of V7–V10 problems grouped by proximity, with style notes and any conditions flags.

**Why this priority**: This is the direct answer to "What can I climb here?" — the second of the three core trip questions (vision.md). Feature 001 answers "Where should we go?"; this feature answers the follow-up once you're there. The V7–V10 cluster is the primary trip focus per Principle III.

**Independent Test**: Open any area's problem cluster and answer "What are the 5–15 best hard problems here?" with names, grades, and enough context to walk to them — without consulting any external source.

**Acceptance Scenarios**:

1. **Given** the group is at Stone Fort, **When** a V10 climber opens the problem cluster, **Then** they see a curated list of V7–V10 problems with names, grades, and proximity groupings within 60 seconds.
2. **Given** a humid afternoon at Rocktown, **When** a climber checks the problem cluster, **Then** problems flagged as "good if conditions suck" (shade, overhung, sheltered) are identifiable without re-reading the full area profile.
3. **Given** any Tier 1 area, **When** a reader scans the V7–V10 cluster, **Then** each problem includes at minimum: name, grade, and location hint (which boulder or sub-area).

---

### User Story 2 - Find Moderate and Easy Climbing Nearby (Priority: P2)

A V5 climber or V0 climber is at the same area as the group. They want to know what's nearby — ideally within walking distance of the hard-climbing zone — so they can climb independently without feeling like a burden. They open the problem cluster and see V4–V6 and V0–V3 sections with curated suggestions and proximity notes relative to the main bouldering.

**Why this priority**: This directly serves group cohesion (Principle III, ability-aware). The V0 and V5 climbers need their own "what can I climb here?" answer. This story is secondary only because the trip's primary focus is hard climbing — but it's critical for morale and independence.

**Independent Test**: Open any area's problem cluster and answer "What can a V5 climber do within a short walk of where the V10 climber is working?" with at least 3 specific suggestions.

**Acceptance Scenarios**:

1. **Given** a V5 climber at HP40, **When** they check the V4–V6 cluster, **Then** they see curated moderate problems with proximity notes relative to the main hard-climbing zones.
2. **Given** a V0 climber at an area with limited easy climbing, **When** they check the V0–V3 cluster, **Then** the cluster honestly states the limitations and suggests alternatives (spotting, hiking, exploring nearby boulders for easy traverses).
3. **Given** any area, **When** a moderate climber reads the V4–V6 section, **Then** body-type notes are included where relevant (reachy, compression-heavy, short-friendly).

---

### User Story 3 - Adapt the Session to Current Conditions (Priority: P3)

Conditions change mid-session — sun hits the wall, humidity spikes, or skin is wrecked from sandstone. A climber wants to know which problems at this area are still viable without abandoning the location entirely. They scan the problem cluster for conditions-tagged problems.

**Why this priority**: Conditions adaptation is a frequent real-world need but it's an enhancement layer on top of US1 and US2. The core lists are useful even without conditions flags; the flags make them better.

**Independent Test**: At any Tier 1 area, identify at least 3 problems that remain viable when conditions deteriorate (shaded, overhung, sheltered, less friction-dependent) using only the problem cluster.

**Acceptance Scenarios**:

1. **Given** afternoon sun hitting the main wall at Stone Fort, **When** a climber checks the problem cluster, **Then** shaded or sheltered alternatives are identifiable.
2. **Given** high humidity at any area, **When** a climber scans for conditions flags, **Then** overhung or less friction-dependent problems are marked.
3. **Given** wrecked skin after two days on sandstone, **When** a climber looks for gentler options, **Then** the cluster notes problems with smoother holds or less abrasive rock where known.

---

### Edge Cases

- What happens when an area has very few problems at a grade band (e.g., V7–V10 at Walden's Ridge)? The cluster section MUST still exist but honestly state the limitation rather than padding with marginal suggestions. A note like "See [other area] for deeper options at this grade" is acceptable.
- What if problem names or grades differ between guidebooks and Mountain Project? Use the most recent guidebook as primary, note discrepancies where significant (e.g., "V8 in guidebook, V7 on MP"), and flag the source.
- What if a problem's conditions data is unknown? Omit the conditions flag rather than guessing. Only tag problems with conditions notes when the information is sourced or well-known.
- What if a classic problem is closed, damaged, or has broken holds? Note it with a flag (e.g., "[BROKEN HOLD reported 2024]") so climbers don't plan around a problem that's changed.
- What about problems above V10? Problems up to V12 MAY be included in the V7–V10 cluster if they're area classics, but the cluster is not obligated to extend beyond the trip's stated ability range.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: Each Tier 1 area profile MUST have a companion problem cluster document containing curated problem lists organized by ability band (V0–V3, V4–V6, V7–V10).
- **FR-002**: Each Tier 2 area SHOULD have a problem cluster document where sufficient data exists. If data is too thin for a meaningful cluster, the area profile's existing grade density section is sufficient.
- **FR-003**: Tier 3 areas (brief profiles) MUST NOT have problem cluster documents — they are not bouldering destinations for this trip.
- **FR-004**: Each ability band section within a problem cluster MUST contain a curated list of 5–15 problems (where the area supports it), not an exhaustive dump.
- **FR-005**: Each listed problem MUST include at minimum: problem name, V-grade, and location hint (boulder name or sub-area).
- **FR-006**: Problems SHOULD include style notes where known (e.g., "compression start to sloper topout", "technical slab", "big moves on crimps").
- **FR-007**: Problems SHOULD include body-type notes where relevant (e.g., "reachy crux at 6'0\"+", "short-friendly beta exists", "compression favors wingspan").
- **FR-008**: Problems SHOULD be tagged with conditions flags where known: "shaded", "overhung/sheltered", "seepage-prone", "afternoon sun", "friction-dependent".
- **FR-009**: Problem clusters MUST NOT become exhaustive tick lists or Mountain Project mirrors. The goal is curated quality, not completeness.
- **FR-010**: Each problem cluster MUST include a brief header noting the area's overall character for that grade band (1–2 sentences), consistent with the area profile's density descriptors from Feature 001.
- **FR-011**: Problem clusters MUST link back to their parent area profile for full area context (conditions, logistics, access).
- **FR-012**: Problems MUST be grouped by proximity within each grade band — problems on the same boulder or in the same sub-area should be listed together, not alphabetically.
- **FR-013**: Each problem listing MUST cite its source (guidebook page/edition, Mountain Project, or local knowledge) or be flagged [UNVERIFIED].
- **FR-014**: Problem clusters MUST be stored as separate documents from the area profiles, linked from the area profile, to keep profiles scannable per Feature 001's design.

### Key Entities

- **Problem Cluster**: A curated, area-scoped document containing recommended problems organized by ability band. One per area (where data supports it). Linked from the parent area profile.
- **Problem Entry**: A single recommended problem within a cluster. Attributes: name, V-grade, boulder/sub-area location, style notes (optional), body-type notes (optional), conditions flags (optional), source citation.
- **Proximity Group**: A grouping of problems within a grade band that are physically close together (same boulder, same trail section, same sub-area). Enables "I'm standing here, what else is nearby?" decisions.

## Assumptions

- Problem data will be sourced primarily from guidebooks (Stone Fort Bouldering 3rd Ed., HP40 guidebook, Rocktown guidebook, ChattBloc 2nd Ed.), Mountain Project, KAYA, and theCrag. Web research will supplement where needed.
- "Curated" means editorially selected for quality, accessibility, and relevance to the group — not every listed problem on a database. Selection criteria: classic status, quality stars, accessibility from main trail, and relevance to the group's ability range.
- Proximity groupings will use sub-area names from guidebooks where available (e.g., Stone Fort's "East Side", HP40's "Main Area"). Where formal sub-areas don't exist, informal location descriptions will be used.
- Body-type and conditions notes will only be included when sourced or widely known — no speculation.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A climber arriving at any Tier 1 area can identify 5+ problems in their grade band within 60 seconds of opening the problem cluster.
- **SC-002**: Every problem listed in a cluster includes name, V-grade, and location hint — no anonymous or unlocatable entries.
- **SC-003**: A V0 climber reading any problem cluster can determine within 30 seconds whether the area has meaningful easy climbing, consistent with the area profile's density assessment.
- **SC-004**: At least 50% of problems in Tier 1 area clusters include a style note or body-type note beyond just name and grade.
- **SC-005**: Problem clusters for Tier 1 areas each contain problems from all three ability bands (V0–V3, V4–V6, V7–V10), with honest density framing per band.
- **SC-006**: No problem cluster exceeds 40 problems total across all bands — curation over completeness.
