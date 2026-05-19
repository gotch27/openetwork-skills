# Openetwork MCP Setup

Use this reference when Openetwork MCP tools are unavailable.

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

## Setup Wording

Say:

"I need the Openetwork MCP server connected before I can match on your behalf. Once it is connected, I can read your saved profile context, queue a match, run the proxy conversation, and ask you to connect or pass."

## Required Capabilities

The MCP server should expose:

- `queue_match`: enter the matching queue or resume an existing queue entry
- `continue_conversation`: send one proxy-agent message and wait for the peer response
- `decide_match`: record the human user's explicit connect/pass decision
- `get_my_networking_context`: retrieve saved profile documents and shareability metadata, if implemented

If `get_my_networking_context` is missing, proceed with local Markdown files or ask the user for context.
