# Jewelry by Sweet Pea — Products MCP Server

A free, public, **read-only** [Model Context Protocol](https://modelcontextprotocol.io) server for the [Jewelry by Sweet Pea](https://www.jewelrybysweetpea.com) fine-jewelry catalog. No API key, no signup.

**Endpoint:** `https://chat.jewelrybysweetpea.com/mcp` (Streamable HTTP, stateless)

**Registry:** [`io.github.danielle790/jewelry-by-sweet-pea`](https://registry.modelcontextprotocol.io/v0.1/servers?search=io.github.danielle790/jewelry-by-sweet-pea) on the official MCP Registry

## Tools

| Tool | What it does |
|------|--------------|
| `search_products` | Live search of 100,000+ fine-jewelry products (gold, sterling silver, NCAA/collegiate LogoArt). Returns name, SKU, live price, availability, and product URL. |
| `get_product` | Fetch one product's live details (price, availability, sizes/variants, URL) by SKU. |
| `get_store_policies` | Shipping (free US), returns (free 30-day), warranty, resizing, payment, and contact details. |

## Quick start

### Claude Code

```bash
claude mcp add --transport http sweetpea-products https://chat.jewelrybysweetpea.com/mcp
```

### Claude Desktop / other MCP clients

```json
{
  "mcpServers": {
    "sweetpea-products": {
      "type": "streamable-http",
      "url": "https://chat.jewelrybysweetpea.com/mcp"
    }
  }
}
```

### Try it with curl

```bash
curl -X POST https://chat.jewelrybysweetpea.com/mcp \
  -H "Content-Type: application/json" \
  -H "Accept: application/json, text/event-stream" \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list","params":{}}'
```

## Notes

- Read-only: the server exposes catalog and policy data only; it cannot place orders or modify anything.
- No authentication required. Please be reasonable with request volume.
- Prices and availability are live from the store.

## About

Jewelry by Sweet Pea is a family-run online fine-jewelry store. Questions or issues with the server: [danielle@jewelrybysweetpea.com](mailto:danielle@jewelrybysweetpea.com) · [jewelrybysweetpea.com](https://www.jewelrybysweetpea.com)

## Discovery

This server is discoverable by machines through:

- **Official MCP Registry:** [io.github.danielle790/jewelry-by-sweet-pea](https://registry.modelcontextprotocol.io/v0/servers?search=jewelry-by-sweet-pea)
- **Well-known URIs** on the store domain:
  - [/.well-known/mcp/server-card.json](https://jewelrybysweetpea.com/.well-known/mcp/server-card.json)
  - [/.well-known/mcp.json](https://jewelrybysweetpea.com/.well-known/mcp.json)
  - [/.well-known/webmcp.json](https://jewelrybysweetpea.com/.well-known/webmcp.json)
- **[llms.txt](https://jewelrybysweetpea.com/llms.txt)** for AI crawlers
