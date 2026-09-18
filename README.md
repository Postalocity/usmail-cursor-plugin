# USMail.ai Cursor plugin

Marketplace-style connector pack so Grok Bot / Cursor show the **USMail.ai** mark on the Added card (bundled `assets/logo.svg`), matching Atlassian/GitHub/Outlook — not letter-avatar fallback from raw `AddMcpServer` URLs.

## Connectors

| Name | URL |
|------|-----|
| `usmail` | https://app.usmail.ai/mcp |
| `usmail-lab` | https://dev.usmail.ai/mcp |

Brand: USMail.ai only. Slogan: You upload. You approve. We produce.

## Install

1. Publish this repo to the Cursor marketplace (or team plugin catalog).
2. Install **USMail.ai** from SearchPlugins / marketplace.
3. Auth each connector (OAuth). Remove old custom URL adds (`usmail` / `usmail-lab` without `plugin=`) to avoid duplicates.

## Why

Custom HTTP MCP Added cards ignore live `logo_uri`. Marketplace plugins use `plugin.json` → `logo`.
