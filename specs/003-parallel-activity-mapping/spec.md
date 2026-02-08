# Feature Specification: Parallel Activity Mapping (Mountain Biking + Climbing)

**Feature Branch**: `003-parallel-activity-mapping`
**Created**: 2026-02-08
**Status**: Draft
**Input**: User description: "Feature 003: Parallel Activity Mapping (Mountain Biking + Climbing) from vision.md"

## User Scenarios & Testing

### User Story 1 — Find Where to Ride Near Today's Climbing Area (Priority: P1)

The group is heading to a climbing area (e.g., Stone Fort, Rocktown, HP40). The mountain biker needs to quickly answer: "Where can I ride while the group climbs?" The answer must include trail options within a reasonable drive of the climbing area, with enough detail to make a go/no-go decision — difficulty, distance, drive time from both lodging and the climbing area, and any conditions concerns.

**Why this priority**: This is the core parallel-activity question. On most trip days, the group will be climbing. The biker needs nearby riding options that pair with the climbing plan without requiring a separate long drive or complex logistics.

**Independent Test**: Open any Tier 1 climbing area's trail pairing information and answer "Where can I ride while they climb here?" with at least 1 specific trail system, its difficulty range, ride length, and drive time — in under 60 seconds.

**Acceptance Scenarios**:

1. **Given** the group is going to Stone Fort, **When** the biker opens the trail pairing information, **Then** they see at least 1 trail system within 30 min drive of Stone Fort with difficulty, distance, estimated ride time, and trailhead logistics.
2. **Given** the group is going to HP40 (~2 hrs from lodging), **When** the biker checks trail options, **Then** they see trail systems near HP40 (not just near lodging) so the biker doesn't have to drive separately.
3. **Given** a climbing area has no nearby trail systems, **When** the biker checks trail options, **Then** the document honestly states there are no nearby rides and suggests the closest alternative.

---

### User Story 2 — Plan a Dedicated Biking Day (Priority: P2)

It's a rest day, a rain day, or the biker simply wants a full day of riding. They need to find the best trail systems near lodging for a satisfying standalone ride — not constrained by proximity to any climbing area.

**Why this priority**: Rest days and weather days are guaranteed to happen during a week-long trip. Having pre-vetted full-day riding options eliminates the scramble of searching on phones mid-trip.

**Independent Test**: Open the trail overview and answer "What are the best full-day rides near the Airbnb?" with at least 2 options including difficulty, total ride time, and logistics.

**Acceptance Scenarios**:

1. **Given** a rest day with no climbing planned, **When** the biker looks for rides near lodging, **Then** they see at least 2 trail systems within 30 min of Enterprise South Nature Park with enough detail for a full-day session (difficulty range, total mileage, estimated ride time).
2. **Given** rain has made conditions poor for climbing, **When** the biker checks trail options, **Then** conditions notes indicate which trails drain well or are rideable in wet conditions.

---

### User Story 3 — Understand Trail Conditions and Logistics Before Riding (Priority: P3)

Before committing to a ride, the biker needs to know: Is the trail open in February? Is there a fee? Where do I park? Are conditions likely to be good? This avoids showing up to a closed or unrideable trail.

**Why this priority**: Conditions and access information prevents wasted time. February in the Southeast can mean wet trails, seasonal closures, or unexpected fees — knowing this before driving saves the day.

**Independent Test**: For any documented trail system, verify that access status (open/closed in February), fees, parking, and conditions notes are present and sourced.

**Acceptance Scenarios**:

1. **Given** a trail system is documented, **When** the biker checks logistics, **Then** they find: parking location, fees (if any), February access status, and trail conditions notes.
2. **Given** a trail has seasonal or weather-dependent closures, **When** the biker reads the document, **Then** the closure risk is flagged with source and date context.
3. **Given** trail information could not be verified, **When** the biker reads the entry, **Then** unverified claims are clearly flagged as [UNVERIFIED].

---

### Edge Cases

- What happens when a climbing area has no mountain biking within 30 minutes? State this honestly and suggest the closest option with drive time, or suggest an alternative activity.
- What happens when February trail conditions are poor across all options? Include at least one "rideable in mud" or gravel/paved alternative if known.
- What if a trail system is excellent but requires a long solo drive away from the climbing group? Note the drive time tradeoff explicitly — the biker can make an informed choice.
- What if trail information is sparse or unverifiable from web sources? Use [UNVERIFIED] flags per established convention. Include the trail but flag data gaps rather than omitting it.
- What happens when a trail system is near multiple climbing areas? Document it once and cross-reference from each relevant climbing area pairing.

## Requirements

### Functional Requirements

