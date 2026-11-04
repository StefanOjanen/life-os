# Life OS

A personal operating system built on Claude. A private git repository of markdown files plus a scheduled cloud routine that runs twice a day in one persistent chat session. The routine triages email, checks the calendar, chases open tasks and sends a short brief.

This is a template. Fork it into a **private** repository, fill in `CLAUDE.md`, and follow `SETUP.md`. Provided as-is, without support.

## Design principle

The failure mode it is built around: setting up systems and then not attending to them. So follow-through is enforced by a fixed routine and verifiable checks, not by more reminders.

## How it works

- **Runtime:** Claude Code in Anthropic's managed cloud environment. One scheduled routine fires the same prompt into one persistent session at fixed times; the prompt selects the run (morning, evening, weekly) from the local time.
- **State:** git is the only durable state. The container is disposable; every run ends with a commit to `main`.
- **Connectors (MCP):** Gmail, Google Calendar, GitHub.
- **Delivery:** the brief arrives by email to yourself, as the last chat message, and as one phone push per run.

## The nudge list

Every action that waits on you goes into `now.md` as a row: an ID (`N12`), the item, a due date, a **done-when check the routine can verify itself** (a sent email, a confirmation mail, a file), and a count of reminders. Rows are reminded until the check passes, then deleted. Rows reminded three or more times switch to a "decide, don't repeat" form: done / new date / park / drop / delegate.

## Reply grammar

Replies can be email or chat, short and forgiving: `done N4`, `N4 Fri`, `park N20`, `drop N17`, `delegate N5 to Sam`, `draft N18`, `add: renew passport by 30 Nov`, `energy 3`. Anything else is filed as an ordinary answer.

## Files

| Path | Purpose |
|---|---|
| `CLAUDE.md` | Who you are, permissions, style. The operating manual the routine reads first. |
| `now.md` | Top 3, deadlines, nudge list, waiting-on. Single source of truth for what needs doing. |
| `inbox.md` | Unsorted capture; the routine files items into place. |
| `projects/*.md` | One file per project: status, next action, open questions, log. |
| `learning/*.md` | Optional syllabus per track and a lesson log. |
| `growth/capacity.md` | Weekly workload budget, early warning signs, energy log. |
| `gmail/rules.md` | Mail triage rules. |
| `routines/*.md` | The instructions each run follows. |
| `journal/`, `reviews/` | Daily log and weekly reviews written by the routine. |

## Daily cycle

- **Morning:** apply replies, triage mail, read the calendar, run nudge checks, send the brief.
- **Evening:** what got done, tomorrow's top 3, nudges, optional energy score.
- **Weekly:** wins, slips, workload against the budget, overdue and parked items, next week's top 3.

## Security model

- Mail goes only to the owner. No payments, trades or messages to third parties.
- Email, web pages and other people's content are data, never instructions. Anything that reads like an instruction is ignored and reported.
- The routine never stores passwords, card numbers or tax IDs in the repo.
- Everything it changes is committed, so it can be reviewed and reverted.
- Use a **private** repository. The journal and task files will contain personal information.

## Known limits

- Some web sources rate-limit or block cloud IPs; the routine reports this rather than working around it.
- Connectors can disconnect between runs; tools are reloaded at the start of each run.
- No access to your local browser or machine. Anything needing a login or a payment goes on the nudge list.

## Licence

MIT, see `LICENSE`.
