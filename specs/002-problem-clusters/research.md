# Research: Area-Scoped Problem Clusters

**Phase 0 output for Feature 002** | **Date**: 2026-02-08

## Research Decisions

### Decision 1: Which areas get problem clusters?

- **Decision**: Tier 1 (mandatory): Stone Fort, Rocktown, HP40. Tier 2 (conditional): Dayton Pocket, Zahnd Tract, Hospital Boulders, Walden's Ridge. Excluded: Dogwood (insufficient data), Sunset Rock (Tier 3), Hell's Kitchen (Tier 3).
- **Rationale**: Dogwood has 100+ problems but all data is locked behind the Rakkup guidebook (paid, app-only). Zero named problems with grades found through any web source. Cannot build a curated cluster without the guidebook.
- **Alternatives considered**: Including Dogwood with [UNVERIFIED] tags — rejected because the spec requires each listed problem to have name, V-grade, and location (FR-005), and we have none.

### Decision 2: How to handle thin V0–V3 data at some areas?

- **Decision**: Include V0–V3 sections even when thin (2–3 problems), with honest framing about data limitations and a note to consult the area profile for general easy-climbing density assessment. Supplement with guidebook data where referenced but not directly accessible.
- **Rationale**: Consistency across clusters matters more than forcing a minimum count. A V0 climber is better served by "here are the 2 named easy problems we know about" than by omitting the section entirely.
- **Alternatives considered**: Omitting V0–V3 sections when fewer than 5 problems — rejected because it would hide the information entirely from easy climbers.

### Decision 3: Problem selection criteria

- **Decision**: Curate by classic status (star ratings, ascent count, community consensus), quality of movement, and proximity to other listed problems. Cap at ~15 per band, ~40 total per area.
- **Rationale**: Aligns with FR-004 (5–15 per band) and SC-006 (40 max). Star ratings and ascent counts from KAYA/Mountain Project are the best available proxy for "classic" status.
- **Alternatives considered**: Using only guidebook "must-do" lists — rejected because not all guidebooks are accessible and online community data adds valuable signal.

### Decision 4: Source hierarchy for grade discrepancies

- **Decision**: Use most recent guidebook grade as primary where available. Note Mountain Project / KAYA consensus when it meaningfully differs (+/- 1 grade). Flag stiff/sandbagged grading culture at HP40 explicitly.
- **Rationale**: Guidebooks represent curated editorial judgment; online databases represent crowd consensus. Both are useful; guidebook takes precedence for the "official" grade listed.
- **Alternatives considered**: Using only Mountain Project grades — rejected because guidebook authors have deeper area knowledge and more consistent grading philosophy.

### Decision 5: Proximity grouping approach

- **Decision**: Use sub-area names from guidebooks/Mountain Project as the primary grouping unit. Within each grade band, problems are organized by proximity group (same boulder or same sub-area), not alphabetically.
- **Rationale**: FR-012 requires proximity-based grouping. Sub-area names provide meaningful geographic anchors that translate to "I'm standing here, what else is nearby?"
- **Alternatives considered**: Free-form location descriptions — rejected because sub-area names are more searchable and consistent with guidebook navigation.

### Decision 6: Conditions flags approach

- **Decision**: Include conditions flags only when specifically documented (shaded, sheltered/overhung, seepage-prone, friction-dependent, sun-exposed). Do not guess.
- **Rationale**: FR-008 says SHOULD, not MUST. The spec edge case section explicitly says "Omit the conditions flag rather than guessing." We have good conditions data for Tier 1 areas and spotty data for Tier 2.
- **Alternatives considered**: Inferring conditions from aspect/elevation — rejected per spec guidance against speculation.

---

## Unverified Items

1. [UNVERIFIED] Stone Fort walking times from parking to sub-areas (estimated from descriptions, not GPS-measured)
2. [UNVERIFIED] Dayton Pocket V0–V3 problem count — web sources show only 2 named problems; ChattBloc 2nd Ed. likely has more
3. [UNVERIFIED] Zahnd Tract V0–V6 problem data — Caffeine and Climbing guide is the primary source and was not directly accessed
4. [UNVERIFIED] Hospital Boulders hard climbing above V7 — only 3 problems confirmed (Eddie V7, Smash Alley V8, Hustle and Flow V10)
5. [UNVERIFIED] Walden's Ridge V7–V10 beyond God's Gas V7 — "V8 Juice" boulder name suggests harder problems may exist
6. [UNVERIFIED] Several HP40 problems have unconfirmed sub-area placement (Crisifix V5, Consumption V8)
7. [UNVERIFIED] Stone Fort Instinct grade — V7 in older sources, V9 in current Mountain Project

