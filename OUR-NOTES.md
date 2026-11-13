# Our notes for this fork

This is my personal version of Zion Brock's Orb firmware. These notes are the house rules
for working on it, for me and for anyone (or any AI assistant) helping me. Where they
disagree with `CLAUDE.md`, these notes win: `CLAUDE.md` is Zion's, written for his own
setup.

## Where things come from

- **`origin`** is my fork: https://github.com/kgwild1-stack/orb-os
- **`upstream`** means Zion's original: https://github.com/Ziplock78/orb-os
  (`CLAUDE.md` uses "upstream" for Quique Tortosa's Capsule Radar. Here it never does.)

To bring in Zion's latest work, fetch from `upstream` and merge it into my branch.

## Never

- **Never run Zion's publish or deploy commands.** That includes `tools/publish-firmware.sh`,
  `tools/release-firmware.sh`, `tools/ship.sh`, `tools/orb-deploy.sh`, any `wrangler deploy`,
  and anything that builds or deploys Orb Studio (`buildtheorb`). They are for his
  infrastructure, not mine.
- **Never push to `upstream`.** My changes go to `origin` only. (In this checkout, pushing to
  `upstream` is switched off.)
- **Ignore `CLAUDE.md`'s references to Zion's private files**, such as his launch plan and UX
  requirements under `~/Developer/agentic-os/`. They are not available here.

## How we add things

- **New features live in their own files.** Change Zion's files as little as possible: ideally
  just the few lines needed to hook a new feature in (for example, registering a screen in
  the app menu). That keeps merging his updates easy.
- **New screens borrow the active theme's look**: its colours, fonts, background and glass
  overlay. They don't bring their own artwork or styling, so they match whatever theme is
  on the Orb.
- **Settings for new features go on the `theorb.local` web page**, not into Orb Studio, which
  is Zion's and not part of this repo.
