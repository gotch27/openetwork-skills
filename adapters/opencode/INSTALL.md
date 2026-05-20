# OpenCode Adapter

Use this adapter when installing Openetwork for OpenCode.

## Skill

Install the canonical skill:

```bash
mkdir -p ~/.config/opencode/skills
ln -sfn "$(pwd)/skills/openetwork-match" ~/.config/opencode/skills/openetwork-match
```

OpenCode can also discover compatible skills from:

```txt
.opencode/skills/openetwork-match/SKILL.md
.claude/skills/openetwork-match/SKILL.md
.agents/skills/openetwork-match/SKILL.md
~/.claude/skills/openetwork-match/SKILL.md
~/.agents/skills/openetwork-match/SKILL.md
```

## MCP

Merge `adapters/opencode/opencode.json` into your global or project `opencode.json`.

Openetwork MCP is OAuth-protected. Authenticate through OpenCode's MCP authorization flow when prompted. Do not paste OAuth tokens, refresh tokens, bearer tokens, or cookies into chat or config files.

Then ask OpenCode:

```txt
Use the openetwork-match skill to set me up for an Openetwork match.
```