---

## Cluster Viability Assessment

| Area | Tier | V0–V3 | V4–V6 | V7–V10 | Cluster? | Notes |
|------|------|-------|-------|--------|----------|-------|
| Stone Fort | 1 | 9 problems | 14 problems | 16 problems | YES (mandatory) | Deepest data set across all bands |
| Rocktown | 1 | 10 problems | 12 problems | 13 problems | YES (mandatory) | Strong across all bands |
| HP40 | 1 | 11 problems | 15 problems | 14 problems | YES (mandatory) | Deepest hard climbing data |
| Dayton Pocket | 2 | 2 problems | 3 problems | 11 problems | YES | Strong V7–V10; V0–V3 thin |
| Zahnd Tract | 2 | 0–1 problems | 2 problems | 8 problems | YES (V7–V10 focus) | Lower bands need guidebook |
| Hospital Boulders | 2 | 8 problems | 8 problems | 3 problems | YES | Best Tier 2 data overall |
| Walden's Ridge | 2 | 1 problem | 13 problems | 1 problem | YES (V4–V6 focus) | Strong moderate; thin at extremes |
| Dogwood | 2 | 0 | 0 | 0 | NO | Data locked in Rakkup guidebook |
| Sunset Rock | 3 | — | — | — | NO (FR-003) | Tier 3 — excluded per spec |
| Hell's Kitchen | 3 | — | — | — | NO (FR-003) | Tier 3 — excluded per spec |

---

## Area Research Data

### Stone Fort (LRC)

#### Sub-Area Layout

| Sub-Area | Walk from Parking | Character |
|----------|-------------------|-----------|
| Front Area | ~5 min | First boulders; Wave Boulder, Castle Boulder, Genghis Khan |
| Main Area | ~5–8 min | Open, sunny, dries fast; Tristar, Crack of Doom, Sternum cluster |
| Sternum Area | ~8–10 min | Corridor opposite Crack of Doom; Sternum Boulder, White Face |
| Super Mario Area | ~10 min | Near-cliff; Super Mario, Cleopatra |
| Jungle Gym | ~10 min | Gulley with stream; Jerry's Kids, Fat Cat. Damper microclimate |
| Now and Zen Area | ~12–15 min | Hidden corridor; Now and Zen, Dr. Atkinson |
| Back Nine | ~15+ min | Farthest; Instinct, Cyclops |

#### V0–V3 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| Spare | V0 | Front Area | Short slab | All body types |
| Uncle Punchy | V0 | Main Area | Flakes | Open, sunny |
| The Crescent | V1 | Front Area | Seam feature | All body types |
| Fire Crack Flake | V1 | Front Area | Crack/flake | — |
| Storming the Castle | V1 | Front Area | Vertical wall, PG-13 for height (~35 ft) | Height helps; committing topout |
| Mystery Groove | V2 | Front Area | Delicate, balancy | Short + tall beta both work |
| Block and Tackle | V0–V2 | Main Area | Slab crux to jug | Grade debated (V0–V2) |
| Swingers | V3 | Front/Main | Dynamic | V3/V4 border |
| Ribcage | V3 | Sternum Area | Sit start, roof to mantle | Near Sternum V5 + White Face V10 |

Source: Mountain Project, KAYA, OpenBeta, Stone Fort Bouldering 3rd Ed.

#### V4–V6 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| Black Carpet | V4 | Front Area | Face | Often wet/seepy — check early |
| Tristar | V4 | Main Area | Face, first-move crux | Multiple beta options |
| Art of the Vogi | V4 | Main Area | Technical face | — |
| Prison Planet | V4 | Main Area | — | — |
| Super Mario | V4 | Super Mario Area | Cave sit start, kneebar | Iconic |
| Genghis Khan | V5 | Front Area | Sustained | No rest |
| Crack of Doom | V5 | Main Area | Splitter hand crack | Hand size matters |
| Sternum | V5 | Sternum Area | Roof/mantle | Next to Ribcage V3 |
| Golden Shower | V5 | Main Area | — | — |
| Fat Cat | V5 | Jungle Gym | Pockets, sidepulls, slopers | Damper area |
| The Wave | V6 | Front Area | Slopey arete, core tension | Technique > reach; 3.9/4 stars, must-do |
| Shotgun | V6 | Shotgun Area | Pocketed face | — |
| Cyclops | V6 | Back Nine | Powerful | Longest walk |
| Super Mario Ext. | V6– | Super Mario Area | Extension of V4 | Soft for grade |

