# Setup

Requirements: a Claude plan with Claude Code and scheduled routines, a GitHub account, a Gmail account, Google Calendar.

1. **Create a private repository** from this template. Do not make it public: the journal and task files will contain personal data.
2. **Edit `CLAUDE.md`.** Fill in who you are, working hours, language, what counts as noise, and the permissions you grant. Start strict: send mail to yourself only, drafts only, calendar read-only.
3. **Connect** the Gmail, Google Calendar and GitHub connectors to Claude and grant the GitHub app access to the private repository.
4. **Create the Gmail labels** listed in `gmail/rules.md`, then replace the example senders with your own. Note the label IDs the connector returns and put them in `gmail/rules.md`.
5. **Create the routine** (Claude Code scheduled routines): repository = your private repo; two daily triggers at your preferred times (for example 08:15 and 18:15 local); prompt = `routine-prompt.md` with your timezone. Add a weekly time if you want the weekly review on its own day.
6. **First run manually.** Check that the brief arrives, labels are applied, and a commit lands on `main`. Fix `CLAUDE.md` and the rules until the output is what you want.
7. **Use it.** Reply to the brief in plain words. Add real tasks to the nudge list in `now.md` or reply `add: ...`.

## Tuning advice

- Keep the brief readable in three minutes. Cut sections before you add them.
- Add a routine step only when you can say what it costs per week and what it replaces.
- Every nudge row needs a check the routine can verify; use "owner says done" rows only when nothing better exists.
- Review `gmail/rules.md` monthly. Trash is recoverable for 30 days; archive is always safe.
