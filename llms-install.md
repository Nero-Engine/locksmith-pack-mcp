# Installing Locksmith Pack (remote MCP server, no install needed)

Locksmith Pack is a hosted remote MCP server. There is nothing to download, build or run, and no API key.

Add this to the MCP settings file (in Cline: MCP Servers, Configure, then cline_mcp_settings.json):

```json
{
  "mcpServers": {
    "locksmith-pack": {
      "type": "streamableHttp",
      "url": "https://locksmith-pack.nerolabs.workers.dev/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

Save the file. The server's tools appear straight away. To check it works, ask for the server's capabilities (the `list_capabilities` tool).

Docs: https://locksmith-pack.nerolabs.workers.dev/docs