Source: Mountain Project, KAYA, OpenBeta, Sendage, Stone Fort Bouldering 3rd Ed.

#### V7–V10 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| Tennessee Thong | V7 | Front Area | — | Close to parking |
| Spyro Gyro | V7 | Front Area | Cool holds, hard moves | — |
| Poison Ivy | V7 | Front Area | Traverse into Black Carpet | Needs dry conditions |
| Celestial Mechanics | V7 | Main Area | Dynamic, big move | Height-dependent; pad stacking for short |
| A Face in the Crowd | V7 | Main Area | — | Faces Grimace |
| Sherman Photo Roof | V7 | Main Area | Roof, undercling to crimp | — |
| Now and Zen | V7 | Now and Zen Area | Pinches, crimps, sidepulls | Shaded corridor |
| Red House Extension | V7–V8 | Main Area | Linkup; greatest-hits compilation | Grade varies by source |
| Jerry's Kids | V7 | Jungle Gym | Tall, committing mantle | Damper area |
| Grimace | V8 | Main Area | Sloper climbing | Needs cold/dry; near Crack of Doom |
| The Orb | V8 | Main Area | Sit start, sloping pinches, mantle | Body tension |
| Cleopatra | V8 | Super Mario Area | — | Near Super Mario V4 |
| Ace of Spades | V9 | Main Area | — | — |
| Bedwetters | V9 | Sternum/Main | Roof, compression | Bad landing — lots of pads |
| Instinct | V9/V10 | Back Nine | — | Grade discrepancy (V7/V9/V10) |
| White Face | V10 | Sternum Area | Credit card crimping | Near Ribcage V3 + Sternum V5 |

Source: Mountain Project, KAYA, Climbing Magazine, Sendage, Stone Fort Bouldering 3rd Ed.

#### Conditions Quick Reference

| Condition | Best Zones | Avoid |
|-----------|-----------|-------|
| After rain | Main Area (sunny, dries fast) | Black Carpet, Jungle Gym |
| Humid/warm | Shaded corridors: Now and Zen, Jungle Gym | Open areas; slopers (Grimace, Orb, Wave) |
| Cold/dry (ideal Feb) | Everything — prime sloper season | Nothing |
| Windy | Main Area, Front Area (wind-assisted drying) | Corridors get no wind |

---

### Rocktown

#### Sub-Area Layout

| Zone | Approach Time | Key Features |
|------|--------------|-------------|
| Orb Area / Front Corridor | 5–10 min | The Orb, Soap on a Rope, Burst Boulder |
| Sherman Roof | 8–12 min | Sherman Photo Roof, Nose Candy |
| Hueco Simulator | 10–15 min | Mario variants, Belly Button — warm-up hub, sun-exposed |
| The Maze (Lower/Middle/Upper) | 15–25 min | Asphalt Boulders, Lab Rats, Tractor Traylor |
| Comet Area | 15–20 min | Always shaded, iron rails stay cool |
| The Valley | 15–20 min | Golden Harvest, Golden Shower |
| Helicopter Area | 20+ min | Inspired by an Idiot |

#### V0–V3 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| Goforia | V0 | Goforia Corridor | Slab, horizontal rail | All body types |
| Makin' Waves | V1–V2 | Hueco Simulator | Juggy warm-up | Sun-exposed |
| King Cobra | V2 | Middle Maze | Sit start, pockets to arete | Less crowded |
| The Scoop | V2 | Scoop Area | Balance, pocket finish | Reach helps for top |
| Ripple | V2 | The Maze | Face on good edges | Sheltered |
| Super Mario | V3 | Hueco Simulator | Pinches, slopers | Sun-exposed |
| Belly Button | V3 | Hueco Simulator | Mono feature | Sun-exposed |
| El Bano | V3 | Asphalt Area | Iron rail, crimp, sloper topout | V2–V4 variants |
| Triple Slaps | V3 | Police Brutality Boulder | Classic moderate | Deeper in field |
| The Standard | V3 | Comet Boulder | Crimp test | Always shaded |

Source: Mountain Project, KAYA, theCrag, Rocktown guidebook (Kearney/Roper)

