# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **knowledge base repository** (not a software project) for planning a Chattanooga-area bouldering trip. It uses the **Specify (Spec-Kit)** workflow to manage features as structured specs, plans, and tasks — applied here to trip research rather than software.

The only source file at the root is `vision.md`, which defines the project's purpose, constraints, and philosophy. All future content is generated through the Specify workflow into `specs/` directories on feature branches.

## Specify (Spec-Kit) Workflow

This repo is scaffolded from a Specify template. The workflow is driven entirely through slash commands, executed in order:

1. `/speckit.specify <description>` — Creates a feature branch and writes `spec.md` from a natural language description
2. `/speckit.clarify` — Asks up to 5 targeted questions to fill gaps in the spec
3. `/speckit.plan` — Generates `plan.md`, `research.md`, `data-model.md`, and contract artifacts
4. `/speckit.tasks` — Produces `tasks.md` with dependency-ordered work items
5. `/speckit.implement` — Executes the tasks
6. `/speckit.analyze` — Cross-artifact consistency check (non-destructive)
7. `/speckit.checklist` — Generates a custom validation checklist
8. `/speckit.constitution` — Creates/updates the project constitution (`.specify/memory/constitution.md`)
9. `/speckit.taskstoissues` — Converts tasks to GitHub issues

Each command's full prompt lives in `.claude/commands/speckit.*.md`. The templates they fill are in `.specify/templates/`. Helper scripts are PowerShell in `.specify/scripts/powershell/`.

## Key Directories

- `.specify/templates/` — Markdown templates for specs, plans, tasks, checklists, and agent context files
- `.specify/scripts/powershell/` — Automation scripts (`create-new-feature.ps1`, `setup-plan.ps1`, `update-agent-context.ps1`)
- `.specify/memory/constitution.md` — Project constitution (currently unpopulated template)
- `.claude/commands/` — Slash command definitions for the Specify workflow

## Trip Domain Context

When generating content for this repo, keep these constraints in mind (from `vision.md`):

- **Bouldering only** — no sport or trad climbing
- **Three ability bands**: V0–V1, ~V5, ~V10 — hard climbing (V10) is the primary focus
- **Mountain biking is a first-class activity**, not an afterthought (one participant brings a bike)
- The repo is a **decision-support system** — skimmable, context-aware, useful when tired
- Content should preserve **optionality** over fixed schedules
- Documents should focus on **what** and **why**, not implementation details (following Specify conventions)
