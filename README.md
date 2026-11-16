# Visual Architect

An adaptive AI creative-direction and website design-specification skill for **Antigravity** (and compatible `.agents/skills` hosts).

Most design prompts fail because they ask users to pick from abstract jargon (*"Do you want Neo-Brutalist or Editorial?"*) and hand coding agents vague adjectives (*"warm, modern, smooth"*). **Visual Architect** fixes both sides:

1. **Show, then ask:** Renders self-contained HTML **visual previews** (direction boards, palette contrast sheets, type specimens, layout wireframes, live motion demos) so you choose by looking.
2. **Decisions you own:** Tracks every choice in a **decision ledger** with explicit status (`Confirmed by user`, `Accepted recommendation`, `Delegated to agent`, `Assumption — needs validation`, `Open question`, `Rejected`).
3. **A handoff a coding agent can build without guessing:** Outputs a 7-point **build-ready specification** paired with production **CSS/JSON design tokens** (`design-tokens.css`) and computed WCAG contrast ratios.

---

## Quick start

### Option 1 — Global install (available in all workspaces)

**Windows (PowerShell):**
```powershell
Copy-Item -Recurse ".agents\skills\visual-architect" "$HOME\.gemini\config\skills\visual-architect" -Force
```

**macOS / Linux:**
```bash
mkdir -p ~/.gemini/config/skills
cp -R .agents/skills/visual-architect ~/.gemini/config/skills/visual-architect
```

### Option 2 — Workspace install (single project)
Copy `.agents/skills/visual-architect/` into your project's `.agents/skills/` directory so the path is:
```text
your-project/.agents/skills/visual-architect/SKILL.md
```

---

## Usage

Invoke `/visual-architect` with a subcommand or natural language:

```text
/visual-architect create
I want a digital library where people can discover, shelve, read, and share books.
```

```text
/visual-architect explore three contrasting creative directions for a specialty coffee roaster
/visual-architect review the checkout page for hierarchy, contrast, and interaction states
/visual-architect enhance the homepage hero with an interactive book-spine shelf
/visual-architect motion specify how a book cover expands into the reader view
/visual-architect status
```

### Commands

| Group | Subcommands | Modifies code? |
|---|---|---|
| **Create & specify** | `create`, `explore`, `specify` | No — writes design docs, previews, and tokens |
| **Focused modules** | `layout`, `motion`, `interactions`, `identity`, `responsive` | Only after explicit approval |
| **Audit** | `review` | Never — read-only P0–P3 rubric report |
| **Improve** | `redesign`, `enhance`, `refine` | Yes — after scope & preview approval |
| **Manage** | `status`, `update`, `help` | No |

See [docs/commands.md](docs/commands.md) and [docs/usage-guide.md](docs/usage-guide.md).

---

## Worked example: *Folio* (Digital Library)

See [`examples/digital-library/`](examples/digital-library/) for a complete, build-ready output package passing all 7 readiness checks:

- [`project-brief.md`](examples/digital-library/project-brief.md) — intake summary, audience, journeys, constraints
- [`previews/direction-board.html`](examples/digital-library/previews/direction-board.html) — interactive 3-option direction board with live WCAG contrast calculator, interactive book spines, and reduced-motion toggle
- [`design-decisions.md`](examples/digital-library/design-decisions.md) — decision ledger (`D-001`–`D-012`)
- [`design-tokens.css`](examples/digital-library/design-tokens.css) — Tier 1 primitives + Tier 2 semantic roles + Night Lamp dark theme + `prefers-reduced-motion` tokens
- [`design-specification.md`](examples/digital-library/design-specification.md) — full page-by-page, interaction, and motion blueprint

---

## Repository structure

```text
visual-architect/
├── README.md
├── CHANGELOG.md
├── LICENSE
├── .agents/skills/visual-architect/
│   ├── SKILL.md                        # Concise router + global guardrails
│   ├── workflows/
│   │   ├── create.md                   # create, explore, specify, focused modules + readiness gate
│   │   ├── review.md                   # Evidence-based P0–P3 audit workflow
│   │   └── change.md                   # redesign, enhance, refine approval + verification loop
│   ├── references/
│   │   ├── previews.md                 # Visual preview types & HTML build rules
│   │   ├── tokens.md                   # 2-tier design token architecture & WCAG contrast math
│   │   ├── anti-generic.md             # Domain mining, signature moves, swap test
│   │   ├── design-taxonomy.md          # Art directions with "use when / watch out for"
│   │   ├── layout-systems.md           # Layout structures, trade-offs, responsive guidance
│   │   ├── visual-identity.md          # Pairing strategies, palette construction
│   │   ├── interaction-patterns.md     # Discovery, navigation, controls, keyboard/touch rules
│   │   └── motion-design.md            # Motion families, easing tokens, reduced-motion safeguards
│   └── templates/
│       ├── project-brief.md
│       ├── design-specification.md
│       ├── design-decisions.md
│       ├── design-tokens.css
│       ├── review-report.md
│       └── preview-starter.html
├── docs/
│   ├── architecture.md
│   ├── commands.md
│   ├── installation.md
│   └── usage-guide.md
└── examples/
    └── digital-library/
```

## License

MIT. See [LICENSE](LICENSE).
