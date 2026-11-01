# Security

Glancet runs on your Mac with access to your coding agents' hook events, their
settings files, and (for usage limits) your Claude Code sign-in. If you find a
way to abuse any of that, please tell us privately first.

**Report a vulnerability:** email **support@glancet.io** with "Security" in the
subject. Please don't open a public issue for it.

Useful to include:

- the Glancet version and build (menu-bar icon → the first menu item, e.g.
  `Glancet 0.2.4 (build 105)`) and your macOS version;
- what an attacker can do, and what they need first (a local process? a crafted
  link? a malicious agent payload?);
- steps to reproduce.

We aim to reply within a few days. Fixes ship through the in-app updater,
which only installs updates signed with Glancet's key.

## What is in scope

- The local event server (`127.0.0.1`, token-authenticated) and the hook scripts
  Glancet installs into `~/.glancet` and into agents' settings files.
- Anything that makes Glancet approve an agent's request without you clicking
  Allow — silence is designed never to approve anything.
- The `glancet://` URL scheme and the licence activation flow.
- The update channel (Sparkle feed and signatures).
