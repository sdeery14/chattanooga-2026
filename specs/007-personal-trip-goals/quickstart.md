# Quickstart: Personal Trip Goals & Preferences (Sean)

## What This Feature Produces

A single file: **`sean-guide.md`** at the repository root.

## How to Build It

1. Run `/speckit.tasks` to generate the task list
2. Run `/speckit.implement` to execute all tasks
3. The output is `sean-guide.md` — a personal decision-support document for Sean

## Key Inputs

- **Climbing picks**: Drawn from `areas/*-problems.md` (Feature 002), filtered for Sean's V1 outdoor / V4 gym level, 6'2" reach, power strengths, and knee/hip constraints
- **Trail rankings**: Drawn from `trails/*.md` (Feature 003), filtered for Jamis Faultline A2 (120/130mm trail bike) and athletic beginner flow/XC + skill-development goals
- **Food/drink**: Researched in `research.md` — IPA-focused breweries, BBQ/burgers/Southern comfort, coffee
- **Sights**: Researched in `research.md` — viewpoints, walks, oddities, shops, cultural spots
- **All cross-references**: Link to existing documents, never duplicate content

## How to Use the Guide (During Trip)

Open `sean-guide.md` and jump to the relevant section:
- **"What should I ride?"** → Mountain Biking section (ranked trail table)
- **"What should I climb here?"** → Climbing Projects → [Area Name]
- **"Where should we eat?"** → Food & Drink → Don't Miss tier
- **"What else can I do?"** → Sights & Experiences
- **"It's the last day, what matters most?"** → Priority Stack (top of document)

## Validation

After implementation, verify:
- [ ] Every cross-reference link resolves to an existing document
- [ ] Every climbing pick has landing quality + body constraint flags
- [ ] Every trail entry has drainage + bike suitability ratings
- [ ] No content duplicated from Features 001–006
- [ ] Priority stack has 10+ ranked cross-category items
- [ ] [UNVERIFIED] flags on all unverified information
