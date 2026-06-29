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
| 1 | agent-tools.cloud | `https://agent-tools.cloud/services/ontario-protocol-ontarioprotocol-com-x402` | Proven. Ontario is already listed as healthy, but conformance is still shown as `fail`. | 10/10 | Fast | Low | No new submission needed; only monitor or request refresh if owner approves. | Conformance changes, listing click/crawler fetch, owner next-step call, x402 probe, paid call. |
| 2 | MCP.Directory | `https://mcp.directory/` | High. Current public directory says it has thousands of MCP servers and agent skills plus a Submit Server path. Ontario has a remote MCP endpoint and manifests. | 9/10 | Medium | Medium | Any submit-server form, login, account action, or maintainer contact. | Accepted listing, listing rejection, crawler fetch, repo traffic, issue #1 comment. |
| 3 | PulseMCP | `https://www.pulsemcp.com/servers` | High. Public MCP directory with submit/discovery surface. Ontario can be framed as remote MCP plus x402 payment-readiness. | 8/10 | Medium | Medium | Any submit form, account action, or maintainer contact. | Accepted listing, crawler fetch, listing rejection, issue #1 comment. |
| 4 | awesome-x402 | `https://github.com/xpaysh/awesome-x402` | High. It is an x402 service directory with live uptime/discovery positioning. Ontario has x402 metadata and USDC-on-Base endpoints. | 8/10 | Medium | Medium | Any PR, issue, maintainer contact, or listing edit outside owned repos. | PR accepted/rejected, issue reply, directory fetch, x402 probe, paid call. |
| 5 | mcpservers.org / community MCP catalogs | `https://mcpservers.org/` | Medium-high. Broad MCP discovery audience, useful for crawler and repo traffic. | 7/10 | Medium | Low-medium | Any submit form, GitHub PR, maintainer contact, or account action. | Listing page, rejection, crawler fetch, repo star/fork/issue. |
| 6 | awesome-mcp-servers | `https://github.com/punkpeye/awesome-mcp-servers` | Medium-high. Very large public MCP list; Ontario must be framed carefully as remote MCP plus x402 readiness. | 7/10 | Medium | Medium | Any PR, issue, or maintainer contact. | PR accepted/rejected, issue reply, crawler fetch, repo traffic. |
| 7 | x402 Bazaar / Coinbase x402 discovery | `https://docs.cdp.coinbase.com/x402/bazaar` | High but account/payment-adjacent. Ontario has x402 metadata, free readiness checks, and paid listing endpoints. | 8/10 | Medium | Medium-high | Any Bazaar listing, wallet/payment setup, Coinbase account action, or paid interaction. | Bazaar discovery hit, listing validation call, paid listing attempt, x402 paid call. |
| 8 | AI Dev Tools Directory | `https://aidevtools.vercel.app/` | Medium. It accepts AI tools, MCP servers, and developer resources. | 6/10 | Fast | Low-medium | Any form submission or account action. | Accepted listing, directory click, crawler fetch, rejection. |

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
- Public fit-check issue: `https://github.com/thom899g/ontario-protocol-mcp-listing/issues/1`

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
