# Design tokens

Tokens turn adjectives into values. "Warm, confident, smooth" can't be built; `--color-accent: #C2410C`, `--ease-out: cubic-bezier(0.16, 1, 0.3, 1)` can.

## Tiers

1. **Primitive**: raw values with no meaning: `--clay-600: #C2410C`, `--space-4: 16px`.
2. **Semantic**: roles that reference primitives: `--color-accent: var(--clay-600)`. Components use only this tier.
3. **Component** (optional): `--button-radius: var(--radius-full)`, only when a component deliberately departs from the system.

## Required categories

| Category | Must include |
|---|---|
| Colour | Primitive ramps; semantic `bg`, `surface`, `surface-raised`, `text`, `text-muted`, `border`, `accent`, `accent-contrast` (text on accent), `focus-ring`, `success`, `warning`, `error`; a dark set if dark mode is in scope |
| Typography | Families with fallback stacks; scale steps each with size, line-height, weight, letter-spacing; fluid `clamp()` values for display sizes if used |
| Spacing | A scale on a 4 px or 8 px base; section spacing |
| Layout | Container max-widths, content measure, grid columns and gutters, breakpoints |
| Shape | Radii, border widths |
| Elevation | Shadow levels, z-index layers (base, sticky, overlay, modal, toast) |
| Motion | Durations (instant, fast, base, slow, deliberate), named easings as `cubic-bezier()`, a reduced-motion policy |

## Rules

- Every value is concrete; no "TBD" or adjectives. If a value was delegated, still pick one and mark it delegated in the ledger.
- Every text/background pair in use is listed with its contrast ratio.
- Cite ledger IDs in comments where a token encodes a decision (`/* D-004 */`).
- Match the stack you found in intake: plain CSS custom properties always; additionally a Tailwind `@theme` block or config extension, a CSS-in-JS theme object, or platform tokens if that is what the project uses.
- Optionally export `design-tokens.json` in the W3C Design Tokens format (`{"color": {"accent": {"$type": "color", "$value": "#C2410C"}}}`) for tooling.

Start from `templates/design-tokens.css`.

## Contrast

For an sRGB channel `c` in 0–1: `c ≤ 0.04045 ? c / 12.92 : ((c + 0.055) / 1.055) ^ 2.4`.
Relative luminance `L = 0.2126 R + 0.7152 G + 0.0722 B`.
Ratio = `(L_lighter + 0.05) / (L_darker + 0.05)`.
AA: 4.5:1 for body text, 3:1 for large text (≥ 24 px, or ≥ 18.66 px bold) and for UI component boundaries and focus indicators. Compute with a script when one can be run; otherwise show your working.
