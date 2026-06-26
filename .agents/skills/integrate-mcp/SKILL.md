---
name: integrate-mcp
description: Guidelines and utility references for integrating Model Context Protocol (MCP) toolsets and servers into ResilienceDesk.
---

# Skill: integrate-mcp

Use this skill to configure, instantiate, and register Model Context Protocol (MCP) clients and toolsets within the ResilienceDesk Java application.

## Integration Guidelines

1. **Client Setup**:
   - Establish transport mechanisms (e.g., StdioTransport or SseTransport) to connect to MCP servers.
   - Configure environment variables and paths for running servers (such as local Node/Python tools or commands).

2. **Toolset Creation**:
   - Use `McpToolset` or equivalent ADK class wrappers to bind tool sets.
   - Expose tools dynamically to the `LlmAgent`.

3. **Security Constraints**:
   - Ensure the agent is only granted permission to call approved tools.
   - Guard against unauthorized tool execution.

4. **Error Handling**:
   - Gracefully handle MCP server crashes or connection drops.
   - Implement timeout limits for tool calls.
