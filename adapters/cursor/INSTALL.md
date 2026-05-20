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
