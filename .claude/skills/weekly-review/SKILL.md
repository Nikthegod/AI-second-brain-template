---
name: weekly-review
description: Weekly vault health check — tag clean-up, orphans, stale seedlings, old inbox items, MOCs, briefs worth keeping.
disable-model-invocation: true
---

# Weekly review

Review the vault's health following CLAUDE.md. Fix what the rules allow; list everything else for me to decide.

## Checks

1. **This week:** list notes created or changed in the last 7 days, grouped by MOC (skip `4-Research_Briefs/`, `Daily_Briefings/`, `6-Archive/`).
2. **Tag clean-up:** collect every tag used in frontmatter and compare with CLAUDE.md's list.
   - Merge synonyms, fold tags used on only one note into a broader tag, add tags in use but missing from the list, remove unused tags from the list.
   - Apply if the change touches 10 files or fewer; otherwise list the changes and ask.
3. **Orphans:** notes with no links in or out. Suggest where each should link.
4. **Stale seedlings:** notes still `status: seedling` after 30 days. List them; don't change their status.
5. **Old inbox items:** anything in `0-Inbox/` for more than 7 days, with why it's likely stuck.
6. **MOCs:** notes missing from their MOC (add them); suggest 1–3 changes to each MOC's `## Key notes`.
7. **Broken links:** `[[links]]` in `Home.md` and MOCs that point to nothing. Leave links to MOCs not yet created.
8. **Research briefs:** from the last 7 days in `4-Research_Briefs/`, name any worth turning into permanent notes and why. Don't edit or move the briefs.
9. **CLAUDE.md:** if this week showed a rule being unclear or ignored, suggest one specific edit. Don't apply it.

## Report

```
## Weekly review — YYYY-MM-DD
Done: … (changes made)
Needs you: … (decisions, one line each)
This week: … (short list by MOC)
```

Keep it to one screen. Put detail in the "Needs you" lines only.

## Commit

If anything changed, `git add -A` and `git commit -m "Weekly review YYYY-MM-DD"`. If the vault isn't a git repository or the commit fails (e.g. no git name/email set), don't retry — note "Not committed: <reason>" in the report.
