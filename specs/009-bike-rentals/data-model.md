# Data Model: Mountain Bike Rentals & Group Riding

**Feature**: 009-bike-rentals
**Date**: 2026-02-10

## Entities

### Rental Shop

Each rental provider documented in the guide.

| Field | Description | Example |
|-------|-------------|---------|
| Name | Business name | Chattanooga Guided Adventures |
| Type | Storefront / Mobile delivery | Mobile delivery |
| Address | Physical address (if storefront) | N/A (delivery-based) |
| Drive from lodging | Minutes from Enterprise South | ~20-25 min (Coolidge Park pickup) |
| Phone | Contact number | [UNVERIFIED] |
| Website | Primary URL | chattanoogaguidedadventures.com |
| Booking URL | Direct booking link | pelago.com/... |
| Hours | Operating hours by day | Available 7 days [UNVERIFIED] |
| Sunday open | Boolean | Yes [UNVERIFIED] |
| Pricing | Rate tiers | $89/24hr, $149/48hr, $209/72hr |
| Bikes available | Models offered | Trek Roscoe, Scott Aspect, Polygon Xtrada |
| Included | What comes with rental | Helmet (MIPS), lock, spare tube |
| Reservation required | Yes/No/Recommended | Yes — online booking |
| Cancellation policy | Terms | Free cancel 2 days before; no refund day-of |
| February notes | Seasonal considerations | [UNVERIFIED: confirm winter availability] |
| Verified | Date of research or [UNVERIFIED] | 2026-02-10 (pricing via Pelago listing) |

### Beginner Trail Recommendation

Filtered subset of trails from `trails/README.md`, curated for first-time riders.

| Field | Description | Example |
|-------|-------------|---------|
| Trail name | Links to existing trail profile | Enterprise South |
| Specific loop | Named beginner route | Black Forest |
| Difficulty rating | Green / Blue | Green |
| Distance | Miles for the beginner loop | ~3 mi |
| Drive from lodging | Minutes | 0 min |
| Estimated ride time | For a beginner pace | 30-45 min |
| Why beginner-friendly | Brief reasoning | Smooth flow, gentle rollers, wide turns, no tech features |
| Warm-up option | Pump track or easy section | ESNP pump track |
| Concerns | Anything a first-timer should know | Directional trail rules by day of week |

### Climbing-to-Ride Pairing

Matches a climbing day with a rental biking option for split-group logistics.

| Field | Description | Example |
|-------|-------------|---------|
| Climbing area | Links to existing area profile | Stone Fort |
| Rental approach | How to get a bike | CGA delivery to Stringer's Ridge |
| Beginner trail | Recommended trail for the rider | Stringer's pump track → ESNP Black Forest |
| Drive times | Area-to-trail, trail-to-lodging | ~15-20 min, ~20-30 min |
| Time budget | Total half-day estimate | ~3-4 hrs (pickup + ride + return) |
| Feasibility | Practical / Not practical | Practical |
| Notes | Logistics details | Group meets at lodging afterward |

## File Placement

| Content | Location | Rationale |
|---------|----------|-----------|
| Rental guide (all content) | `trails/bike-rentals.md` | New standalone file in `trails/` directory. Too much content for a section in `trails/README.md`. Consistent with how individual trail profiles are separate files. |
| Cross-reference link | `trails/README.md` | Add a link in the existing "Rest-Day Rides" section pointing to the rental guide. |
| Cross-reference link | `rest-days/README.md` | Add a note near the biking cross-reference that already exists at the bottom of that file. |

## Content Sections (in `trails/bike-rentals.md`)

1. **Header + context** — Who this is for, trip dates, lodging reference
2. **Rental Shop Comparison Table** — Side-by-side comparison of all viable shops
3. **Detailed Shop Profiles** — One subsection per shop with full details
4. **Beginner-Friendly Trails** — Ranked recommendations with reasoning
5. **Climbing Day Pairings** — "The group is climbing at ___. How do I rent and ride?"
6. **First-Timer Tips** — What to wear, what to bring, sizing, etiquette
7. **February Considerations** — Weather, closures, Presidents' Day weekend