#### V4–V6 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| Soap on a Rope | V4 | Orb Area | Arete, tricky topout | Close to parking |
| Pythagorean Theorem | V5 | Asphalt Boulders | Undercling to triangle hold | Trailside in Maze |
| Golden Shower | V5 | The Valley | Sidepull slaps, committing topout | Most popular boulder at Rocktown; friction-sensitive |
| Breaking and Entering | V5 | Orb Area | Roof to awkward crux | Close to parking |
| Pinch Loaf | V5 | Asphalt Boulders | Pinch-intensive | Near Pythagorean |
| Police Brutality | V5 | Police Brutality Boulder | Classic | Deeper in field |
| The Variation | V5 | Comet Boulder | Iron rail crimps | Always shaded |
| Standard Deviation | V6 | Comet Boulder | Iron rail crimps, swoopy | Always shaded; go-to V6 |
| Lab Rats | V6 | The Maze | Sharp sidepull, slopers | Easier if tall |
| Nose Candy | V6 | Sherman Roof | Crimps and pinches | Near Sherman Photo Roof |
| Pullin' Tubes | V6 | Asphalt Boulders | Part of Asphalt cluster | Near Pinch Loaf |
| Inspired by an Idiot | V6 | Helicopter Area | Roof problem | Sheltered; 20+ min approach |

Source: Mountain Project, KAYA, theCrag, Sendage, Rocktown guidebook

#### V7–V10 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| Sherman Photo Roof | V7 | Sherman Roof | Roof, undercling to crimp | Sheltered cave |
| The Comet | V7 | Comet Boulder | Dyno, iron rails | Always shaded; V6 on Sendage |
| Iron Claw | V7 (sit: V9) | The Valley | Improbable heel hooks | Needs dry conditions; lots of pads |
| The Orb | V8 | Orb Area | Slopers, compression, mantle | Most famous problem in the South; friction-dependent |
| The Vagina | V8 | Front Corridor | Overhang | Sheltered between boulders |
| Brown Hole | V8 | The Maze | Cave start to pocket | May favor reach; sheltered start |
| Tractor Traylor | V8 | The Maze | Slab to roof | Quieter area |
| Burst of Joy | V9 | Orb Area | Power + technical blend | Close to parking |
| B-Cubed | V9 | Front Corridor | Shallow holds, body tension | Close to parking |
| Blackout | V9 | Front Area | Hard holds, powerful | Close to parking |
| Sherman Roof Traverse | V9 | Sherman Roof | Full traverse, endurance | Sheltered |
| Iron Claw Sit | V9 | The Valley | Extended sit start | Dry spell required |
| Golden Harvest | V10 | The Valley | Slopers, sidepulls, tension | Best problem in the Southeast; cold/dry essential |

Source: Mountain Project, KAYA, theCrag, Sendage, Rocktown guidebook

#### Key Tactical Note

Golden Harvest V10 shares a boulder with Golden Shower V5 — the Valley is a natural mixed-ability destination. The Comet Boulder covers V3–V7 in one always-shaded spot.

---

### HP40

#### Sub-Area Layout

| Zone | Location | Key Features |
|------|----------|-------------|
| Upper Boulders | Near parking/campground | Skywalker Area (Merlin, Genesis, Skywalker), Sandbox, Hammerhead, Ten Pins (Popeye) |
| Lower Boulders | Downhill from parking | Cadillac Thrills, Slider, Mulletino, Millipede/Great White, Redneck |
| Flow Area | Middle section | The Flow |

All problems within short walk of parking — the entire park is compact.

#### Grading Culture

HP40 grades are widely considered **stiff/sandbagged**. A V8 at Stone Fort may feel like V7 at HP40. Bumboy V3 is the famous litmus test — many V5 climbers cannot send it. Sloper/compression style inflates perceived difficulty for climbers from crimp-heavy areas.

#### V0–V3 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| Silky | V0 | Upper | Perfect warm-up | All body types |
| Merlin | V1 | Skywalker Area | Highball slab, rippled face | 4.7/5 KAYA — highest rated at HP40 |
| Ketchup | V1 | Upper | Intro to highballs | Committing |
| Sandbox | V2 | Upper | Sandy arete to beach mantle | V5 sit start variant |
| Copa Cabana | V2 | Upper | Short overhanging arete | 4.3/5 KAYA |
| Wasp | V2 | Upper | Honeycomb pinches, tough topout | Mantle skills |
| Eight Ball | V2 | Upper | HP40 topout experience | Mantle-dependent |
| Red Arrow | V3 | Lower (Cadillac Thrills) | Sloper topout warm-up | Same boulder as Cadillac Thrills V9 + Hot 'N Tot V10 |
| Bumboy | V3 | Lower | Pods, runnel, slopers | STIFF — many V5 climbers fail. Friction canary. 4.6/5, 127 ascents |
| Genesis | V3 | Skywalker Area | Undercling to pocket | Reachy — favors taller climbers |
| Boogey Wonderland | V3 | Front Slabs | Approachable V3 | Somewhat sheltered |

