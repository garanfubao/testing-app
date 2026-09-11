# testing-app

Repository set up with the [Appllama Skills](https://github.com/Appllama/appllama-skills)
for Claude Code — a skills collection for mobile app design research and native-quality
Expo / React Native screen building.

## Installed skills

Located in `.claude/skills/` (project-scoped, available automatically in this repo):

- **`appllama-app-design-skill`** — Build native-feeling, benchmark-quality mobile app
  screens (Expo / React Native): onboarding, paywalls, flows, motion, navigation
  semantics, with a simulator-verified iteration loop.
- **`appllama-usage`** — Use the Appllama MCP to research real top-grossing apps, walk
  their screens, and study onboarding/paywall flows, then build from what wins.

## Appllama MCP server

Configured in `.mcp.json`. It connects to the Appllama MCP over HTTP:

```json
{
  "mcpServers": {
    "Appllama": {
      "type": "http",
      "url": "https://mcp.appllama.io/mcp"
    }
  }
}
```

Claude Code picks up project MCP servers from `.mcp.json` automatically (you may be
prompted to approve the server on first use). The `appllama-usage` skill activates once
the Appllama MCP is connected.

## Reinstalling / updating

```bash
# Recommended (npm helper)
npx skills@latest add appllama/appllama-skills -a claude-code -y

# Manual
git clone https://github.com/Appllama/appllama-skills
cp -r appllama-skills/skills/* .claude/skills/
```

Skills can also be installed user-wide in `~/.claude/skills/` (add the `-g` flag to the
npm command).
