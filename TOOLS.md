# Prod public tools (18)

Confirmed against production `https://app.usmail.ai/mcp` (same names as lab).

| Tool | Role |
|------|------|
| `get_account_status` | Meter, account. `mcpVersion` when the tool returns it. |
| `list_mail_products` | Products. No public unit prices. |
| `create_mail_job` | Draft job. |
| `upload_document` | PDF artwork / letter. Not CSV. |
| `get_document_upload_params` | S3 POST for large PDFs. |
| `detect_zone` | Page size → Letter vs Postcard; address candidates. |
| `configure_zone` | Document-path address zone. Not CSV. |
| `configure_mail_job` | One chip at a time. |
| `add_recipients` | CSV digest (`name,company1,address1,address2,city,state,zip`). |
| `generate_proof` | Start mill process. Not Approve. |
| `get_mail_job` | Status, proof, mill_error. |
| `list_mail_jobs` | List. |
| `submit_mail_job` | Grant on → mill-approve. Grant off → Pay & Approve URL. |
| `cancel_mail_job` | Cancel a draft. |
| `unapprove_mail_job` | Unlock an approved job; grant spend should return. |
| `list_address_quality` | AQ rows. Fix/Still-mail/Ignore on the app. |
| `get_agent_spend_grant` | Read grant. |
| `set_agent_spend_grant` | Ask first. Capped / uncapped / off. |

Live names still come from the connected server after login.
