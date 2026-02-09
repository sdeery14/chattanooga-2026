# Feature Specification: Personal Trip Goals & Preferences (Sean)

**Feature Branch**: `007-personal-trip-goals`
**Created**: 2026-02-09
**Status**: Draft
**Input**: User description: "A deeply personal, single-user reference for Sean — the group's V0–V1 outdoor climber and only mountain biker. Climbing growth targets, mountain biking skill-development goals, brewery/food wishlists, sightseeing, and a ranked priority stack."

## Sean's Profile

This section captures Sean's physical profile, constraints, and preferences so that all content in this guide can be personalized accordingly.

- **Age**: 34
- **Height/Weight**: 6'2", 200 lbs
- **Athletic background**: Semi-pro football (linebacker) in his 20s. Explosive power, strong upper body, strong pulling muscles.
- **Injury history**: 4 knee surgeries including ACL reconstruction on each knee. Knees are recovered but stiff. Tight hips identified as root cause — actively strengthening but still limited.
- **Current training**: Hangboard (10s on / 10s off for 10 min), hanging leg raises (core), ATG knees-over-toes rehab, bodybuilding-style lifting, football-style rotational/throwing movements.
- **Climbing level**: V1 outdoor, V4 gym. Athletic beginner with enormous physical ceiling.
- **Mountain biking level**: Athletic beginner. Rode bikes a lot as a kid. Enjoys flow/XC, wants to develop trail/enduro skills.
- **Bike**: Jamis Faultline A2 (XL) — full-suspension 29er trail bike, 120mm rear / 130mm fork (RockShox Recon Silver RL), Shimano Deore 1x11, hydraulic disc brakes, dropper post. Aggressive trail tires (WTB Vigilante front / Trail Boss rear). Capable for flow, XC, and moderate technical trail riding. Not suited for full gravity/DH lines — skill and bike both cap out at moderate enduro terrain.
- **Beer preference**: IPA / hop-forward
- **Food preference**: Hearty/casual — BBQ, burgers, Southern comfort, big portions. Post-climb/ride fuel over fine dining.
- **Sightseeing**: Open — nothing specific pre-planned, research cool stuff

### What This Means for Climbing

