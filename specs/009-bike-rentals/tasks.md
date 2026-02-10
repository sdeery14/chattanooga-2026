# Tasks: Mountain Bike Rentals & Group Riding

**Input**: Design documents from `specs/009-bike-rentals/`
**Prerequisites**: plan.md (required), spec.md (required), research.md, data-model.md, quickstart.md

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

---

## Phase 1: Setup

**Purpose**: Create the rental guide file with header and structure.

- [x] T001 Create `trails/bike-rentals.md` with header block: title ("Mountain Bike Rentals: Chattanooga Region"), context line ("Quick reference for renting a mountain bike and joining Sean for a ride"), trip dates (February 14–21, 2026), lodging reference (Enterprise South Nature Park area), and a "2-Minute Version" summary block at the top. Source: quickstart.md for the summary content, data-model.md § Content Sections for section order. The 2-minute version should cover: book from CGA ($89/24hr), request delivery to ESNP, ride Black Forest (3 mi Green), what to bring.

**Checkpoint**: File exists with header. Remaining sections will be added per user story.

---

## Phase 2: User Story 1 — Find a Rental Shop (Priority: P1)

**Goal**: A trip participant with no bike can identify a rental shop, understand pricing, and determine if they need a reservation within 2 minutes.

**Independent Test**: The rental shop section answers "where can I rent a bike, how much, and do I need to reserve?" for at least 2 shops. Sunday closures are flagged. [UNVERIFIED] tags present for unconfirmed details.

### Rental Shop Content

- [x] T002 [US1] Write the Rental Shop Comparison Table in `trails/bike-rentals.md` § Rental Shops. Table columns: Shop, Type, Pricing, Hours, Sunday, Bikes, Included, Reserve?, Verified. Rows for 3 shops: Chattanooga Guided Adventures (mobile delivery, $89/24hr–$209/72hr, available 7 days [UNVERIFIED], Trek Roscoe/Scott Aspect/Polygon Xtrada, helmet+lock+tube, yes online), Suck Creek Cycle (storefront, [UNVERIFIED] pricing, Mon–Sat, closed Sundays, [UNVERIFIED] rental program, premium brands, call to reserve), REI Chattanooga (storefront, [UNVERIFIED] ~$60-90/day, [UNVERIFIED] hours, open Sundays, [UNVERIFIED] rental program, call to confirm). Source: research.md § 1a-1c.

