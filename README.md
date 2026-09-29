# BragsGlobal

## Elementor MCP server

`.mcp.json` connects Claude Code to the Elementor MCP endpoint on
https://bragspressurewashing.com (`/wp-json/elementor/mcp/`).

The WordPress application password is **not** stored in this repo. The
`Authorization` header reads it from the `BRAGS_WP_MCP_AUTH` environment
variable, which must hold `base64("<wp-username>:<application-password>")`:

```sh
export BRAGS_WP_MCP_AUTH="$(printf '%s' 'USERNAME:APP_PASSWORD' | base64)"
```

For Claude Code on the web, add `BRAGS_WP_MCP_AUTH` to the environment's
variables instead. Then restart Claude Code and approve the project MCP server.
