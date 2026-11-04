# Setup

Requirements: a Claude plan with Claude Code and scheduled routines, a GitHub account, a Gmail account, Google Calendar.

1. **Create a private repository** from this template. Do not make it public: the journal and task files will contain personal data.
2. **Edit `CLAUDE.md`.** Fill in who you are, working hours, language, what counts as noise, and the permissions you grant. Start strict: send mail to yourself only, drafts only, calendar read-only.
3. **Connect** the Gmail, Google Calendar and GitHub connectors to Claude and grant the GitHub app access to the private repository.
4. **Create the Gmail labels** listed in `gmail/rules.md`, then replace the example senders with your own. Note the label IDs the connector returns and put them in `gmail/rules.md`.
5. **Create the routine** (Claude Code scheduled routines): repository = your private repo; two daily triggers at your preferred times (for example 08:15 and 18:15 local); prompt = `routine-prompt.md` with your timezone. Add a weekly time if you want the weekly review on its own day.
6. **First run manually.** Check that the brief arrives, labels are applied, and a commit lands on `main`. Fix `CLAUDE.md` and the rules until the output is what you want.
7. **Use it.** Reply to the brief in plain words. Add real tasks to the nudge list in `now.md` or reply `add: ...`.

## Home-screen shortcut to the chat (optional)

The routine writes into one persistent chat session, and you answer there. A one-tap shortcut on your phone makes replying frictionless.

1. **Get the link:** open the routine's chat in the Claude app or at claude.ai/code and copy its `https://claude.ai/code/session_...` URL. Treat the link as private: it only opens for your logged-in account, but do not post it.
2. **Android, opens in the Claude app (recommended):**
   - Install a shortcut app such as *Shortcut Maker* (any app that creates launcher shortcuts for web links works).
   - Choose *Websites* (or the equivalent "URL shortcut"), paste the `https` link, name it `Life OS`, pick an icon, and add it to the home screen.
   - Android should open the `https` link in the Claude app. The app's own `claude://` links are rejected by most shortcut apps, so use the `https` link.
3. **Android, opens in the browser (fallback):** in Chrome, open the link, then menu (three dots) > *Add to Home screen*. This always opens in Chrome, not in the Claude app.
4. **iPhone:** in the *Shortcuts* app create a shortcut with the action *Open URLs*, paste the link, then *Add to Home Screen*. It may open in the browser instead of the app.
5. **Check it:** tap the icon, confirm the chat opens, and reply once (for example `energy 3`) to see it filed in the next run.

If the shortcut stops working, check that the routine still posts into the same session; if you recreate the routine, copy the new session link and make the shortcut again.

## Tuning advice

- Keep the brief readable in three minutes. Cut sections before you add them.
- Add a routine step only when you can say what it costs per week and what it replaces.
- Every nudge row needs a check the routine can verify; use "owner says done" rows only when nothing better exists.
- Review `gmail/rules.md` monthly. Trash is recoverable for 30 days; archive is always safe.
