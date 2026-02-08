# Quickstart: Using the Logistics Guide

## What the Logistics Guide Is

The logistics guide is a "how do we get there and what do we need to know?" document. It consolidates drive times, access requirements, parking, approach details, and critical warnings for all climbing areas into a single reference.

It is NOT a replacement for per-area profiles or the conditions guide. It's the logistics layer — the practical "don't waste time or make access mistakes" complement to conditions-based area selection.

## How It Relates to Other Features

- **Area profiles** (Feature 001) = per-area details (style, problems, vibes)
- **Conditions guide** (Feature 005) = "Given today's weather, which area?" + timing for friction
- **Logistics guide** (this feature) = "How do we get there? What do we need before we arrive?"

The logistics guide links to area profiles and the conditions guide — it doesn't duplicate their content.

## Before the Trip

1. **Read the "Don't Screw This Up" section** — these are pre-trip action items (request gate codes, register online, note gate hours)
2. **Skim the drive-time table** to build mental map of area distances
3. **Note multi-area pairings** for days when you might visit two areas

## During the Trip

### "How long to get to HP40?"

1. Open `logistics/README.md`
2. Check the **Drive-Time Comparison** table
3. Find HP40 row → see drive time, distance, time zone note
4. Done in under 15 seconds.

### "We're heading to Dayton Pocket — what do we need to know?"

1. Open `logistics/README.md`
2. Jump to **Area Access Cheat Sheets** → Dayton Pocket
3. See gate hours (8 AM – 7 PM, locked at 7 PM), online registration requirement, parking location, approach info
4. Done in under 30 seconds.

### "We want to visit two areas today — what pairs well?"

1. Open `logistics/README.md`
2. Jump to **Multi-Area Day Pairings**
3. Find a logical combination with combined drive-time estimate
4. Plan the day around the pairing logistics.

### "Do we need to pay? Check in? Get a code?"

1. Open `logistics/README.md`
2. Check the **Don't Screw This Up** section for critical warnings
3. Check the specific area's access cheat sheet for fee, check-in, and code details.

## File Layout

```
logistics/
└── README.md            ← The complete logistics guide

areas/                   ← Existing area profiles (linked, not duplicated)
conditions/              ← Existing conditions guide (linked, not duplicated)
trails/                  ← Existing trail profiles (linked for group-split logistics)
rest-days/               ← Existing rest-day guide (linked)
```
