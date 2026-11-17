# SHVL workspace review

Read the selected business's overdue invoices, synced Xero invoices and contacts, and live Xero financial reports. Start by selecting an authorised SHVL workspace, then inspect its stored accounting source and last sync.

Published by Studea Limited. [SHVL](https://shvl.app) · Support: hello@shvl.app.

## Gemini CLI

Review overdue invoices, receivables health and recorded SHVL cases.

```sh
gemini extensions install https://github.com/jlucwright/shvl-agent-plugin --ref v1.0.0
```

Start Gemini CLI and use `/mcp auth shvl` to sign in through the browser when needed. A SHVL account with access to the requested records and the applicable service plan is required. Installation does not grant account access.

This Gemini extension uses `https://shvl.app/mcp/v2` with an explicit read-only tool allowlist. It exposes `list_shvl_workspaces`, `get_shvl_workspace_status`, `get_credit_control_brief`, `get_receivables_health`, `search_credit_control_cases`, `get_credit_control_case`. The client and model service process the records you request under their data settings.

`gemini-extension.json` and `GEMINI.md` configure Gemini CLI. The existing Agent Plugin files and skills below retain their separate client-specific scope.

## Install and connect

Import this Git repository as an Agent Plugin in a compatible client. `mcp.json` points to SHVL's existing public read-only endpoint at `https://shvl.app/mcp/v2`. Sign in through OAuth and select a returned workspace. An account alone does not create a workspace or connect accounting software; workspace access and an applicable active trial or subscription are required.

Cursor supports the root `plugin.json` Agent Plugins format. Use [Cursor’s plugin installation and management guidance](https://cursor.com/docs/plugins) for your account; an official Marketplace listing requires Cursor review. The community Cursor Directory listing is separate.

### Hermes OAuth setup

In a Hermes installation, include its declared MCP extra with `hermes pm install --extra mcp`, then install and enable this plugin. The portable `mcp.json` supplies the public tool catalogue. For Hermes's native OAuth login flow, add the SHVL server explicitly:

```sh
hermes mcp add shvl --url https://shvl.app/mcp/v2/oauth --auth oauth
hermes mcp test shvl
```

Complete the account consent in the browser when prompted. The explicit native `shvl` server configuration takes precedence over the portable entry in Hermes and uses standard read-only access. Select a workspace returned for the signed-in account before asking for its data. Do not paste access tokens or create manual authorisation headers. This setup does not request write scopes.

The `shvl-workspace-review` skill covers workspace selection, overdue briefs, receivables health, case search and detail, synced Xero invoice/contact search and detail, and live Profit and Loss, Balance Sheet and Trial Balance reports for explicit dates. Standard connections are read-only. Xero reads require owner access to the selected business and its connected Xero organisation; live reports also require report permission. Invoice/contact results use the latest completed sync. Creating reviewed Xero drafts requires a separately approved write connection and approval of the exact action. Standard access cannot create, authorise, pay or send records. Live QA on 3 November 2026 confirmed the ordinary 12-tool read-only catalogue. End-to-end Cursor OAuth is not yet verified, so this package is not claimed to be a tested Cursor connection.

## Scope

This is the workspace-first scope used by the approved SHVL public connector. It is not the separate expanded developer API. The historical CSV helper and CSV-led package were removed from this package in version 1.0.1. The server retains a legacy optional CSV tool for compatibility; this skill does not use or promote it.

Material used with an AI client remains subject to that client and model service's data settings. This package contains no install scripts, hooks, dependencies or credentials. Only authorised workspace data should be shared with the client.

Root `plugin.json` is the Agent Plugins manifest. `.plugin/plugin.json` mirrors public metadata for Cursor Directory's current indexer. Logo URLs refer to the existing company website icon. MIT applies to these package files; product names and service access remain subject to their respective terms.
