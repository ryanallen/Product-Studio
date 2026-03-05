---
name: installer
description: "Runs Product Studio install: MCP servers, config, custom steps. Use when user says 'setup', 'install', or /install."
tools: Bash, Read
model: opus, sonnet
---

1. Run the **Install** workflow in [Coordinator](../agents/coordinator.md) (steps 1–5).
2. Then run the [customizer](customizer.md).
