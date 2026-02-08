# Feature Specification: Logistics & Access Cheat Sheets

**Feature Branch**: `006-logistics-access-cheat-sheets`
**Created**: 2026-02-08
**Status**: Draft
**Input**: User description: "Feature 006: Logistics & Access Cheat Sheets from the vision.md doc"

## User Scenarios & Testing

### User Story 1 — Drive-Time Comparison & Daily Departure Planning (Priority: P1) 🎯 MVP

The group is at the ESNP lodging deciding which area to visit. They need to quickly see how far each climbing area is, what time they need to leave, and whether the drive is worth it for today's plan. A single drive-time comparison table lets them weigh distance against conditions, crowds, and skin state without opening multiple area profiles.

**Why this priority**: Drive-time is the most frequently referenced logistics data point — it affects every single day of the trip. Knowing "HP40 is 2 hours away in a different time zone" vs. "Walden's Ridge is 30 minutes" shapes the daily plan before anything else.

**Independent Test**: Open the logistics guide and answer "How long does it take to drive from our lodging to each climbing area?" for all Tier 1 and Tier 2 areas in under 15 seconds.

**Acceptance Scenarios**:

1. **Given** the group is at ESNP lodging, **When** they open the logistics guide, **Then** they see a single drive-time comparison table listing every climbing area with estimated drive time, distance, and route notes from ESNP.
2. **Given** a user wants to visit HP40, **When** they check the drive-time table, **Then** they see the drive time in both Eastern and Central time with the time-zone crossing noted.
3. **Given** the group is planning a morning start, **When** they check the logistics guide, **Then** they can calculate departure time by subtracting drive time from the area's gate opening or desired arrival time.

---

### User Story 2 — Access Requirements & "Don't Screw This Up" Warnings (Priority: P2)

The group is heading to a climbing area and needs to know the access requirements before arriving: fees, gate hours, registration requirements, gate codes, check-in procedures, and critical rules that, if missed, would ruin the session (e.g., getting locked in at Dayton Pocket, needing a gate code for Hospital Boulders, paying at the clubhouse before climbing Stone Fort).

**Why this priority**: Access mistakes are the most costly logistics failures — arriving without a gate code, missing gate hours, or not registering online can waste an entire day. These are "don't screw this up" items that need to be in one consolidated place.

**Independent Test**: Open the logistics guide and identify all access requirements for any area (fee, gate hours, registration, rules) in under 30 seconds.

**Acceptance Scenarios**:

1. **Given** the group is heading to Dayton Pocket, **When** they check the logistics guide, **Then** they see gate hours (8 AM – 7 PM), the lock-in warning, and the online registration requirement with a link to the TN State Parks system.
2. **Given** the group wants to visit Hospital Boulders, **When** they check the logistics guide, **Then** they see the gate code requirement, how to request it from SCC, and the dawn-to-dusk access window.
3. **Given** a user is visiting Stone Fort on a weekend, **When** they check the logistics guide, **Then** they see the weekend fee ($12), the clubhouse check-in requirement, and parking location.

---

### User Story 3 — Parking & Approach Information (Priority: P3)

A group member is navigating to a climbing area for the first time. They need parking location details, approach trail information (distance, time, terrain), and pad-carry notes so they don't waste time circling for parking or hiking the wrong trail.

**Why this priority**: Parking confusion and approach uncertainty are common first-visit frustrations. Having this info consolidated saves 10-20 minutes of fumbling on arrival, but the impact is lower than drive-time and access requirements since most areas have straightforward access.

**Independent Test**: Open the logistics guide and find parking and approach info for any area in under 30 seconds — including where to park and how long the approach takes.

**Acceptance Scenarios**:

1. **Given** the group is driving to Rocktown for the first time, **When** they check the logistics guide, **Then** they see the parking area description, approach trail distance (15-20 minutes), and pad-carry notes.
2. **Given** the group has multiple pads, **When** they check the logistics guide, **Then** they see notes about which areas have short vs. long approaches that affect pad logistics.
3. **Given** a user is visiting Stone Fort, **When** they check the logistics guide, **Then** they see the Montlake Golf Course clubhouse parking location and the check-in-before-climbing requirement.

---

### Edge Cases

- **Area temporarily closed or access changed**: The guide notes that access information is based on research as of early 2026 and provides contact info or verification links so users can confirm before the trip.
- **Multi-area day logistics**: When visiting two areas in one day (e.g., HP40 + Hospital Boulders), the guide surfaces logical pairings with combined drive-time estimates.
- **Winter road conditions**: Mountain roads (Pigeon Mountain to Rocktown, Chandler Mountain to HP40) can be affected by ice or flooding in February. The guide notes known road-condition concerns for mountain access routes.
- **Group splitting for different activities**: When the group splits (some climb, some bike), the guide references the trails guide for trailhead locations near climbing areas.

