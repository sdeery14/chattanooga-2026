# Feature Specification: Rest Day & Low-Energy Decision Pack

**Feature Branch**: `004-rest-day-pack`
**Created**: 2026-02-08
**Status**: Draft
**Input**: User description: "Rest Day & Low-Energy Decision Pack from vision.md"

## User Scenarios & Testing

### User Story 1 — Decide What to Do on a Rest Day (Priority: P1)

It's a rest day — nobody wants to climb, or the group needs recovery. The trip planner opens the rest-day guide and quickly finds pre-vetted options organized by energy level: "do nothing" options (food, coffee, lounging), low-energy options (town walks, breweries, easy sightseeing), and active-rest options (easy rides, short hikes, swimming). The answer should be obvious within 60 seconds without searching on a phone.

**Why this priority**: Rest days are guaranteed during a week-long climbing trip. Without pre-vetted options, the group defaults to aimless phone-scrolling, decision fatigue, and wasted hours. This is the core "sanity saver" use case from the vision.

**Independent Test**: Open the rest-day guide and answer "What should we do today? Nobody wants to climb." with at least 2 options per energy level (zero, low, active) — in under 60 seconds.

**Acceptance Scenarios**:

1. **Given** a full rest day with no climbing planned, **When** the planner opens the rest-day guide, **Then** they see at least 2 options per energy tier (zero-energy, low-energy, active) with enough detail to make a go/no-go decision (location, drive time, what to expect, hours).
2. **Given** the group is tired and wants zero effort, **When** they look for "true rest" options, **Then** they find food/drink/hangout options near lodging that require minimal driving.
3. **Given** one person wants to ride while others rest, **When** they check the guide, **Then** they see mountain biking cross-references to existing trail profiles (Feature 003) without duplicated content.

---

### User Story 2 — Salvage a Weather-Ruined Day (Priority: P2)

It's raining, trails are closed, rock is wet — the original climbing plan is scrapped. The group needs weather-appropriate alternatives fast: indoor activities, covered attractions, or options that work in rain. The guide provides weather-dependent alternatives pre-organized so the group can pivot without a 30-minute phone research session.

**Why this priority**: February in Chattanooga means ~41% chance of precipitation on any given day. Weather-blown days are not edge cases — they're expected. Having alternatives ready prevents the worst trip dynamic: a group stuck in an Airbnb with no plan.

**Independent Test**: Open the rest-day guide, find the weather-dependent section, and identify at least 2 rain-friendly alternatives within 30 minutes of lodging — in under 60 seconds.

**Acceptance Scenarios**:

1. **Given** rain has cancelled the climbing plan, **When** the planner checks weather alternatives, **Then** they find at least 2 rain-proof options near lodging (indoor activities, covered attractions, or weather-insensitive activities) with drive time and logistics.
2. **Given** a partial weather day (morning rain, afternoon clearing), **When** checking the guide, **Then** they find suggestions for how to use a split day (morning activity + afternoon climbing or riding).

---

### User Story 3 — Find a Low-Energy Climbing or Riding Session (Priority: P3)

It's not a full rest day — the group has some energy but doesn't want a big day. They want a short, close-to-lodging climbing session or an easy ride without the commitment of driving to a Tier 1 area. The guide surfaces "half-day" or "low-commitment" options that pair well with afternoon rest.

**Why this priority**: The space between "rest day" and "full send day" is where most trip days actually land. Having pre-vetted low-commitment options prevents over-committing on low-energy days (and the regret that follows).

**Independent Test**: Open the guide and answer "Where can we do something easy and close?" with at least 2 options (climbing or riding) within 20 minutes of lodging.

**Acceptance Scenarios**:

1. **Given** the group wants a short morning session, **When** they check low-energy options, **Then** they find at least 2 close-to-lodging options (climbing areas with easy access or nearby trail systems) with estimated session length.
2. **Given** a climber wants to pair a short session with afternoon rest, **When** they check the guide, **Then** they see suggestions for morning-only sessions at nearby areas with notes on what makes them good "half-day" spots.

---

### Edge Cases

- What happens when all outdoor options are weather-cancelled? Include at least 1-2 indoor-only alternatives (gym, museum, movie theater) as absolute fallbacks.
- What if the group splits — some want to rest, some want to be active? The guide should support this explicitly by organizing options by energy level so subgroups can self-select.
- What if a rest day turns into a climbing day mid-morning? Note which Tier 1/2 areas are close enough to pivot to on short notice.
- What if the group wants to leave the Chattanooga area entirely for a day trip? Include 1-2 day-trip options if compelling destinations exist within ~1 hour (e.g., a town worth visiting, a notable restaurant).

## Requirements

### Functional Requirements

- **FR-001**: The feature MUST provide a rest-day guide document organized by energy level: zero-energy (food, lounging, no driving), low-energy (town walks, breweries, easy sightseeing), and active-rest (short hikes, easy rides, swimming).
- **FR-002**: Each rest-day option MUST include: name, type of activity, location or area, drive time from lodging, brief description (1-2 sentences), and any relevant logistics (hours, cost, reservations).
- **FR-003**: The feature MUST include a weather-dependent alternatives section with rain-proof and indoor options near lodging.
- **FR-004**: The feature MUST cross-reference existing trail profiles (Feature 003) for mountain biking rest-day options rather than duplicating trail content. References should link to the relevant trail profile.
- **FR-005**: The feature MUST cross-reference existing climbing area profiles (Feature 001) for low-energy climbing sessions rather than duplicating area content. References should link to the relevant area profile.
- **FR-006**: Each option MUST cite at least one verifiable source (website, Google Maps listing, or community recommendation) per the project's established source convention.
- **FR-007**: The feature SHOULD include a "Quick Decision" section or table at the top of the document for scanning all options at a glance, analogous to the comparison tables in Features 001 and 003.
- **FR-008**: Unverified information MUST be flagged with [UNVERIFIED] per the project's established convention.
- **FR-009**: The feature MUST NOT duplicate content already in area profiles (Feature 001), problem clusters (Feature 002), or trail profiles (Feature 003). It references those documents by link.
- **FR-010**: The feature SHOULD note February-specific availability for each option (seasonal closures, winter hours, weather sensitivity).

### Key Entities

- **Rest-Day Option**: A pre-vetted activity or destination suitable for a rest or low-energy day. Key attributes: name, energy tier (zero/low/active), activity type, location, drive time from lodging, description, logistics, source.
- **Weather Alternative**: A subset of rest-day options specifically viable in rain or poor weather. Key attributes: same as rest-day option plus weather-resilience note.
- **Quick Decision Table**: A summary table listing all rest-day options with key attributes for rapid scanning.

## Success Criteria

### Measurable Outcomes

- **SC-001**: A reader can answer "What should we do on a rest day?" with at least 2 options per energy tier (zero, low, active) within 60 seconds of opening the guide.
- **SC-002**: At least 2 rain-proof alternatives within 30 minutes of lodging are documented with complete logistics.
- **SC-003**: Every rest-day option includes all mandatory fields (name, type, location, drive time, description, source).
- **SC-004**: All cross-references to Features 001 and 003 resolve to existing documents with working links.
- **SC-005**: The guide passes the project's 5 content quality gates (skimmability, decision-orientation, scope, ability coverage adapted for rest days, source citation).
- **SC-006**: A reader can find a weather-appropriate alternative within 60 seconds when the original plan is cancelled.

## Assumptions

- Lodging is near Enterprise South Nature Park (ESNP) in NE Chattanooga. All drive times reference this location.
- "Rest day" means a day without committed climbing or major physical activity. It does not mean the group must stay indoors.
- The guide covers the Chattanooga metro area and immediate surroundings (~30 min drive from lodging for most options, up to ~1 hour for day trips).
- February hours and availability may differ from summer — research should verify winter/February access where possible.
- The group is 4-6 people with varied interests. Options should appeal to a range of preferences, not just climbers.
- Food and drink recommendations should focus on notable/destination-worthy spots, not exhaustive restaurant lists. Quality over quantity.
- Mountain biking rest-day options are already documented in Feature 003. This feature links to them, not re-documents them.
- Climbing area profiles (Feature 001) already contain access, conditions, and logistics. This feature references them for "low-energy session" recommendations.

## Dependencies

- **Feature 001** (Primary Bouldering Areas): Required — low-energy climbing references link to area profiles.
- **Feature 003** (Parallel Activity Mapping): Required — active-rest riding options link to trail profiles.
- **Feature 002** (Problem Clusters): Not required, but "easy morning session" recommendations may reference cluster documents for quick problem selection.
