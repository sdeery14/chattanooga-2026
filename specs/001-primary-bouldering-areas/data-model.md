# Data Model: Primary Bouldering Areas

**Phase 1 output for Feature 001** | **Date**: 2026-02-08

## Entities

### Bouldering Area (one Markdown file per area)

Each area profile follows the structured template defined in FR-011.
Fields map directly to the template sections.

| Field | Required | Type | Description | Validation |
|-------|----------|------|-------------|------------|
| Name | MUST | Text | Full area name with common nicknames | Non-empty; unique across all profiles |
| Tier | MUST | Enum | `primary`, `supplementary`, `brief` | Determines profile depth expectation |
| Overview | MUST | Paragraph | What makes the area notable; who it best serves | 2–4 sentences max |
| Hard Appeal (V7–V10) | MUST | Bullets | Concentration, classic problems, style | Density descriptor required: outstanding/excellent/strong/moderate/limited/minimal/negligible |
| Grade Density: V0–V3 | MUST | Bullets | Easy climbing availability | Density descriptor required: abundant/moderate/limited/nearly nonexistent |
| Grade Density: V4–V6 | MUST | Bullets | Moderate climbing availability | Same descriptors as above |
| Conditions | MUST | Bullets | Shade/sun, humidity, elevation, wind, best time | Must reference February context |
| Logistics | MUST | Bullets | Drive time from ESNP, parking, approach length | Drive time must be from Enterprise South Nature Park |
| Access | MUST | Bullets | Ownership, fees, permits, closures, etiquette | Must flag any barriers to entry |
| Style & Body-Type Notes | SHOULD | Bullets | Climbing style, reachy/compression/technical | Informational; omit if unknown |
| Sources | MUST | Links/refs | Guidebooks, Mountain Project, databases | At least one source per area; unverified claims flagged |

**Density Descriptors** (canonical terms per FR-003):

- **abundant** — deep selection; you won't run out in a session
- **strong** — solid options; good variety
- **moderate** — decent options exist but not the area's strength
- **limited** — a few problems; will exhaust quickly
- **nearly nonexistent** — essentially nothing at this grade range
- For V7–V10 specifically: **outstanding**, **excellent**, **strong**,
  **moderate**, **limited**, **minimal**, **negligible**

### Ability Band

| Band | Grade Range | Label | Target Climber |
|------|-------------|-------|----------------|
| Easy | V0–V3 | easy | V0–V1 climbers |
| Moderate | V4–V6 | moderate | ~V5 climbers |
| Hard | V7–V10 | hard | ~V10 climbers |

### Comparison Reference (areas/README.md)

Single Markdown table with one row per area. Columns:

| Column | Description |
|--------|-------------|
| Area | Name (linked to profile file) |
| Drive | Minutes from ESNP |
| V7–V10 | Density descriptor |
| V4–V6 | Density descriptor |
| V0–V3 | Density descriptor |
| Feb Conditions | Key conditions note for trip window |
| Access/Fees | Quick summary (free, $X, permit, etc.) |
| Style | 2–3 word style summary |

## Relationships

```
Comparison Reference (README.md)
  └── links to → Bouldering Area profiles (1 per .md file)
       └── references → Ability Bands (shared vocabulary)
```

## File Naming Convention

Area profile files use kebab-case: `{area-name}.md`
Examples: `stone-fort.md`, `hp40.md`, `dayton-pocket.md`
