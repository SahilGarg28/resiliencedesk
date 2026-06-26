---
name: demo-scenario
description: Steps to run and verify the interactive ResilienceDesk flood preparation demo scenario.
---

# Skill: demo-scenario

Use this skill to execute and verify the end-to-end interactive demo scenario of ResilienceDesk.

## Scenario Runner Guidelines

1. **Prerequisites**:
   - Verify `.env` is loaded with `GOOGLE_API_KEY`.
   - Ensure the application compiles successfully (`mvn clean compile`).

2. **Execution Steps**:
   - Run the main demo application entry point using Maven Executive Plugin (e.g. `mvn exec:java -Dexec.mainClass="com.resiliencedesk.DemoScenario"`).
   - Feed mock queries representing different user profiles (e.g. resident in a low-lying zone, business owner requesting asset protection advice).

3. **Validation Points**:
   - Observe if the agent correctly utilizes tools (like retrieving weather/flood maps, calculating sandbox/barrier requirements).
   - Verify that safety disclaimers are prominently displayed.
   - Confirm that the final output advises local evacuation/safety procedures if conditions warrant.
