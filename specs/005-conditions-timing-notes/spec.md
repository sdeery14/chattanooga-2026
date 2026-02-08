# Feature Specification: Conditions, Timing & Reality Notes

**Feature Branch**: `005-conditions-timing-notes`
**Created**: 2026-02-08
**Status**: Draft
**Input**: User description: "Feature 005: Conditions, Timing & Reality Notes from the vision.md"

## User Scenarios & Testing

### User Story 1 — Know Today's Conditions Before Leaving Lodging (Priority: P1)

It's 7am at the Airbnb. The trip planner checks the conditions guide to understand what today's weather and temperature mean for climbing. They need to quickly answer: "Given today's forecast, which areas will climb well and which should we avoid?" The guide provides area-specific conditions logic — sun/shade timing, humidity thresholds, wind exposure, and seepage patterns — so the group can make a smart area choice before driving anywhere.

**Why this priority**: Conditions determine whether a day is great or wasted. Driving 45 minutes to Stone Fort only to find greasy slopers from overnight humidity is the single most frustrating trip mistake. This is the core "don't waste a day" use case.

**Independent Test**: Given a February morning weather scenario (e.g., "45°F, 70% humidity, overnight rain"), use the conditions guide to identify which areas will climb well and which to avoid — in under 60 seconds.

**Acceptance Scenarios**:

1. **Given** a February morning with known temperature and humidity, **When** the planner checks the conditions guide, **Then** they find area-specific guidance on which rock types and areas handle those conditions well (e.g., "sandstone slopers need <50% humidity; if humid, go to crimp-heavy areas or sheltered problems").
2. **Given** overnight rain, **When** the planner checks the guide, **Then** they find drying-time estimates by area and rock type (e.g., "Stone Fort: shaded boulders may seep for 12-24 hours after rain; sunny boulders dry in 2-4 hours").
3. **Given** a cold, dry February morning (ideal conditions), **When** the planner checks the guide, **Then** they find confirmation that this is peak friction season and which areas benefit most.

---

### User Story 2 — Avoid Crowds and Timing Mistakes (Priority: P2)

The group wants to plan around other climbers. They check the conditions guide for crowd patterns: which areas are packed on weekends, which are quieter, what time to arrive for parking, and whether February is a peak season. The guide also covers timing realities — sunrise/sunset, gate closure times, and how long approaches take in practice.

**Why this priority**: Crowd avoidance directly affects trip quality. Arriving at Stone Fort at 11am on a Saturday in February (peak season) means competing for problems and parking. Knowing to arrive early — or to pick a less popular area — is the kind of insight that only comes from experience or research.

**Independent Test**: Open the conditions guide and answer "It's Saturday — where can we go to avoid crowds?" with at least 2 area recommendations and timing advice, in under 60 seconds.

**Acceptance Scenarios**:

1. **Given** a Saturday in February, **When** the planner checks crowd patterns, **Then** they find which areas are likely to be busy (e.g., "Stone Fort is the most popular area in the Southeast — expect crowds on weekends, especially in peak season") and which are less crowded alternatives.
2. **Given** a weekday in February, **When** the planner checks, **Then** they find that crowds are significantly lower and most areas are uncrowded.
3. **Given** an area with gate or access restrictions, **When** the planner checks timing, **Then** they find gate hours, recommended arrival times, and sunset/daylight estimates for February.

---

### User Story 3 — Manage Skin and Multi-Day Sustainability (Priority: P3)

It's day 4 of a week-long trip. Fingertips are wrecked. The planner checks the conditions guide for skin management advice: which rock types are more abrasive, how to rotate areas to preserve skin, rest-day timing for skin recovery, and tips for maintaining sendable skin through a full week.

**Why this priority**: Skin is the limiting factor on multi-day bouldering trips, especially on sandstone. Without conscious management, climbers burn through their skin by day 3 and spend the rest of the week frustrated. This is "things you only learn by being there" — directly from the vision.

**Independent Test**: Open the conditions guide and find skin management advice that helps plan a 7-day trip rotation — which days to push, which to rest, and which rock types to favor when skin is thin.

**Acceptance Scenarios**:

1. **Given** a 7-day trip starting Saturday, **When** the planner checks skin management, **Then** they find general guidance on pacing climbing days vs. rest days for skin preservation (e.g., "don't climb 4 consecutive days on sandstone; plan rest or active-rest days every 2-3 climbing days").
2. **Given** that the group climbed aggressively on sandstone the previous two days, **When** they check the guide, **Then** they find suggestions for skin-friendly alternatives (smoother rock, crimp-heavy vs. sloper-heavy, indoor gym as backup).
3. **Given** that a climber's skin is thin, **When** they check the guide, **Then** they find area-specific notes on which areas/rock types are more or less abrasive.

---

### Edge Cases

