# Connect SHVL from Cline or Copilot

## Cline CLI

With Cline CLI installed, run:

```sh
cline mcp install shvl --transport http https://shvl.app/mcp/v2/oauth
```

Complete the installation wizard and use browser OAuth when the client requests sign-in. Use your own SHVL account with access to the requested records. Review requested permissions before consent. Use the read tools for this review workflow; do not approve changes or sends as part of setup.

Cline CLI 3.0.74 completed browser OAuth and a protected read with an existing fictional QA account on 17 November 2026.

## Copilot native configuration

Merge the entry from [copilot-mcp.json](copilot-mcp.json) into the existing `mcpServers` object in your Copilot user `mcp-config.json`, or into a workspace-root `.mcp.json`. Preserve other server entries. In VS Code, you can instead open Chat: Open Customizations, select MCP Servers and Add Server, then choose Global > Copilot Global.

The supplied native configuration selects only these read tools: `list_shvl_workspaces`, `get_shvl_workspace_status`, `get_credit_control_brief`, `get_receivables_health`, `search_credit_control_cases`, `get_credit_control_case`, `search_xero_invoices`, `get_xero_invoice`, `search_xero_contacts`, `get_xero_contact`, `get_xero_financial_report`. Tool selection does not change the permissions requested during OAuth. Review consent separately.

## VS Code installation link

[Review SHVL in VS Code](https://vscode.dev/redirect?url=vscode%3Amcp%2Finstall%3F%257B%2522name%2522%253A%2522shvl%2522%252C%2522type%2522%253A%2522http%2522%252C%2522url%2522%253A%2522https%253A%252F%252Fshvl.app%252Fmcp%252Fv2%2522%257D)

This opens an installation preview for the HTTP endpoint. The editor-managed link does not include the native Copilot tool selection above. For the read-tool selection, use the native configuration. Complete browser sign-in and verify a tool call in the intended session.

VS Code/Copilot configuration was checked against Microsoft's documented format. The editor and authenticated tool calls have not yet been exercised.

## Account review

Follow [GEMINI.md](../GEMINI.md) for the product's read workflow, record identifiers and evidence rules. SHVL users must select an authorised workspace before reading its records. An installation does not grant a service plan, workspace membership or accounting-provider permissions.

Sources: [Cline MCP setup](https://github.com/cline/cline/blob/main/docs/cli/cli-reference.mdx), [Copilot configuration](https://code.visualstudio.com/docs/agents/reference/mcp-configuration), [VS Code installation links](https://code.visualstudio.com/api/extension-guides/ai/mcp).
