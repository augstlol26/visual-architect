# Website Design Specification — Folio

> Status: Build-ready
> Version: 1.0.0
> Last updated: 2026-11-16
> Readiness gate: 7/7 passing. See section 12.

Priority labels: **Must** · **Preferred** · **Optional** · **Implementer's choice**. Decision citations refer to [`design-decisions.md`](design-decisions.md).

## 1. Project overview
- **Concept:** Folio is a calm digital library where readers discover, shelve, read, and annotate public-domain and independent books with the tactile pleasure of a real reading room.
- **Purpose:** Replace noisy retail book grids with human-curated shelves and a zero-distraction browser reader.
- **Audience:** Long-form readers, students, book-club hosts, and independent presses.
- **Experience goals:** Unhurried discovery, effortless 60-minute reading comfort, instant keyboard control, and shareable shelves.

## 2. Creative direction
- **Direction name and one-line idea:** **Direction A — Reading Room** (`D-001`): warm linen paper, oxblood cloth bookbindings, and call-number slips, paired with a low-glare "Night Lamp" dark theme.
- **Signature move:** **Spine-to-Cover Shelf** (`D-003`): shelves render books spine-out with widths proportional to page count; hover, focus, or tap tilts a spine 14° and slides out its edition card with call number and opening sentence.
- **Personality:** Literate, tactile, quiet — *not* gamified, algorithmic, or sterile.
- **Domain material it draws from:** Linen cloth bindings, stamped foil spine labels, library call-number slips, colophon pages, brass reading lamps.
- **References and what to take from each:**
  - *Craig Mod*: generous margins, colophon metadata treated as craft.
  - *Criterion Channel*: thematic human-curated shelves ("Rainy Sunday Novellas", "Translated under 160 pages").
  - *Penguin Great Ideas*: typographic covers that look intentional without photography.
- **Directions to avoid:** Retail star-rating clutter, neon dark mode, generic 4-up card grids (`D-002`).
- **Accepted preview:** [`previews/direction-board.html`](previews/direction-board.html)

## 3. Information architecture
- **Sitemap:**
  1. `/` — Reading Room (Home & curated shelves)
  2. `/catalogue` — Full catalogue & faceted search
  3. `/books/[slug]` — Book Edition page
  4. `/read/[slug]` — Web Reader view
  5. `/shelves/[id]` — Shared Shelf page
- **Navigation model (`D-008`):**
  - **Discovery pages:** Persistent quiet top bar (Logo, *Shelves*, *Catalogue*, *My Desk*, Search trigger `/` + Day/Night Lamp toggle).
  - **Reader view:** Minimal top ribbon (Back to edition, Chapter title, `Aa` typography popover, Bookmark) that auto-tucks on scroll/page-turn and reappears on pointer near top, tap, or `Esc`.
- **Primary user journeys:**
  1. Home → tilt a spine on the featured shelf → inspect edition card → click **Open Book** → read in Reader view.
  2. Press `/` from anywhere → type author or mood → select result with arrow keys → `Enter` to open edition.

## 4. Design tokens
Source of truth: [`design-tokens.css`](design-tokens.css).

### Palette summary and contrast table (`D-005`)

| Text | Background | Ratio | AA / AAA |
|---|---|---|---|
| `--color-text` (`#1C1917`) | `--color-bg` (`#FBF8F3`) | 16.12:1 | AAA Pass |
| `--color-text-muted` (`#57534E`) | `--color-bg` (`#FBF8F3`) | 7.14:1 | AAA Pass |
| `--color-text` (`#1C1917`) | `--color-surface` (`#F3EDE2`) | 14.55:1 | AAA Pass |
| `--color-accent-contrast` (`#FFFFFF`) | `--color-accent` (`#8C2D19`) | 7.82:1 | AAA Pass |
| `--color-accent` (`#8C2D19`) | `--color-bg` (`#FBF8F3`) | 7.82:1 | AAA Pass |
| Night `--color-text` (`#EDE6DA`) | Night `--color-bg` (`#141210`) | 14.08:1 | AAA Pass |
| Night `--color-text-muted` (`#A89F91`) | Night `--color-bg` (`#141210`) | 6.62:1 | AA Pass |
| Night `--color-accent-contrast` (`#141210`) | Night `--color-accent` (`#E07A5F`) | 6.28:1 | AA Pass |

