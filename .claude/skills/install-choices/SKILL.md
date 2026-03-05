---
name: install-choices
description: Ask custom or express install; custom continues with choices, express runs install-express then workflow continues. Part of Install workflow.
disable-model-invocation: true
---

# Install Choices

First ask: **Custom or express install?** Custom walks through each choice. Express: run [install-express](../install-express/SKILL.md), then workflow continues from step 3 (install-mcp) in [Coordinator](../../agents/coordinator.md).

- **Express:** Run install-express, then installer continues at install-mcp.
- **Custom:** Continue with the steps below.

**Custom install steps:**

1. **Show hidden files:** Ask if they want to show hidden files. If no, continue. If yes:
   - **macOS:** Run (if it fails due to permissions, continue): `defaults write com.apple.finder AppleShowAllFiles TRUE && killall Finder`
   - **Windows:** File Explorer → View → Show → Hidden items. (Or Folder Options → View → Show hidden files and folders.)

2. **What to install:** Ask if they want all of these installed, or to pick and choose.
   - **All** – figma-console, playwright, atlassian-rovo. Figma token needed next if figma-console.
   - **Pick and choose** – For each of figma-console, playwright, atlassian-rovo ask if they want it.
   Record which MCPs they chose; later steps use only those.

3. **Figma token (if they chose figma-console):** Give instructions, then ask them to paste the token. Do not ask whether they have one.
   - **How to get it:** Figma → profile → Settings → Security. Personal access tokens: create (e.g. "Figma Console MCP", all scopes, up to 90 days), copy.
   - **Ask:** Paste your Figma token (starts with `figd_`).
