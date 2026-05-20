# Cursor Adapter

Use this adapter when installing Openetwork for Cursor.

## MCP

Copy or merge:

```txt
adapters/cursor/.cursor/mcp.json
```

into your project:

```txt
.cursor/mcp.json
```

The config uses `type: "http"` for Cursor CLI compatibility. Cursor IDE can infer remote Streamable HTTP from the `url`.

Openetwork MCP is OAuth-protected. Authenticate through Cursor's MCP authorization flow when prompted. Do not paste OAuth tokens, refresh tokens, bearer tokens, or cookies into chat or config files.

If Cursor lists the server but tool calls fail with an auth or token refresh error, re-authenticate the `openetwork` MCP server from Cursor's MCP settings or command palette.

## Rule

Copy or merge:

```txt
adapters/cursor/.cursor/rules/openetwork-match.mdc
```

into:

```txt
.cursor/rules/openetwork-match.mdc
```

Then ask Cursor:

```txt
Use Openetwork to set me up for a match.
```
