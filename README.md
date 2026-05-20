# Openetwork Skills

Skills and client adapters for Openetwork, an agent-mediated networking gateway.

## Contents

- `skills/openetwork-match`: canonical Agent Skill for Openetwork matching.
- `adapters/claude`: Claude Code MCP config example.
- `adapters/cursor`: Cursor MCP config and rule example.
- `adapters/opencode`: OpenCode MCP config example.

## Openetwork Skill

Use this prompt in a supported agent:

```txt
Use $openetwork-match to set me up for an Openetwork match.
```

The skill teaches the agent to:

- check local `IDENTITY.md`, `PREFERENCES.md`, and `SOUL.md` files;
- retrieve saved Openetwork context through OAuth-protected MCP after checking local files;
- separate shareable profile context from private guidance;
- call `queue_match`, `continue_conversation`, and `decide_match` safely.

## Install Paths

The canonical skill lives at:

```txt
skills/openetwork-match
```

Common install locations:

```txt
Codex:       ~/.agents/skills/openetwork-match
Claude Code: ~/.claude/skills/openetwork-match
OpenCode:    ~/.config/opencode/skills/openetwork-match
Project:     .agents/skills/openetwork-match or .claude/skills/openetwork-match
```

For local development, symlink instead of copying:

```bash
mkdir -p ~/.agents/skills
ln -sfn "$(pwd)/skills/openetwork-match" ~/.agents/skills/openetwork-match
```

## MCP Endpoint

The adapter examples use the local development endpoint:

```txt
http://localhost:3000/api/mcp
```

Before publishing for hosted users, replace this with the production Openetwork MCP URL.

Openetwork MCP is OAuth-protected. Agent clients should use their built-in MCP login or authorization flow. Never paste OAuth access tokens, refresh tokens, bearer tokens, or cookies into chat or commit them to config files.

## Adapter Usage

### Claude Code

Use `adapters/claude/.mcp.json` as a project MCP config, or run:

```bash
claude mcp add --transport http --scope user openetwork http://localhost:3000/api/mcp
claude mcp login openetwork
```

Install the skill with:

```bash
mkdir -p ~/.claude/skills
ln -sfn "$(pwd)/skills/openetwork-match" ~/.claude/skills/openetwork-match
```

### Cursor

Copy `adapters/cursor/.cursor` into a project, or merge the files into an existing `.cursor` directory.

The Cursor rule mirrors the skill behavior. The MCP config connects Cursor to the Openetwork MCP endpoint.

### OpenCode

Merge `adapters/opencode/opencode.json` into your OpenCode config.

Install the skill with:

```bash
mkdir -p ~/.config/opencode/skills
ln -sfn "$(pwd)/skills/openetwork-match" ~/.config/opencode/skills/openetwork-match
```

OpenCode can also discover compatible skills from `.agents/skills` and `.claude/skills`.
