# Review

Read-only audit of an existing website or implementation. Modify no files other than the review report itself.

## Steps

### 1. Scope and benchmark
Confirm the target (whole site, page, flow, or component) if it's unclear. Read `docs/design/` if it exists; its specification and ledger are the benchmark. Without one, review against the rubric below and the brief you can infer, and label that inferred brief as an assumption.

**Done when** the target and benchmark are stated in two lines.

### 2. Gather evidence
Collect every type of evidence the environment allows, and record which types you had:

- **Code**: pages, components, stylesheets, theme or token files, asset usage. Inventory design values in the CSS: count distinct colours, font sizes, spacing values, radii, shadows. Drift shows up here.
- **Rendered**: if a browser tool is available, run the site and capture screenshots at 375, 768, and 1440 px widths, plus key states (navigation open, hover and focus, form error, empty and loading views).
- **Keyboard**: tab through the primary journey; note focus visibility, order, and traps.
- **Motion**: observe with reduced motion emulated, if available.
- **Performance hints**: image sizes and formats, font loading, heavy libraries, layout shift on load.

**Done when** each evidence type is either collected or listed as unavailable.

### 3. Evaluate
Give every rubric area a verdict: **Pass**, **Findings**, or **Not assessable** (with the reason).

| Area | Look for |
|---|---|
| Hierarchy | One clear focal point per view; the primary action is obvious; scale contrast is deliberate |
| Consistency | Token drift (near-duplicate colours, off-scale spacing), inconsistent components |
| Typography | Pairing intent, scale, measure (about 45–75 characters), leading, widows on display text |
| Colour and contrast | Computed WCAG AA ratios; meaning carried by more than colour alone |
| Layout and responsive | Intentional breakpoints, no horizontal overflow, touch targets of at least 44 px |
| Interaction states | Hover, focus-visible, active, disabled, loading, error all present and distinct |
| Motion | Purposeful, interruptible, reduced-motion respected, no scroll hijacking |
| Accessibility | Semantics, labels, alt text, landmarks, keyboard reachability |
| Performance risk | Large or unoptimised media, render-blocking fonts, heavy effects on mobile |
| Distinctiveness | Run [anti-generic.md](../references/anti-generic.md): does it look like a template? |
| Spec fidelity | Deviations from confirmed decisions (only when a spec exists) |

### 4. Grade
- **P0**: blocks a core task or fails accessibility outright (for example a keyboard trap, unreadable contrast on body text).
- **P1**: major harm to usability, trust, or brand intent.
- **P2**: noticeable polish or consistency issue.
- **P3**: refinement or nitpick.

### 5. Report
Write the report using `templates/review-report.md` (save it to `docs/design/reviews/` if writing is allowed). Each finding needs: ID, severity, area, location (file:line, or page + viewport), evidence labelled **Observed** or **Inferred**, impact, and recommended fix. Lead with the top three findings, and close with the limitations of the evidence you had.

**Done when** every rubric area has a verdict and every finding has all fields.

Offer `enhance` or `refine` for follow-up work; never begin it from a review.
