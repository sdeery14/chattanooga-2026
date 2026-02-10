# Feature Specification: Mountain Bike Rentals & Group Riding

**Feature Branch**: `009-bike-rentals`
**Created**: 2026-02-10
**Status**: Draft
**Input**: User description: "Feature 009: Mountain Bike Rentals & Group Riding"

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Find a Rental Shop (Priority: P1)

A trip participant who didn't bring a mountain bike wants to join Sean for a ride. They open the repo and quickly find which local shops rent mountain bikes, what it costs, whether they need to reserve ahead, and what hours the shop is open — all without Googling from the trailhead parking lot.

**Why this priority**: Without knowing *where* to rent, nothing else in this feature matters. This is the entry point for any non-biker who wants to ride.

**Independent Test**: Can be fully tested by reading the rental shop section and confirming it answers "where can I rent a bike, how much, and do I need to reserve?" for at least 2 shops.

**Acceptance Scenarios**:

1. **Given** a trip participant with no bike, **When** they open the bike rentals section, **Then** they see at least 2 local shops with name, location, drive time from lodging, rental pricing, hours, and whether reservations are required.
2. **Given** a participant checking on a Sunday, **When** they look up shop hours, **Then** they can immediately tell which shops are open and which are closed (e.g., Suck Creek Cycle is closed Sundays).
3. **Given** a participant who has never rented a mountain bike, **When** they read the rental info, **Then** they understand what's included (helmet, pedals, etc.) and what to bring themselves.

---

### User Story 2 - Pick a Beginner-Friendly Trail (Priority: P2)

A rental rider with little or no mountain biking experience needs to know which trails are appropriate for a first-timer on an unfamiliar rental bike. They want a short list of recommended trails filtered for beginners, not the full trail comparison table.

**Why this priority**: Sending a first-timer to Walden's Ridge Park gravity trails or Raccoon Mountain tech singletrack would be a bad experience. Matching rider ability to trail difficulty is essential for safety and fun.

**Independent Test**: Can be fully tested by confirming the beginner trail recommendations exist, reference only green/blue-rated trails, and include drive time and approximate ride length.

**Acceptance Scenarios**:

1. **Given** a first-time mountain biker on a rental, **When** they check the beginner trail recommendations, **Then** they see at least 2 trails rated green or blue with estimated ride time and drive time from lodging.
2. **Given** a rental rider reviewing trail options, **When** they compare recommendations, **Then** each trail notes why it's good for beginners (e.g., wide, smooth flow, no mandatory features).

---

### User Story 3 - Pair a Rental Ride with a Climbing Session (Priority: P3)

The group wants to split for a half-day — some climb, one or two rent bikes and ride. They need to know which rental shops and trails pair well with which climbing areas so both subgroups minimize driving and can meet up afterward.

**Why this priority**: The trip is primarily a climbing trip. Biking needs to fit *around* climbing logistics, not compete with them. Pairing guidance makes biking a seamless addition rather than a scheduling headache.

**Independent Test**: Can be fully tested by confirming at least 2 climbing-area-to-rental-ride pairings exist with drive times and logistics notes.

**Acceptance Scenarios**:

1. **Given** the group is climbing at Stone Fort, **When** a participant wants to rent a bike instead, **Then** they can find a recommended rental shop and beginner trail that minimizes total driving for both subgroups.
2. **Given** a half-day pairing scenario, **When** a participant reviews the pairing guidance, **Then** they see estimated time budget (drive + ride + return) so they know if it fits a half-day window.

---

### User Story 4 - Know What to Expect as a First-Time Renter (Priority: P4)

A participant who has never rented a mountain bike — and may have limited cycling experience — wants a quick "what to know before you go" primer covering sizing, what to wear, what's provided vs. what to bring, and basic trail etiquette.

**Why this priority**: Reduces anxiety and prevents rookie mistakes (showing up in jeans and sandals, not knowing how to set seat height, etc.). Nice to have but not critical — experienced outdoor folks can figure most of this out.

**Independent Test**: Can be fully tested by confirming a "first-timer tips" section exists and covers clothing, gear, sizing, and basic etiquette in a skimmable format.

