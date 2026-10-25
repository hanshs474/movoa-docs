# MCP server

Three tools for any MCP client: `generate_video` (text or photo to video), `check_status`, `credits`.

## Local (stdio)

```bash
claude mcp add movoa -e MOVOA_API_KEY=sk-... -- npx -y movoa-mcp
```

Any client that takes a JSON config:

```json
{ "mcpServers": { "movoa": { "command": "npx", "args": ["-y", "movoa-mcp"], "env": { "MOVOA_API_KEY": "sk-..." } } } }
```

Gemini CLI: `gemini extensions install https://github.com/hanshs474/movoa-mcp`

## Hosted (Streamable HTTP)

```
https://movoa.ai/api/mcp
```

Send your key with each request as `Authorization: Bearer sk-...`. Listing the tools needs no key; running one does.

```bash
claude mcp add --transport http movoa https://movoa.ai/api/mcp --header "Authorization: Bearer sk-..."
```

Source: [github.com/hanshs474/movoa-mcp](https://github.com/hanshs474/movoa-mcp).
