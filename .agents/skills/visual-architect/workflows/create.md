# Create, explore, specify

Use for `create` (new website), `explore` (creative directions only), `specify` (produce or update the handoff), and the focused commands. `explore` runs steps 1–3; `specify` runs steps 5–6 against whatever the ledger already holds; `create` runs everything.

## Steps

### 1. Intake
Get the idea in the user's own words if it isn't given. Read `docs/design/` if it exists, and skim the repository for its stack (framework, CSS approach, existing tokens or theme files) so the handoff targets what is really there.

**Done when** you have played back purpose, audience, primary journey, key content, and constraints in five lines or fewer, listed your material assumptions, and the user has confirmed or corrected the summary.

### 2. Roadmap
Pick only the relevant modules, in a sensible order:
1. Creative direction
2. Information architecture and content hierarchy
3. Layout and composition: [layout-systems.md](../references/layout-systems.md)
4. Visual identity, colour, typography: [visual-identity.md](../references/visual-identity.md)
5. Imagery, illustration, iconography, 3D
6. Motion: [motion-design.md](../references/motion-design.md)
7. Interactions and microinteractions: [interaction-patterns.md](../references/interaction-patterns.md)
8. Navigation, usability, accessibility
9. Responsive and touch behaviour
10. Technical feasibility and performance
11. Content states: loading, empty, error, success

Propose a depth per module: **Essential** (high-impact choices only), **Detailed** (alternatives and behaviour), **Expert** (advanced patterns, edge cases, implementation implications).

**Done when** the user accepts, edits, or delegates the roadmap.

### 3. Creative directions
Produce **two or three contrasting directions**: different answers to the brief, not variations of one. For each: a letter, a name, a one-line idea, why it fits this audience, its *signature move* (see [anti-generic.md](../references/anti-generic.md)), and its main trade-off. Render them side by side as a direction board ([previews.md](../references/previews.md)). Invite the user to pick, combine ("B's colour with A's type"), push one further, or delegate.

**Done when** one direction (or a named combination) is in the ledger with a status.

### 4. Module interviews
Work through the roadmap one module at a time, using the catalogue rules below. Render a preview for every visual choice. Follow up only when an answer changes the design.

**Done when** the module's section of the specification has no blanks, other than items explicitly logged as `Open question` or `Delegated to agent`.

### 5. Tokens
Derive design tokens from the accepted direction and module decisions per [tokens.md](../references/tokens.md). Render a token sheet (palette with contrast ratios, type scale, spacing, radius, elevation, motion curves) and get confirmation.

**Done when** every required token category holds concrete values and the user has confirmed the token sheet or delegated it.

### 6. Specify
Write or update, in `docs/design/`:
- `project-brief.md` from `templates/project-brief.md`
- `design-specification.md` from `templates/design-specification.md`
- `design-decisions.md` from `templates/design-decisions.md`
- `design-tokens.css` (and `design-tokens.json` when useful) per `tokens.md`
- `builder-handoff-prompt.md` from `templates/builder-handoff-prompt.md` (when ready to hand off to a coding agent)
- `previews/`: the accepted preview files

Mark every requirement as **Must**, **Preferred**, **Optional**, or **Implementer's choice**. Then run the readiness gate.

**Done when** the files are written (or the in-conversation fallback is delivered) and the gate report is shown.

## Readiness gate

The specification is **build-ready** only when every line passes. Report each line as pass or fail; each failure becomes the next question.

- [ ] Every page in the sitemap has a purpose, a primary action, a section order, and a layout described at mobile and desktop widths.
- [ ] Every token category in `tokens.md` holds concrete values; no adjectives standing in for values.
- [ ] Every text/background pair in use has a computed contrast ratio meeting WCAG AA (4.5:1 body text, 3:1 large text and UI boundaries).
- [ ] Every specified interaction lists its applicable states (default, hover, focus-visible, active, disabled, loading, error) and its keyboard and touch equivalents.
- [ ] Every specified animation has a trigger, a duration, an easing value, and a reduced-motion alternative.
- [ ] Every data-driven view defines loading, empty, error, and success states.
- [ ] No `Open question` is marked blocking; every assumption is listed.

## Focused commands

`layout`, `motion`, `interactions`, `identity`, `responsive`: run step 4 for that one module against the existing ledger (run step 1 first if there is no ledger), plus step 5 when tokens change (identity, motion, layout spacing). Update the specification section and ledger. If the user wants the result applied to code, continue with [change.md](change.md).

## Catalogue rules

When presenting options for any design area:
1. Start from this project's brief, content, and earlier decisions. Generic lists come last.
2. Draw on the reference catalogues and broader design knowledge, grouped into useful families (for example discovery, feedback, spatial).
3. For each option, say in plain language how it would look and behave *in this product*.
4. Span the range: a conventional option, a polished one, an ambitious one, and an experimental one where the project can carry it.
5. Show each option's trade-offs: usability, accessibility, performance, build cost, mobile fit.
6. Show a curated first set of three to five; offer to go deeper rather than dumping everything.
7. Recommend a coherent combination and say why.
8. The catalogue is inspiration. The user may combine, customise, invent their own, or delegate.

## Specification detail

For each important **animation** capture: trigger and preconditions; initial and final state; elements and sequence; distance, scale, rotation, or depth; duration, delay, stagger, easing (as a token); link to scroll, pointer, or touch; interruption and reversal; reduced-motion alternative; mobile and performance notes.

For each **interaction** capture: user goal and trigger; target and affordance; applicable states; feedback and resulting state; keyboard and touch behaviour; accessibility semantics (role, name, announcements); responsive behaviour and failure cases.
