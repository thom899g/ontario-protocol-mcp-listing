# Ontario Protocol MCP/x402 Listing Package

Ontario Protocol is an x402 payment preflight and trust surface for autonomous agents. It exposes MCP-compatible discovery, free readiness checks, and paid trust tools so agents can verify service metadata before paying.

Homepage: <https://ontarioprotocol.com>

MCP manifest: <https://ontarioprotocol.com/.well-known/mcp.json>

Remote MCP endpoint: <https://ontarioprotocol.com/mcp>

x402 manifest: <https://ontarioprotocol.com/.well-known/x402.json>

Agent buyer guide: <https://ontarioprotocol.com/.well-known/agent-buyer.json>

Discovery: <https://ontarioprotocol.com/discover>

Free readiness checker: <https://ontarioprotocol.com/verify>

Free owner next step: <https://ontarioprotocol.com/api/mcp-owner-next-step>

## Recommended Directory Description

Ontario Protocol exposes MCP and x402 tools for verifying paid agent endpoints before agents pay. Start with free readiness and can-pay tools, then use paid trust, reputation, and listing tools only after policy allows.

## Tools

| Tool | Method | Endpoint | Price |
| --- | --- | --- | --- |
| `agent_can_pay` | POST | `https://ontarioprotocol.com/api/agent/can-pay` | free |
| `x402_readiness_verify` | POST | `https://ontarioprotocol.com/api/verify/x402-readiness` | free |
| `agent_verify_payment` | POST | `https://ontarioprotocol.com/api/agent/verify-payment` | free |
| `discover` | GET | `https://ontarioprotocol.com/discover` | free |
| `agent-trust-scan` | POST | `https://ontarioprotocol.com/api/x402/agent-trust-scan` | 0.01 USDC |
| `reputation-lookup` | GET | `https://ontarioprotocol.com/api/x402/reputation/{agent_id}` | 0.001 USDC |
| `list-agent` | POST | `https://ontarioprotocol.com/api/x402/list-agent` | 0.10 USDC |
| `list-service` | POST | `https://ontarioprotocol.com/api/x402/list-service` | 0.50 USDC |

## Listing Purpose

This package exists to support agent/tool directory review. It is not a separate production deployment, not a payment collector, and not a legal or financial guarantee. Ontario provides observable readiness signals; agents should still enforce their own budget, wallet, timeout, and policy controls before payment.

## Free-First Owner Path

If you run an MCP or x402 endpoint and found Ontario through a directory, start here before any paid action:

- owner handoff route: `GET https://ontarioprotocol.com/api/mcp-owner-next-step`
- human owner page: <https://ontarioprotocol.com/docs/mcp-owner-paid-call>
- free mini-check request: `POST https://ontarioprotocol.com/api/mcp-mini-check`
- free listing validation: `POST https://ontarioprotocol.com/api/x402/list-service/validate`

The paid `list-service` route is only for owners who want a public Ontario catalog listing after the free checks are useful.

## Verification

Directory crawlers should inspect the live MCP manifest rather than treating this repository as the server implementation:

```bash
curl -fsSL https://ontarioprotocol.com/.well-known/mcp.json
curl -fsSL https://ontarioprotocol.com/.well-known/x402.json
curl -fsSL https://ontarioprotocol.com/api/demand/stats
```

The remote MCP endpoint accepts `POST /mcp` for JSON-RPC MCP calls. `GET /mcp` returns a `200` JSON discovery document with the manifest URL, POST usage, free owner next-step, and paid listing boundary.

For a full ingestion sequence, see [Directory Crawler Guide](DIRECTORY_CRAWLER_GUIDE.md).

For ranked owner-reviewed submission targets and evidence criteria, see [Directory Target Shortlist](DIRECTORY_TARGETS.md).

For observed external MCP crawler compatibility, see [Crawler Compatibility Receipt](CRAWLER_COMPATIBILITY.md).

## Evidence Contract

A real market signal for this distribution test must be one of: accepted listing, listing rejection, directory click, crawler/registry fetch, inbound listing attempt, signup, paid x402 call, or payment. Drafts and local reports do not count.

## Boundary

This repository contains public listing metadata only. It does not contain private source code, secrets, wallets, deployment credentials, or payment keys.