**Acceptance Scenarios**:

1. **Given** a first-time rental rider, **When** they read the first-timer section, **Then** they know what clothing/shoes to wear, what the shop provides, and what to bring (water, snacks).
2. **Given** a rental rider at the shop, **When** they need to pick a bike size, **Then** the guide includes a basic sizing reference (height-to-frame-size) or notes that the shop will fit them.

---

### Edge Cases

- What if all rental shops are closed (e.g., Sunday + holiday)? The guide should note this gap and suggest alternatives (e.g., REI may have limited rental availability, or skip biking that day).
- What if rental inventory is sold out during peak season / holiday weekend? The guide should recommend reserving ahead, especially for Presidents' Day weekend (Feb 14-16).
- What if conditions are too wet to ride? Cross-reference the existing wet-weather fallback section in `trails/README.md` — some trails (White Oak, Enterprise South) drain well and may still be rideable on a rental.
- What if a rental rider gets hurt or has a mechanical issue? Note whether rental shops include basic roadside tools / repair coverage, and recommend riding with a phone.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The guide MUST list at least 2 local bike shops that offer mountain bike rentals, with name, address, drive time from lodging, phone number, hours, and website/booking link.
- **FR-002**: Each rental shop listing MUST include pricing (daily rate at minimum), what's included with the rental (helmet, pedals, tools), and whether reservations are required or recommended.
- **FR-003**: The guide MUST include a "Beginner-Friendly Trails" section recommending at least 2 trails rated green or blue, with drive time from lodging, approximate ride length, and why each is good for first-timers.
- **FR-004**: The guide MUST include at least 2 climbing-area-to-rental-ride pairings showing which rental shop and trail to use when the group is climbing at a given area, with drive times.
- **FR-005**: The guide MUST include a "First-Timer Tips" section covering what to wear, what the shop provides vs. what to bring, basic sizing guidance, and trail etiquette.
- **FR-006**: The guide MUST note February-specific considerations: Presidents' Day weekend inventory pressure, winter hours if different from summer, and wet-weather trail closures.
- **FR-007**: The guide MUST flag Sunday closures and any other known schedule gaps that would prevent same-day rentals.
- **FR-008**: All rental shop information MUST include a date-of-research note or [UNVERIFIED] tag for details that could not be confirmed, consistent with existing repo conventions.

### Key Entities

- **Rental Shop**: Name, address, drive time from lodging, phone, website, hours, Sunday open/closed, pricing (half-day, full-day), what's included, reservation policy, February notes
- **Beginner Trail Recommendation**: Trail name (linking to existing trail profile), difficulty rating, drive time from lodging, recommended ride length/time, why it's beginner-friendly
- **Climbing-to-Ride Pairing**: Climbing area, recommended rental shop, recommended trail, total drive time, time budget estimate, logistics notes

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A trip participant with no bike can identify a rental shop, understand pricing, and determine if they need a reservation within 2 minutes of opening the guide.
- **SC-002**: At least 2 rental shops are documented with complete information (name, location, hours, pricing, inclusions, reservation policy).
- **SC-003**: At least 2 beginner-friendly trail recommendations are provided, each linking to an existing trail profile in the repo.
- **SC-004**: At least 2 climbing-area-to-rental-ride pairings are documented with drive times and time budgets.
- **SC-005**: All information follows existing repo conventions: [UNVERIFIED] tags where needed, drive times from lodging, February-specific notes, and skimmable table format.
- **SC-006**: A first-time renter can read the "what to know" section and feel prepared for the experience within 5 minutes.

## Assumptions

- The primary audience for this feature is trip participants who did *not* bring a mountain bike and want to try riding for a half-day or full day.
- Sean (who brings his own bike) is the riding companion — he sets the pace and picks trails. This feature helps others join him, not plan independent rides.
- Rental availability and pricing are subject to change; the guide documents what's known at research time and tags unverified details per repo convention.
- The feature adds a new section to the trails README or creates a standalone `trails/bike-rentals.md` file, consistent with existing repo structure.
- Beginner trail recommendations are a filtered subset of trails already documented in the repo — no new trail research is needed.
