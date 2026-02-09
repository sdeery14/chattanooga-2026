# Data Model: Personal Trip Goals & Preferences (Sean)

**Branch**: `007-personal-trip-goals` | **Date**: 2026-02-09 | **Spec**: [spec.md](spec.md)

## Overview

This feature produces a single markdown document (`sean-guide.md`) at the repository root. No database, no API — just structured markdown with consistent entity formats for each section. The data model defines the fields and format for each entity type so the guide stays consistent and scannable.

## Entity Definitions

### Climbing Pick

A specific boulder problem curated for Sean's physical profile.

| Field | Required | Format | Example |
|-------|----------|--------|---------|
| Problem Name | Yes | Text | Genesis |
| Grade | Yes | V-scale | V3 |
| Area | Yes | Text (matches Feature 001 area name) | HP40 |
| Sub-Area | Yes | Text | Skywalker Area |
| Walk from Parking | Yes | Minutes | ~5 min |
| Category | Yes | `send list` or `stretch goal` or `moonshot` | stretch goal |
| Why It Suits Sean | Yes | Short phrase | REACHY — favors taller climbers |
| Body/Safety Flags | If applicable | Emoji + text | ⚠️ Highball — assess landing for knee safety |
| Landing Quality | Yes | `Good` / `OK` / `Caution` / `WARNING` | Good |
| Link to Area Profile | Yes | Relative markdown link | [HP40](../../areas/hp40.md) |
| Link to Problem Cluster | Yes | Relative markdown link | [HP40 Problems](../../areas/hp40-problems.md) |

### Trail Target

A specific mountain bike trail system Sean wants to ride.

| Field | Required | Format | Example |
|-------|----------|--------|---------|
| Trail Name | Yes | Text | White Oak Mountain |
| Personal Rank | Yes | Number | 1 |
| Drive from Lodging | Yes | Minutes | 15–25 min |
| Total Miles | Yes | Number | ~25 mi |
| Ride Character | Yes | `Flow` / `Tech` / `Mixed` / `Gravity` | Flow |
| Ride Purpose | Yes | `Flow/Fun` / `Skill Development` / `Both` | Both |
| Bike Suitability | Yes | `Perfect` / `Adequate` / `Pushing it` / `Skip` | Perfect |
| February Drainage | Yes | `Excellent` / `Good` / `Check conditions` / `Poor` | Excellent |
| Climbing Pairing | Yes | Text or "All areas" | All areas (central location) |
| Key Trails for Sean | Yes | Trail names + difficulty | Black Forest (Green), TNT (Blue), 25-jump trail |
| Skill Dev Note | Yes | Text | Machine-built flow aligns with progression goals |
| Link to Trail Profile | Yes | Relative markdown link | [White Oak Mountain](../../trails/white-oak-mountain.md) |

### Food/Drink Target

A specific brewery, restaurant, or coffee spot Sean wants to visit.

| Field | Required | Format | Example |
|-------|----------|--------|---------|
| Name | Yes | Text | Hutton & Smith Brewing |
| Type | Yes | `Brewery` / `BBQ` / `Burgers` / `Southern` / `Coffee` | Brewery |
| Tier | Yes | `Don't miss` / `If nearby` | Don't miss |
| Location | Yes | Neighborhood + address | MLK Blvd, Southside |
| Standout Item | Yes | Text | **Igneous IPA** (flagship West Coast) |
| Vibe | Yes | Short phrase | Craft-focused taproom, 21+ only |
| Hours | Yes | Text | Check website |
| Closed Days | If applicable | Text | — |
| Reservations | If applicable | `Yes` / `No` / `Walk-in only` | No |
| Sean Note | If applicable | Text | THE IPA brewery. If you hit one brewery, this is it |
| Source | Yes | URL or citation | [huttonandsmithbrewing.com](https://huttonandsmithbrewing.com/) |

### Sight/Experience

A non-climbing, non-biking point of interest.

| Field | Required | Format | Example |
|-------|----------|--------|---------|
| Name | Yes | Text | Sunset Rock |
| Location | Yes | Text | W. Lookout Mountain |
| Time Needed | Yes | Duration | 30–60 min |
| Cost | Yes | Text | Free |
| Why | Yes | 1–2 sentences | Iconic panoramic view. Leafless February trees = wider sightlines. Go for sunset (~6pm) |
| February Note | If applicable | Text | Trail can be icy after freeze |

### Priority Stack Entry

A cross-category ranked item.

| Field | Required | Format | Example |
|-------|----------|--------|---------|
| Rank | Yes | Number | 1 |
| Category | Yes | Emoji + text | 🚲 Biking |
| Name | Yes | Text | White Oak Mountain |
| One-Line Context | Yes | Text | 25 mi stacked flow. Best progression + drainage |
| Status | At trip time | `☐` (open) or `☑` (done) | ☐ |

## Document Structure

The single output file (`sean-guide.md`) follows this heading structure:

```
# Sean's Personal Trip Guide
## Quick Profile
## Priority Stack (cross-category top 10)
## Mountain Biking
### Trail Wishlist (ranked table)
### Climbing-Area Pairings (what to ride when the group climbs where)
### Wet-Weather Fallbacks
## Climbing Projects
### Stone Fort
### Rocktown
### HP40
### Tier 2 Quick Notes
## Food & Drink
### Don't Miss (ranked)
### If Nearby
### IPA Crawl Route
### Tactical Notes (hours, closures, Valentine's Day)
## Sights & Experiences
### Quick Hits (under 1 hour, free/cheap)
### Worth the Time (1-3 hours)
### Half-Day Experiences
### Gear Shops
## Personal Logistics
### Bike Transport
### Gear Checklist
### Knee/Body Notes
```

## Relationships

```
sean-guide.md
  ├── references → areas/*.md (Feature 001)
  ├── references → areas/*-problems.md (Feature 002)
  ├── references → trails/*.md (Feature 003)
  ├── references → rest-days/README.md (Feature 004)
  ├── references → conditions/README.md (Feature 005)
  └── references → logistics/README.md (Feature 006)
```

All cross-references use relative markdown links. No content is duplicated — the personal guide adds Sean-specific context on top of existing documents.
