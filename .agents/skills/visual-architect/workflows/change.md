# Redesign, enhance, refine

Changes to an existing design, and optionally its code.

- **Redesign**: rethink the visual concept, composition, or experience of the target.
- **Enhance**: improve a bounded area while keeping the wider design language and functionality.
- **Refine**: polish execution (spacing, alignment, states, timing, consistency) without changing direction.

## Steps

### 1. Scope
Confirm the target and the change type if they're unclear. Read `docs/design/` (specification, ledger, tokens) and the relevant code.

**Done when** you can name the files and pages in scope.

### 2. Preserve and change lists
List what must be preserved (confirmed decisions, functionality, content, brand elements) and what may change.

**Done when** the user has seen both lists. Silence on a preserved item counts as keep.

### 3. Show the change
- **Redesign**: two or three directions as a preview board ([previews.md](../references/previews.md)), each rendered against the current design.
- **Enhance**: a before/after preview of the target area.
- **Refine**: a concrete diff list (for example "card padding 18px → 24px (`--space-6`)") with a before/after preview for anything visible at a glance.

Apply [anti-generic.md](../references/anti-generic.md) to every proposed direction.

### 4. Plan and approval
Present the change plan: files to touch, tokens to add or alter, trade-offs, risks.

**Done when** the user explicitly approves. Without approval, stop here and leave the plan in the ledger as an `Open question`.

### 5. Implement
Change only the approved scope. Express new values as tokens (add them to the token file and reference them) rather than hard-coding. Keep reduced-motion and focus states intact or improved.

### 6. Verify and record
Run the project's build, lint, and tests if they exist. If a browser tool is available, screenshot the changed area at 375, 768, and 1440 px and compare it against the approved preview. Update the specification, tokens, and ledger (with a dated change-history entry).

**Done when** the report lists what changed (files), what was verified and how, and what remains unverified.
