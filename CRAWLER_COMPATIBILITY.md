# Crawler Compatibility Receipt

Ontario Protocol has been observed responding successfully to external MCP directory crawler traffic.

This receipt is for MCP directories, x402 discovery systems, and agent-tool catalogs that want a quick compatibility check before indexing Ontario.

## Observed External Crawlers

Sources observed in Google Cloud Run logs:

```text
PRSM-MCP-Graph/1.0 (+https://prsm.network)
agent-tools.cloud-crawler/0.1 (+https://agent-tools.cloud)
```

Observed PRSM events:

| Timestamp | Method | Status | Endpoint |
| --- | --- | ---: | --- |
| 2026-06-18T14:16:05.770945Z | POST | 200 | `/mcp` |
| 2026-06-18T14:16:05.908067Z | POST | 202 | `/mcp` |
| 2026-06-18T14:16:06.022920Z | GET | 200 | `/mcp` |
| 2026-06-18T14:16:06.033825Z | POST | 200 | `/mcp` |

Observed agent-tools.cloud events:

| Timestamp | Method | Status | Endpoint |
| --- | --- | ---: | --- |
| 2026-06-18T14:26:18.790373Z | POST | 200 | `/mcp` |
| 2026-06-18T14:26:18.940381Z | POST | 202 | `/mcp` |
| 2026-06-18T14:26:18.990981Z | POST | 200 | `/mcp` |

## Directory Probe Checklist

Use these public, unauthenticated probes first:

```bash
curl -fsSL https://ontarioprotocol.com/.well-known/mcp.json
curl -fsSL https://ontarioprotocol.com/.well-known/mcp
curl -fsSL https://ontarioprotocol.com/mcp
curl -fsSL https://ontarioprotocol.com/.well-known/x402.json
```

Then confirm the MCP JSON-RPC transport:

```bash
curl -fsSL -X POST https://ontarioprotocol.com/mcp \
  -H 'content-type: application/json' \
  -d '{"jsonrpc":"2.0","id":1,"method":"tools/list","params":{}}'
```

## Expected Compatibility Results

| Probe | Expected result |
| --- | --- |
| `GET /.well-known/mcp.json` | `200` JSON manifest |
| `GET /.well-known/mcp` | `200` JSON manifest alias |
| `GET /mcp` | `200` transport discovery JSON |
| `POST /mcp` with `tools/list` | `200` JSON-RPC response |
| `GET /.well-known/x402.json` | `200` x402 metadata |

## Free Owner Path

Endpoint owners who discover Ontario through a directory should use the free path before any paid action:

- `GET https://ontarioprotocol.com/api/mcp-owner-next-step`
- `POST https://ontarioprotocol.com/api/mcp-mini-check`
- `POST https://ontarioprotocol.com/api/x402/list-service/validate`

## Evidence Boundary

This receipt proves only that external crawlers reached the public MCP transport and received successful responses.

It does not prove:

- accepted listing
- buyer interest
- signup
- payment
- paid listing
- legal or financial endorsement

Useful next evidence would be a directory listing, explicit rejection, release asset download, owner handoff call, listing validation call, or paid x402 attempt.

Known listing evidence:

- agent-tools.cloud listing: `https://agent-tools.cloud/services/ontario-protocol-ontarioprotocol-com-x402`
