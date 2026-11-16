# Changelog

## 0.2.0 — Visual Previews, Design Tokens, and Progressive Disclosure
- **Visual previews (`references/previews.md`, `templates/preview-starter.html`):** Added "Show, then ask" rule requiring self-contained HTML previews (direction boards, palette contrast sheets, type specimens, wireframes, motion demos) with live WCAG contrast calculation and reduced-motion toggles.
- **Design tokens (`references/tokens.md`, `templates/design-tokens.css`):** Added two-tier token architecture (primitive + semantic roles) so accepted previews convert directly into production CSS custom properties or W3C Design Tokens JSON.
- **7-point readiness gate (`workflows/create.md`):** Replaced vague completion language with a checkable build-readiness checklist across pages, tokens, WCAG AA contrast, interaction states, reduced-motion alternatives, data states, and blocking questions.
- **Progressive disclosure architecture (`SKILL.md`, `workflows/`):** Refactored `SKILL.md` into a compact router and split route workflows into `workflows/create.md`, `workflows/review.md`, and `workflows/change.md`.
- **Anti-generic guardrails (`references/anti-generic.md`):** Added domain-artefact mining, mandatory "signature moves", recognition rules against generic AI templates, and the competitor swap test.
- **Evidence-based reviews (`workflows/review.md`, `templates/review-report.md`):** Added P0–P3 severity grading, an 11-area rubric, CSS design-value drift inventory, and multi-viewport inspection rules.
- **Deepened reference catalogues:** Expanded `design-taxonomy.md`, `layout-systems.md`, `visual-identity.md`, `interaction-patterns.md`, and `motion-design.md` with decision tables, trade-offs, and accessibility notes.
- **Worked example (`examples/digital-library/`):** Added a complete end-to-end example (*Folio*) including brief, interactive direction board, decision ledger, token stylesheet, and build-ready specification.

## 0.1.0 — Initial foundation
- Added Antigravity skill entry point.
- Added adaptive discovery and contextual curation instructions.
- Added `create`, `explore`, `specify`, `review`, `redesign`, `enhance`, `refine`, and focused commands.
- Added design taxonomy, interaction, motion, layout, and visual identity references.
- Added project brief, specification, and decision-log templates.
- Added installation, usage, command, and architecture documentation.
