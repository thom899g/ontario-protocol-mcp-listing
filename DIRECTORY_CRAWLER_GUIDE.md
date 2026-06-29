# Directory Crawler Guide

This guide is for MCP directories, x402 marketplaces, and agent-tool catalogs that want to index Ontario Protocol without manual contact.

For a ranked owner-reviewed target list, see [Directory Target Shortlist](DIRECTORY_TARGETS.md).

For a concrete external crawler receipt, see [Crawler Compatibility Receipt](CRAWLER_COMPATIBILITY.md).

## Canonical Fetch Order

1. Fetch the MCP manifest:

   ```bash
   curl -fsSL https://ontarioprotocol.com/.well-known/mcp.json
   ```

2. If your crawler uses extensionless well-known paths, fetch the alias:

   ```bash
   curl -fsSL https://ontarioprotocol.com/.well-known/mcp
   ```

3. Fetch the MCP transport discovery document:

   ```bash
   curl -fsSL https://ontarioprotocol.com/mcp
   ```

4. Confirm the MCP JSON-RPC transport:

   ```bash
   curl -fsSL -X POST https://ontarioprotocol.com/mcp \
     -H 'content-type: application/json' \
     -d '{"jsonrpc":"2.0","id":1,"method":"tools/list","params":{}}'
   ```

5. Fetch x402 payment metadata:

   ```bash
   curl -fsSL https://ontarioprotocol.com/.well-known/x402.json
   ```

6. Probe the lowest-price paid endpoint without payment:

   ```bash
   curl -i https://ontarioprotocol.com/api/x402/reputation/demo-agent
   ```

7. Before signing payment, run the free can-pay preflight:

   ```bash
   curl -fsSL -X POST https://ontarioprotocol.com/api/agent/can-pay \
     -H 'content-type: application/json' \
     -d '{"endpoint":"https://ontarioprotocol.com/api/x402/reputation/demo-agent","max_usdc":"0.001","agent_policy":"standard"}'
   ```

## Expected Results

| Surface | Expected result |
| --- | --- |
| `/.well-known/mcp.json` | `200` JSON manifest with tools |
| `/.well-known/mcp` | `200` JSON manifest alias |
| `GET /mcp` | `200` JSON discovery document |
| `POST /mcp tools/list` | `200` JSON-RPC response with tools |
| `/.well-known/x402.json` | `200` x402 metadata |
| `GET /api/x402/reputation/demo-agent` | `402` x402 payment challenge with free alternatives and retry instructions |
| `POST /api/agent/can-pay` | policy decision JSON for a supplied endpoint |

## Free-First Owner Path

Endpoint owners who find Ontario through a directory should start with free checks:

- `GET https://ontarioprotocol.com/api/mcp-owner-next-step`
- `POST https://ontarioprotocol.com/api/mcp-mini-check`
- `POST https://ontarioprotocol.com/api/verify/x402-readiness`
- `POST https://ontarioprotocol.com/api/x402/list-service/validate`

The paid listing route is only for endpoint owners who want public catalog distribution after the free checks are useful:

```text
POST https://ontarioprotocol.com/api/x402/list-service
price: 0.50 USDC
```

## What Counts As A Useful Directory Signal

Useful market evidence:

- accepted listing
- listing rejection
- directory click or crawler fetch
- owner next-step call
- mini-check submission
- readiness verifier run from a real endpoint owner
- listing validation call
- paid listing attempt
- paid x402 call

Not enough by itself:

- local package edits
- README changes
- self-generated test calls
- vague "looks promising"