**Strengths that translate to climbing**:
- Reach advantage (6'2") is massive at low grades — many V2–V4 problems that are "hard for short people" become much more accessible
- Raw pulling power and upper body strength from football/lifting — overhanging moves at low grades, campus-style reaches
- Developing finger strength (hangboard training) — can handle crimp-dependent moves better than a typical V1 climber
- Core strength (hanging leg raises) — body tension on slightly overhung terrain

**Constraints that shape project selection**:
- Weight (200 lbs) — sustained roofs and long overhang sequences are significantly harder; slopers become less friendly
- Tight hips — high steps, drop-knees, aggressive flagging, and hip-turnover moves are limited. Problems requiring wide stems or deep hip rotation should be flagged.
- Knee history — aggressive heel hooks (especially torquing), deep mantles, and high-impact landings need caution. Tall boulders with bad landings are a concern.
- Gym-to-outdoor gap — outdoor reading, friction trust, and real rock tactics are still developing. V1 outdoor is well below gym level, which is normal.

**Ideal problem styles**:
- Reachy/span-dependent moves where height eliminates the crux
- Power pulls on moderate overhang with good footholds
- Crimp ladders on vertical to slightly overhung terrain
- Problems with large, positive footholds (not requiring precise hip positioning)
- Short-duration power problems over long sustained sequences

**Styles to approach with caution**:
- Technical slab requiring hip turnover and precise foot placement
- Sustained roof climbing (weight + endurance tax)
- Problems with mandatory high heel hooks or deep drop-knees
- Compression/hug-style problems (harder at his size)
- Tall boulders with bad or uneven landings (knee safety)

## User Scenarios & Testing

### User Story 1 — Pick a Mountain Bike Ride (Priority: P1)

Sean has a free half-day, a rest day, or the group is climbing an area with nothing compelling for him. He opens his personal guide and sees his pre-ranked trail wishlist — organized by ride goal (flow session vs. skill-development session), pairing with the day's group plans, and personal priority. He picks a ride in under 60 seconds.

**Why this priority**: Mountain biking is Sean's primary parallel activity and the thing he's most likely to do independently from the group. He's the only rider, so this decision is always personal. The group trail research (Feature 003) documents 13 trail systems — Sean needs a personal filter: "Which ones do I actually want to ride, in what order, and for what purpose?"

**Independent Test**: Open the personal guide's biking section and identify Sean's top 3 ride priorities with character notes, skill-development value, and day-pairing suggestions — in under 60 seconds.

**Acceptance Scenarios**:

1. **Given** Sean has a full rest day with no climbing, **When** he checks his ride wishlist, **Then** he sees his top-ranked all-day ride options with expected ride time, character description (flow vs. tech), skill-development notes, and drive time from lodging.
2. **Given** the group is climbing at Rocktown and Sean wants to ride instead, **When** he checks his guide, **Then** he sees which nearby trails pair with Rocktown and whether they're worth the detour vs. riding near lodging.
3. **Given** it rained yesterday, **When** Sean checks his ride list, **Then** he can identify which trails drain well enough to ride today — via his personal notes or cross-reference to the trail profiles.
4. **Given** Sean wants to work on technical skills, **When** he checks his list, **Then** he can identify which trails offer the best skill-development terrain (roots, rocks, technical features) at a manageable difficulty for his level.

---

### User Story 2 — Find Climbing Problems That Suit Me (Priority: P2)

Sean arrives at a climbing area with the group and wants to know what to try. He opens his personal guide, finds the area, and sees a curated list of problems that play to his strengths — reachy V0–V3 sends and V2–V4 "stretch goal" projects. Each entry notes why it suits him (reach advantage, power-friendly, good footholds) and flags anything to watch out for (landing quality, hip-intensive moves).

**Why this priority**: Without a personalized list, Sean either wanders aimlessly or defaults to whatever the group suggests. With his specific physical profile, generic "best V0–V3" lists miss important context — a V2 slab that requires hip turnover is a bad pick for Sean, while a V3 overhang with big moves could be very doable.

**Independent Test**: Open the personal guide to any Tier 1 area section and identify at least 3 problems suited to Sean's profile — in under 30 seconds.

**Acceptance Scenarios**:

1. **Given** Sean is at Stone Fort, **When** he opens his personal climbing section, **Then** he sees curated V0–V3 problems that favor his strengths (reachy, power, good feet) with notes on why each is a good pick for him, plus V2–V4 stretch projects.
2. **Given** Sean wants to push himself, **When** he checks his "stretch goals" for the area, **Then** he sees V2–V4 problems where his reach or power gives him an advantage over typical climbers at that grade, with honest notes on what will be hard.
3. **Given** a problem involves a high landing or sketchy pad zone, **When** Sean checks the entry, **Then** he sees a flag about landing quality so he can make an informed risk decision given his knee history.
4. **Given** Sean is at a Tier 2 area, **When** he checks his guide, **Then** he sees any worthwhile problems for his level at that area or a clear "focus on the group session / go ride instead" note.

---

### User Story 3 — Find a Brewery or Restaurant (Priority: P3)

The group is heading back from climbing or it's evening and Sean wants to hit a specific spot. He opens his personal food/drink wishlist and sees his targets organized by tier ("don't miss" vs. "if we're nearby") and location. IPA-focused brewery picks are front and center.

**Why this priority**: Group rest-day research (Feature 004) covers food broadly. Sean wants a personal "I specifically want to try these places" list — curated toward his IPA preference, opinionated, and ranked — so he doesn't forget targets when tired.

**Independent Test**: Open the personal guide's food section and identify Sean's top 3 "don't miss" spots with enough detail (location, vibe, IPA notes) to make a decision — in under 30 seconds.

**Acceptance Scenarios**:

1. **Given** the group is driving back from Stone Fort, **When** Sean checks his food wishlist, **Then** he sees which of his target spots are on the route or near lodging, with a note on what makes each one worth a stop.
2. **Given** Sean wants a brewery with strong IPAs, **When** he checks his "don't miss" tier, **Then** he sees breweries ranked by IPA program quality with specific beer recommendations or styles to look for.
3. **Given** the group wants to go out for dinner, **When** Sean checks his picks, **Then** he sees vibe notes (casual/fancy, loud/chill) and any logistics (reservations needed, hours, closed days).

---

### User Story 4 — Sights, Experiences & Side-Trips (Priority: P4)

Sean wants to see or do something non-climbing, non-biking during the trip. He checks his personal sights list for lookout points, downtown walks, local oddities, or experiences worth his time.

**Why this priority**: Lower priority than biking/climbing/food, but valuable. Without a pre-researched list, these "it'd be cool to see" items get forgotten entirely or require phone-scrolling to rediscover.

**Independent Test**: Open the personal guide's sights section and find at least 2 specific experiences with enough detail to act on.

**Acceptance Scenarios**:

1. **Given** Sean has an hour to kill in downtown Chattanooga, **When** he checks his sights list, **Then** he sees specific points of interest with location, time needed, and a note on why they're worth seeing.
2. **Given** the group is driving past a notable spot, **When** Sean checks his list, **Then** he can quickly determine if it's worth a stop or a "next time" item.

---

### User Story 5 — "Last Day" Priority Call (Priority: P5)

It's the final day and Sean hasn't hit everything. He opens the priority stack and sees his cross-category ranked list: the single most important things across biking, climbing, food, and sights. This answers "if I only have one day left, what matters most?"

**Why this priority**: This is the capstone — only useful if the other sections exist. But on the last day of a trip, it's the most important page in the repo.

**Independent Test**: Open the priority stack and identify Sean's top 5 cross-category priorities in order — in under 15 seconds.

**Acceptance Scenarios**:

1. **Given** it's the last full day, **When** Sean opens his priority stack, **Then** he sees a ranked list of his top unfinished priorities across all categories with enough context to act immediately.
2. **Given** Sean has already completed some priorities, **When** he reviews the stack, **Then** the format makes it easy to visually skip completed items and identify what's still open.

---

### Edge Cases

- What if Sean's top ride is unrideable (rain, trail closure)? The biking section should note drainage/wet-weather viability for each trail on his list.
- What if an area has nothing compelling for Sean's climbing level? Include an honest "nothing great here for you — go ride or spot" note rather than forcing bad recommendations.
- What if a brewery or restaurant is closed when the group arrives? Each food entry should include hours, days closed, and whether reservations are needed.
- What if Sean's priorities conflict with group plans? The guide is explicitly personal — it doesn't override group decisions, it informs Sean's advocacy and solo-time choices.
- What if conditions are bad for both climbing and biking? The guide should include a "total washout day" note pointing to indoor/covered alternatives from the rest-day guide.
- What if a problem has a sketchy landing? Flag landing quality explicitly given Sean's knee history — some problems worth trying for others may not be worth the risk for Sean.

## Requirements

### Functional Requirements

- **FR-001**: The feature MUST provide a single personal guide document organized into clearly separated sections: Sean's Profile (quick reference), Mountain Biking, Climbing Projects, Food & Drink, Sights & Experiences, Priority Stack, and Personal Logistics.
- **FR-002**: The Sean's Profile section MUST summarize his physical profile, climbing level, biking level, strengths, and constraints as a quick-reference for anyone helping him pick problems or rides.
- **FR-003**: The Mountain Biking section MUST present Sean's personal trail wishlist as a ranked list, drawing from the trail systems documented in Feature 003, with each trail tagged as "flow/fun" or "skill development" or both.
- **FR-004**: Each trail entry in the biking section MUST include: trail name, ride character (flow/tech/gnar), estimated ride time, drive time from lodging, climbing-area pairing note, wet-weather viability, skill-development note for Sean's level, and a bike-suitability note (the Jamis Faultline A2 handles flow through moderate tech comfortably; full gravity/DH terrain exceeds both bike and current rider capability).
- **FR-005**: The Climbing Projects section MUST provide curated picks for Tier 1 areas (Stone Fort, Rocktown, HP40) with V0–V3 "send list" problems and V2–V4 "stretch goal" projects. For Tier 2 areas, the section MUST include an honest assessment: either 1–2 worthwhile picks if they exist, or a clear "ride or spot — nothing compelling here for your level" note. No filler recommendations.
- **FR-006**: Each climbing entry MUST include: problem name, grade, area, why it suits Sean (reach, power, good feet, etc.), any flags (landing quality, hip-intensive moves, knee risk), and a personal category (send list / stretch goal).
- **FR-007**: The Climbing Projects section MUST flag landing quality for every problem — noting tall boulders, uneven landings, or situations requiring extra pads — given Sean's knee surgery history.
- **FR-008**: The Climbing Projects section MUST note when a problem requires movements that are hard for Sean (high steps, aggressive heel hooks, drop-knees, hip turnover, sustained overhang) so he can make informed choices.
- **FR-009**: The Food & Drink section MUST organize spots into tiers: "don't miss" (must visit) and "if we're nearby" (opportunistic), with IPA-focused brewery picks prominently featured.
- **FR-010**: Each food/drink entry MUST include: name, type (brewery/restaurant/coffee/etc.), location or neighborhood, standout items or vibe notes (with IPA/hop-forward beer specifics for breweries), and logistics (hours, reservations, closed days). Restaurant picks should skew hearty/casual — BBQ, burgers, Southern comfort, big portions — prioritizing post-climb/ride refueling over fine dining.
- **FR-011**: The Sights & Experiences section MUST list specific non-climbing, non-biking points of interest with location, time needed, and why they're worth seeing.
- **FR-012**: The Priority Stack MUST be a single ranked list crossing all categories (biking, climbing, food, sights) representing Sean's "if I only have one day" priorities.
- **FR-013**: The feature MUST cross-reference existing documents (area profiles, problem clusters, trail profiles, rest-day guide) by link rather than duplicating content. Personal notes add context on top of those references.
- **FR-014**: Each entry that references an existing document MUST include a working link to that document.
- **FR-015**: Unverified information MUST be flagged with [UNVERIFIED] per the project's established convention.
- **FR-016**: The feature MUST include a Personal Logistics section for Sean-specific items: bike transport notes, bike gear checklist, knee brace/support notes, and anything that doesn't belong in the group logistics doc (Feature 006).

### Key Entities

- **Climbing Pick**: A specific boulder problem curated for Sean's profile. Key attributes: name, grade, area, why it suits Sean, body/safety flags, category (send list / stretch goal).
- **Trail Target**: A specific mountain bike trail system Sean wants to ride. Key attributes: name, character, ride time, drive time, climbing pairing, wet-weather viability, ride purpose (flow/fun vs. skill development), personal priority rank.
- **Food/Drink Target**: A specific brewery, restaurant, or food spot Sean wants to visit. Key attributes: name, type, location, tier (don't miss / if nearby), standout items (IPA specifics for breweries), logistics.
- **Sight/Experience**: A non-climbing, non-biking point of interest. Key attributes: name, location, time needed, reason flagged.
- **Priority Stack Entry**: A cross-category ranked item. Key attributes: rank, category, name, one-line context.

## Success Criteria

### Measurable Outcomes

- **SC-001**: Sean can pick a mountain bike ride matching his energy level, skill-development goal, and the day's group plans within 60 seconds.
- **SC-002**: Sean can identify 3+ problems suited to his profile at any Tier 1 area within 30 seconds of opening the guide.
- **SC-003**: Sean can name his top 3 "don't miss" food/drink targets without opening any other document.
- **SC-004**: The priority stack enables a "last day" decision in under 15 seconds.
- **SC-005**: Every climbing pick includes a landing-quality flag and a body-constraint flag where applicable.
- **SC-006**: Every cross-reference to Features 001–006 resolves to an existing document with a working link.
- **SC-007**: The guide passes the project's content quality gates (skimmability, decision-orientation, scope, source citation where applicable).
- **SC-008**: No content is duplicated from existing area profiles, problem clusters, trail profiles, or rest-day options — all shared data is referenced by link.

## Assumptions

- Sean climbs at V1 outdoors (V4 gym) and is interested in V0–V3 problems as sends and V2–V3 problems as realistic stretch goals, with 1–2 flagged V4 "moonshots" per Tier 1 area where his reach or power make them plausible.
- Sean's physical strengths (reach, power, finger-strength development) give him access to problems above his nominal grade when the movement suits him.
- Sean's constraints (tight hips, knee history, 200 lbs) meaningfully shape which problems are good targets vs. frustrating or risky. The guide is opinionated about this.
- Sean is the only mountain biker in the group and is bringing his own bike. Mountain biking is his primary parallel activity.
- Sean prefers IPA/hop-forward beers. Brewery recommendations should lead with IPA program quality. Restaurant picks should skew hearty/casual (BBQ, burgers, Southern comfort).
- The guide is a single markdown document with clear heading anchors for each section. No multi-file navigation — optimized for quick access when tired.
- Lodging is near Enterprise South Nature Park (ESNP) in NE Chattanooga, consistent with all other features.
- Trip dates are February 14–21, 2026. All hours, availability, and conditions notes assume this window.
- The priority stack is a living document — Sean may reorder it during the trip. The format should make reordering easy.
- This guide is explicitly personal. It does not represent group consensus and should not override group decision-making. It supports Sean's advocacy and solo-time planning.

## Clarifications

### Session 2026-02-09

- Q: What type of mountain bike is Sean bringing? → A: Jamis Faultline A2 (XL) — full-suspension 29er trail bike, 120mm rear / 130mm fork, Shimano Deore 1x11, dropper post, aggressive trail tires (Vigilante/Trail Boss). Capable for flow through moderate tech; not suited for full gravity/DH.
- Q: Should climbing picks cover all areas or just where it's worth Sean's time? → A: Curate Tier 1 areas (Stone Fort, Rocktown, HP40) with full picks. Tier 2 areas get honest "ride/spot instead" notes unless there are genuinely worthwhile problems for his level.
- Q: Food and restaurant preferences beyond beer? → A: Hearty/casual — BBQ, burgers, Southern comfort, big portions. Post-climb/ride fuel over fine dining.

## Dependencies

- **Feature 001** (Primary Bouldering Areas): Required — climbing picks reference area profiles.
- **Feature 002** (Problem Clusters): Required — climbing picks drawn from curated problem lists with style/grade data.
- **Feature 003** (Parallel Activity Mapping): Required — trail wishlist references trail profiles and pairing data.
- **Feature 004** (Rest Day Pack): Recommended — food/drink targets may overlap or extend the rest-day guide.
- **Feature 005** (Conditions & Timing): Recommended — conditions notes inform ride and climb decisions.
- **Feature 006** (Logistics & Access): Recommended — personal logistics section complements but doesn't duplicate group logistics.
