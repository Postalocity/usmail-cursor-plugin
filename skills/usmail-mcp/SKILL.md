---
name: usmail-mcp
description: >-
  Use when connecting or using USMail.ai production MCP for print-to-mail —
  OAuth on app.usmail.ai/mcp, proof, postage grant, human Pay & Approve.
---
# USMail.ai MCP (production)

SSOT: https://www.usmail.ai/skills.md and https://www.usmail.ai/AGENTS.md. Re-read skills after Connect. Slogan: **You upload. You approve. We produce.** Not USPS. Never mill `postalocity_*` names.

## Connector

One server: **`usmail`** → `https://app.usmail.ai/mcp` (OAuth).

If needsAuth: first beat is `get_account_status` so the host raises **Connect / Authorize** on the **existing** `usmail` server. **Never `AuthenticateMcpServer`.** That surfaces **Added**, not Authorize. Do not add a second connector. Do not sign out.

After Connect, match skills **Version:** to `initialize.serverInfo.version` (connect-time). If `get_account_status.mcpVersion` is present, it should match. If skills are older, re-read the file. Cite `skills <Version>` on status cards.

Job links: `https://app.usmail.ai/?job={id}`.

## Tools (prod = 18)

`get_account_status`, `list_mail_products`, `create_mail_job`, `upload_document`, `get_document_upload_params`, `detect_zone`, `configure_zone`, `configure_mail_job`, `add_recipients`, `generate_proof`, `get_mail_job`, `list_mail_jobs`, `submit_mail_job`, `cancel_mail_job`, `unapprove_mail_job`, `list_address_quality`, `get_agent_spend_grant`, `set_agent_spend_grant`.

Ask the live server after login. Do not invent names.

## Product walls

- Agents **prepare**: upload, lists, setup, proof, status, cancel a draft, unapprove-to-edit.
- Humans **fund the meter** and **approve production mail**. Agents never approve, never spend, never run card deposits.
- Prompt for the **postage grant early** (after the PDF is on the job, before chips). Capped/uncapped → later `submit_mail_job` mill-approves. Decline → Pay & Approve on the app.
- Show a proof only when mill is ready. If `progress.millPercent` is present, wait until **100**. Never reuse a stored `proofUrl`.
- Paste mill `message` / `mill_error` **verbatim**.
- Status cards include live **Open job** only on Proof ready, Production queued, or Paused — not while Building.

## Sequence (short)

1. Attach PDF (`fileBase64` bytes, or S3 via `get_document_upload_params` then `upload_document`). Never `@/path`.
2. `detect_zone` → Letter vs Postcard from page size.
3. Recipients? Document vs CSV — wait. CSV = `add_recipients` (7-col: name, company1, address1, address2, city, state, zip).
4. `create_mail_job`. Document: upload then zone. CSV: `add_recipients` first, then artwork.
5. Grant if off.
6. Chips one field at a time (`setup.next.prompt`).
7. `generate_proof`. Coarse-poll `get_mail_job` silently until proof or hung.
8. Proof ready card → Looks good → `submit_mail_job`.

Full cards and fail classes: https://www.usmail.ai/skills.md
