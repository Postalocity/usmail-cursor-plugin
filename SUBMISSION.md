# Cursor marketplace submission (Grok bots)

Public listing. Production only. Do not include lab.

## Repo

https://github.com/Postalocity/usmail-cursor-plugin

Default branch must be **0.2.0** (`feat/v0.2.0-prod-only` merged to `main`) before submit.

## Publish

https://cursor.com/marketplace/publish

Paste the GitHub repo URL. Cursor reviews manually.

## Checklist

- [ ] `.cursor-plugin/plugin.json` version `0.2.0`, kebab-case `name`: `usmail`
- [ ] Description names production MCP only; human approve; not USPS
- [ ] `mcp.json` / `.mcp.json` have a single server: `https://app.usmail.ai/mcp`
- [ ] No `usmail-lab`, no `dev.usmail.ai`
- [ ] Logo `assets/logo.svg` committed and referenced
- [ ] `README.md` documents Connect/Authorize (not Added / AuthenticateMcpServer)
- [ ] Skill `skills/usmail-mcp/SKILL.md` points at https://www.usmail.ai/skills.md
- [ ] LICENSE MIT
- [ ] Repo is public
- [ ] Human walked Connect → one job on `app.usmail.ai/mcp` after listing

## Listing copy

**Name:** USMail.ai  
**Short:** AI print-to-mail. You upload. You approve. We produce.  
**Connector:** https://app.usmail.ai/mcp  