- What if conditions change mid-day (morning fog burns off, afternoon rain rolls in)? The guide should note intra-day condition shifts common in the Chattanooga area in February.
- What if humidity is borderline (e.g., 55-65%)? The guide should provide nuanced guidance rather than a hard cutoff, since friction sensitivity varies by problem style.
- What if the group has never climbed on Southeastern sandstone before? The guide should include a "first-timers" note about how sandstone friction differs from granite or limestone.
- What if one area is in sun and another in shade on the same morning? The guide should note sun/shade timing differences between east-facing and west-facing areas.

## Requirements

### Functional Requirements

- **FR-001**: The feature MUST provide a conditions guide document with area-specific conditions information for all Tier 1 bouldering areas (Stone Fort, Rocktown, HP40) and Tier 2 areas where conditions differ meaningfully.
- **FR-002**: Each area's conditions entry MUST include: sun/shade patterns (morning vs. afternoon), humidity sensitivity (which grip styles are affected), wind exposure, seepage/drying behavior after rain, and best time-of-day to climb.
- **FR-003**: The feature MUST include a "Conditions Quick Reference" section or table for rapid scanning — mapping weather scenarios (cold/dry, humid, rainy, windy) to area recommendations.
- **FR-004**: The feature MUST include crowd and timing information: weekend vs. weekday patterns, February peak-season notes, recommended arrival times, and gate/access hours where applicable.
- **FR-005**: The feature MUST include skin management guidance: rock abrasiveness by area, pacing recommendations for a week-long trip, and area rotation strategies for skin preservation.
- **FR-006**: The feature MUST include February-specific seasonal notes: daylight hours, typical temperature ranges, precipitation patterns, and how these affect climbing conditions.
- **FR-007**: The feature MUST cross-reference existing area profiles (Feature 001) and problem clusters (Feature 002) by link rather than duplicating their content. The conditions guide adds cross-cutting wisdom that sits above individual area profiles.
- **FR-008**: Each claim about conditions MUST cite a verifiable source (guidebook, community forum, weather data, or personal research) or be flagged with [UNVERIFIED] per the project's established convention.
- **FR-009**: The feature MUST NOT duplicate per-area conditions information already in area profiles (Feature 001). It synthesizes and compares conditions across areas to support area-selection decisions.
- **FR-010**: The feature SHOULD include a "Southeastern Sandstone Primer" section for climbers unfamiliar with the rock type — how friction, humidity, and temperature interact differently than on granite or limestone.

### Key Entities

- **Conditions Quick Reference**: A summary table mapping weather scenarios to area recommendations for rapid decision-making.
- **Area Conditions Profile**: Cross-cutting conditions information for each major climbing area — synthesized from research, not duplicated from area profiles.
- **Skin Management Guide**: Pacing and rotation advice for multi-day sandstone bouldering trips.
- **Timing & Crowds Profile**: Crowd patterns, gate hours, sunrise/sunset, and arrival timing for each area.

## Success Criteria

### Measurable Outcomes

- **SC-001**: A reader can answer "Given today's weather, which area should we go to?" with a specific recommendation in under 60 seconds using the conditions quick reference.
- **SC-002**: At least 3 weather scenarios (cold/dry, humid, post-rain) are mapped to specific area recommendations with reasoning.
- **SC-003**: Crowd and timing information is documented for all Tier 1 areas, including weekend vs. weekday patterns and recommended arrival times.
- **SC-004**: Skin management guidance covers a 7-day trip rotation with at least 2 actionable strategies for preserving skin.
- **SC-005**: All cross-references to Features 001 and 002 resolve to existing documents with working links.
- **SC-006**: Every conditions claim cites a source or is flagged [UNVERIFIED].
- **SC-007**: The guide passes the project's 5 content quality gates (skimmability, decision-orientation, scope, ability coverage adapted for conditions, source citation).

## Assumptions

- Lodging is near Enterprise South Nature Park (ESNP) in NE Chattanooga. Drive times reference this location.
- Trip dates are February 14-21, 2026. All seasonal information targets this specific window.
- "Conditions" refers to climbing conditions (friction, humidity, temperature, seepage, wind) — not trail conditions (which are covered in Feature 003).
- Area profiles (Feature 001) already contain per-area conditions sections. This feature adds cross-area comparison and synthesis — the "meta" conditions wisdom.
- Problem clusters (Feature 002) already flag conditions-dependent problems. This feature provides the context for interpreting those flags.
- The guide is primarily for outdoor bouldering conditions. Indoor gym conditions (Synergy, High Point) are not in scope.
- Skin management advice is general guidance, not medical advice. Individual variation is significant.
- Crowd information is based on research and community reports, not real-time data. February 2026 patterns may differ from historical norms.

## Dependencies

- **Feature 001** (Primary Bouldering Areas): Required — conditions guide references area profiles for detailed per-area information.
- **Feature 002** (Problem Clusters): Required — conditions guide references cluster documents for conditions-sensitive problem flags.
- **Feature 003** (Parallel Activity Mapping): Not required, but trail conditions may be briefly mentioned for active-rest alternatives on bad climbing-conditions days.
- **Feature 004** (Rest Day Pack): Not required, but the conditions guide may reference rest-day options when conditions make climbing inadvisable.
