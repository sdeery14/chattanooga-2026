<!--
  Sync Impact Report
  ==================
  Version change: 0.0.0 (unpopulated template) → 1.0.0
  Modified principles: N/A (all new)
  Added sections:
    - Core Principles (5 principles derived from vision.md)
    - Scope & Constraints
    - Content Quality Gates
    - Governance
  Removed sections: None
  Templates requiring updates:
    - .specify/templates/plan-template.md — ✅ No update needed
      (Constitution Check section is generic; gates will be
      evaluated dynamically against these principles)
    - .specify/templates/spec-template.md — ✅ No update needed
      (Template structure is domain-agnostic)
    - .specify/templates/tasks-template.md — ✅ No update needed
      (Task phases are generic; domain tasks will be generated
      per spec)
    - .specify/templates/checklist-template.md — ✅ No update needed
      (Checklist items are generated dynamically)
    - .specify/templates/agent-file-template.md — ✅ No update needed
    - CLAUDE.md — ✅ No update needed
      (Already references constitution and vision constraints)
  Follow-up TODOs: None
-->

# Chattanooga Trip Knowledge Base Constitution

## Core Principles

### I. Decision-Support First

Every document, research note, and curated list in this repository
MUST serve rapid, in-the-moment decision-making. Content that does
not help answer "Where should we go?", "What can I climb/ride here?",
or "What else can I do nearby?" MUST be removed or restructured until
it does.

- All content MUST be skimmable under fatigue or time pressure
- Documents MUST lead with actionable context (conditions, tradeoffs,
  recommendations) before background detail
- Fixed itineraries and exhaustive tick-lists are prohibited;
  optionality MUST be preserved

### II. Bouldering Scope Boundary (NON-NEGOTIABLE)

All climbing research MUST be limited to bouldering (pad-based access
only). Sport climbing, trad climbing, and any rope-based discipline
are explicitly out of scope.

- Area research MUST assume crashpad logistics only
- Grade references MUST use the V-scale
- Any content referencing non-bouldering disciplines MUST be rejected
  during review

### III. Ability-Aware, Hard-Climbing Priority

Research and area selection MUST prioritize high-quality hard
bouldering (V10-level objectives) as the primary trip focus, while
surfacing lower-grade options where they exist nearby.

- Every area document MUST identify primary objectives for the
  ~V10 band
- When moderates (V0–V5) exist in the same zone, they MUST be noted
- Documents MUST NOT enforce artificial parity between ability levels
- Style and body-type notes (reachy, compression-heavy, technical)
  SHOULD be included when known

### IV. Mountain Biking as First-Class Activity

Mountain biking MUST be treated as a parallel activity with equal
research rigor to bouldering, not as a fallback or afterthought.

- Each area or rest-day document MUST note nearby trail access
  when it exists
- Research MUST include dedicated biking options: rest-day rides,
  half-day pairings with climbing, and parallel climbing + biking days
- Trail information SHOULD include difficulty, distance, and
  access logistics

### V. Source Accuracy & Recency

All research content MUST cite verifiable sources and note when
information may be outdated or seasonal.

- Guidebook editions, Mountain Project links, and trail databases
  MUST be cited where applicable
- Seasonal or condition-dependent information (access closures,
  seepage, trail status) MUST be flagged with date or season context
- Unverified claims MUST be marked as such

## Scope & Constraints

This constitution governs a **knowledge base**, not a software
codebase. The Specify workflow is used to structure research features
(e.g., "research Stone Fort bouldering", "compile rest-day options")
as specs, plans, and tasks.

**In scope**: Bouldering areas, curated problem suggestions by grade
band, style/conditions/proximity notes, mountain biking routes, rest
day and split-activity options, lightweight logistics (driving, access,
timing), personal notes.

**Out of scope**: Sport or trad climbing, fixed daily itineraries,
exhaustive tick-lists, grade-maximization goals, detailed beta
documentation.

## Content Quality Gates

Before any research document is considered complete:

1. **Skimmability gate**: Can the key information be absorbed in
   under 60 seconds?
2. **Decision-orientation gate**: Does the document answer at least
   one of the three core questions (where to go, what to climb/ride,
   what else nearby)?
3. **Scope gate**: Does the document stay within bouldering +
   mountain biking boundaries?
4. **Ability coverage gate**: Are objectives identified for the
   primary (V10) band, and are lower-grade options noted where
   they exist?
5. **Source gate**: Are claims sourced or flagged as unverified?

## Governance

This constitution supersedes all other content guidelines in the
repository. Amendments require:

1. A clear description of the change and its rationale
2. Version bump following semantic versioning (MAJOR for principle
   removal/redefinition, MINOR for new principles or material
   expansion, PATCH for clarifications and wording)
3. A sync impact review of dependent templates

All spec and plan reviews MUST verify compliance with these
principles. The Constitution Check section in `plan-template.md`
MUST evaluate gates against the principles defined here.

**Version**: 1.0.0 | **Ratified**: 2026-02-08 | **Last Amended**: 2026-02-08
