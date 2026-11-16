# Website Design Specification

> Status: Draft / Build-ready
> Version:
> Last updated:
> Readiness gate: _n_/7 passing. See section 12.

Priority labels: **Must** · **Preferred** · **Optional** · **Implementer's choice**. Cite decision IDs from `design-decisions.md` as `(D-000)`.

## 1. Project overview
- Concept:
- Purpose:
- Audience:
- Experience goals:

## 2. Creative direction
- Direction name and one-line idea:
- Signature move:
- Personality (is / is not):
- Domain material it draws from:
- References and what to take from each:
- Directions to avoid:
- Accepted preview: `previews/...`

## 3. Information architecture
- Sitemap:
- Navigation model:
- Primary user journeys:

## 4. Design tokens
Source of truth: `design-tokens.css` (and `design-tokens.json`). Summarise here; record values in the token file only.
- Palette summary and contrast table:

| Text | Background | Ratio | AA |
|---|---|---|---|
| | | | |

- Typography: families (intended + fallback), scale:
- Spacing base and scale:
- Layout: containers, measure, breakpoints:
- Shape and elevation:
- Motion: durations, easings, reduced-motion policy:

## 5. Imagery and assets
- Photography / illustration / 3D direction:
- Crops and aspect ratios per breakpoint:
- Iconography:
- Asset formats and size budgets:

## 6. Page specifications
Repeat for each page.

### Page: [name]
- Purpose:
- Primary action:
- Section order:
- Layout, desktop:
- Layout, mobile:
- Content hierarchy and focal point:
- Interactions (link to section 7):
- Motion (link to section 8):
- Loading / empty / error / success:
- Accessibility notes:
- Preview: `previews/...`

## 7. Interaction system
For each interaction: goal · trigger · states (default, hover, focus-visible, active, disabled, loading, error) · feedback and result · keyboard · touch · semantics · failure cases.

## 8. Motion system
For each animation: name · trigger · initial state · sequence · duration / delay / stagger · easing token · final state · interruption · reduced-motion alternative · mobile and performance notes.

## 9. Responsive strategy
- Mobile:
- Tablet:
- Desktop:
- What changes at each breakpoint:
- Touch adaptations (targets ≥ 44 px):

## 10. Accessibility
- Target: WCAG 2.2 AA
- Landmarks and heading structure:
- Focus treatment:
- Motion and media controls:

## 11. Technical constraints
- Stack and styling approach:
- Performance budgets (LCP, JS, image weight):
- Browser support:
- Font loading strategy:

## 12. Readiness gate
- [ ] Every page has purpose, primary action, section order, and layout at mobile and desktop.
- [ ] Every token category holds concrete values.
- [ ] Every text/background pair meets WCAG AA (computed).
- [ ] Every interaction lists applicable states plus keyboard and touch equivalents.
- [ ] Every animation has trigger, duration, easing, and reduced-motion alternative.
- [ ] Every data-driven view defines loading, empty, error, and success states.
- [ ] No blocking open questions; assumptions listed.

## 13. Decisions and uncertainty
Summary only; full record in `design-decisions.md`.
- Open questions:
- Assumptions needing validation:
- Delegated decisions:
