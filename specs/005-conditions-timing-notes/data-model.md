# Data Model: Conditions, Timing & Reality Notes

**Feature**: 005-conditions-timing-notes | **Date**: 2026-02-08

## Entities

### Conditions Quick Reference

A summary table for rapid area selection based on current weather. Located at the top of `conditions/README.md`.

| Column | Required | Description |
|--------|----------|-------------|
| Scenario | MUST | Weather condition (cold/dry, humid, post-rain, windy, warm) |
| Best Areas | MUST | Recommended areas for this scenario |
| Avoid | MUST | Areas to avoid or approach with caution |
| Why | MUST | Brief reasoning (friction, seepage, exposure) |
| Alt Activity | SHOULD | Non-climbing alternative if conditions are bad for all areas |

### Area Conditions Synthesis

Cross-cutting conditions profile for each major climbing area. NOT a duplicate of Feature 001 — this compares areas against each other for decision-making.

| Field | Required | Format | Description |
|-------|----------|--------|-------------|
| Area Name | MUST | H3 heading | Links to existing area profile |
| Rock Type | MUST | Inline | Sandstone variant and key grip characteristics |
| Humidity Sensitivity | MUST | Scale (Low/Medium/High) | How much humidity degrades friction |
| Sun/Shade Pattern | MUST | Text | Morning vs. afternoon sun exposure |
| Wind Exposure | MUST | Scale (Sheltered/Moderate/Exposed) | How wind affects the area |
| Seepage After Rain | MUST | Text | Drying time estimates and behavior |
| Best Conditions | MUST | Text | Ideal weather for this area |
| Worst Conditions | MUST | Text | When to avoid this area |
| Source | MUST | Link | Guidebook, community source, or [UNVERIFIED] |

### Crowd & Timing Profile

Per-area crowd and timing information for trip planning.

| Field | Required | Format | Description |
|-------|----------|--------|-------------|
| Area Name | MUST | H3 heading | Links to existing area profile |
| Weekend Crowds | MUST | Scale (Light/Moderate/Heavy) | Expected weekend traffic in February |
| Weekday Crowds | MUST | Scale (Light/Moderate/Heavy) | Expected weekday traffic |
| Peak Season | MUST | Text | Whether February falls in peak season |
| Recommended Arrival | SHOULD | Time | Best time to arrive for parking and problem access |
| Gate Hours | SHOULD | Text | If applicable (e.g., Dayton Pocket) |
| February Daylight | MUST | Text | Sunrise/sunset times for February |

### Skin Management Guide

Not a per-area entity — a standalone advisory section.

| Field | Required | Format | Description |
|-------|----------|--------|-------------|
| Rock Abrasiveness | MUST | Per-area comparison | Which areas/rock types are harder on skin |
| Pacing Strategy | MUST | Text | Recommended climb/rest pattern for a 7-day trip |
| Rotation Strategy | MUST | Text | How to alternate area types to preserve skin |
| Recovery Tips | SHOULD | Text | General skin care between sessions |
| Source | MUST | Link | Climbing community sources or [UNVERIFIED] |

### February Seasonal Profile

Standalone section with Chattanooga-specific February conditions.

| Field | Required | Format | Description |
|-------|----------|--------|-------------|
| Temperature Range | MUST | Text | Typical highs/lows for Feb 14-21 |
| Precipitation | MUST | Text | Average rain days, total inches |
| Humidity Patterns | MUST | Text | Typical daily humidity cycle |
| Daylight Hours | MUST | Text | Sunrise/sunset for mid-February |
| Wind Patterns | SHOULD | Text | Prevailing wind direction and speed |

## Document Structure

### Conditions Guide Template

```markdown
# Conditions, Timing & Reality Notes

> Cross-cutting conditions guide for all bouldering areas. For per-area details, see individual [area profiles](../areas/README.md).
> Trip dates: February 14–21, 2026.

## Conditions Quick Reference

| Scenario | Best Areas | Avoid | Why | Alt Activity |
|----------|-----------|-------|-----|-------------|
| {scenario} | {areas} | {areas} | {reasoning} | {alternative} |

## Southeastern Sandstone Primer

{How sandstone friction works, humidity/temperature interaction, comparison to granite/limestone}

---

## Area Conditions Synthesis

{Cross-cutting comparison of conditions across all major areas}

### {Area Name}

{Rock type, humidity sensitivity, sun/shade, wind, seepage, best/worst conditions}

---

## Crowds & Timing

{Per-area crowd patterns, recommended arrival times, gate hours}

### February Daylight & Timing

{Sunrise/sunset, practical climbing window}

### {Area Name}

{Weekend vs. weekday crowds, peak season status, parking notes}

---

## Skin Management

{Rock abrasiveness comparison, pacing strategy, rotation advice, recovery tips}

---

## February Seasonal Profile

{Temperature, precipitation, humidity, daylight, wind patterns}

---

## Sources

{Consolidated source list}
```