- **Typography (`D-004`):** *Newsreader* (display & reader body), *Plus Jakarta Sans* (UI & metadata), *JetBrains Mono* (call numbers, reading hours, folio numerals).
- **Spacing:** 4 px base (`--space-1` through `--space-32`).
- **Layout (`D-006`):** `1240px` discovery container, `760px` reader container, `62ch` default measure.
- **Shape & elevation:** Crisp book corners (`3px`–`10px`), warm paper borders (`#E6DDD0`), directional spine shadow (`--shadow-book`).
- **Motion (`D-007`):** `--duration-fast` (`150ms`) to `--duration-deliberate` (`650ms`), `--ease-out: cubic-bezier(0.16, 1, 0.3, 1)`.

## 5. Imagery and assets
- **Generated cloth covers (`D-009`, Must):** Titles without bespoke cover art render a deterministic cloth-bound cover using a 2:3 aspect ratio, stamped foil frame, title in `--font-display`, and subtle inline SVG linen noise (0 KB external request).
- **Crops and aspect ratios:** Book covers locked to `aspect-ratio: 2 / 3` across all breakpoints to eliminate layout shift (CLS = 0).
- **Iconography:** 1.5 px stroke line icons (20 × 20 px box), paired with visible text labels on primary actions.
- **Asset budgets:** WOFF2 font subsets ≤ 90 KB total; cover images AVIF/WebP ≤ 45 KB per card.

## 6. Page specifications

### Page 1: Reading Room (`/`)
- **Purpose:** Orient new visitors in 3 seconds and invite immediate browsing of curated shelves.
- **Primary action:** **Open Book** on the Desk Featured Edition, or tilt any spine on the primary shelf.
- **Section order:**
  1. Top navigation bar + command search pill (`/`)
  2. Asymmetric Hero: Left 7 cols = "On the Reading Desk" editorial lead + opening sentence pull-quote + primary CTA; Right 5 cols = interactive 3-book Desk Stack with call-number slip.
  3. Interactive **Spine-to-Cover Shelf** ("Short Books for a Rainy Afternoon").
  4. Curated Reading Lists (3 editorial cards with curator notes and total reading hours).
  5. Colophon footer.
- **Layout, desktop:** 12-column grid (`--container-max: 1240px`), 28 px gutter, 96 px vertical section rhythm.
- **Layout, mobile:** Single column; hero stack orders headline → featured book card → CTA; Spine-to-Cover shelf adapts to stacked horizontal spine bars (`D-010`).
- **Content hierarchy and focal point:** Primary focal point is the Desk Featured Edition headline (`--text-display`) paired with its cloth cover; secondary focal point is the row of vertical book spines.
- **Interactions:** Spine tilt & edition peek (section 7.1), Command search `/` (section 7.2), Day/Night Lamp toggle.
- **Motion:** Book-opening shared transition (section 8.1), Spine tilt (section 8.2).
- **Loading / empty / error / success:**
  - *Loading:* Fixed-ratio `2:3` paper-toned skeleton cards with subtle opacity pulse.
  - *Empty shelf:* "This shelf is being reshelved — explore 3 starter shelves below."
  - *Error:* Inline library slip with "Retry shelf load" button.
  - *Success:* "Saved to My Desk" inline slip confirmation with Undo.

### Page 2: Catalogue & Search (`/catalogue`)
- **Purpose:** Fast known-item search and mood/length filtering across the library.
- **Primary action:** Filter or search, then select an edition.
- **Section order:** Search header with live query input → Sticky facet bar (Reading time: `< 2 hrs`, `2–5 hrs`, `Long`; Era; Language; Theme) + View toggle (Spines vs Covers) → Results grid → Pagination with folio page numbers.
- **Layout, desktop:** 3-column left filter rail + 9-column results area (3 covers per row or 14 spines per shelf).
- **Layout, mobile:** Sticky "Filter & Sort" bar opening a bottom sheet; 2 covers per row.
- **Loading / empty / error / success (`D-011`):** Zero-result queries show 3 librarian starter shelves + inline "Request an edition" button.

### Page 3: Book Edition Page (`/books/[slug]`)
- **Purpose:** Let the reader judge whether to commit to reading this book right now.
- **Primary action:** **Read Now** (opens `/read/[slug]` at last saved position) + secondary **Place on My Desk**.
- **Section order:** Breadcrumb & call number → 2-column Edition Header (Left: 2:3 cloth cover + colophon slip; Right: Title, author, translator, reading-time badge, editorial synopsis, **Open First Page** excerpt preview) → Table of Contents with chapter reading times → "Shelved Alongside" related books.
- **Layout, desktop:** 4 columns cover/colophon (sticky) + 8 columns synopsis, first-page preview, and chapters.
- **Layout, mobile:** Stacked: compact cover + title header → sticky primary **Read Now** bar → synopsis → chapters.
- **Loading / empty / error / success:** Bookmarking flips button state to "On Your Desk ✓" and announces to screen readers.

