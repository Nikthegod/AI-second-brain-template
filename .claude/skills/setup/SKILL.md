---
name: setup
description: First-run setup — a few questions, then fills in CLAUDE.md and goals.md and clears the examples.
disable-model-invocation: true
---

# Set up this second brain

Personalise the template for a new user. Only change what's listed here; leave every rule in CLAUDE.md as it is.

## 1. Check the starting point

Read `CLAUDE.md` and `5-Resources/Claude Rules/goals.md`. If neither contains `<placeholders>`, say setup looks done and ask whether to redo any part. Otherwise continue.

## 2. Ask, in one message

Ask these together, numbered, and wait for the answers. Say that short answers are fine and any question can be skipped.

1. What will you mainly use this vault for? (e.g. university, work, side projects, reading)
2. About you in one or two lines: background, and current role or studies.
3. What goals should your notes support? Any paths you're weighing up, or ruled out?
4. Any key dates coming up? (optional)
5. British or US English?
6. 5–15 broad topics you'll take notes on. (Offer suggestions based on answers 1–3.)
7. Any projects or long-term areas to set up now? (e.g. "Thesis" project, "Health" area)
8. The examples: keep them for now, archive them, or delete them?

## 3. Fill in the files

- **`CLAUDE.md`:** replace the placeholders in the opening line, `## About me`, and the spelling line from the answers. Replace the tag list with the user's topics, keeping `second-brain` (used by the Operating Manual) and keeping `example` only if the examples are kept. Delete the `<!-- ... -->` hint comments and the "remind me to run `/setup`" line. Keep About me to 3–5 lines.
- **`goals.md`:** fill in Timeline, Target tracks, and Open questions from answers 3–4. Remove any section left empty.
- **Projects and areas:** create each folder under `2-Projects/` or `3-Long-term Areas/` and link it from `Home.md`. Don't create MOCs yet; CLAUDE.md creates them at 3 notes.

## 4. Handle the examples

Example content (all tagged `example`, or inside an example folder):
- `0-Inbox/Example - Article Clipping.md`
- `1-Notes/Present Value.md`, `Discount Rate.md`, `Compound Interest.md`
- `2-Projects/Investment Advisor Agent/` (whole folder)
- `3-Long-term Areas/Studies/` (whole folder)
- `4-Research_Briefs/2026-01-10 Index Funds vs Active Funds.md`
- `5-Resources/Books/The Art of War.md`
- `5-Resources/Life-Admin/10-Identity/Passport Renewal.md`
- `6-Archive/Old Reading List.md`
- `Daily_Briefings/2026-01-15.md`

Then:
- **Keep:** change nothing.
- **Archive:** move each item into `6-Archive/Examples/`, keeping its folder path, and remove the example links from `Home.md`.
- **Delete:** only if the user explicitly chose delete — remove the items above and their `Home.md` links. Keep every `.gitkeep` so empty folders survive.

Never touch the example inside `5-Resources/Claude Rules/study-notes.md` (it's the template itself) or `5-Resources/Operating Manual.md` (it's the user guide, not an example).

## 5. Git

If the vault isn't a git repository, offer to run `git init`. Then offer a first commit (`git add -A`, `git commit -m "Set up second brain"`). If the commit fails because no git name or email is set, show the two `git config --global` commands and stop — don't set them yourself.

## Report

A short summary: what was filled in, folders created, what happened to the examples, and git status. End with: "Drop something into `0-Inbox/` and run `/process-inbox`."
