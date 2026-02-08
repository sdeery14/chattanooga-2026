# Data Model: Logistics & Access Cheat Sheets

**Feature**: 006-logistics-access-cheat-sheets | **Date**: 2026-02-08

## Entities

### Drive-Time Comparison Table

A summary table for rapid area logistics lookup. Located at the top of `logistics/README.md`.

| Column | Required | Description |
|--------|----------|-------------|
| Area | MUST | Climbing area name (linked to area profile) |
| Drive Time | MUST | Estimated drive time from ESNP |
| Distance | MUST | Approximate miles from ESNP |
| Route | SHOULD | Key roads or route description |
| Time Zone | MUST | ET or CT (flag crossings) |
| Road Notes | SHOULD | February-specific road concerns (ice, unpaved) |

### Area Access Cheat Sheet

Per-area structured entry with all access logistics. Each area gets an H3 heading in `logistics/README.md`.

| Field | Required | Format | Description |
|-------|----------|--------|-------------|
| Area Name | MUST | H3 heading | Links to existing area profile |
| Fee | MUST | Text | Day use fee, per-person vs per-car, payment method |
| Gate Hours | MUST | Text | Open/close times; "No gate" if open access |
| Check-in | SHOULD | Text | Registration, check-in, or sign-in requirements |
| Critical Rules | MUST | Text | Rules that, if missed, would ruin the session |
| Parking | MUST | Text | Location description, capacity, landmarks |
| Approach | MUST | Text | Trail distance, time, terrain, pad-carry notes |
| Contact | MUST | Link/Text | Phone number, website, or email for verification |
| Source | MUST | Link | Guidebook, official site, or [UNVERIFIED] |

### Don't Screw This Up Checklist

Consolidated critical warnings. Located prominently near the top of `logistics/README.md`, after the drive-time table.

| Field | Required | Format | Description |
|-------|----------|--------|-------------|
| Warning | MUST | Bold text | What can go wrong |
| Area | MUST | Text | Which area(s) this applies to |
| Prevention | MUST | Text | What to do to avoid the problem |
| Severity | SHOULD | Scale | How bad if you miss it (Annoying / Day-Ruining / Trip-Ruining) |

### Multi-Area Day Pairings

Logical same-day combinations with combined logistics.

| Field | Required | Format | Description |
|-------|----------|--------|-------------|
| Pairing Name | MUST | H4 heading | e.g., "Alabama Corridor: HP40 + Hospital Boulders" |
| Areas | MUST | Links | Linked area names |
| Total Drive Time | MUST | Text | Combined drive time from ESNP and between areas |
| Why It Works | MUST | Text | Why these areas pair well logistically |
| Logistics Notes | SHOULD | Text | Timing tips, order of visits, etc. |

## Document Structure

### Logistics Guide Template

```markdown
# Logistics & Access Cheat Sheets

> Quick-reference logistics for all climbing areas. For conditions and timing, see the [conditions guide](../conditions/README.md). For per-area details, see [area profiles](../areas/README.md).
> Trip dates: February 14–21, 2026. Lodging: ESNP area.

## Drive-Time Comparison

| Area | Drive Time | Distance | Route | Time Zone | Road Notes |
|------|-----------|----------|-------|-----------|------------|
| {area} | {time} | {miles} | {route} | {tz} | {notes} |

## Don't Screw This Up

{Consolidated critical access warnings}

## Area Access Cheat Sheets

### {Area Name}

{Fee, gate hours, check-in, rules, parking, approach, contact}

---

## Multi-Area Day Pairings

### {Pairing Name}

{Areas, total drive time, why it works, logistics notes}

---

## Sources

{Consolidated source list}
```
