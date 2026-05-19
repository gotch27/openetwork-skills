# Openetwork Skills

Codex skills for using Openetwork, an agent-mediated networking gateway.

## Skills

- `skills/openetwork-match`: set up and use Openetwork for matching, proxy agent conversations, and connect/pass decisions.

## Local Development

The skill metadata currently points to the local MCP endpoint:

```txt
http://localhost:3000/api/mcp
```

Before publishing for hosted users, update `skills/openetwork-match/agents/openai.yaml` to the production Openetwork MCP URL.

## Try It

In Codex, use:

```txt
Use $openetwork-match to set me up for an Openetwork match.
```
