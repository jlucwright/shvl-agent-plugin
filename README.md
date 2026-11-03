# SHVL invoice CSV review

Prepare review-only invoice chase wording and indicative UK B2B calculations from an aged-debtors CSV.

Published by Studea Limited. Product: [shvl](https://shvl.app). Support: hello@shvl.app.

## Install

Import this Git repository as an Agent Plugin in Cursor or another compatible client. The package contains the `shvl-csv-review` skill. It has no install scripts, hooks, dependencies or bundled credentials. Material used with Cursor remains subject to the model service and account settings; this package does not upload it to SHVL except when the user authorises a SHVL tool call.

## Connection

The MCP configuration points to SHVL’s hosted read-only endpoint. Anonymous CSV analysis was checked with a fictional fixture on 3 November 2026. Sending a CSV transmits it to SHVL; use only data the user authorises for that purpose. The separate workspace-read tools require OAuth; Cursor workspace authentication is not claimed as verified. No message is sent and no CSV is imported into the account.

## Package layout

`plugin.json` declares the portable Agent Plugins manifest. `skills/` contains the product-specific review workflow. See the skill for inputs, boundaries and an example.

MIT applies to these package files. Product names and service access remain subject to their respective terms.

`.plugin/plugin.json` repeats public metadata for Cursor Directory’s current indexer, which does not read the standard root manifest for listing metadata. The root manifest remains the portable runtime contract. Logo URLs reference existing company website icons.
