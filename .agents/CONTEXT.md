# ResilienceDesk Project Context & Standards

This document establishes development standards, security guardrails, and quality check requirements for the ResilienceDesk project.

---

## 1. Technical Stack
- **Language**: Java 17
- **Base Package**: `com.resiliencedesk`
- **Default LLM Model**: `gemini-2.5-flash`
- **Build Tool**: Maven (`pom.xml` in root)

---

## 2. Security & Credentials
- **API Key Policy**: **NEVER** commit `GOOGLE_API_KEY`, vertex credentials, or other sensitive keys.
- **Environment variables**: Use `.env` file for local development. Define credentials locally in `.env` and load them at runtime using environment-specific tools.
- **Access check**: Verify authentication using standard GCP utilities before running workflows.

---

## 3. Safety & Disclaimer Requirements
- **Flood Prep Disclaimer**: ResilienceDesk is a planning and preparation aid. It is **NOT** an emergency dispatch system or immediate rescue responder. Any outputs from ResilienceDesk must clearly specify this context when recommending actions.
- **Disclaimer Text Requirement**: Ensure UI/console messages and reports include a warning indicating that the software provides advisory information only and users should follow instructions from local emergency authorities during active flooding.

---

## 4. Pre-modification Check
- **Location Guardrails**: Before modifying files inside `src/main/java/com/resiliencedesk/agents/` or `src/main/java/com/resiliencedesk/guardrails/` (or general agent config/guardrail folders):
  - **MUST** run the `threat-model` skill.
  - Review threat modeling criteria to ensure no prompt injection vulnerabilities or unsafe execution paths are introduced.

---

## 5. Pre-commit & Build Checks
- Before making a commit or proposing a pull request:
  1. Run the `demo-scenario` skill to ensure the end-to-end flow executes without exceptions.
  2. Run `mvn clean compile` to ensure there are no Java build compilation failures.

---

## 6. Ponytail (minimal implementation)
- **Default:** invoke `@ponytail` (full) for Java implementation tasks unless user says "stop ponytail".
- **Goal:** shortest working diff; reuse ADK patterns; no speculative abstractions.
- **Hard stops:** ponytail does **not** waive `threat-model`, `SafetyAgent`, eval gates, or flood disclaimers.
- **Help:** `@ponytail-help` for level reference.
