---
name: mcp-server-building
description: Use when designing, implementing, reviewing, or testing an MCP server or connector for an external API, local tool, database, file system, SaaS service, or workflow that should be exposed to AI agents as tools/resources/prompts.
---

# MCP Server Building

Build MCP servers around agent usability, not just API coverage. Good tools are discoverable, typed, safe, and return focused results.

## Planning

1. Identify the real user workflows the MCP server should support.
2. Review the target service API, auth model, rate limits, pagination, and error formats.
3. Decide whether tools should be low-level API wrappers, higher-level workflow tools, or a mix.
4. Define read-only and write tools separately.
5. Plan pagination and filtering before implementation.

## Tool Design

Each tool should have:

- action-oriented name
- concise description
- typed input schema with constraints
- safe defaults
- actionable error messages
- structured output where useful
- clear read/write/destructive semantics

## Implementation Workflow

1. Set up the smallest working server.
2. Implement auth and shared API client.
3. Add one read-only tool first.
4. Test with realistic prompts or inspector tools.
5. Add write tools only after read paths and error handling are solid.
6. Include logging that helps debug without leaking secrets.

## Evaluation

Create realistic questions an agent should answer using the server. Prefer tasks that require multiple calls, filtering, and interpretation. Avoid evals whose answers change daily unless the goal is monitoring.

## Safety

- Mark destructive operations clearly.
- Require explicit identifiers for write/delete actions.
- Never log tokens, passwords, or full secrets.
- Return enough context for the agent to verify before writing.