## Requirements

### Functional Requirements

- **FR-001**: The guide MUST include a drive-time comparison table from ESNP lodging to every Tier 1 and Tier 2 climbing area, listing estimated drive time, approximate distance, and route highlights or warnings.
- **FR-002**: The guide MUST include a per-area access cheat sheet for every Tier 1 and Tier 2 area covering: fees, gate hours, registration/check-in requirements, and critical access rules.
- **FR-003**: The guide MUST include parking location descriptions and approach trail details (distance, estimated time, terrain/pad-carry notes) for every Tier 1 and Tier 2 area.
- **FR-004**: The guide MUST flag time-zone crossings (Eastern to Central) for areas in Alabama (HP40, Hospital Boulders) with gate hours shown in both time zones.
- **FR-005**: The guide MUST include a consolidated "Don't Screw This Up" section highlighting the most critical access pitfalls across all areas.
- **FR-006**: The guide MUST cross-reference existing area profiles (Feature 001) and conditions guide (Feature 005) without duplicating their content — link, don't repeat.
- **FR-007**: The guide MUST include contact information or verification links for each area so users can confirm access details before the trip.
- **FR-008**: Every logistics claim MUST cite a source or be flagged [UNVERIFIED] per the project constitution (Principle V).
- **FR-009**: The guide MUST include multi-area day pairings with combined logistics for same-day visits (at least 3 pairings).
- **FR-010**: The guide SHOULD note road condition concerns for mountain access roads in February (ice, flooding, unpaved sections).

### Key Entities

- **Drive-Time Comparison Table**: One-page matrix of all areas with distance, drive time, and route notes from ESNP.
- **Area Access Cheat Sheet**: Per-area structured entry with fees, gate hours, registration, parking, approach, and critical rules.
- **Don't Screw This Up Checklist**: Consolidated list of the highest-stakes access pitfalls across all areas.
- **Multi-Area Day Pairings**: Logical area combinations with combined logistics for same-day visits.

## Success Criteria

### Measurable Outcomes

- **SC-001**: A reader can determine drive time from ESNP to any area in under 15 seconds using the comparison table.
- **SC-002**: A reader can identify all access requirements (fee, gate hours, registration) for any area in under 30 seconds.
- **SC-003**: The "Don't Screw This Up" section contains at least 5 critical access warnings covering all Tier 1 areas and gated Tier 2 areas.
- **SC-004**: All areas with gate hours or fees include contact info or a verification link.
- **SC-005**: All cross-reference links to area profiles, conditions guide, and trails guide resolve to existing files.
- **SC-006**: Every logistics claim cites a source or is flagged [UNVERIFIED].
- **SC-007**: Multi-area day pairings include at least 3 logical combinations with drive-time totals.

## Assumptions

- **Lodging location**: Enterprise South Nature Park (ESNP) area, as established in the trip planning baseline. All drive times are measured from ESNP.
- **Vehicle access**: The group has a car and all areas are accessed by driving. No public transit or ride-share assumptions.
- **February 2026 trip window**: Access hours and fees are researched for the Feb 14-21, 2026 trip window. Seasonal variations are noted where known.
- **Scope boundary**: This guide covers logistics for getting to and accessing climbing areas only. Trail logistics for mountain biking are covered in Feature 003 (trails/). Rest-day logistics are covered in Feature 004 (rest-days/).
- **Single document**: All logistics content goes into one file (`logistics/README.md`), consistent with the single-file pattern used by Features 004 and 005.

## Scope Boundary

### In Scope

- Drive times and distances from ESNP to all climbing areas
- Fees, gate hours, and access requirements for all areas
- Parking locations and approach trail details
- Critical access warnings ("don't screw this up" items)
- Multi-area day pairings with logistics
- Road condition notes for February
- Contact info and verification links

### Out of Scope

- Per-area climbing conditions (Feature 005 conditions guide)
- Per-area crowd patterns and timing strategy (Feature 005 conditions guide)
- Trail/biking logistics (Feature 003 trails)
- Rest-day logistics (Feature 004 rest-days)
- Detailed turn-by-turn driving directions (use GPS navigation)
- Lodging recommendations or booking details
- Gear lists or packing guides

## Dependencies

- **Feature 001** (Area Profiles): Provides per-area access details that this guide synthesizes and cross-references.
- **Feature 005** (Conditions Guide): Contains gate hours and time-zone notes with different emphasis (conditions focuses on timing for friction; logistics focuses on access mechanics). Cross-referenced, not duplicated.
