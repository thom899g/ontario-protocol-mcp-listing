# Directory Target Shortlist

This shortlist is for owner-reviewed submission or crawler monitoring. It is not evidence by itself and it does not authorize account creation, posting, paid promotion, or maintainer contact.

## Evidence Rule

Ontario Protocol should count a target as market evidence only when one of these happens:

- accepted listing
- explicit rejection
- directory crawler fetch visible in logs
- directory click
- repo star, fork, or issue from an external user
- owner next-step call
- mini-check submission
- readiness verification for a real endpoint
- listing validation call
- paid x402 call or paid listing attempt

## Ranked Targets

| Rank | Target | Public URL | Fit | Expected value | Speed to signal | Submission risk | Approval boundary | Evidence to watch |
| ---: | --- | --- | --- | ---: | --- | --- | --- | --- |
| 1 | Official MCP Registry | `https://registry.modelcontextprotocol.io/` | High. It is the canonical MCP discovery surface and Ontario exposes a remote MCP endpoint plus manifests. | 9/10 | Medium | Medium | Any namespace/package registration, account linking, or submission PR. | Accepted listing, registry fetch, listing rejection, crawler hit on `/.well-known/mcp.json` or `/mcp`. |
| 2 | Smithery | `https://smithery.ai/` | High. Smithery is a visible MCP server directory and deployment/listing surface. | 8/10 | Medium | Medium | Any account login, repo connection, deploy, or add-server submission. | Accepted listing, rejected listing, crawler fetch, issue/star from Smithery user. |
| 3 | x402 Bazaar / Coinbase x402 discovery | `https://docs.cdp.coinbase.com/x402/bazaar` | High. Ontario has x402 metadata, free readiness checks, and paid listing endpoints. | 8/10 | Medium | Medium | Any Bazaar listing, wallet/payment setup, Coinbase account action, or paid interaction. | Bazaar discovery hit, listing validation call, paid listing attempt, x402 paid call. |
| 4 | AI Dev Tools Directory | `https://aidevtools.vercel.app/` | Medium-high. It accepts AI tools, MCP servers, and developer resources. | 6/10 | Fast | Low-medium | Any form submission or account action. | Accepted listing, directory click, crawler fetch, rejection. |
| 5 | mcpservers.org / community MCP catalogs | `https://mcpservers.org/` | Medium. Broad MCP discovery audience, useful for crawler and repo traffic. | 6/10 | Medium | Low-medium | Any submit form, GitHub PR, maintainer contact, or account action. | Listing page, rejection, crawler fetch, repo star/fork/issue. |

## Submission Copy

Short description:

```text
Remote MCP and x402 tools for verifying paid agent endpoints before agents pay.
```

Long description:

```text
Ontario Protocol helps autonomous agents and developers avoid unsafe paid API calls. It exposes free MCP/x402 readiness and can-pay checks, a machine-readable buyer guide, and paid x402 tools for trust scans, reputation lookup, and marketplace listing once policy allows payment.
```

Primary links:

- Homepage: `https://ontarioprotocol.com`
- MCP manifest: `https://ontarioprotocol.com/.well-known/mcp.json`
- MCP manifest alias: `https://ontarioprotocol.com/.well-known/mcp`
- Remote MCP endpoint: `https://ontarioprotocol.com/mcp`
- x402 manifest: `https://ontarioprotocol.com/.well-known/x402.json`
- Agent buyer guide: `https://ontarioprotocol.com/.well-known/agent-buyer.json`
- Free owner next step: `https://ontarioprotocol.com/api/mcp-owner-next-step`
- Free listing validation: `https://ontarioprotocol.com/api/x402/list-service/validate`

## No-Approval Actions

Allowed without another approval:

- update this owned repository
- improve public listing metadata
- verify live public Ontario endpoints
- watch release downloads, repo events, and Cloud Run logs
- record evidence honestly as no signal, signal, blocked, kill, revise, or scale

## Approval-Required Actions

Require explicit owner approval before:

- submitting to any directory or registry
- opening pull requests in third-party repositories
- creating accounts
- connecting wallets
- paying for promotion or listing
- messaging maintainers or community members
- making any legal, payment, or platform commitment
