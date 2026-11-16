# Project brief — Folio

## Project
- **Name:** Folio
- **One-sentence concept:** A calm digital library where readers discover, shelve, read, and annotate public-domain and independent books with the tactile pleasure of a real reading room.
- **Product/site type:** Web application + editorial storefront (marketing landing, catalogue, book detail, web reader, shared shelves).

## Purpose and audience
- **Primary purpose:** Give long-form readers a distraction-free place to discover and read books online, and share curated shelves with friends or reading groups.
- **Intended audience:** Avid readers, students, book-club organisers, and independent essays/presses who find mainstream retail book sites noisy and algorithmic.
- **Main user needs:**
  - Browse by mood, theme, length, or human-curated shelf rather than bestseller rankings.
  - Open a book immediately in the browser and resume anywhere.
  - Adjust typography, paper tone, and margins for comfortable 60-minute reading sessions.
  - Save passages with margin notes and share a link to a shelf or quote.

## Core journeys and functionality
- **Primary journey:** Land on homepage → browse a curated shelf or search → inspect a book's spine/edition card → open the reader → read and highlight a passage.
- **Secondary journeys:** Build and publish a personal shelf; switch the site and reader into evening ("Night Lamp") mode; filter catalogue by reading time and period.
- **Required features:** Instant search (`/` or `Cmd/Ctrl+K`), facet filters, spine-and-cover shelf view, full-screen reader with typography controls, passage permalink, keyboard page turning.

## Content and structure
- **Known pages:**
  1. Reading Room (Home / Discovery)
  2. Catalogue & Search
  3. Book Edition Page
  4. Reader View
  5. Shared Shelf Page
- **Important content:** Book covers and generated cloth spines, colophon metadata (translator, year, page count, estimated reading hours), pull quotes, reader annotations.
- **Integrations or data dependencies:** OPDS / EPUB ingestion pipeline, full-text search index, local storage + account sync for reading progress.

## Creative direction
- **Initial aesthetic thoughts:** Warm paper, linen cloth bookbindings, library call-number slips, brass reading lamps.
- **Desired feeling:** Quiet, unhurried, literate, tactile — like stepping into an architecture library on a rainy afternoon.
- **References:**
  - * Craig Mod's books & essays*: generous margins, colophon obsession, quiet typography.
  - *Criterion Channel / MUBI*: human curation over endless carousels.
  - *Penguin Great Ideas*: typographic covers where hierarchy and ink texture do the work.
- **Things to avoid:** Amazon-style star-rating clutter, neon dark mode, bouncy startup illustrations, infinite auto-playing carousels.

## Constraints
- **Existing stack or repository:** Greenfield Next.js / semantic HTML + CSS Custom Properties (`design-tokens.css`).
- **Device/browser requirements:** Responsive across phone (one-handed commuter reading), tablet, and desktop; modern evergreen browsers.
- **Accessibility requirements:** WCAG 2.2 AA minimum (AAA 7:1 target Inside the Reader view); full keyboard navigation; `prefers-reduced-motion` support.
- **Performance constraints:** LCP < 1.8 s on 4G; font payload < 90 KB (WOFF2 subset); zero layout shift when book covers load.

## Open questions
- None blocking. Annotation export format (Markdown vs Readwise JSON) deferred to v1.1 (`D-012`).
