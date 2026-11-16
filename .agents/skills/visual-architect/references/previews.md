# Visual previews

Render options so the user chooses by looking. A preview is a small, self-contained HTML page whose CSS custom properties *are* the candidate tokens, so an accepted preview turns into the token file by copying, not by reinterpretation.

## Preview types

| Type | Use for | Contents |
|---|---|---|
| **Direction board** | Creative direction (create step 3, redesign) | One column per direction (A/B/C): name, signature move, palette swatches with hex, display and body type at real sizes, a mini hero composition, a sample button, card, and input, a surface or texture cue, three adjectives |
| **Palette board** | Colour decisions | Primitive swatches, semantic roles, every text/background pair with its computed contrast ratio and AA pass/fail |
| **Type specimen** | Typography | Each scale step with size, line-height, and weight; a paragraph at the real measure; the heading/body pairing in context |
| **Layout wireframes** | Composition, IA, responsive | Greybox sections with labels, rendered at desktop and mobile widths side by side; the same content in two or three compositions |
| **Motion demo** | Animation | A live CSS/JS animation with Replay, timing and easing labelled, a reduced-motion toggle showing the alternative |
| **State sheet** | Interactions | One component in default, hover, focus-visible, active, disabled, loading, and error states |
| **Before/after** | Enhance, refine | The current design and the proposal at the same size, side by side |
| **Token sheet** | Create step 5 | Palette, type scale, spacing ruler, radii, elevations, motion curves |

## Build rules

1. Start from `templates/preview-starter.html`. Keep it a single file with inline CSS and JS and no build step.
2. Put candidate values in `:root` custom properties named as in [tokens.md](tokens.md); style elements only through those variables.
3. Use the project's real content: actual product name, headings, sample data. Placeholder Latin hides whether the hierarchy works.
4. **Fonts:** external font loading may be blocked by the host. Use the closest local or system stack and label the intended face on the preview ("Intended: Fraunces · shown in Georgia"). A fallback is never presented as final.
5. **Imagery:** use CSS gradients, shapes, or inline SVG placeholders captioned with the intended art direction ("duotone portrait, warm shadows, subject left").
6. Label options with letters and give every option equal care, so the comparison is fair.
7. Compute contrast ratios rather than estimating them (formula in [tokens.md](tokens.md#contrast)).

## Delivery

- **Hosts that render HTML** (for example Antigravity's generative UI or artifacts): render it there. Compact previews (≤ 450 px tall) go inline; direction boards and wireframes usually need a standalone or side-pane view. Previews use the design's own colours rather than the host theme; that is the point of them.
- **Everywhere else:** save to `docs/design/previews/<area>-<option>.html` and give the user the path to open in a browser.
- Keep accepted previews in `docs/design/previews/` and link them from the specification; they are part of the handoff.
- When rendering is unavailable, describe each option with concrete values (hex, px, ms, cubic-bezier) and say that no preview was rendered.
