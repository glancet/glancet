<p align="center">
  <img src="https://glancet.io/icon-180.png" width="96" height="96" alt="">
</p>

<h1 align="center">Glancet</h1>

<p align="center">
  Live status for your AI coding agents — in the MacBook notch.<br>
  <a href="https://glancet.io">glancet.io</a>
</p>

<p align="center">
  <img src="https://glancet.io/og.png" alt="Glancet in the MacBook notch" width="800">
</p>

---

Run several coding agents at once and you lose track of which one is thinking,
which is blocked on your approval, and which one already finished. Glancet puts
that answer where you are already looking.

A pixel-art alien lives in the notch. It marches while an agent works and shows
elapsed time. Hover to expand every session, your usage bars, and recent
history. On external monitors nothing appears until something actually needs
you — an approval, a completion, a near-limit warning — and then it gets out of
the way.

## Install

```sh
brew tap glancet/glancet
brew install --cask glancet
```

Or download it from [glancet.io](https://glancet.io). Updates arrive through the
app itself, cryptographically verified before they install.

**Apple silicon, macOS 13 (Ventura) or newer.** There is no Intel build.

## What it does

**See what's happening**
- Per-session state: working, needs input, done, failed — and *idle*, rendered
  like "no session" so an open terminal can never fake a completion.
- The prompt each session is working on, so parallel runs in one repo stay
  tellable apart, plus the agent's closing message when a turn ends.
- Elapsed time, project, git branch, model, and context left per session.
- Live subagents fold out with each task and whether it's still running.
- Permission mode surfaced only when it isn't `default` — plan, accept-edits,
  bypass change what an agent does *without asking*.

**Survive a relaunch**
- Glancet reads the agents' own transcripts on launch, so an update or a crash
  no longer shows "no active sessions" while three agents are mid-turn.

**Act without leaving**
- <kbd>⇧⌘G</kbd> opens the panel on whichever screen your cursor is on.
- Click a session — or <kbd>⌘1</kbd>–<kbd>⌘5</kbd> — to jump straight back to
  it, landing on the exact pane where your terminal allows it.
- Answer Claude Code's permission prompts and questions from the notch
  (off by default). Silence never approves anything: if Glancet isn't running,
  is quit mid-decision, or you simply ignore it, the prompt appears in your
  terminal exactly as it does today.
- **Reply from the panel.** A finished session grows a reply field — type a
  follow-up and it's typed into that session's terminal. Only for finished
  sessions, and only where the exact pane can be addressed (tmux, iTerm2):
  keystrokes aimed at "whatever is frontmost" land in the wrong shell.
- Rename any session; the name sticks to the project across restarts.

**Claude usage**
- Session, weekly and model-family limits with reset countdowns, polled
  conservatively. Optional alerts at 75 / 90 / 100%.
- One switch turns the feature *and* the credential read off — it is a privacy
  control, not a display toggle.

## Agents

Ten agents connect today, and every one has been exercised end to end against a
real install.

| Agent | Notes |
|---|---|
| Claude Code | the fully wired one: approvals, questions, usage limits, transcript enrichment |
| Gemini CLI | hooks run synchronously there, so Glancet's stay async and short |
| Codex, Cursor, Kimi CLI, Qwen Code, Qoder, CodeBuddy, Factory, OpenCode | connected via each agent's own hook or plugin format |

A newly added agent carries a **beta** tag in Settings until someone has
actually run it — Glancet doesn't claim more than has been measured. Nothing
carries it right now.

Agents appear in Settings only once they are actually installed — presence means
the agent has written a file into its config directory, not merely that the
directory exists.

Jumps land on the exact pane in **iTerm2, tmux, WezTerm, kitty and Terminal.app**
(the last matched by its controlling terminal). Everywhere else — Ghostty, Warp,
Alacritty, VS Code, Cursor, the JetBrains IDEs — Glancet raises the project's
window instead.

No notch? The same always-on capsule sits under the menu bar instead, and the
menu-bar icon can be switched off entirely if you'd rather have neither.

## Privacy

Everything that describes your work stays on your machine. State comes from
local agent hooks over loopback HTTP with token auth; your Claude token is read
locally.

Three small requests do leave, and none of them describe your work: the usage
call to Anthropic's own endpoint, a once-a-day update check, and a single
anonymous "+1" on first launch so installs can be counted. The last two can be
switched off in Settings. Full detail: [glancet.io/privacy](https://glancet.io/privacy).

## This repository

**This is the community home — bug reports and feature requests.** Glancet is
not open source, so there is no application code here. Use the
[issues](../../issues) for anything you hit, and star the repo if it is useful
to you.

**Free while it's in beta** — the full app, no card, no account. When the store
opens it becomes a one-time unlock: a perpetual licence, not a subscription,
valid on one Mac at a time and movable as often as you like.

- [Website](https://glancet.io) · [Changelog](https://glancet.io/changelog) · [Support](https://glancet.io/support)
- [Privacy](https://glancet.io/privacy) · [EULA](https://glancet.io/eula) · [Refunds](https://glancet.io/refunds)
