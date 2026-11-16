# Layout systems

## Structures

| Structure | Use when | Avoid when | Responsive note |
|---|---|---|---|
| **Single-column editorial** | Long reading, narrative, simple funnels | Dense comparison or dashboards | Naturally mobile-first |
| **Multi-column editorial grid** | Magazines, portfolios, content hubs | Content too thin to fill columns | Collapse 12 → 6 → 4 columns |
| **Split-screen** | Two equal ideas (product + story, image + form) | Either side has little content | Stack; decide which half leads on mobile |
| **Full-bleed hero** | Strong imagery, a single message | No art-directed image available | Art-direct crops per breakpoint |
| **Bento grid** | Several features of different weight | Everything is equally important (it becomes a card wall) | Re-flow to 1–2 columns; keep size hierarchy |
| **Card collection / masonry** | Browsable items of varied ratios | Items need comparison of attributes (use a table/list) | Fix aspect ratios to prevent layout shift |
| **List–detail / master–detail** | Email-like or catalogue browsing | Few items | Becomes push navigation on mobile |
| **Sidebar + content** | Docs, apps, filters | Marketing pages | Sidebar becomes drawer or top tabs |
| **Dashboard grid** | Monitoring, multiple live widgets | Storytelling | Prioritise the single most important widget on mobile |
| **Layered / overlapping** | Expressive brands, depth | Dense information | Reduce overlap on small screens |
| **Horizontal narrative** | Timelines, galleries, storytelling | Primary content (horizontal scroll hides it) | Provide visible controls; never trap vertical scroll |
| **Pinned scroll narrative** | Product explainers, step-by-step reveals | Content people need to scan quickly | Often unpin on mobile; offer reduced-motion static version |

## Vocabulary
- **Container**: width-constrained content region; record its max-width as a token.
- **Measure**: line length of body text; 45–75 characters.
- **Gutter**: space between columns and at the page edges.
- **Rhythm**: a repeating spacing scale shared across the page.
- **Focal point**: the first thing the eye lands on; one primary per view.
- **Sticky / fixed**: attached to the viewport during a scroll range / always.
- **Fold**: the first viewport; varies by device, so it's not a fixed line.
- **Breakpoint**: a width at which layout rules change; set by content, not devices.

## Record per page
Container and measure; grid columns and gutters per breakpoint; section order and relative proportions; primary and secondary focal points; spacing rhythm (tokens); sticky and fixed elements; density; overflow and scroll behaviour; what changes at each breakpoint.

Choose layouts for the content and the task in front of the user.
