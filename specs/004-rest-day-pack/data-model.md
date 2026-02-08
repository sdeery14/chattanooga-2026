# Data Model: Rest Day & Low-Energy Decision Pack

**Feature**: 004-rest-day-pack | **Date**: 2026-02-08

## Entities

### Rest-Day Option

A pre-vetted activity or destination suitable for a rest or low-energy day.

| Field | Required | Format | Description | Constraints |
|-------|----------|--------|-------------|-------------|
| Name | MUST | Bold text | Activity or destination name | Canonical name from primary source |
| Energy Tier | MUST | Section placement | Zero / Low / Active | Determines which section the option appears in |
| Type | MUST | Inline | Category (restaurant, brewery, hike, museum, etc.) | — |
| Location | MUST | Inline | Neighborhood or area | — |
| Drive from Lodging | MUST | Inline | Minutes from Enterprise South Nature Park | Same reference point as climbing/trail profiles |
| Description | MUST | Text | 1-2 sentence summary of what to expect | Decision-oriented, not promotional |
| Hours | SHOULD | Inline | Operating hours, especially February/winter | Flag seasonal changes |
| Cost | SHOULD | Inline | Free / $ / $$ / $$$ / $$$$ | Rough range, not exact prices |
| Weather-Proof | SHOULD | Tag | Yes / No / Partial | Whether viable in rain |
| Source | MUST | Link | Website, Google Maps, or community source | At least 1 verifiable source per FR-006 |

### Quick Decision Table

A summary table at the top of `rest-days/README.md` for rapid scanning.

| Column | Required | Description |
|--------|----------|-------------|
| Option | MUST | Name (not linked — all options are in the same document) |
| Energy | MUST | Zero / Low / Active |
| Type | MUST | Category (food, brewery, hike, museum, etc.) |
| Drive | MUST | Minutes from ESNP |
| Cost | SHOULD | Free / $ / $$ / $$$ |
| Rain-OK | MUST | Yes / No / Partial |
| Notes | SHOULD | 1-line context |

### Weather Alternative

Not a separate entity — weather alternatives are rest-day options tagged with `Rain-OK: Yes` and collected in a dedicated section for quick access during weather pivots.

## Document Structure

### Rest-Day Guide Template

```markdown
# Rest Days & Low-Energy Options

> Quick reference for non-climbing days. All drive times from Enterprise South Nature Park area (lodging).
> Trip dates: February 14–21, 2026.

## Quick Decision Table

| Option | Energy | Type | Drive | Cost | Rain-OK | Notes |
|--------|--------|------|-------|------|---------|-------|
| {Name} | {Zero/Low/Active} | {type} | ~{X} min | {$} | {Yes/No} | {1-line} |

## When It Rains

{Quick list of rain-proof options with cross-references}

---

## Zero-Energy Options

{Options requiring minimal effort — food, drink, lounging}

### {Option Name}

{Type} — {Location} (~{X} min from lodging)

{1-2 sentence description}

- **Hours**: {hours}
- **Cost**: {range}
- **Source**: [{name}]({url})

---

## Low-Energy Options

{Easy sightseeing, town walks, museums, scenic drives}

### {Option Name}

{Same format as above}

---

## Active-Rest Options

{Short hikes, easy rides (cross-ref to trails/), other moderate activities}

### {Option Name}

{Same format as above}

For mountain biking rest-day rides, see [Trail Comparison](../trails/README.md#rest-day-rides-top-3-near-lodging).

---

## Low-Energy Climbing Sessions

{Cross-references to existing area profiles for short, casual sessions}

For climbing area details, see [Bouldering Areas](../areas/README.md).

---

## Day Trips (~1 Hour)

{1-2 compelling destinations worth the drive}
```
