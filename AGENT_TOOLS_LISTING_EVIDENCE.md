# agent-tools.cloud Listing Evidence

Ontario Protocol is publicly listed on agent-tools.cloud.

Listing URL:

```text
https://agent-tools.cloud/services/ontario-protocol-ontarioprotocol-com-x402
```

## Observed Listing State

Checked: 2026-06-18

| Field | Observed value |
| --- | --- |
| Name | Ontario Protocol |
| Endpoint | `https://ontarioprotocol.com/mcp` |
| Health | `healthy` |
| Category | `model-context-protocol-mcp` |
| Conformance | `fail` |

This is accepted-listing evidence for the Ontario directory distribution experiment. It is not payment evidence.

## Verified Live Endpoints

The listing points at the remote MCP endpoint:

```text
https://ontarioprotocol.com/mcp
```

Additional public probes currently return `200`:

```text
https://ontarioprotocol.com/.well-known/mcp.json
https://ontarioprotocol.com/.well-known/mcp
https://ontarioprotocol.com/.well-known/x402.json
https://ontarioprotocol.com/.well-known/x402
```

MCP JSON-RPC checks:

| Method | Result |
| --- | --- |
| `initialize` | `200` with server info |
| `tools/list` | `200` with Ontario tools |

## Follow-Up

The listing is live and healthy, but conformance is currently shown as `fail`.

Next useful work:

- identify the exact conformance rule that fails
- make the smallest live endpoint or manifest correction
- wait for recrawl or request owner-approved directory refresh if needed
- track whether conformance changes from `fail` to passing

## Evidence Boundary

This receipt proves:

- public listing exists
- endpoint is considered healthy by the directory
- Ontario is categorized as an MCP service
- conformance still needs correction

This receipt does not prove:

- payment
- signup
- buyer intent
- accepted paid listing
- legal, financial, or security endorsement
