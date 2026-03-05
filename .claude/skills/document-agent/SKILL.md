---
name: document-agent
description: Use Claude Code subagents when documenting, or when writing/updating agent files (.claude/agents/). Use when user says document with a subagent, use a subagent for documentation, write an agent, update agent, or /document-agent.
---

# Document Agent

**Agents are subagent definitions.** Files in `.claude/agents/` (project) or `~/.claude/agents/` (user) use YAML frontmatter plus a markdown body. The body becomes the subagent's system prompt; frontmatter defines name, description (required), tools, model, and optionally skills, disallowedTools, permissionMode, hooks, memory. Official spec: [Create custom subagents](https://code.claude.com/docs/en/sub-agents.md).

## When writing or updating an agent file

Write a full system prompt in the body: role, scope, and "When invoked:" steps that reference skills. Match the pattern of existing agents (e.g. documenter, verifier). Only `name` and `description` are required in frontmatter; set `tools` and `model` as needed.

## Using subagents when documenting

| Subagent | Use when |
|----------|----------|
| **Explore** | Codebase or file discovery. Read-only, fast (Haiku). Specify thoroughness: quick, medium, or very thorough. Keeps exploration out of main context. |
| **general-purpose** | Multi-step documentation (gather context then write). All tools, inherits model. Use when the task needs both discovery and writing (e.g. read source then produce README). |
| **Plan** | Read-only research during plan mode before presenting a plan. |

**Chaining:** Subagents cannot spawn other subagents. Chain from the main conversation: e.g. Explore for discovery, then run the document skill in main context; or general-purpose for one full pass.

**When to delegate:** Use subagents when the work is self-contained and can return a summary. Use the main conversation when the task needs frequent back-and-forth or shared context across phases.

## Reference

[Create custom subagents](https://code.claude.com/docs/en/sub-agents.md)
