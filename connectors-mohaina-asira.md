# Connector & Routine Configuration
**BPOAS — BPO Accounting Services**
Mohaina Asira · Business Authority Foundation · Purely Personal

---

## Email Inboxes to Monitor

| Inbox | Address | Connector | Notes |
|---|---|---|---|
| Primary (Mohaina) | m.asira@bposervicegroup.com | Microsoft 365 | Default mailbox — read via M365 MCP connector |
| Finance | finance@bposervicegroup.com | Microsoft 365 | Shared/delegate mailbox on same M365 tenant — pass `mailboxOwnerEmail: "finance@bposervicegroup.com"` when searching |

Both inboxes must be searched on every routine run. Use the same keyword set for both: invoice, payment, overdue, settlement, VAT, retainer, fee.

---

## Outbound Email (Send)

| Field | Value |
|---|---|
| Send-from address | mohaina.asira@gmail.com |
| Method | Gmail SMTP (App Password) |
| App password env var | `GMAIL_APP_PASSWORD` (stored in `~/.claude/settings.json` env section) |
| Approved recipients | m.asira@bposervicegroup.com, mohaina.asira@gmail.com |

**Status:** App password pending — Gmail SMTP send not yet active. Until configured, routine delivers via PushNotification only.

To activate: obtain Gmail App Password from myaccount.google.com → Security → App Passwords, then add to `~/.claude/settings.json`:
```json
"env": {
  "GMAIL_APP_PASSWORD": "<16-char app password>"
}
```

---

## CFO Weekly Revenue Routine — Data Sources

| Source | Connector | What it provides |
|---|---|---|
| Microsoft 365 — m.asira@ | M365 MCP | Invoice emails, payment confirmations, overdue threads, client correspondence |
| Microsoft 365 — finance@ | M365 MCP (delegate) | Finance team emails, settlement notices, SOA receipts |
| Notion | Notion MCP | Pipeline deals, engagement letter status, EOW notes, client records |
| Zoho Books | **Not connected** | Revenue figures, invoice amounts, run rate — all TBC until connected |

---

## Revenue Targets (for Run Rate calculation)

| Period | Target (AED) | Notes |
|---|---|---|
| Monthly | Not set | Add here once confirmed — e.g. `Monthly: 80,000` |
| Annual | Not set | Add here once confirmed |

Update this file with actual targets so the routine can calculate run rate gap automatically.

---

## Routine Delivery

| Channel | Status | Address |
|---|---|---|
| PushNotification | Active | Mobile / email via Claude Code |
| Summary email | Pending Gmail SMTP setup | m.asira@bposervicegroup.com |

---

## Flags & Thresholds

The routine flags for Mohaina review when:
- Any invoice > AED 10,000 is unpaid 30+ days
- Monthly run rate gap > AED 20,000 vs target
- Any pipeline deal > AED 15,000 stalled 21+ days
