# Usage guide

## 1. Start a new website (`create`)

```text
/visual-architect create
I want a digital library where people can discover, shelve, read, and share books.
```

What happens:
1. **Intake:** The agent summarises purpose, audience, primary journey, and constraints in ≤ 5 lines and asks you to confirm.
2. **Roadmap:** It proposes only the relevant discovery modules and depth (*Essential*, *Detailed*, or *Expert*).
3. **Visual direction board:** It mines domain artefacts (linen bindings, call numbers, reading lamps) and renders 2–3 contrasting directions as an HTML preview with real copy, colour swatches, computed WCAG contrast ratios, and a motion demo.
4. **One question at a time:** For each module, you can say:
   - **I'll direct it** — answer targeted questions to shape the details.
   - **Help me decide** — inspect curated options, trade-offs, and a recommendation.
   - **Delegate it** — let the agent choose and log the decision as `Delegated to agent`.
5. **Tokens & specification:** Once decisions are in place, the agent writes `docs/design/design-tokens.css`, `design-specification.md`, `design-decisions.md`, and `project-brief.md`, then runs the **7-point readiness gate**.

## 2. Explore directions only (`explore`)

```text
/visual-architect explore three directions for an independent ceramics studio
```

Runs intake and renders a 3-column direction board without stepping through the full specification interview.

## 3. Audit an existing site (`review`)

```text
/visual-architect review
```

Performs a read-only audit across 11 rubric areas (hierarchy, token drift, typography, computed contrast, responsive breakpoints, interaction states, motion, accessibility, performance, distinctiveness, spec fidelity) and grades every finding from **P0** to **P3** with observed evidence.

## 4. Improve an existing page (`redesign`, `enhance`, `refine`)

```text
/visual-architect enhance the product detail header so specifications are easier to scan
```

1. Lists what will be **preserved** and what will **change**.
2. Renders a **before/after preview**.
3. Presents the file-by-file plan and waits for your approval.
4. Applies changes using design tokens, verifies build/viewports, and updates the decision ledger.

## 5. Check progress (`status`)

```text
/visual-architect status
```

Shows decision counts by status, your current score on the 7-point readiness gate, any blocking open questions, and the single next question to answer.
