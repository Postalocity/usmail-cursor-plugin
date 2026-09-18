# USMail.ai Cursor / Grok Bot plugin

Marketplace-style pack so the Added card shows the USMail mark (bundled `assets/logo.svg`) instead of the gray letter avatar from raw `AddMcpServer` URLs.

## Connectors

| Name | URL |
|------|-----|
| `usmail` | https://app.usmail.ai/mcp |
| `usmail-lab` | https://dev.usmail.ai/mcp |

## Install (team — fastest)

1. Cursor Dashboard → **Plugins & MCPs** → Team Marketplaces → **Add Marketplace** → **Import from Repo**
2. Repo: `https://github.com/Postalocity/usmail-cursor-plugin`
3. Add plugin to marketplace → install **USMail.ai**
4. Remove old URL-only `usmail` / `usmail-lab` connectors if present
5. Auth each connector (OAuth)

## Install (public marketplace)

Submit at https://cursor.com/marketplace/publish — manual Cursor review.

## Skills

- `usmail-mcp` — grant off happy path; chips one-by-one; proof ≠ Approve; human Pay & Approve

Lab skills SSOT: https://dev.usmail.ai/skills.md