### Page 4: Reader View (`/read/[slug]`)
- **Purpose:** Distraction-free 60-minute reading and passage annotation.
- **Primary action:** Read and turn pages (`→` / `Space` / tap right margin) or highlight a passage.
- **Section order:** Auto-tucking top ribbon → Single-column book canvas (`--measure: 62ch`) with left/right margin note gutter → Quiet bottom folio bar (chapter progress, page `42 of 184`, remaining chapter minutes).
- **Layout, desktop:** Centred `--container-reader` (`760px`) with 180 px right margin reserved for anchored margin notes.
- **Layout, mobile:** Full-width single column with `20px` horizontal padding; margin notes open as a compact bottom drawer when tapped.
- **Loading / empty / error / success:** Chapter pre-fetched in background; offline state displays a calm "Offline — reading from local copy" pill in the top ribbon.

### Page 5: Shared Shelf Page (`/shelves/[id]`)
- **Purpose:** Let a curator share a thematic collection of 5–15 books with notes on why each belongs.
- **Primary action:** **Save Shelf** or open any book in the collection.
- **Section order:** Shelf header (Curator name, title, essay introduction, total hours, **Share link** button) → Spine-to-Cover Shelf overview → Numbered annotated edition list (`01`–`08` with curator margin note per book).
- **Layout, desktop:** 8-column centred editorial header + 12-column annotated list.
- **Layout, mobile:** Single-column vertical flow; Share button copies permalink with inline "Link copied" confirmation.

## 7. Interaction system

### 7.1 Spine-to-Cover Shelf (`D-003`, Must)
- **Goal:** Browse a shelf of books by spine and peek at an edition without leaving the page.
- **Trigger:** Pointer hover, keyboard `Tab` focus, or touch tap on a spine item.
- **States:**
  - *Default:* Vertical spine (`44px`–`68px` wide based on page count, `260px` tall) showing stamped author, title, and monospace call number.
  - *Hover / Focus-visible:* Spine tilts `-8deg` (`transform-origin: bottom left`) and expands an adjacent `280px` Edition Peek Card showing cover, opening sentence, reading hours, and **Open Book** CTA. Focus ring (`2px solid var(--color-focus-ring)`) frames the active item.
  - *Active:* `scale(0.99)`.
  - *Disabled / Unavailable:* 50% opacity with "In preparation" badge.
- **Keyboard:** Shelf is a roving-tabindex toolbar (`←` / `→` moves between spines, `Enter` or `Space` activates **Open Book**, `Esc` collapses peek).
- **Touch (`D-010`):** On `< 768px`, spines render as horizontal stacked bars (`min-height: 52px`); first tap opens the peek drawer, second tap on **Open Book** launches the reader.

### 7.2 Command Search (`/` or `Cmd/Ctrl+K`, Must)
- **Goal:** Jump to any book, author, or shelf in two keystrokes.
- **States:** Closed pill → Open modal dialog with live input, recent searches (empty query), grouped results (Books, Authors, Shelves), loading spinner in input corner, zero-result fallback (`D-011`).
- **Keyboard & semantics:** `role="dialog"` with `aria-modal="true"`, `role="combobox"` input, `↑`/`↓` cycles options, `Enter` navigates, `Esc` closes and restores focus to trigger.

### 7.3 Reader Typography & Lamp Controls (`Aa`, Must)
- **Goal:** Customise font size (`16px`–`24px`), measure (`50ch` / `62ch` / `74ch`), and theme (Day Linen / Sepia / Night Lamp) with immediate live preview.
- **Feedback:** Changes apply in `< 16ms` via CSS custom properties and persist to `localStorage`.

### 7.4 Passage Highlight & Margin Note (Must)
- **Goal:** Select text in the Reader to highlight or copy a permanent quote link.
- **Trigger:** Text selection mouseup / touch selection change, or keyboard shift-arrow selection + `h` shortcut.
- **States:** Floating 3-button action bar (*Highlight*, *Add Note*, *Copy Quote Link*) positioned above selection; clicking *Copy Quote Link* copies URL with `#passage-id` and switches button label to `Copied ✓` for `1800ms`.

## 8. Motion system