Source: Mountain Project, KAYA, Every Last Rock, Sendage, HP40 guidebook (Adam Henry)

#### V4–V6 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| Honky Tonkin' | V4 | Upper | Amazing arete | Technique > body type |
| The Beach | V4 | Upper | Arete with heelhooks | Hip flexibility |
| Lowdown | V4 | Lower | Roof to mantle | Sheltered — good in rain/sun |
| Mortal Kombat | V4 | Lower | Technical arete | Precision footwork |
| Man With a Slow Hand | V4 | Lower | Classic HP40 line | — |
| Hammerhead | V5 | Upper | Arete, endurance | 4.4/5 KAYA; save energy for top |
| Popeye | V5 | Upper (Ten Pins) | Water groove intro | Body tension; quintessential HP40 |
| Sandbox Sit | V5 | Upper | Compression sit start of V2 | Strong squeeze |
| Mulletino | V5 | Lower (near road) | Powerful, sketchy topout | Committing |
| Cuts Like a Knife | V5 | Lower | Shares finish with Litz Pocket V7 | — |
| Millipede | V5 | Lower | HP40's best squeeze problem | Shorter climbers/strong squeeze may have advantage |
| Crisifix | V5 | [unconfirmed] | — | — |
| Trick or Treat | V6 | Upper | Technical | Shaded |
| Redneck | V6 | Lower | Iron cross, dynamic | Reachy — wingspan favors |
| Stepchild | V6/V7 | Upper | — | V6 guidebook / V7 KAYA |

Source: Mountain Project, KAYA, Gripped Magazine, Every Last Rock, HP40 guidebook

#### V7–V10 Problems

| Problem | Grade | Sub-Area | Style | Body/Conditions Notes |
|---------|-------|----------|-------|----------------------|
| The Thief | V7 | Upper | Entry-level hard | Close to parking |
| Don't Rock My Boat | V7 | Upper | — | Close to parking |
| Great White | V7 | Lower | Compression, "meat-wrappiest" | 3 stars theCrag; near Millipede V5 |
| The Flow | V7 | Flow Area | Crimp start (unusual for HP40) + water groove + arete | Sheltered start under roof |
| Litz Pocket Problem | V7 | Lower | Roof, shallow pockets | Sheltered from weather |
| Skywalker | V8 | Skywalker Area | Compression to slopers — quintessential HP40 | Same area as Merlin V1 + Genesis V3 |
| Ghetto Superstar | V8 | Lower | Mixed crimps AND slopers | Wider style appeal |
| Lawdog | V8 | Lower | Powerful test piece | — |
| Consumption | V8 | [unconfirmed] | — | — |
| Slider | V9 | Lower (Slider Boulders) | Power endurance, crimps + slopers | Most iconic hard problem in SE; friction-dependent; skin-shredding |
| Cadillac Thrills | V9 | Lower (Cadillac Thrills) | Road-side | Same boulder as Red Arrow V3 + Hot 'N Tot V10 |
| No Tranquility | V9 | Lower | Competition classic | — |
| Hot 'N Tot | V10 | Lower (Cadillac Thrills) | Shares start with Cadillac Thrills V9 | Reachy crux |
| God Module | V11 | [unconfirmed] | Crimp + dynamic (unusual for HP40) | Included as area classic |

Source: Mountain Project, KAYA, Blue Ridge Outdoors, theCrag, HP40 guidebook

#### Proximity Circuits (Mixed-Ability Groups)

**Skywalker Area** (all within steps): Silky V0, Merlin V1, Genesis V3, Skywalker V8
**Cadillac Thrills Boulder** (same boulder): Red Arrow V3, Cadillac Thrills V9, Hot 'N Tot V10
**Millipede/Great White Cluster**: Millipede V5, Cuts Like a Knife V5, Great White V7, Litz Pocket V7

#### Conditions Notes

- Below 50F ideal for sloper friction
- Bumboy V3 = friction canary (if impossible, conditions are bad for all slopers)
- Sheltered options for marginal conditions: Litz Pocket V7 (roof), Lowdown V4 (under roof), The Flow V7 (starts under roof)
- Sandstone wears skin — plan rest days for multi-day sessions

