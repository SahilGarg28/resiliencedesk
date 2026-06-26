---
name: scaffold-adk-java
description: Setup and scaffold a new Java 17 Maven project structure for ResilienceDesk including dependency configurations for Google AI ADK Java.
---

# Skill: scaffold-adk-java

Use this skill to create and set up the foundation of the ResilienceDesk Java project.

## Scaffolding Standards

1. **Build Tool & Directory Layout**:
   - Use Maven (`pom.xml` in root).
   - Core directory structure:
     - `src/main/java/com/resiliencedesk/` (for application source code)
     - `src/test/java/com/resiliencedesk/` (for unit/integration tests)
     - `src/main/resources/` (for property files, configs, prompt templates)

2. **Java Version**:
   - Set compiler compliance to **Java 17** in `pom.xml`.

3. **Required Core Dependencies**:
   - Include relevant Google AI GenAI SDK or ADK artifacts.
   - Include MCP SDK artifacts if applicable.
   - Include JUnit 5 for testing and evaluations.
   - Include `dotenv-java` or similar tool to load `.env` safely.

## Workflow

1. Initialize `pom.xml` with coordinates `com.resiliencedesk:resiliencedesk:1.0-SNAPSHOT`.
2. Configure plugins for compiling Java 17 and packaging.
3. Build the initial directory structure.
4. Add a dummy test and compile with `mvn clean test` to verify the scaffold.
