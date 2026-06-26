---
name: add-agent
description: Design principles and class setup instructions for implementing LlmAgent and FunctionTool instances using Java ADK.
---

# Skill: add-agent

Use this skill when introducing new agents or defining custom tools for the Java ADK in ResilienceDesk.

## Guidelines

1. **System Persona**:
   - Every `LlmAgent` should have a clear, focused system instruction definition.
   - Inject the safety disclaimer ("ResilienceDesk is a planning and preparation aid. It is NOT an emergency dispatch system...") into system prompts where appropriate.

2. **Function Tools**:
   - Define custom tools using `FunctionTool` wrappers.
   - Ensure tool parameters are fully documented with descriptions, enabling the model to call them accurately.
   - Perform strict validation on tool inputs.

3. **Topology / Orchestration**:
   - Define clear delegation patterns if one agent needs to call another or invoke specific workflows.
   - Maintain context and conversation history accurately across turns.
