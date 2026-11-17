# Vibe-to-Token Translator

Users give feedback in sensory language, not CSS variables. Use this map during `enhance`, `refine`, `update`, and interviews to translate 20 common phrases into exact token adjustments—never guess randomly.

Always check WCAG contrast after any palette or border adjustment, and record confirmed shifts in `design-decisions.md`.

| When the user says… | Concrete token adjustments |
|---|---|
| **"Make it quieter / calmer"** | Reduce `--color-border` contrast by ~35% toward `--color-bg`; raise section spacing (`--space-16` → `--space-24`); cut `--shadow-*` opacity in half; slow `--duration-base` to `300ms`–`360ms`. |
| **"Make it feel more editorial / bookish"** | Switch `--font-display` (or `--font-body` for long reading) to a high-contrast serif; tighten `--measure` to `58ch`–`64ch`; warm `--color-bg` slightly off pure white (`#FBF8F3` / `#F7F5F0`); bump `--leading-base` to `1.65`. |
| **"Make it snappier / faster"** | Cut `--duration-fast` to `90ms`–`120ms`, `--duration-base` to `160ms`–`180ms`; switch `--ease-out` to `cubic-bezier(0.2, 1, 0.3, 1)`; reduce stagger intervals to `20ms`–`30ms`. |
| **"Less corporate / less template-y"** | Replace symmetric 3-column card walls with an asymmetric grid; drop neutral blue defaults for a domain-derived accent; add one signature move (see [anti-generic.md](anti-generic.md)); tighten `--radius-*` or vary border treatments. |
| **"More tactile / physical"** | Add subtle hairline borders (`1px solid var(--color-border)`) + crisp `--shadow-1`; warm neutral surfaces; add `:active { transform: scale(0.98) }` tactile press feedback; introduce subtle 0-KB paper/grain texture. |
| **"Give it more breathing room"** | Increase `--space-16` / `--space-24` section padding by 25–50%; step up card internal padding (`--space-4` → `--space-6`); relax `--leading-base` by `+0.1`; reduce visible card density per row. |
| **"Make it denser / more pro"** | Reduce card padding (`--space-6` → `--space-4`); tighten `--space-8` section gaps; switch tabular data to `--font-mono` with `font-variant-numeric: tabular-nums`; cap headings at `--text-xl`. |
| **"More authoritative / institutional"** | Tighten `--tracking-tight` (`-0.025em`) on headings; reduce `--radius-md`/`--radius-lg` (`8px` → `4px` or `2px`); shift accent toward deep ink/cobalt/oxblood; remove playful bounce/overshoot from easing. |
| **"Warmer / more inviting"** | Shift neutral base hue toward warm parchment/sand (`+3deg`–`+8deg` warm tint); increase `--radius-md` (`4px` → `8px`–`10px`); swap pure `#000000` ink for `#1C1917` or `#1F2418`. |
| **"Crisper / sharper"** | Drop soft diffused shadows (`blur > 12px`) for `1px` structural borders or hard `2px–3px` offset shadows; set `--radius-sm` to `0px–2px`; boost border contrast slightly. |
| **"Higher contrast / easier to read"** | Push body text to ≥ 10:1 (`#111827` / `#1C1917` on light, `#F3F4F6` on dark); push `--color-text-muted` to ≥ 6.5:1; bump `--text-base` from `16px` to `17px–18px`. |
| **"Softer / gentler"** | Lower primary text from `#000000` to warm charcoal (`~14:1` contrast); soften borders (`opacity: 0.5`); raise `--radius-lg` to `12px–16px`; lengthen `--duration-base` to `260ms`. |
| **"More dramatic / cinematic"** | Widen display-to-body ratio (`--text-display` ≥ `3.5 × --text-base`); introduce dark high-contrast hero bands; slow signature reveals to `--duration-deliberate` (`600ms–750ms`). |
| **"More technical / utilitarian"** | Pair grotesk sans with `--font-mono` uppercase overlines (`--tracking-wide: 0.08em`); use `1px` architectural hairlines (`--radius-sm: 2px`); enable `tabular-nums` globally on metrics. |
| **"More luxurious / elevated"** | Maximize negative space (`--space-24`–`--space-32`); drop `--font-display` weight (`400` or `500` instead of `700`); pair thin serif display with quiet sans metadata; trim to one restrained metallic/earth accent. |
| **"Less busy / too noisy"** | Cut competing accent colors down to **one** `--color-accent`; replace filled secondary buttons with ghost/border links; collapse multi-badge clutter into single-line metadata. |
| **"Feels flat / lifeless"** | Add clear surface separation between `--color-bg`, `--color-surface`, and `--color-surface-raised`; introduce directional `--shadow-1` + crisp border highlight; refine hover/focus state delta. |
| **"Feels heavy / clunky"** | Reduce border thickness (`2px` → `1px`); lighten shadow alpha by 50%; reduce `--text-xl`/`--text-2xl` font-weight by one step (`700` → `600` or `500`); increase gutter width. |
| **"More playful / expressive"** | Increase `--radius-lg` (`12px–20px`) and pill buttons (`--radius-full`); allow a lively spring curve (`cubic-bezier(0.34, 1.56, 0.64, 1)`) on small microinteractions (never large containers). |
| **"More grounded / timeless"** | Anchor layout to a strict 12-col grid; avoid gradient fills and glass blurs; pair one proven serif + one grotesk sans; lock palette to 85% neutral surfaces + 15% ink/accent. |
