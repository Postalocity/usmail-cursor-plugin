# USMail.ai Cursor / Grok Bot plugin

Public production plugin for **USMail.ai** (AI print-to-mail). Bundled `assets/logo.svg`. **You upload. You approve. We produce.** Not USPS.

Version **0.2.0**. Production MCP only.

## Connector

| Name | URL |
|------|-----|
| `usmail` | https://app.usmail.ai/mcp (OAuth) |

No lab / `dev.usmail.ai` in this package.

## Install (public marketplace)

1. Submit this repo at https://cursor.com/marketplace/publish (Cursor reviews).
2. After listing: Customize → install **USMail.ai**.
3. **Connect / Authorize** on the existing `usmail` server. Added is not Authorize. Do not `AuthenticateMcpServer`.
4. Agents follow https://www.usmail.ai/skills.md (match **Version:** to connect-time `initialize.serverInfo.version`).

## Install (team)

1. Cursor Dashboard → **Plugins & MCPs** → Team Marketplaces → **Add Marketplace** → **Import from Repo**
2. Repo: `https://github.com/Postalocity/usmail-cursor-plugin`
3. Add plugin → install **USMail.ai** → OAuth on `usmail`

## Skills

- `usmail-mcp` — prod OAuth; grant early; chips one-by-one; proof ≠ Approve; human funds and approves

SSOT: https://www.usmail.ai/skills.md · https://www.usmail.ai/AGENTS.md · https://www.usmail.ai/docs/mcp

## Product walls

Agents prepare (upload, lists, setup, proof, status, cancel draft). Humans fund the meter and approve production mail. Proof only when mill is ready (100% when `millPercent` is present). Mill errors verbatim. Job links: `https://app.usmail.ai/?job={id}`.

## Submit checklist

See [SUBMISSION.md](./SUBMISSION.md).
