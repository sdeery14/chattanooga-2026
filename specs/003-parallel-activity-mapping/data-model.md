# Data Model: Parallel Activity Mapping

**Feature**: 003-parallel-activity-mapping | **Date**: 2026-02-08

## Entities

### Trail System Profile

A structured document describing one mountain biking trail destination.

| Field | Required | Format | Description | Constraints |
|-------|----------|--------|-------------|-------------|
| Name | MUST | H1 heading | Trail system name | Canonical name from primary source |
| Location | MUST | Blockquote metadata | City/area, state | — |
| Drive from Lodging | MUST | Blockquote metadata | Minutes from Enterprise South Nature Park | Same reference point as climbing areas |
| Nearby Climbing | MUST | Blockquote metadata | Link(s) to paired climbing area profiles | Drive time between trail and climbing area |
| Difficulty Range | MUST | Section | IMBA ratings or local system with key noted | Note if local system differs from IMBA |
| Total Trail Miles | MUST | Section | Approximate rideable distance | — |
| Ride Time | MUST | Section | Estimated time for representative loop(s) | Note skill-dependent variance if significant |
| Style / Character | SHOULD | Section | Flow, technical singletrack, XC, gravel, etc. | — |
| Conditions | SHOULD | Section | Drainage, February concerns, shade/sun | Only include what's sourced |
| Access & Logistics | MUST | Section | Parking, fees, February open/closed status | Flag closures with source |
| Sources | MUST | Section | Trail databases, park websites, community | At least 1 verifiable source per FR-004 |

### Climbing Area Pairing Matrix

A table in `trails/README.md` mapping each climbing area to its nearest trail systems.

| Field | Required | Format | Description |
|-------|----------|--------|-------------|
| Climbing Area | MUST | Link | Link to area profile in `areas/` |
| Nearest Trail(s) | MUST | Link + drive time | Trail system name with drive time from climbing area |
| Notes | SHOULD | Text | Brief context (e.g., "same direction from lodging", "requires separate drive") |

### Trail Comparison Table

A quick-reference table in `trails/README.md`, analogous to `areas/README.md`.

| Column | Required | Description |
|--------|----------|-------------|
| Trail System | MUST | Name with link to profile |
| Drive from Lodging | MUST | Minutes from ESNP |
| Miles | MUST | Total rideable trail distance |
| Difficulty | MUST | Range (e.g., green–black) |
| Style | SHOULD | Primary character (flow, tech, XC) |
| Feb Status | MUST | Open / Seasonal / Unknown |
| Fees | MUST | Free / $X / Unknown |
| Best Pairing | MUST | Which climbing area(s) this pairs with |

## Document Structure

### Trail System Profile Template

```markdown
# {Trail System Name}

> **Location**: {City/Area, State}
> **Drive from lodging**: ~{X} min from Enterprise South Nature Park area
> **Nearby climbing**: [{Climbing Area}]({area}.md) (~{X} min)

## Overview

{1-2 sentence description: what kind of riding, who it's for, why it's notable}

## Trails & Difficulty

{Difficulty range, key loops/routes with distance and estimated ride time}
{Note rating system if not standard IMBA}

## Conditions

{February-specific notes, drainage, shade/sun, mud tolerance}

## Access & Logistics

- **Parking**: {Location/address}
- **Fees**: {Free / $X per day / annual pass}
- **February status**: {Open year-round / seasonal closure risk / unknown}
- **Hours**: {If applicable}

## Sources

- {Trail database with link}
- {Park website}
```

## Trail Profile Counts

### Full Profiles (8)

| Trail System | Data Quality | Miles | Key Pairings |
|-------------|-------------|-------|-------------|
| Enterprise South Nature Park | HIGH | ~15 mi | All areas (zero-drive base) |
| White Oak Mountain | HIGH | ~25 mi | All areas (best drainage) |
| Raccoon Mountain | HIGH | ~28-30 mi | Stone Fort, Walden's Ridge |
| Walden's Ridge Park | HIGH | ~10 mi | Walden's Ridge bouldering (same location!) |
| Five Points | HIGH | ~20-25 mi | Rocktown, Zahnd Tract |
| Stringer's Ridge | HIGH | ~7 mi | Stone Fort (quick urban session) |
| Coldwater Mountain | HIGH | ~50-56 mi | HP40, Hospital Boulders |
| Chickamauga Battlefield | HIGH | ~27 mi | Always-rideable paved/gravel fallback |

### Brief Profiles (4)

| Trail System | Data Quality | Miles | Notes |
|-------------|-------------|-------|-------|
| Booker T Washington | HIGH | ~7.3 mi | Close to ESNP, lakeside, not wet-weather |
| Lookout Mountain (Moonshine/CCT) | MODERATE | ~8 mi | Descent-oriented, pairs with Five Points |
| Pigeon Mountain | LOW-MODERATE | ~12-15 mi | Near Rocktown, WMA access caveats |
| Oak Mountain State Park | HIGH | ~50 mi | IMBA Epic, too far for pairing, standalone only |
