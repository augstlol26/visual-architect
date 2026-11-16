# Design decision log — Folio

The single record of what was decided, by whom, and why.

| ID | Area | Decision | Status | Rationale | Blocking? | Date |
|---|---|---|---|---|---|---|
| D-001 | Direction | **Direction A — Reading Room** (warm linen paper `#FBF8F3`, oxblood cloth `#8C2D19`, serif-led hierarchy) with Direction C's warm dusk palette adopted as the dark-mode theme | Confirmed by user | User wanted tactile warmth by day and a true low-glare reading lamp mode at night | No | 2026-11-16 |
| D-002 | Direction | Direction B — Catalogue Drawer (cold brutalist index-card grid, monospace-first) | Rejected | Memorable, but felt too archival and sterile for 60-minute leisure reading | No | 2026-11-16 |
| D-003 | Signature move | **Spine-to-Cover Shelf**: shelves display books spine-out at proportional page-count widths; hovering, focusing, or tapping tilts a spine 14 deg and slides out the edition card with call number and opening sentence | Confirmed by user | Grounds the site in a real library object instead of a generic 4-up card grid | No | 2026-11-16 |
| D-004 | Typography | Display & Reader Serif: *Newsreader* (optical size variable); UI & Metadata Sans: *Plus Jakarta Sans*; Call Numbers & Folio Marks: *JetBrains Mono* | Accepted recommendation | Newsreader holds up at both 56 px display headlines and 19 px long-form body; monospace gives catalogue slips crisp tabular alignment | No | 2026-11-16 |
| D-005 | Colour & contrast | Body text `#1C1917` on `#FBF8F3` (16.1:1, AAA); muted metadata `#57534E` on `#FBF8F3` (7.1:1, AAA); accent `#8C2D19` with `#FFFFFF` text (7.8:1, AAA) | Confirmed by user | Long-form reading benefits from AAA contrast without harsh pure-#000-on-#FFF glare | No | 2026-11-16 |
| D-006 | Layout | 12-column asymmetric editorial grid on discovery pages (`1240px` max); single-column reading canvas (`62ch` default measure, user-adjustable `50ch`–`74ch`) | Accepted recommendation | Separates browsing density from reading calm | No | 2026-11-16 |
| D-007 | Motion | Book-opening transition uses shared-element cover expansion (`420ms`, `--ease-out`); under `prefers-reduced-motion: reduce`, cross-fades in `140ms` with zero scale or 3D rotation | Confirmed by user | Keeps the physical book metaphor without forcing motion on sensitive readers | No | 2026-11-16 |
| D-008 | Navigation | Persistent quiet top bar with 4 destinations + `/` command search; inside the Reader, chrome auto-tucks on scroll/page-turn and reappears on pointer move, `Esc`, or tap | Accepted recommendation | Prevents navigation chrome from competing with the book text | No | 2026-11-16 |
| D-009 | Imagery | Generated cloth-bound covers for public-domain titles lacking high-res art, using deterministic palette + typographic grid + subtle SVG linen grain | Delegated to agent | Avoids broken placeholders or ugly stretched JPEGs in the catalogue | No | 2026-11-16 |
| D-010 | Responsive | On screens < `768px`, the Spine-to-Cover shelf switches from horizontal spines to a compact stacked spine list with tap-to-peek drawer and 48 px minimum tap targets | Delegated to agent | Thin vertical spines are hard to tap accurately on phones | No | 2026-11-16 |
| D-011 | Content states | Empty search results recommend 3 librarian-curated starter shelves and show a "Request an edition" inline action | Delegated to agent | Dead-end empty states kill discovery sessions | No | 2026-11-16 |
| D-012 | Integrations | Annotation export format (Markdown vs Readwise JSON) deferred to v1.1; UI shows "Copy Markdown" only for launch | Open question | Non-blocking for initial build | No | 2026-11-16 |

## Change history
- 2026-11-16 — Initial discovery completed (`D-001` through `D-012`). Readiness gate 7/7 passing.
