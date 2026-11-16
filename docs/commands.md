# Commands

Invoke `/visual-architect` followed by a subcommand or a natural-language brief. Subcommands are interpreted by the skill rather than registered as separate native IDE commands.

## Create and specify

| Syntax | Behaviour |
|---|---|
| `/visual-architect create [idea]` | Run full discovery: intake summary, tailored roadmap, rendered direction board, adaptive module interviews, design tokens, and build-ready specification. |
| `/visual-architect explore [target]` | Explore 2–3 contrasting creative directions with a rendered direction board and trade-off comparison. |
| `/visual-architect specify` | Generate or update `project-brief.md`, `design-specification.md`, `design-decisions.md`, and `design-tokens.css`, then run the 7-point readiness gate. |

## Review and improve

| Syntax | Behaviour |
|---|---|
| `/visual-architect review [target]` | Read-only audit against the 11-area rubric and P0–P3 severity scale; inventories CSS value drift and captures multi-viewport evidence when available. |
| `/visual-architect redesign [target]` | Reimagine the visual concept or composition with a rendered direction board; requires explicit approval before modifying code. |
| `/visual-architect enhance [target]` | Improve a bounded area while preserving the wider system; shows a before/after preview and requires approval before code changes. |
| `/visual-architect refine [target]` | Polish spacing, alignment, states, timing, and token consistency; requires approval before code changes. |

## Focused design modules

| Syntax | Behaviour |
|---|---|
| `/visual-architect layout [target]` | Composition, grid, hierarchy, spacing rhythm, and breakpoint structure. |
| `/visual-architect motion [target]` | Animation choreography, duration/easing tokens, interruption, and `prefers-reduced-motion` alternatives. |
| `/visual-architect interactions [target]` | Interaction patterns, all 7 component states, keyboard navigation, and touch equivalents. |
| `/visual-architect identity [target]` | Art direction, domain-derived colour ramps, WCAG contrast table, and typeface pairing. |
| `/visual-architect responsive [target]` | Mobile, tablet, desktop adaptation, fluid sizing, and ≥ 44 px touch targets. |

## Project management

| Syntax | Behaviour |
|---|---|
| `/visual-architect status` | Report ledger counts by status, 7-point readiness gate pass/fail, blocking open questions, and the single next question. |
| `/visual-architect update [change]` | Amend the brief, specification, tokens, or decision ledger and log a dated entry. |
| `/visual-architect help` | List subcommands, decision modes, and depth modes. |

## Approval and safety rules

- `review`, `status`, and `help` are strictly read-only.
- `create`, `explore`, and `specify` write design documents, tokens, and previews under `docs/design/` (or in-conversation if file access is unavailable).
- `redesign`, `enhance`, `refine`, and any focused command that touches application code must present a preserve/change list, show a preview, and obtain explicit user approval before editing implementation files.
