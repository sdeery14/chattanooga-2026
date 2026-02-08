# Quickstart: Using Problem Clusters

## What Problem Clusters Are

Problem clusters are curated "what can I climb here?" documents — one per area. Each contains 15–40 recommended problems organized by ability band (V0–V3, V4–V6, V7–V10), grouped by proximity so you can find things to climb near where you're standing.

They are NOT exhaustive tick lists. They're shortlists of the best problems at each area, selected for classic status and quality.

## How They Relate to Area Profiles

Each problem cluster is a companion document to an area profile (Feature 001):

- **Area profile** = "Should we go here?" (overview, conditions, logistics, access)
- **Problem cluster** = "What should I climb here?" (specific problems by grade)

The area profile links to its problem cluster. The problem cluster links back to the area profile.

## Before the Trip

1. **Scan the comparison table** in `areas/README.md` to narrow down areas
2. **Read area profiles** for areas you're likely to visit (conditions, access)
3. **Browse problem clusters** for those areas to build mental tick lists by grade band
4. **Note proximity groups** — which sub-areas concentrate problems at your level?

## During the Trip

### "We just arrived at Stone Fort. What should I climb?"

1. Open `areas/stone-fort-problems.md`
2. Find your grade band section (V7–V10, V4–V6, or V0–V3)
3. Scan the proximity groups — problems are organized by sub-area
4. Pick a starting zone based on approach time and problem density

### "Conditions changed — sun hit the wall. What's still climbable?"

1. Scan for conditions flags in the problem cluster: look for **shaded**, **sheltered**, **overhung**
2. Check the conditions quick reference at the bottom of the cluster (Tier 1 areas)
3. Move to the sub-area with the best conditions match

### "I climb V5 and the V10 climber is projecting at the Main Area. What's nearby for me?"

1. Open the problem cluster, go to V4–V6 section
2. Find the proximity group matching where the hard climbing is happening (e.g., "Main Area")
3. Pick from the moderate problems in that same zone

### "The V0 climber wants to know if there's anything for them."

1. Open the problem cluster, go to V0–V3 section
2. Read the band density summary at the top of the section — it honestly states whether easy climbing is abundant, moderate, limited, or thin
3. If limited: the summary suggests alternatives (spotting, hiking, exploring)

## File Layout

```
areas/
├── stone-fort.md              ← Area profile
├── stone-fort-problems.md     ← Problem cluster (this feature)
├── rocktown.md
├── rocktown-problems.md
├── hp40.md
├── hp40-problems.md
├── dayton-pocket.md
├── dayton-pocket-problems.md
├── zahnd-tract.md
├── zahnd-tract-problems.md
├── hospital-boulders.md
├── hospital-boulders-problems.md
├── waldens-ridge.md
├── waldens-ridge-problems.md
├── dogwood.md                 ← No cluster (insufficient data)
├── sunset-rock.md             ← No cluster (Tier 3)
├── hells-kitchen.md           ← No cluster (Tier 3)
└── README.md                  ← Comparison table (update with cluster links)
```

## Reading a Problem Entry

Each problem entry looks like:

```
- **Grimace** (V8) — Sloper climbing at its finest. Body tension and open-hand grip.
  _Needs cold/dry conditions._ [Stone Fort 3rd Ed., MP]
```

Breaking it down:
- **Name** (Grade) — always present
- Style notes — what the climbing is like
- Body-type note — if one exists (reachy, short-friendly, etc.)
- _Conditions flag_ — in italics when present
- [Source] — where the data comes from
