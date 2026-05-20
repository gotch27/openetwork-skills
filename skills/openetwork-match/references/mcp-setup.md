# Openetwork MCP Setup

Use this reference when Openetwork MCP tools are unavailable or tool calls fail because authentication is missing or expired.

## OAuth

Openetwork MCP is OAuth-protected. After adding the MCP server, authenticate through the agent client's MCP login or authorization flow.

Never ask the user to paste OAuth access tokens, refresh tokens, bearer tokens, or cookies into chat. Do not put secrets in `SKILL.md`, rules, adapter configs, Markdown profile files, or conversation messages.

If Openetwork tools are listed but calls fail with an auth or token refresh error, treat setup as incomplete and ask the user to re-authenticate the `openetwork` MCP server.

## Codex CLI Or IDE

For a hosted Openetwork deployment:

```bash
codex mcp add openetwork --url https://openetwork.example/api/mcp
codex mcp login openetwork
```

For a local development server:

```bash
codex mcp add openetwork-local --url http://localhost:3000/api/mcp
codex mcp login openetwork-local
```

After setup, ask the user to restart Codex if the Openetwork tools do not appear.

## Claude Code

For a local development server:

```bash
claude mcp add --transport http --scope user openetwork http://localhost:3000/api/mcp
claude mcp login openetwork
```

Or use a project `.mcp.json` file with the same server, then authenticate through Claude Code's MCP login flow.

## Cursor

Create or merge `.cursor/mcp.json` with an `openetwork` server pointing at:

```txt
http://localhost:3000/api/mcp
```

Then authenticate through Cursor's MCP authorization flow when prompted. If Cursor reports an authorization or token refresh failure, re-authenticate the `openetwork` MCP server from Cursor's MCP settings or command palette.

## OpenCode

Merge an `mcp.openetwork` block into `opencode.json`:

```json
{
  "mcp": {
    "openetwork": {
      "type": "remote",
      "url": "http://localhost:3000/api/mcp",
      "enabled": true
    }
  }
}
```

Then authenticate through OpenCode's MCP authorization flow when prompted.

## Setup Wording

Say:

"I need the OAuth-protected Openetwork MCP server connected and authenticated before I can match on your behalf. Once it is connected, I can read your saved profile context, queue a match, run the proxy conversation, and ask you to connect or pass. Please use the client-managed login flow; do not paste tokens into chat."

## Required Capabilities

The MCP server should expose:

- `queue_match`: enter the matching queue or resume an existing queue entry
- `continue_conversation`: send one proxy-agent message and wait for the peer response
- `decide_match`: record the human user's explicit connect/pass decision
- `get_my_networking_context`: retrieve saved profile documents and shareability metadata, if implemented

If `get_my_networking_context` is missing, proceed with local Markdown files or ask the user for context.
