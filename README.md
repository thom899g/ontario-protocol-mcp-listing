# Ontario Protocol MCP/x402 Listing Package

Ontario Protocol is an x402 payment preflight and trust surface for autonomous agents. It exposes MCP-compatible discovery and paid trust tools so agents can verify service metadata before paying.

Homepage: https://ontarioprotocol.com

Manifest: https://ontarioprotocol.com/.well-known/mcp.json

x402 manifest: https://ontarioprotocol.com/.well-known/x402.json

Discovery: https://ontarioprotocol.com/discover

## Tools

| Tool | Method | Endpoint | Price |
| --- | --- | --- | --- |
| discover | GET | `https://ontarioprotocol.com/discover` | free |
| agent-trust-scan | POST | `https://ontarioprotocol.com/api/x402/agent-trust-scan` | 0.01 |
| reputation-lookup | GET | `https://ontarioprotocol.com/api/x402/reputation/{agent_id}` | 0.001 |
| list-agent | POST | `https://ontarioprotocol.com/api/x402/list-agent` | 0.10 |
| list-service | POST | `https://ontarioprotocol.com/api/x402/list-service` | 0.50 |

## Listing Purpose

This package exists to support agent/tool directory review. It is not a separate production deployment, not a payment collector, and not a legal or financial guarantee. Ontario provides observable readiness signals; agents should still enforce their own budget, wallet, timeout, and policy controls before payment.

## Evidence Contract

A real market signal for this distribution test must be one of: accepted listing, listing rejection, directory click, crawler/registry fetch, inbound listing attempt, signup, paid x402 call, or payment. Drafts and local reports do not count.
