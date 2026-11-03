# SHVL workspace review

Review the selected business's overdue invoices, receivables totals and recorded case information. Start by selecting an authorised SHVL workspace, then inspect its stored accounting source and last sync.

Published by Studea Limited. [SHVL](https://shvl.app) · Support: hello@shvl.app.

## Install and connect

Import this Git repository as an Agent Plugin in a compatible client. `mcp.json` points to SHVL's existing public read-only endpoint at `https://shvl.app/mcp/v2`. Sign in through OAuth and select a returned workspace. An account alone does not create a workspace or connect accounting software; workspace access and an applicable active trial or subscription are required.

The `shvl-workspace-review` skill covers workspace selection, overdue briefs, receivables health, case search and case detail. It does not send reminders or change accounting records. Live discovery on 3 November 2026 confirmed the ordinary six-tool read-only catalogue. End-to-end Cursor OAuth is not yet verified, so this package is not claimed to be a tested Cursor connection.

## Scope

This is the workspace-first scope used by the approved SHVL public connector. It is not the separate expanded developer API. The historical CSV helper and CSV-led package were removed from this package in version 1.0.1. The server retains a legacy optional CSV tool for compatibility; this skill does not use or promote it.

Material used with an AI client remains subject to that client and model service's data settings. This package contains no install scripts, hooks, dependencies or credentials. Only authorised workspace data should be shared with the client.

Root `plugin.json` is the Agent Plugins manifest. `.plugin/plugin.json` mirrors public metadata for Cursor Directory's current indexer. Logo URLs refer to the existing company website icon. MIT applies to these package files; product names and service access remain subject to their respective terms.