- **FR-001**: The feature MUST document mountain biking trail systems within the Chattanooga trip radius (~2 hours from Enterprise South Nature Park area, or within ~30 min of any documented climbing area).
- **FR-002**: Each trail system MUST include: trail system name, location, drive time from lodging (Enterprise South Nature Park area), difficulty range (using standard trail ratings), approximate total rideable distance, and estimated ride time for a representative loop or route.
- **FR-003**: Each trail system MUST include access logistics: parking location, fees, and February access/closure status.
- **FR-004**: Each trail system MUST cite at least one verifiable source (trail database, park website, or MTB community resource).
- **FR-005**: The feature MUST map trail systems to nearby climbing areas, showing which rides pair with which climbing days. Drive time between the trail system and each nearby climbing area MUST be included.
- **FR-006**: The feature MUST identify at least 2 trail systems suitable for a full-day dedicated biking session from lodging (rest-day or rain-day options).
- **FR-007**: Trail conditions notes SHOULD include: drainage/mud tolerance, February-specific concerns (seasonal closures, cold weather considerations), and shade/sun exposure where known.
- **FR-008**: Unverified trail information MUST be flagged with [UNVERIFIED] per the project's established convention.
- **FR-009**: The feature MUST NOT duplicate climbing content already in area profiles or problem clusters. Trail documents reference climbing areas by link, not by re-describing them.
- **FR-010**: The feature MUST honestly communicate when trail data is thin or when a climbing area has no nearby riding options, rather than padding with low-quality suggestions.
- **FR-011**: Trail difficulty SHOULD use standard IMBA-style ratings (green circle, blue square, black diamond) or the local trail system's own rating where it differs. Rating system MUST be noted.
- **FR-012**: Each trail system entry SHOULD note ride style/character (flow trail, technical singletrack, gravel, cross-country, downhill) to help the rider choose based on energy and mood.

### Key Entities

- **Trail System**: A named mountain biking destination with one or more rideable trails. Key attributes: name, location, difficulty range, total distance, ride time, style/character, conditions notes, access logistics, source citations.
- **Climbing Area Pairing**: A relationship between a trail system and one or more climbing areas, defined by drive time between them and suitability for parallel-activity days.
- **Trail Overview**: A summary document listing all trail systems with quick-reference comparison, analogous to the `areas/README.md` comparison table for climbing.

## Success Criteria

### Measurable Outcomes

- **SC-001**: For each Tier 1 climbing area (Stone Fort, Rocktown, HP40), the biker can identify at least 1 nearby trail system and its key details in under 60 seconds.
- **SC-002**: At least 2 trail systems suitable for full-day standalone rides from lodging are documented with complete logistics.
- **SC-003**: Every documented trail system includes all mandatory fields (name, location, drive time, difficulty, distance, ride time, access logistics, source).
- **SC-004**: Trail-to-climbing-area pairings cover all 7 areas with problem clusters (or honestly note when no nearby trails exist).
- **SC-005**: All trail entries pass the project's 5 content quality gates (skimmability, decision-orientation, scope, ability coverage adapted for biking, source citation).
- **SC-006**: A reader can answer "Where should I ride today?" from the trail overview in under 60 seconds, analogous to the climbing README comparison table.

## Assumptions

- One mountain bike will be available during the trip (brought by the V0 climber).
- The rider is capable across all trail difficulty levels — research should cover the full range but does not need to prioritize any particular difficulty.
- "Nearby" for climbing-area pairing means within ~30 minutes drive of the climbing trailhead. Longer drives may be documented but flagged as requiring separate logistics.
- February trail conditions in the Chattanooga area are generally rideable but may be affected by rain and mud. This assumption needs verification during research.
- Trail data will come from online sources (Trailforks, MTB Project, Singletracks, AllTrails, park websites). Guidebook data is not expected to be a primary source for biking.
- Enterprise South Nature Park (the lodging location) is itself likely a significant trail system and should be documented as a "zero-drive" option.
- The scope is limited to mountain biking — road cycling, gravel grinding, and bike park/lift-served options are out of scope unless a trail system naturally includes gravel segments.
- This feature does not create rest-day itineraries (that's Feature 004). It provides the trail data that Feature 004 can reference.

## Dependencies

- **Feature 001** (Primary Bouldering Areas): Required — trail pairings reference area profiles by link.
- **Feature 002** (Problem Clusters): Not required, but trail pairings may reference cluster documents for "what's nearby for the climbers" context.
- **Feature 004** (Rest Day & Low-Energy Decision Pack): Feature 003 provides input to Feature 004, not the reverse. Feature 003 can be completed independently.