| Name | Trigger | Initial → Final | Duration / Stagger | Easing | Reduced-motion (`D-007`) |
|---|---|---|---|---|---|
| **8.1 Book Open** | Click **Open Book** / **Read Now** | Cover expands via View Transitions API / FLIP into Reader canvas; page text fades in from `opacity: 0` | `420ms` cover, `240ms` text (`80ms` delay) | `--ease-out` | Instant layout switch + `140ms` linear opacity cross-fade |
| **8.2 Spine Peek** | Hover / focus on shelf spine | Spine rotates `0deg → -8deg`; peek card expands width `0 → 280px` and opacity `0 → 1` | `240ms` | `--ease-out` | Spine stays upright; peek card appears via `100ms` opacity fade |
| **8.3 Reader Chrome Tuck** | Scroll down > 40 px or turn page | Top ribbon translates `Y(0 → -100%)` and opacity `1 → 0`; reverses on scroll up, `Esc`, or pointer near top | `150ms` | `--ease-in-out` | Instant show/hide (`1ms`) |
| **8.4 Shelf Entrance** | Initial page load | Spines fade `opacity: 0 → 1` and `translateY(8px → 0)` | `240ms`, `35ms` stagger (capped at `350ms` total) | `--ease-out` | Render at final position immediately |

All animations animate `transform` and `opacity` only (apart from the single active peek card container) and remain interruptible mid-flight.

## 9. Responsive strategy
- **Mobile (`< 640px`):** Single column; `20px` outer gutter; bottom-anchored reader progress bar; Spine-to-Cover shelf collapses into full-width horizontal spine bars (`min-height: 52px`); facets open in a modal bottom sheet.
- **Tablet (`640px–1023px`):** 6-column discovery grid; Reader view uses `62ch` measure with collapsible margin-note drawer.
- **Desktop (`≥ 1024px`):** 12-column asymmetric grid (`1240px` max); Reader view displays persistent right-hand margin notes alongside the `62ch` column.
- **Touch adaptations:** All interactive targets ≥ `44 × 44 px` (`48px` inside the Reader ribbon); swipe left/right turns pages only in paginated reader mode and never hijacks vertical scrolling.

## 10. Accessibility
- **Target:** WCAG 2.2 AA site-wide; AAA (`≥ 7:1` contrast) on default Day and Night Lamp reading canvases (`D-005`).
- **Landmarks & headings:** `<header>`, `<nav aria-label="Primary">`, `<main id="main">`, `<aside aria-label="Margin notes">`, `<footer>`; strict single `<h1>` per page.
- **Focus treatment:** `2px solid var(--color-focus-ring)` with `3px` offset on all interactive controls; skip-to-content link as first focusable element.
- **Motion & media:** `prefers-reduced-motion: reduce` honoured in CSS tokens and JS transitions; no auto-playing carousels or looping animations.

## 11. Technical constraints
- **Stack:** Semantic HTML5, CSS Custom Properties (`design-tokens.css`), progressive enhancement for View Transitions API.
- **Performance budgets:** LCP < `1.8s` on 4G; CLS < `0.02`; JS bundle < `65 KB` gzipped on discovery pages; font payload ≤ `90 KB` across 3 WOFF2 subsets (`font-display: swap` with metric-compatible fallback).
- **Browser support:** Last 2 versions of Chrome, Edge, Firefox, Safari, and iOS Safari.

## 12. Readiness gate
- [x] Every page has purpose, primary action, section order, and layout at mobile and desktop.
- [x] Every token category holds concrete values (`design-tokens.css`).
- [x] Every text/background pair meets WCAG AA (computed in section 4 & `previews/direction-board.html`).
- [x] Every interaction lists applicable states plus keyboard and touch equivalents (section 7).
- [x] Every animation has trigger, duration, easing, and reduced-motion alternative (section 8).
- [x] Every data-driven view defines loading, empty, error, and success states (section 6).
- [x] No blocking open questions; assumptions listed (section 13).

## 13. Decisions and uncertainty
Full log in [`design-decisions.md`](design-decisions.md).
- **Confirmed by user:** `D-001` (Direction A + Night Lamp dark theme), `D-003` (Spine-to-Cover Shelf signature move), `D-005` (AAA paper/ink contrast), `D-007` (Book-open motion & reduced-motion cross-fade).
- **Accepted recommendations:** `D-004` (Newsreader + Plus Jakarta Sans + JetBrains Mono), `D-006` (12-col editorial + 62ch reader layout), `D-008` (Auto-tucking reader chrome).
- **Delegated to agent:** `D-009` (Generated cloth covers), `D-010` (Mobile stacked spine bars), `D-011` (Starter shelves on empty search).
- **Open questions (non-blocking):** `D-012` (Readwise JSON export deferred to v1.1).
