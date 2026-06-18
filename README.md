# Ontario Protocol MCP Listing

Public listing metadata for Ontario Protocol's remote MCP and x402 verification surfaces.

Ontario Protocol helps agents and developers verify paid HTTP 402 / x402 endpoints before spending. It exposes free pre-payment checks, machine-readable discovery manifests, and paid x402 tools for trust scans, reputation lookup, and service listing.

## Live MCP Surface

- MCP manifest: <https://ontarioprotocol.com/.well-known/mcp.json>
- Remote MCP endpoint: <https://ontarioprotocol.com/mcp>
- x402 manifest: <https://ontarioprotocol.com/.well-known/x402.json>
- Agent buyer guide: <https://ontarioprotocol.com/.well-known/agent-buyer.json>
- Discovery catalog: <https://ontarioprotocol.com/discover>
- Free readiness checker: <https://ontarioprotocol.com/verify>

## Recommended Directory Description

Ontario Protocol exposes MCP and x402 tools for verifying paid agent endpoints before agents pay. Start with free readiness and can-pay tools, then use paid trust, reputation, and listing tools only after policy allows.

## Tool Classes

- `agent_can_pay`: free policy decision before paying an x402 endpoint.
- `x402_readiness_verify`: free readiness check for paid endpoint discovery and payment safety.
- `agent_verify_payment`: free idempotent payment verification before settlement.
- `agent_trust_scan`: paid x402 trust scan for an agent or service surface.
- `reputation_lookup`: paid reputation lookup for an agent.
- `list_agent`: paid listing route for agent directory submissions.
- `list_service`: paid listing route for third-party x402 service submissions.

## Verification

Directory crawlers should inspect the live MCP manifest rather than treating this repository as the server implementation:

```bash
curl -fsSL https://ontarioprotocol.com/.well-known/mcp.json
curl -fsSL https://ontarioprotocol.com/.well-known/x402.json
curl -fsSL https://ontarioprotocol.com/api/demand/stats
```

The remote MCP endpoint is POST-only. A `GET /mcp` request may return `405 Method Not Allowed`; that is expected and should not be treated as downtime.

## Boundary

This repository contains public listing metadata only. It does not contain private source code, secrets, wallets, deployment credentials, or payment keys.
