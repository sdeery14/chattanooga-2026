# Data Model: Area-Scoped Problem Clusters

**Phase 1 output for Feature 002** | **Date**: 2026-02-08

## Entities

### Problem Cluster (one Markdown file per area)

Each problem cluster is a companion document to an area profile from Feature 001. It contains curated problem recommendations organized by ability band.

| Field | Required | Type | Description | Validation |
|-------|----------|------|-------------|------------|
| Area Name | MUST | Text | Must match the parent area profile name | Links to `areas/{area-name}.md` |
| Header | MUST | Paragraph | 1–2 sentence area character summary for climbing, consistent with area profile | Non-empty |
| Link to Area Profile | MUST | Markdown link | Back-link to parent area profile | Valid relative link |
| V7–V10 Section | MUST | Section | Band header (1–2 sentences) + curated problem list | 5–15 problems where area supports it |
| V4–V6 Section | MUST | Section | Band header + curated problem list | 5–15 problems where area supports it |
| V0–V3 Section | MUST | Section | Band header + curated problem list | 5–15 problems where area supports it; honest if thin |
| Sources | MUST | Links/refs | Guidebooks, databases cited | At least one source |

### Problem Entry (within a grade band section)

Each problem is listed within a proximity group under its grade band.

| Field | Required | Type | Description | Validation |
|-------|----------|------|-------------|------------|
| Name | MUST | Text | Problem name as listed in primary source | Non-empty |
| V-Grade | MUST | Text | V-scale grade (e.g., V7, V8/V9) | V-scale format; note discrepancies |
| Location | MUST | Text | Boulder name or sub-area | Matches known sub-area names |
| Style Notes | SHOULD | Text | Movement style (compression, crimps, slab, etc.) | Omit if unknown |
| Body-Type Notes | SHOULD | Text | Reachy, short-friendly, compression-favors-wingspan | Only when sourced |
| Conditions Flags | SHOULD | Tags | shaded, sheltered, seepage-prone, friction-dependent, sun-exposed | Only when known |
| Source | MUST | Text | Guidebook, MP, KAYA, etc. | At least one source per problem |
| Flags | MAY | Text | [UNVERIFIED], [BROKEN HOLD], grade discrepancy notes | Where applicable |

### Proximity Group (within a grade band section)

Problems are grouped by physical proximity — same boulder or same sub-area.

| Field | Required | Type | Description |
|-------|----------|------|-------------|
| Group Name | MUST | Text | Sub-area name or boulder name (e.g., "Main Area", "Skywalker Area") |
| Walk from Parking | SHOULD | Text | Approximate time from parking (e.g., "~5–10 min") |

## Document Structure Template

```markdown
# {Area Name}: Problem Clusters

> **Area Profile**: [{Area Name}]({area-name}.md)
> Brief area character summary (1–2 sentences)

## V7–V10 (Hard)

> Band density summary (1–2 sentences from area profile)

### {Sub-Area / Proximity Group} (~X min from parking)

- **Problem Name** (VX) — Style notes. _Conditions flag._ [Source]
- **Problem Name** (VX) — Style notes. Body-type note. [Source]

### {Another Proximity Group}

- ...

## V4–V6 (Moderate)

> Band density summary

### {Proximity Group}

- ...

## V0–V3 (Easy)

> Band density summary

### {Proximity Group}

- ...

## Sources

- [Source 1]
- [Source 2]
```

## Relationships

```
Area Profile (areas/{name}.md, Feature 001)
  └── links to → Problem Cluster (areas/{name}-problems.md, Feature 002)
       └── contains → Grade Band Sections (V7–V10, V4–V6, V0–V3)
            └── contains → Proximity Groups
                 └── contains → Problem Entries

Comparison Reference (areas/README.md, Feature 001)
  └── may link to → Problem Clusters (update links)
```

## File Naming Convention

Problem cluster files: `{area-name}-problems.md` (kebab-case, matching area profile)
Examples: `stone-fort-problems.md`, `hp40-problems.md`, `dayton-pocket-problems.md`

## Cluster Counts per Area

| Area | V0–V3 Target | V4–V6 Target | V7–V10 Target | Total Cap |
|------|-------------|-------------|--------------|-----------|
| Stone Fort | ~9 | ~12 | ~12 | ≤40 |
| Rocktown | ~10 | ~10 | ~12 | ≤40 |
| HP40 | ~10 | ~12 | ~12 | ≤40 |
| Dayton Pocket | ~2 (honest) | ~3 | ~10 | ≤20 |
| Zahnd Tract | ~1 (honest) | ~2 | ~8 | ≤15 |
| Hospital Boulders | ~8 | ~8 | ~3 | ≤25 |
| Walden's Ridge | ~1 (honest) | ~10 | ~1 | ≤15 |
