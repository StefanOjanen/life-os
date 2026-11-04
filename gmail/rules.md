# Gmail triage rules

Applied by the morning run to `in:inbox newer_than:2d` and lightly by the evening run. Every action is reversible: labels can be removed, archived mail stays in All Mail, Trash keeps mail for 30 days. When in doubt, leave it in the inbox and mention it.

**Principle:** the inbox only holds mail that needs the owner or comes from a real person. Everything else gets a label and is archived. Sort by sender, never by Gmail category.

## Labels to create

`Action`, `Life OS` (routine mail), `Money/Banking`, `Money/Tax`, `Money/Insurance`, `Receipts/Orders`, `Receipts/Subscriptions`, `Home`, `Travel`, `Work`, `Reading/News`, `Reading/AI`, `Social`, `Accounts/Security`, `People/Family`.

After creating them, list the label IDs from the connector and note them here so the routine can apply them directly:

| Label | ID |
|---|---|

## Never touch (leave in the inbox, a label is fine)

- Anything starred.
- Anything from a real person writing to the owner.
- Anything about payment failures, invoices, overdue notices, tax, insurance, banks, housing, employer, legal, government or healthcare.
- Security alerts from the last 7 days.

## Rules by sender (first match wins)

| Match | Label | Then |
|---|---|---|
| your employer's domain | `Work` | inbox |
| your bank, broker or tax authority | `Money/...` | statements: archive; anything to do: inbox + `Action` |
| order and shipping notifications | `Receipts/Orders` | archive |
| SaaS billing | `Receipts/Subscriptions` | archive; a failed payment: inbox + `Action` |
| newsletters you want | `Reading/...` | archive |
| social network notifications | `Social` | archive |
| sign-in alerts, 2FA, password resets | `Accounts/Security` | inbox for 7 days |
| retail promotions (list them) | none | Trash |
| anything else that is clearly bulk marketing | best-fit label | archive, do not trash unknown senders |
| anything else | none | leave in the inbox |

## Output of each run

In the brief: counts (archived, trashed, left in the inbox), then the items that need the owner, each with a one-line reason and a Gmail link.
