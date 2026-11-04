# Delivery and replies

Routines run in the cloud and cannot push to the owner's phone, so email is the channel; replies can also be written in the chat.

## Sending

- Send **only** to the owner's own address, using the Gmail connector. Never to anyone else.
- Subject format: `[Life OS] Morning · Sat 17 Oct`, `[Life OS] Evening · Sat 17 Oct`, `[Life OS] Weekly review · W42`.
- Plain text, skimmable on a phone: short headed sections, bullets, Gmail links for items.
- Every routine email ends with this footer line exactly, which marks it as routine-sent:
  `— Life OS · reply to answer; everything you write gets filed.`
- After sending, apply the `Life OS` label to the thread (keep it in the inbox).
- Send **one** push notification per run (max 200 characters) that leads with the most important item.
- Finish the run with the brief itself as the last chat message, written to the owner, same content and order as the email.
- If sending fails, still write the brief to `journal/` and send the push saying where it is.

## Reading replies (every run does this first)

1. Search `label:"Life OS" newer_than:7d`.
2. In a thread whose first message carries the footer, every later message from the owner is a reply. Read only the new text.
3. A thread whose first message has a `[Life OS]` subject but no footer is a capture the owner sent: add it to `inbox.md`.
4. Keep `journal/processed.txt`: one Gmail message ID per line; skip IDs already listed.
5. Apply nudge commands to `now.md`; free-text answers count too if they match a row.
6. File each answer where it belongs: project files, `now.md`, `growth/`, `learning/` logs, `inbox.md`.
7. If a reply grants a new permission or changes a rule, update `CLAUDE.md` or `gmail/rules.md` and say so in the next email.

## Reply commands

Case, order and punctuation do not matter; several commands can go in one reply.

| Reply | Effect |
|---|---|
| `done N4` | Delete the row. Run its check first if possible; if the check fails, still delete it and log the mismatch. |
| `N13 7 Nov` | New due date, reset the nudge count. |
| `park N20` | Move to "Later (dated)"; not nudged again until the weekly review asks. |
| `drop N17` | Delete the row and log "dropped". |
| `delegate N5 to Sam` | Move to "Waiting on others" with a check date 7 days out. |
| `draft N18` | Prepare a Gmail draft for that item (see below). |
| `add: <task> by <date>` | New row with the next free number and a check the routine picks. |
| `energy 3` | Record today's energy in `growth/capacity.md`. |
| `signs 1 3` / `signs none` | Record this week's warning signs. |

After applying commands, the next email starts with one line confirming what changed. If a command was ambiguous, say so and change nothing.

## Ready drafts

Any row whose action is "send an email to someone" gets a Gmail draft so finishing it means opening the draft and pressing send.

- Write it in the owner's voice and language for that recipient. Put anything Claude cannot know in `[[double brackets]]`.
- Add `Draft: <subject>` to the row so later runs know it exists. Never put IDs, account numbers or passwords in a draft.
- The done-when check stays a check on **sent** mail. Claude never sends these drafts.
