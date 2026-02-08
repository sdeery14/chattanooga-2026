# Quickstart: Using Trail Profiles

## What Trail Profiles Are

Trail profiles are "where can I ride?" documents — one per trail system. Each contains trail details (difficulty, distance, ride time), conditions notes, access logistics, and which climbing areas are nearby. They are companion resources to the bouldering area profiles from Feature 001.

They are NOT exhaustive trail guides. They're curated summaries with enough information to make a go/no-go riding decision quickly.

## How They Relate to Climbing Area Profiles

Each trail profile links to nearby climbing areas. Each climbing area profile links to nearby trail profiles. The relationship is:

- **Climbing area profile** = "Should we climb here?" (overview, conditions, logistics)
- **Trail profile** = "Where can I ride nearby?" (trails, difficulty, pairing logistics)

The `trails/README.md` provides a quick-reference comparison table and a climbing-area pairing matrix.

## Before the Trip

1. **Scan the trail comparison table** in `trails/README.md` to understand riding options
2. **Note which trails pair with which climbing areas** using the pairing matrix
3. **Read trail profiles** for the 2-3 most likely riding destinations (conditions, logistics)
4. **Identify rest-day rides** near lodging (Enterprise South Nature Park is at the doorstep)

## During the Trip

### "The group is climbing at Stone Fort. Where can I ride?"

1. Open `trails/README.md`
2. Find Stone Fort in the climbing-area pairing matrix
3. See which trail systems are within ~30 min drive
4. Open the trail profile for details (difficulty, conditions, parking)

### "It's a rest day. What are the best rides near the Airbnb?"

1. Open `trails/README.md`
2. Look for trail systems with shortest drive from lodging
3. Enterprise South Nature Park is at the lodging — zero-drive option
4. Pick based on difficulty, distance, and conditions

### "It rained last night. Can I still ride?"

1. Check the trail profile's conditions section for drainage notes
2. Look for trails noted as "drains well" or "rideable in wet conditions"
3. Avoid trails flagged as "mud-prone" or "clay soil"

### "I want to ride near HP40 instead of driving back to Chattanooga."

1. Open `trails/README.md` climbing-area pairing matrix
2. Find HP40 row — see nearby trail options in Alabama
3. If no nearby trails exist, the matrix honestly states this and suggests alternatives

## File Layout

```
trails/
├── README.md                ← Comparison table + climbing-area pairing matrix
├── enterprise-south.md      ← Trail profile (at lodging)
├── raccoon-mountain.md      ← Trail profile
├── {other-systems}.md       ← Additional trail profiles
└── ...

areas/
├── stone-fort.md            ← Existing area profile (gains "Nearby MTB" link)
├── rocktown.md              ← Existing area profile (gains "Nearby MTB" link)
└── ...
```

## Reading a Trail Profile Entry

Each trail profile contains:

- **Header metadata**: location, drive time, nearby climbing links
- **Overview**: what kind of riding and why it's notable
- **Trails & Difficulty**: key routes with distance and ride time
- **Conditions**: February concerns, drainage, shade/sun
- **Access & Logistics**: parking, fees, open/closed status
- **Sources**: where the data comes from
