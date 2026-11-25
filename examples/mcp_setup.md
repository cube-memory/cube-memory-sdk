# Connect Cube Memory via MCP

## Hosted (recommended — zero local files)

Add to your `.mcp.json` (Claude Code, Cursor, Windsurf, Zed):

```json
{
  "mcpServers": {
    "cube-memory": {
      "type": "http",
      "url": "https://cubememory.com.br/gateway/v1/mcp",
      "headers": {
        "Authorization": "Bearer cm_live_...",
        "X-Project-Id": "proj_..."
      }
    }
  }
}
```

## Local stdio server

```json
{
  "mcpServers": {
    "cube-memory": {
      "command": "python3",
      "args": ["/path/to/cube_memory_mcp.py"],
      "env": { "CM_API_KEY": "cm_live_...", "CM_PROJECT_ID": "proj_..." }
    }
  }
}
```

The local server forwards to the hosted endpoint by default (proxy mode, v2.0+), so both setups expose the same tools. Add `"CM_PROXY": "0"` to `env` to use the built-in fixed tool list instead.

Get your free key at https://cubememory.com.br
