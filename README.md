# Hermes Agent: 7 levels setup

[![Watch the video](https://img.youtube.com/vi/qi_2nHZ9yoA/maxresdefault.jpg)](https://youtu.be/qi_2nHZ9yoA)

The companion files for my video **Hermes Agent Setup: 7 Levels to Your Own AI Team**.

One message to a boss agent on Telegram. He hands the work to two writer agents on a Kanban board, they write at the same time, and he sends back a Threads post and a short video script. A fourth agent checks the server every morning. All of it runs on a 4 GB server.

- Video: [youtu.be/qi_2nHZ9yoA](https://youtu.be/qi_2nHZ9yoA)
- Full written guide: [stackagen.com/guides/hermes-agent-setup-after-install](https://stackagen.com/guides/hermes-agent-setup-after-install)

> Watch the video or read the guide first. This repo holds the files you paste, not the walkthrough.

## What's in this repo

```
profiles/
  michael/SOUL.md   the boss: creates Kanban cards, reviews drafts, sends the final pack
  creed/SOUL.md     writes one Threads post per card
  kelly/SOUL.md     writes one 30 to 45 second short script per card
  dwight/SOUL.md    ops engineer: read-only server health report
prompts/
  prompts.md        every prompt from the video, in order
```

## How to use the SOUL.md files

1. In Hermes Desktop, create a profile per folder name (`michael`, `creed`, `kelly`, `dwight`), cloned from your default profile.
2. Open that profile's **SOUL.md** in the app, replace everything with the file from this repo, and save.
3. Make them yours. The files are written for me (Aniket) and my content. Change the name, the voice rules and the job to fit your team. A research team or a support team works the same way.

On disk, each one lives at `~/.hermes/profiles/<name>/SOUL.md`.

## The one command

Lets Michael use the Kanban board from Telegram. Run it in the Hermes Desktop terminal (`Ctrl+P` or `Cmd+P`, then "terminal"):

```bash
hermes -p michael tools enable kanban --platform telegram && hermes gateway restart
```

## Claude subscription as the model (optional)

Only if you use a Claude Pro or Max plan through the Claude Subscription DirectSDK plugin. On the machine Hermes runs on:

```bash
claude --version        # is Claude Code installed?
claude auth login       # open the link, sign in, paste the code back
claude auth status      # should say "loggedIn": true
```

No Claude Code yet? Install it from the [official setup page](https://code.claude.com/docs/en/setup).

## Before you rely on it

- **Allowed users.** Hermes can run commands on your server. Keep the Telegram allowed users list to people you trust.
- **`/sethome`.** Send it in each bot's chat, or scheduled job results have nowhere to go.
- **Memory loads on a new session.** After saving a memory, send `/new`.
- **Nothing gets posted.** The writers produce drafts only. Read everything before you post.
- **Dwight only reads.** He shows you a fix and waits for your yes. Keep it that way.

## Docs

- [Hermes Agent documentation](https://hermes-agent.nousresearch.com/docs/)
- [Profiles](https://hermes-agent.nousresearch.com/docs/user-guide/profiles), [Kanban](https://hermes-agent.nousresearch.com/docs/user-guide/features/kanban), [Cron](https://hermes-agent.nousresearch.com/docs/user-guide/features/cron), [Telegram](https://hermes-agent.nousresearch.com/docs/user-guide/messaging/telegram)

## Questions

Leave a comment on the video. It's the fastest way to reach me, and it helps the next person who hits the same problem.