---

### Dayton Pocket

#### V0–V3: 2 named problems (Head Smacking Sound V0, Tollbooth ~V3)
- Data is thin — ChattBloc 2nd Ed. likely has more
- Honest framing: limited named easy problems; the gorge hike and spotting are alternatives

#### V4–V6: 3 named problems (Bedrocker V4, Seduction V4, Reconciliation V5)
- Reconciliation is on the Vapor Roof — gateway to the signature feature

#### V7–V10: 11 named problems
- White Noise V7, Tommy Turns Tricks V7, Torpedo V7, Tavalin Shaft V7
- Peace Love and Smile V9, 300 V9, Dune Blasting V9, Riverdance V9, Creation of Adam V9
- Honeycomb V10, Wild Wild West V10
- Most hard climbing concentrated on Vapor Lock Cave (overhung/sheltered)
- Above V10: Standard Lines V11, Western Gold V11, Future Spray V11, Vapor Lock V11

Source: Mountain Project, 27crags, theCrag, KAYA, Betacache, ChattBloc 2nd Ed.

---

### Zahnd Tract

#### V0–V3: 0–1 named problems (Holy Forrest ~V3/V4 only)
- Area has 100+ problems but data is in Caffeine and Climbing guide

#### V4–V6: 2 named problems (Razors Edge V6, Razorback V6)

#### V7–V10: 8 named problems
- Rhino V7, Castle in the Sky V7, Harvest Moon V8, Pray Like a Mantis V9
- Harvest Moon Sit V9/V10, Rhino Low V10, Storm Crow V10, Ode to Austria V10
- Harvest Moon is the area's signature classic

Source: Mountain Project, KAYA, 8a.nu, RV Project, Caffeine and Climbing guide (referenced)

---

### Hospital Boulders

#### V0–V3: 8 named problems
- Nosey V1, Slippery When Wet V2, Saddle V2, Ballast V3, Scales V3, Gadfly V3, Hero V3, Ok Joe V0

#### V4–V6: 8 named problems
- Get Low V4, Low & Slow V4, Madness V5, Savage Problem V5, Angina V5, Mystified V5, Aggravated Assault I ~V5, Deadhead V6

#### V7–V10: 3 named problems
- Eddie V7, Smash Alley V8, Hustle and Flow V10
- Hard data above V7 is thin [UNVERIFIED]

Sub-areas: Barn Area, Eddie Area, Lower Area, Middle Area, Water Tower Area, Kill Taker Area

Source: Mountain Project, KAYA, 27crags, RV Project, SCC

---

### Walden's Ridge Park

#### V0–V3: 1 named problem (Ok Joe V0)
- Unnamed moderate slab at parking lot also described

#### V4–V6: 13 named problems
- Meathook V4, Handicap Parking V4, Epitaph V4, Isosceles V4, Circumference V4
- Overcrimp V5, Compact Car V5, Jet-Puffed V5, Eulogy V5, Stranger Danger V5, The Last Spot V5
- The Upside-Down V6, Double Parked Dually V6

#### V7–V10: 1 named problem (God's Gas V7)
- Minimal hard climbing; "V8 Juice" boulder name suggests more may exist

Sub-areas: Upper Parking Area, Falls Connector, Boy Scout Trail, Waterfall Area

Source: Mountain Project, KAYA, waldensridgepark.com

---

## Sources Summary

### Guidebooks (Primary)
- Stone Fort Bouldering, 3rd Ed. — Andy Wellman
- Rocktown Bouldering — Sean Kearney & Zak Roper (Wolverine Publishing, 2nd Ed.)
- HP40 Bouldering — Adam Henry (Rockery Press)
- ChattBloc, 2nd Ed. — Gentry, Jenkins, Drumm (Rockery Press, 2024)
- Caffeine and Climbing — Zahnd Tract guide (referenced, not directly accessed)
- Dogwood Guidebook — Leblanc/Gentry on Rakkup (not accessed — paid, app-only)

### Online Databases
- Mountain Project, KAYA, theCrag, 27crags, OpenBeta, Sendage, 8a.nu, Betacache

### Community / Editorial
- Southeastern Climbers Coalition (area access info)
- Every Last Rock, Gripped Magazine, Blue Ridge Outdoors, Climbing Magazine
- MadBoulder (beta videos), RV Project (trip reports)
