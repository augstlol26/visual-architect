# Architecture

## Overview

Visual Architect is a progressively disclosed instruction skill. `SKILL.md` acts as a compact router holding only universal rules and command routing; route-specific workflows live in `workflows/` and domain catalogues live in `references/` so the agent loads only what the active task requires.

## Components

1. **Router (`SKILL.md`):** Interprets `/visual-architect` subcommands and natural-language requests, enforces global rules (*Show, then ask*, *One question per turn*, *Distinctive by default*, *Decision ledger*, *Evidence over assertion*), and handles `status`, `update`, and `help` inline.
2. **Workflows (`workflows/`):**
   - `create.md` — Intake, roadmap selection, 2–3 contrasting directions, adaptive module interviews, token derivation, specification handoff, and the 7-point readiness gate.
   - `review.md` — Read-only audit across an 11-area rubric with P0–P3 severity grading, CSS token-drift inventory, and viewport/keyboard/reduced-motion checks.
   - `change.md` — Controlled implementation loop for `redesign`, `enhance`, and `refine` with preserve/change lists, before/after previews, explicit approval gate, and post-change verification.
3. **Core references (`references/`):**
   - `previews.md` — Rules for self-contained HTML previews where `:root` CSS variables are candidate design tokens.
   - `tokens.md` — Two-tier token system (primitive + semantic) and WCAG 2.x relative luminance contrast math.
   - `anti-generic.md` — Domain artefact mining, signature moves, template recognition list, and the swap test.
   - `design-taxonomy.md`, `layout-systems.md`, `visual-identity.md`, `interaction-patterns.md`, `motion-design.md` — Decision tables with trade-offs and accessibility requirements.
4. **Templates (`templates/`):** Repeatable starting points for project briefs, specifications, decision logs, CSS tokens, review reports, and HTML direction boards.

## Data flow

```text
User idea or command
        │
        ▼
SKILL.md router
        │
        ├──► workflows/create.md ──► HTML previews (references/previews.md)
        │           │                        │
        │           ▼                        ▼
        │    Decision ledger ◄────── User picks / combines / delegates
        │           │
        │           ▼
        │    Tokens + Specification + 7-point Readiness Gate
        │
        ├──► workflows/review.md ──► Evidence collection + 11-area Rubric ──► P0–P3 Report
        │
        └──► workflows/change.md ──► Preserve/Change list + Preview ──► Approval ──► Code + Verify
```

## Project persistence

Generated design artifacts belong in the user's project repository, never inside the reusable skill folder:

```text
docs/design/
├── project-brief.md
├── design-specification.md
├── design-decisions.md
├── design-tokens.css
├── previews/
│   └── direction-board.html
└── reviews/
    └── YYYY-MM-DD-review.md
```