- [x] T003 [US1] Write the Chattanooga Guided Adventures detailed profile in `trails/bike-rentals.md` § Rental Shops → Chattanooga Guided Adventures. Include: description (mobile delivery service), pricing tiers, bike models with specs (Trek Roscoe 27.5+ dropper, Scott Aspect 950 29", Polygon Xtrada 27.5), what's included (MIPS helmet, keyless lock, spare tube), what's NOT included (water, snacks, shoes, gloves), delivery (free in Coolidge Park area, trailhead delivery [UNVERIFIED fee for ESNP]), booking links (Pelago + Visit Chattanooga), cancellation policy (free 2 days before, no refund day-of), recommendation note (Trek Roscoe best for beginners). Source: research.md § 1a.

- [x] T004 [P] [US1] Write the Suck Creek Cycle detailed profile in `trails/bike-rentals.md` § Rental Shops → Suck Creek Cycle. Include: address (630 W Bell Ave, North Shore), drive from lodging (~20-25 min), phone (423-266-8883), email (suckcreekcycle@gmail.com), website (suckcreek.com), hours (Mon–Thu 10-6, Fri 10-5, Sat 8:30-3), Sunday CLOSED, rental availability [UNVERIFIED — call to confirm], brands (Yeti, Santa Cruz, Orbea, Ibis, Norco, Juliana), note: "#1 source for trail conditions even if renting elsewhere". Source: research.md § 1b.

- [x] T005 [P] [US1] Write the REI Chattanooga detailed profile in `trails/bike-rentals.md` § Rental Shops → REI Chattanooga. Include: address (2507 Lifestyle Way, Hamilton Place), drive from lodging (~10-15 min), phone (423-485-1249 bike shop), website (rei.com/stores/chattanooga), hours [UNVERIFIED — typical Mon–Sat 10-9, Sun 10-7], Sunday open, rental program [UNVERIFIED — varies by store, call to confirm], pricing [UNVERIFIED ~$60-90/day], Presidents' Day note (Feb 16 may have holiday hours), note: "closest to lodging, open Sundays, familiar brand". Source: research.md § 1c.

**Checkpoint**: Rental shop section is complete with comparison table + 3 detailed profiles. A reader can identify where to rent, how much, and whether to reserve. All [UNVERIFIED] tags in place.

---

## Phase 3: User Story 2 — Pick a Beginner-Friendly Trail (Priority: P2)

**Goal**: A first-time mountain biker on a rental can find at least 2 beginner-appropriate trails with drive time, distance, and reasoning.

**Independent Test**: Beginner trail recommendations exist, reference only green/blue-rated trails, link to existing trail profiles, and include drive time and ride length.

### Beginner Trail Content

- [x] T006 [US2] Write the Beginner-Friendly Trails section in `trails/bike-rentals.md` § Beginner-Friendly Trails. Include ranked list of 4 options with table for each: (1) Enterprise South — Black Forest (~3 mi Green, 0 min drive, smoothest singletrack, pump track warm-up, link to [enterprise-south.md](enterprise-south.md)); (2) White Oak Mountain — Green Loop (~1.7 mi Green, ~15-25 min drive, machine-built flow, stacked loops, excellent drainage, link to [white-oak-mountain.md](white-oak-mountain.md)); (3) Chickamauga Battlefield — Paved Road Tour (~12.6 mi shortenable, ~25-35 min, flat/paved fallback if singletrack isn't their thing, link to [chickamauga-battlefield.md](chickamauga-battlefield.md)); (4) Stringer's Ridge — Pump Track Only (small circuit, ~20-30 min, skills practice, link to [stringers-ridge.md](stringers-ridge.md)). Each entry: trail name, specific loop, miles, drive time, estimated ride time at beginner pace, why it's good, concerns/caveats. Source: research.md § 2.

- [x] T007 [US2] Write the "Not Recommended for First-Timers" callout in `trails/bike-rentals.md` § Beginner-Friendly Trails → Skip These. Brief table: Booker T. Washington (all Blue, gnarly/rooty), Raccoon Mountain (tough even at Green rating), Walden's Ridge Park (gravity/DH), Lookout Mountain (descent trails), Five Points (too far for a first rental ride). Source: research.md § 2, "Not Recommended" table.

**Checkpoint**: Beginner trail section is complete. A first-timer can pick a trail appropriate for their skill level without wading through the full trail comparison table.

---

## Phase 4: User Story 3 — Pair a Rental Ride with a Climbing Session (Priority: P3)

**Goal**: When the group splits (some climb, some ride), a renter can find a rental shop + trail that pairs well with the climbing area, with time budgets.

**Independent Test**: At least 2 climbing-area-to-rental-ride pairings exist with drive times and half-day time budgets.

### Climbing Pairing Content

- [x] T008 [US3] Write the Climbing Day Pairings section in `trails/bike-rentals.md` § Climbing Day Pairings. Header: "The group is climbing at ___. How do I rent and ride?" Table columns: Climbing Area, Rental Approach, Beginner Trail, Time Budget, Feasibility. Rows: (1) Stone Fort — CGA delivery to Stringer's or rent from Suck Creek (Mon-Sat), pump track → ESNP Black Forest, ~3-4 hr half-day, Practical; (2) Walden's Ridge — CGA delivery to ESNP or Suck Creek pickup, ESNP Black Forest, ~2-3 hr, Practical (simplest — rider stays at lodging); (3) Rocktown/Zahnd — Not practical (nearest beginner trails 40+ min away), skip biking or do independent ESNP ride; (4) HP40 — Not practical (2 hrs from lodging, no beginner trails nearby). Link climbing areas to existing area profiles. Source: research.md § 3.

**Checkpoint**: Climbing pairing section answers "can I rent a bike while the group climbs at X?" for all major climbing areas.

---

## Phase 5: User Story 4 — First-Timer Tips (Priority: P4)

**Goal**: A first-time renter feels prepared for the experience after a 5-minute read.

**Independent Test**: First-timer section covers clothing, gear, sizing, and etiquette in skimmable format.

### First-Timer Content

- [x] T009 [US4] Write the First-Timer Tips section in `trails/bike-rentals.md` § First-Timer Tips. Subsections: (1) What to Wear — athletic shorts/pants (no jeans), moisture-wicking shirt (no cotton), closed-toe grippy shoes (trail runners/hiking shoes, no sandals), sunglasses, optional light gloves; (2) What's Included with Rental — bike, MIPS helmet, lock, spare tube (CGA); (3) What to Bring — water (1+ bottle), phone, snacks for rides >1hr, sunscreen; (4) Sizing — rental companies size by height at delivery, general reference table (5'4"-5'8" Small, 5'8"-6'0" Medium, 6'0"-6'4" Large), CGA handles sizing; (5) Trail Etiquette — yield to hikers/horses, don't ride muddy trails (1/2 inch rut rule), stay on marked trails, call out when passing, no skidding. Source: research.md § 4.

**Checkpoint**: First-timer section complete. A nervous first-time renter knows what to wear, what to bring, and how to behave on the trail.

---

## Phase 6: Polish & Cross-Cutting Concerns

**Purpose**: February notes, cross-references, and verification.

### February Considerations

- [x] T010 [P] Write the February Considerations section in `trails/bike-rentals.md` § February Considerations. Include: (1) Presidents' Day weekend (Feb 14-16) — book early, inventory may be limited; (2) Winter hours — Suck Creek closes early on Fridays (5pm) and Saturdays (3pm); (3) Sunday gap — Suck Creek closed, CGA [UNVERIFIED], REI typically open; (4) Wet weather — cross-reference trails/README.md wet-weather fallback table (White Oak drains best, ESNP drains OK, Chickamauga always rideable); (5) Trail closures — check SORBA Chattanooga daily; (6) Freeze/thaw — don't ride during thaw, ride frozen or wait for dry-out. Source: research.md § 1a-1c February notes + trails/README.md § February Riding Conditions.

### Cross-References

- [x] T011 [P] Add cross-reference to `trails/bike-rentals.md` in `trails/README.md`. Insert after the "Rest-Day Rides (Top 3 Near Lodging)" section (after line ~117). Add a brief note: "**Don't have a bike?** See [Mountain Bike Rentals](bike-rentals.md) for rental shops, beginner trail picks, and how to pair a ride with a climbing day." Keep it to 1-2 lines.

- [x] T012 [P] Update the existing biking cross-reference in `rest-days/README.md`. The file already has a note near line ~503: "> **Looking for a rest-day ride?** Mountain biking options are documented in the trail profiles." Expand this to also mention rentals: add "No bike? See [Mountain Bike Rentals](../trails/bike-rentals.md) for rental shops and beginner trails." Keep the existing trail link.

### Verification

- [x] T013 Verify all internal links in `trails/bike-rentals.md` resolve correctly: trail profile links (enterprise-south.md, white-oak-mountain.md, chickamauga-battlefield.md, stringers-ridge.md), area profile links (../areas/stone-fort.md, ../areas/waldens-ridge.md, ../areas/rocktown.md, ../areas/hp40.md), external links (Pelago booking, Visit Chattanooga, suckcreek.com, REI). Verify [UNVERIFIED] tags present for all unconfirmed details. Verify table formatting is valid markdown.

**Checkpoint**: Feature complete. All 4 user stories implemented, cross-references added, February notes in place, links verified.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Phase 1 (Setup)**: No dependencies — start immediately
- **Phase 2 (US1 — Rental Shops)**: Depends on T001 (file must exist)
- **Phase 3 (US2 — Beginner Trails)**: Depends on T001. Can run in parallel with Phase 2.
- **Phase 4 (US3 — Climbing Pairings)**: Depends on T001. Can run in parallel with Phases 2-3.
- **Phase 5 (US4 — First-Timer Tips)**: Depends on T001. Can run in parallel with Phases 2-4.
- **Phase 6 (Polish)**: T010 depends on T001. T011-T012 are independent (different files). T013 depends on all prior tasks.

### User Story Dependencies

- **US1 (P1)**: No dependencies on other stories
- **US2 (P2)**: No dependencies on other stories
- **US3 (P3)**: References rental shops from US1 and trails from US2 — best written after both, but not strictly blocked
- **US4 (P4)**: No dependencies on other stories

### Parallel Opportunities

All user story content goes into the same file (`trails/bike-rentals.md`), so true parallel execution is limited. However:
- T004 and T005 (Suck Creek + REI profiles) can be written in parallel
- T010, T011, T012 (February notes + cross-references) can be written in parallel (T011 and T012 are different files)
- Recommended execution: sequential T001 → T002 → T003 → T004/T005 → T006 → T007 → T008 → T009 → T010/T011/T012 → T013

---

## Implementation Strategy

### MVP First (User Story 1 Only)

1. Complete T001 (Setup — file header)
2. Complete T002–T005 (Rental shop comparison + profiles)
3. **STOP and VALIDATE**: Can a reader find a rental shop, understand pricing, and know if they need a reservation?

### Incremental Delivery

1. T001 → File exists with 2-minute summary
2. T002–T005 → Rental shops complete (MVP)
3. T006–T007 → Beginner trails added
4. T008 → Climbing pairings added
5. T009 → First-timer tips added
6. T010–T013 → February notes, cross-references, verification

Each increment adds value without breaking previous content.
