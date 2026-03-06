---
name: install-mcp
description: Add chosen MCP servers to user global config via CLI. Part of Install workflow.
disable-model-invocation: true
---

# Install MCP

Edit only the user's global config. Do not edit Cursor/VSCode project config.

**Config file:**
- **macOS/Linux:** `$HOME/.claude.json`
- **Windows:** `%USERPROFILE%\.claude.json`

For each MCP they chose (from install-choices), add with the CLI below. Do not use Write or Edit tool; use only these commands.

**figma-console** (replace `figd_xxx` with the token from install-choices; use quoted `-e` so the token is valid):
```bash
claude mcp add -e "FIGMA_ACCESS_TOKEN=figd_xxx" -e "ENABLE_MCP_APPS=true" figma-console -- npx -y figma-console-mcp@latest
```

**atlassian-rovo:**
```bash
claude mcp add --transport sse atlassian-rovo https://mcp.atlassian.com/v1/sse
```

After the full Install workflow: user must fully restart the app (Cursor, Claude Code, etc.), then run `/mcp` for OAuth.
