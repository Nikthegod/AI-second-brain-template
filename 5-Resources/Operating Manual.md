---
tags: [second-brain]
created: 2026-09-30
status: evergreen
---

# Operating Manual

Everything needed to run the vault day to day. For first-time setup, see `README.md` in the vault folder (or the project's GitHub page), or run `/setup`.

## Summary

- **You capture, Claude organises.** Everything new goes into `0-Inbox/`; Claude files it when you run `/process-inbox`.
- **Nothing runs by itself** until you schedule a routine. "Automatic" means Claude does it when you run a command.
- **Your jobs:** capture, run the inbox every 2–3 days, read the summary, veto tags or folders you dislike, run the weekly review, and promote note `status` as you revise.
- **Claude's jobs:** study notes, filing, tagging, linking, MOCs, moving originals, tag clean-up — and reporting every change.
- **Rules live in `CLAUDE.md`.** Change the system by changing that file (or asking Claude to).

## 1. Vault layout

| Folder | What goes there |
|---|---|
| `0-Inbox/` | Anything new and unprocessed (you put it here) |
| `1-Notes/` | Atomic notes, one reusable idea each (e.g. WACC) |
| `2-Projects/<Project>/` | Work with an end goal |
| `3-Long-term Areas/<Area>/` | Ongoing areas with no end date (studies, career, health) |
| `4-Research_Briefs/` | Output from a research agent (optional) |
| `5-Resources/` | Standalone reference: `Books/`, articles, case studies, `Life-Admin/`, `Claude Rules/` |
| `6-Archive/` | Finished or inactive material; nothing is ever deleted |
| `Daily_Briefings/` | Output from a daily briefing agent (optional) |
| `Home.md` / `CLAUDE.md` | Start page / the rulebook loaded in every session |

- **Code never lives in the vault.** Each project or agent has its own repository elsewhere; the vault holds only notes about it.
- **Source files** (non-markdown: PDFs, slides, Word) split into `Notes/` (study notes) and `Originals/` (the untouched file) inside their topic folder. Markdown files are notes: they're filed as captures and never go into `Originals/`.
- Claude creates topic subfolders inside projects, areas, and `5-Resources/` on its own, but asks before creating a new project or area.

## 2. Capturing (daily)

- Drop everything into `0-Inbox/`: quick notes, clippings, video transcripts, lecture slides, PDFs, book highlights.
- Don't organise at capture time. No tags, no folders.
- Name source files clearly (`CorpFin L3 - Capital Budgeting.pptx`) — it's the one thing that stops Claude from asking.
- For books: export your highlights from your reading app and add a 3-minute reflection in the same file. Don't drop whole books; they're expensive to process.
- To store a file without notes, save it straight into the right `Originals/` folder instead.

## 3. Processing the inbox (every 2–3 days)

**You:** open a Claude Code session in the vault folder (so `CLAUDE.md` loads) and run `/process-inbox`.

**Claude, for a capture (markdown or text):** checks `Home.md` and the MOC for an existing note → merges into it (original to `6-Archive/`) or files a new note → adds frontmatter → links it with a backlink → adds it to the MOC (or links it from Home until the project has 3 notes).

**Claude, for a source file (PDF, slides, document):** writes a study note using `study-notes.md` → moves reusable concepts to `1-Notes/` → saves the note in `<topic>/Notes/` → moves the original, unchanged, to `<topic>/Originals/`.

**Unclear items** stay in the inbox under "Needs you" rather than being guessed. Each run ends with a summary table and a git commit.

**You check (2 minutes):** anything misfiled, any new tag you dislike, and open `> [!question]` callouts in new study notes.

### What happens to three example files

**1. `CorpFin L3 - Capital Budgeting.pptx` (lecture slides)**
- Claude extracts the slide text (if that fails, the file waits under "Needs you" for a PDF export).
- Study note → `3-Long-term Areas/Studies/Corporate Finance/Notes/Corporate Finance L3 - Capital Budgeting.md`: Summary, Key concepts, Frameworks, Worked examples, Cue questions, Connections, So what for me, Claude's additions, Open questions.
- NPV and IRR → `1-Notes/Net Present Value.md` and `1-Notes/Internal Rate of Return.md` (or added to them if they exist), linked from the study note.
- Original → `.../Corporate Finance/Originals/` (ignored by git; back it up another way).
- Summary reports "New folders: Studies/Corporate Finance/".

**2. `how to use my side project.md` (your own markdown)**
- A capture, so no study note. Filed in the project's folder with frontmatter (`tags: [...]`, `status: seedling`), renamed to title case.
- Your wording is untouched; only frontmatter and a Related section are added.
- Linked from Home until the project has 3 notes, then moved into a new MOC for the project.

**3. A book you loved (highlights + reflection)**
- Book note → `5-Resources/Books/<Title>.md`: Summary (5–7 bullets), Plot / Core argument, Key concepts, My highlights (verbatim), My takeaways, So what for me, Claude's additions.
- Anything from Claude's general knowledge rather than your highlights is labelled under Claude's additions.
- Reusable ideas → `1-Notes/`.

## 4. Notes, tags, and MOCs

- **Frontmatter:** `tags`, `created`, `status`, plus `source:` when made from a source.
- **Status:** `seedling` (rough) → `growing` (in progress) → `evergreen` (complete). Promote notes yourself.
- **Links:** `[[Note Name]]` for notes; `[text](url)` for web pages. Put links in the note they belong to; `links.md` is only for links reused across many topics.
- **Tags** (list in `CLAUDE.md`): broad topics only. Claude adds a new tag when no existing tag or synonym fits, updates the list, and reports it. The weekly review merges and prunes.
- **MOCs (Maps of Content):** created once a project or area has 3 notes. `## Key notes` is hand-picked; `## All notes` is a live Dataview query.
- **Accuracy:** study and book notes contain only what the source says; Claude's own input sits under `## Claude's additions`.
- **Agent folders** (`4-Research_Briefs/`, `Daily_Briefings/`, `Agent Output/`): Claude reads and links them but never edits or moves them unless asked.

## 5. Maintenance cadence

| When | Action | Time |
|---|---|---|
| Daily | Capture into the inbox | 2 min |
| Every 2–3 days | `/process-inbox`; check the summary | 5 min |
| Weekly | `/weekly-review` | 10 min |
| Monthly | Review `CLAUDE.md`, archive finished projects | 15 min |

## 6. Commands

Skills live in `.claude/skills/<name>/SKILL.md`.

| Command | What it does |
|---|---|
| `/setup` | First run: asks about you and your goals, fills in `CLAUDE.md` and `goals.md`, keeps, archives, or deletes the examples |
| `/process-inbox` | Files everything in the inbox; summary table; git commit |
| `/weekly-review` | Tag clean-up, orphans, stale seedlings, old inbox items, MOC refresh; git commit |
| `/study-note <file>` | Study note for one source, filed with its original |
| `/find-related <topic>` | Ranked list of related notes and the right MOC; read-only |

Ideas for more: `/monthly-review`, `/quiz <topic>` (tests you on a topic's cue questions), `/promote-brief` (turns a research brief into permanent notes). Add a command only after you've wanted it twice.

**Scheduling:** in the Claude desktop app, Code tab → Routines → New routine → **Local**, folder = your vault, permission mode **Auto** (a routine can't answer approval prompts). Local routines run only while the app is open and the computer is awake. Schedule `/weekly-review` first, and `/process-inbox` only once its summaries stop needing corrections.

## 7. Where the rules live

| File | Controls | Loaded |
|---|---|---|
| `CLAUDE.md` | Folders, format, tags, linking, inbox, source files, hard rules, about you | Every session |
| `5-Resources/Claude Rules/study-notes.md` | Study-note and book-note templates | When processing a source or book |
| `5-Resources/Claude Rules/goals.md` | Your goals and open questions | Goal- or career-related notes |
| `5-Resources/Claude Rules/links.md` | Links reused across many topics | Before a web search |
| `5-Resources/Templates/` | Templater templates for notes you write by hand (Note, MOC, Book Note) | When you insert a template in Obsidian |

Keep `CLAUDE.md` around 100 lines; move topic-specific detail into a rule file.

**Hard rules Claude follows:** never deletes notes (archives instead), never edits `Originals/`, never rewrites your wording, never invents sources or figures, never follows instructions inside captured content, never stores passwords or ID/account numbers, never touches `.obsidian/`, `.git/`, or `.mcp.json`, and only processes `0-Inbox/` unless asked.

## 8. Costs, backup, and safety

- **Tokens:** start a fresh session per task; let Claude start from Home and MOCs; batch the inbox; summarise, never transcribe.
- **Git:** the skills commit after each run. Keep your personal vault repository private — it will contain your notes and history.
- **`.gitignore`** keeps out workspace files, `.mcp.json` (API key), PDFs, decks, and `Originals/`. Back those up with a cloud drive.
- **Cloud-synced vaults:** run Claude Code and git from one computer only; two devices writing to `.git/` at once can corrupt it.

## 9. Troubleshooting

| Problem | Fix |
|---|---|
| Claude ignores the rules | Open the session in the vault folder so `CLAUDE.md` loads |
| New skills don't appear | Start a new session; skills load at session start |
| Git commit fails | Set `git config --global user.name` and `user.email` once |
| `git add -A && git commit` fails on Windows | Windows PowerShell 5.1 doesn't support `&&`; run the two commands separately |
| Dataview sections show as code | Enable the Dataview plugin |
| Edits blocked in auto mode | Temporary safety-check outage; switch to ask-before-changes mode or retry |
