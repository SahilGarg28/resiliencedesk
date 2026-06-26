---
name: ponytail-help
description: >
  Quick-reference card for ponytail levels and commands. One-shot display only —
  does not change mode or persist state. Trigger: ponytail help, /ponytail-help.
---

# Skill: ponytail-help

Display this reference when invoked. Do **not** change mode or write flag files.

---

## Levels

| Level | Trigger | What it does |
|-------|---------|--------------|
| **Lite** | `@ponytail lite` | Build what's asked; name lazier alternative in one line. |
| **Full** | `@ponytail` | Ladder enforced: YAGNI → reuse → stdlib/ADK → minimum. **Default.** |
| **Ultra** | `@ponytail ultra` | YAGNI extremist; challenges requirement before building. |

Level sticks until changed or session end.

---

## Antigravity commands

| Command | Action |
|---------|--------|
| `@ponytail` | Enable full lazy mode for this task |
| `@ponytail lite` | Build + suggest simpler path |
| `@ponytail ultra` | Minimal diff; question scope |
| `@ponytail-help` | This card |
| "stop ponytail" / "normal mode" | Deactivate |

---

## ResilienceDesk guardrails (always on)

Ponytail **never** skips:

- `@threat-model` before `agents/` / `guardrails/` edits
- `@demo-scenario` before commit
- `SafetyAgent` / eval gates
- Flood prep disclaimer

---

## More

Full docs: https://github.com/DietrichGebert/ponytail
