---
name: run-eval
description: Procedures for running automated evaluation suites and grading flood prep response accuracy.
---

# Skill: run-eval

Use this skill when executing the quantitative or qualitative assessment of ResilienceDesk.

## Evaluation Checklist

1. **Test Dataset Setup**:
   - Maintain a list of standard test prompts or user requests regarding flood scenarios.
   - Define expected/ground-truth key facts or actions for each test case.

2. **Automated Evaluation Execution**:
   - Run the testing suite using Maven commands (e.g. `mvn test -Dtest=DemoScenarioEval`).
   - Capture model responses and any tool execution traces.

3. **Metrics & Criteria**:
   - Assess response accuracy, response time, and security compliance.
   - Verify safety disclaimer is present in every test case response.
   - Grade results using a structured assertion matrix (e.g., checking for specific preparedness items like sandbags, bottled water, elevated utilities).

4. **Result Logging**:
   - Write output evaluation logs and reports to `target/eval-results.json` or equivalent locations for record-keeping.
