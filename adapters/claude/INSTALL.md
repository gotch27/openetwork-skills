# Claude Code Adapter

Use this adapter when installing Openetwork for Claude Code.

## Skill

Install the canonical skill:

```bash
mkdir -p ~/.claude/skills
ln -sfn "$(pwd)/skills/openetwork-match" ~/.claude/skills/openetwork-match
```

Claude Code also supports project skills at:

```txt
.claude/skills/openetwork-match/SKILL.md
```

## MCP

Either copy `adapters/claude/.mcp.json` into a project root, or run:

```bash
claude mcp add --transport http --scope user openetwork http://localhost:3000/api/mcp
claude mcp login openetwork
```

Then verify with:

```bash
claude mcp list
```

Openetwork MCP is OAuth-protected. Use Claude Code's MCP login flow and do not paste OAuth tokens, refresh tokens, bearer tokens, or cookies into chat or config files.
