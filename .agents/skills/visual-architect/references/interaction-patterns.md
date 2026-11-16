# Interaction patterns

Curate around the user's task, and describe behaviour rather than just naming the pattern.

## Discovery and browsing

| Pattern | Use when | Avoid when | A11y / mobile note |
|---|---|---|---|
| Search with autocomplete + recents | Large catalogue, known-item seeking | Under ~30 items | Announce suggestions; full-screen search on mobile |
| Faceted filtering | Items with several comparable attributes | Few attributes | Show active filters as removable chips; filters in a sheet on mobile |
| Hover preview | Rich items where a peek saves a click | Touch-first audiences only | Needs equivalent focus and tap access |
| Spatial carousel / coverflow | Browsing *is* the experience (covers, art) | Content needs comparison | Visible prev/next, keyboard arrows, pause |
| Compare tray / shortlist | Considered purchases | Impulse flows | Persist across pages |
| Infinite scroll | Feeds, inspiration | Goal-directed search, footers needed | Prefer load-more; preserve position on back |
| Pagination | Findable, shareable positions | Inspiration browsing | Clear current page |

## Navigation
Persistent top bar (≤ 7 items) · side rail (apps, docs) · contextual tabs · breadcrumbs (deep hierarchies) · command palette (power users; always with a visible alternative) · scroll-spy section nav (long pages) · bottom tab bar (mobile apps, 3–5 destinations) · gesture navigation only alongside visible controls.

## Controls and feedback

| Need | Pattern | Note |
|---|---|---|
| Quick edit in place | Inline editing | Clear save/cancel; Esc cancels |
| Secondary detail | Drawer / side panel | Keeps context; trap focus while open |
| Interruptive decision | Modal dialog | Only for decisions that must block |
| Lightweight info | Popover / tooltip | Never the only place for essential info |
| Background result | Toast | Pair with an inline state; give undo for destructive actions |
| Progress | Determinate bar > spinner | Skeletons for layout-shaped loading |
| Consequential action | Undo > confirm dialog | Confirm only when it can't be undone |
| Binary setting | Toggle | Applies instantly; otherwise use a checkbox |

## Microinteractions
Button press · focus-ring transition · save/bookmark confirmation · copy confirmation · inline validation (on blur, then live once corrected) · progress feedback · notification arrival · toggle transition · magnetic or cursor-follow effects (rarely, desktop only, never on core controls).

## Reading and media
Page-turn simulation (signature moment only; offer a plain mode) · single page or spread · continuous scroll · progress and chapter navigation · reader controls for type size, spacing, theme, width · media scrubber with captions · focus or full-screen mode.

## Specify every selected pattern
User goal, trigger, visible change, feedback, resulting state, applicable states, keyboard, screen-reader, and touch equivalents, mobile fit, implementation cost. Every hover or gesture behaviour has a visible equivalent for keyboard and touch.
