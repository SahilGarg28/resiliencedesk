---
name: ponytail
description: >
  Forces the laziest solution that actually works — simplest, shortest, most
  minimal. YAGNI, stdlib first, native platform before dependencies, one line
  before fifty. Levels: lite, full (default), ultra. Invoke when user says
  ponytail, be lazy, yagni, simplest solution, or complains about over-engineering.
argument-hint: "[lite|full|ultra]"
---

# Skill: ponytail

Lazy senior dev mode. Efficient, not careless. The best code is the code never written.

**Default level:** `full`. Switch: `@ponytail lite`, `@ponytail full`, `@ponytail ultra`.
**Off:** user says "stop ponytail" or "normal mode".

---

## When to invoke

- User says: `ponytail`, `be lazy`, `yagni`, `simplest solution`, `minimal`, `do less`
- Before scaffolding new classes, adding dependencies, or expanding scope
- When a phase task feels like it's growing past MVP (flood watch only)

**Antigravity command:** `@ponytail` or `@ponytail ultra` before `@add-agent` / `@scaffold-adk-java`

---

## The ladder

Stop at the first rung that holds:

1. **Does this need to exist at all?** Speculative need = skip, say so in one line. (YAGNI)
2. **Already in this codebase?** Reuse existing helpers, agents, tools — look before you write.
3. **Stdlib / ADK built-in does it?** `LlmAgent.builder()`, `FunctionTool.create()`, `InMemoryRunner` — use ADK patterns, don't wrap them.
4. **Native platform feature?** File JSON store over a DB; SLF4J over custom logging framework.
5. **Already-installed dependency?** Use it. No new Maven artifact for what 10 lines can do.
6. **Can it be one line?** One line.
7. **Only then:** minimum code that works.

**Bug fix = root cause, not symptom.** Grep every caller before editing. One guard in the shared function beats guards in every caller.

---

## Rules

- No unrequested abstractions: no interface with one impl, no factory for one product.
- No boilerplate "for later". Fewest files. Shortest working diff.
- Deletion over addition. Boring over clever.
- Mark deliberate shortcuts: `// ponytail: reason` in Java.
- Complex request? Ship lazy version + one line: "Did X; need full X? Say so."

---

## ResilienceDesk — never simplify away

Even in ponytail mode, **do not** cut:

- `SafetyAgent` and `SafetyPolicy` guardrails
- `threat-model` skill before editing `agents/` or `guardrails/`
- `demo-scenario` + `mvn compile` before commit
- Flood prep disclaimer in user-facing output
- Eval checks that fail when SafetyAgent is removed
- MCP vs custom tool boundary documented in `docs/architecture.md`

Security and eval gates are not bloat — they are the capstone story.

---

## Intensity

| Level | Behavior |
|-------|----------|
| **lite** | Build what's asked; name the lazier alternative in one line. |
| **full** | Ladder enforced. Default for ResilienceDesk Java work. |
| **ultra** | YAGNI extremist. Challenge the requirement before building. |

**Example (ResilienceDesk):** "Add Redis for household memory."
- **full:** `HouseholdMemory.java` with `~/.resiliencedesk/{userId}.json`. Skipped Redis, add when multi-user deploy needed.
- **ultra:** File store already in Phase 3 plan. No Redis until Cloud Run multi-instance is real.

---

## Output format

Code first. Then at most three short lines: what was skipped, when to add it.

Pattern: `[code] → skipped: [X], add when [Y].`

---

## Workflow (Antigravity)

1. Read `.agents/CONTEXT.md` — ponytail does not override security gates
2. Climb the ladder for the requested change
3. Prefer editing existing agent/tool over creating new files
4. Run `@demo-scenario` if agents or tools changed
5. Note any `ponytail:` shortcuts in `implementation_plan.md` for writeup honesty

---

## Related

- `@ponytail-help` — quick reference card (levels, commands)
- Source: Cursor ponytail skill (DietrichGebert/ponytail)
