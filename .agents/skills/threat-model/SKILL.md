---
name: threat-model
description: Guidelines for security reviews, threat modeling, and testing LLM guardrails for ResilienceDesk.
---

# Skill: threat-model

Use this skill when auditing agents, prompts, or safety guardrails in the ResilienceDesk project.

## Threat Modeling Strategy

1. **Prompt Injection Mitigation**:
   - Verify that user inputs are isolated from system instructions.
   - Do not trust inputs to directly control downstream logic or execute shells.

2. **Tool Execution Scope**:
   - Check if agent tools (MCP or custom function tools) validate parameters (e.g. preventing path traversal, SSRF, or arbitrary code execution).
   - Ensure the agent operates under the principle of least privilege.

3. **Disclaimer & Safety Policy Enforcement**:
   - Check that the safety disclaimer is present in key user interactions.
   - Review how the system responds to query boundaries (e.g. refusing to give official emergency dispatch instructions).

4. **Security Reviews**:
   - Run a mental walkthrough / code-review of changes in `agents/` and `guardrails/` directories to identify potential leaks or exploits.
