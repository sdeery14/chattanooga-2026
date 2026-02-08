# Quickstart: Using the Conditions Guide

## What the Conditions Guide Is

The conditions guide is a "given today's weather, where should we climb?" document. It provides cross-cutting conditions wisdom across all bouldering areas so you can make a smart area choice before driving anywhere.

It is NOT a replacement for per-area conditions sections in the area profiles. It's the synthesis layer — comparing areas against each other to help you pick the right one for today's conditions.

## How It Relates to Other Features

- **Area profiles** (Feature 001) = per-area conditions details (sun/shade, seepage, access)
- **Problem clusters** (Feature 002) = conditions-sensitive problem flags ("good in humidity", "needs cold/dry")
- **Conditions guide** (this feature) = "Given today's weather, which area should we go to?"

The conditions guide links to area profiles and problem clusters — it doesn't duplicate their content.

## Before the Trip

1. **Read the Southeastern Sandstone Primer** if anyone in the group hasn't climbed on Southern sandstone before
2. **Skim the February Seasonal Profile** to set expectations for temperature, rain, and daylight
3. **Note the Conditions Quick Reference table** — you'll use this every morning

## During the Trip

### "It's 7am. Where should we climb today?"

1. Check the weather app (temperature, humidity, wind, rain forecast)
2. Open `conditions/README.md`
3. Find today's scenario in the **Conditions Quick Reference** table
4. Go to the recommended area. Done.

### "It rained overnight. Can we still climb?"

1. Open `conditions/README.md`
2. Check the "post-rain" row in the Quick Reference table
3. Look at the drying-time estimates for specific areas
4. Pick an area with faster drying or sheltered boulders

### "It's Saturday. Where will be less crowded?"

1. Open `conditions/README.md`
2. Jump to the **Crowds & Timing** section
3. Check weekend crowd levels by area
4. Pick a less crowded alternative or plan to arrive early

### "My skin is wrecked. What should I do?"

1. Open `conditions/README.md`
2. Jump to the **Skin Management** section
3. Check abrasiveness ratings by area
4. Either rest or pick a less abrasive area/style

## File Layout

```
conditions/
└── README.md            ← The complete conditions guide

areas/                   ← Existing area profiles (linked, not duplicated)
areas/*-problems.md      ← Existing problem clusters (linked, not duplicated)
trails/                  ← Existing trail profiles (linked for bad-conditions alternatives)
rest-days/               ← Existing rest-day guide (linked for rest-day alternatives)
```
