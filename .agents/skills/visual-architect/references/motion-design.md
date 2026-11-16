# Motion design

Motion communicates state, hierarchy, causality, and spatial relationships. Essential tasks stay instantly usable while it plays.

## Families

| Family | Communicates | Typical duration | Note |
|---|---|---|---|
| State transition | A control changed | 100–200 ms | Fast; must never feel laggy |
| Enter / exit | Content appears or leaves | 200–300 ms in, ~70% of that out | Exits faster than entrances |
| Shared element | Continuity between views | 300–500 ms | View Transitions API, FLIP |
| Scroll-triggered reveal | New section arrives | 400–700 ms, once | Content must be readable without it |
| Scroll-linked | Progress through a story | Bound to scroll | Never hijack scroll speed |
| Parallax | Depth | Bound to scroll | Subtle; disable for reduced motion |
| Stagger | Group relationship and order | 30–80 ms between items | Cap total group time at ~600 ms |
| Morph / layout | Same thing, new form | 250–400 ms | Animate transforms, not layout properties |
| 3D transform | Physical metaphor (cards, books) | 400–900 ms | Signature moments only |
| Kinetic type | Voice, emphasis | Varies | Keep the final state readable |
| Spring / physics | Direct manipulation, tactility | Spring-defined | Ideal for drag and gesture release |

## Easing tokens (starting points)

| Token | Value | Use |
|---|---|---|
| `--ease-out` | `cubic-bezier(0.16, 1, 0.3, 1)` | Entrances, responses to input |
| `--ease-in` | `cubic-bezier(0.7, 0, 0.84, 0)` | Exits |
| `--ease-in-out` | `cubic-bezier(0.65, 0, 0.35, 1)` | On-screen movement from A to B |
| `--ease-linear` | `linear` | Progress, continuous loops, scroll-linked |

## Specification checklist
Trigger and preconditions · start and end states · elements and order · duration, delay, stagger · easing token or spring (stiffness/damping) · transform origin and perspective · interruption and reversal · reduced-motion alternative · mobile adaptation · performance budget.

## Safeguards
- `prefers-reduced-motion: reduce` replaces movement with an opacity fade or an instant change; it doesn't just shorten durations.
- Status is never carried by motion alone.
- Large continuous motion stays out from behind reading content.
- Animate `transform` and `opacity`; profile anything heavier on a mid-range phone.
- Controls stay responsive during animation; interrupted animations reverse from their current state.
- Anything that loops for more than 5 seconds gets a pause control (WCAG 2.2.2).
