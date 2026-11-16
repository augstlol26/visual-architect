# Installation

## Option 1 — Global installation (recommended)

Installing globally makes `/visual-architect` available across every workspace on your machine.

### Windows (PowerShell)
```powershell
New-Item -ItemType Directory -Force "$HOME\.gemini\config\skills" | Out-Null
Copy-Item -Recurse ".agents\skills\visual-architect" "$HOME\.gemini\config\skills\visual-architect" -Force
```

Verify that the entry file exists at:
```text
C:\Users\<YourUsername>\.gemini\config\skills\visual-architect\SKILL.md
```

### macOS / Linux
```bash
mkdir -p ~/.gemini/config/skills
cp -R .agents/skills/visual-architect ~/.gemini/config/skills/visual-architect
```

Verify that the entry file exists at:
```text
~/.gemini/config/skills/visual-architect/SKILL.md
```

---

## Option 2 — Workspace installation

To scope the skill to a single repository:

1. Copy `.agents/skills/visual-architect/` into the target repository's `.agents/skills/` directory.
2. Confirm the path is:
   ```text
   your-project/.agents/skills/visual-architect/SKILL.md
   ```
3. Open the project in Antigravity and invoke `/visual-architect help`.

> **Note:** Copy only the `.agents/skills/visual-architect` folder into your skills directory, not the outer documentation repository.

## Updating

Re-run the copy command above to overwrite the installed skill folder with the latest version. Because project specifications are saved inside your project's `docs/design/` folder, updating the skill never overwrites your project design files.
