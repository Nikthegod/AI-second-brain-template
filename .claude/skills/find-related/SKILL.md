---
name: find-related
description: Find existing notes related to a topic or tag, ranked with a reason for each. Read-only.
argument-hint: <topic, tag, or note name>
---

# Find related notes

Find notes in the vault related to `$ARGUMENTS`. This skill only reads; change nothing unless I say yes at the end.

## Steps

1. Start at `Home.md` and the most relevant `MOC - <Topic>.md`. Note which MOC the topic belongs to.
2. Search, in this order, stopping once you have enough strong matches:
   - frontmatter `tags` and note titles
   - note contents, including close terms and synonyms (e.g. "discount rate" also finds WACC)
   - backlinks to the strongest matches
   - `4-Research_Briefs/`
3. Skip `6-Archive/` unless nothing else matches, and say if you used it.

## Answer

```
## Related to: <topic> — MOC: [[MOC - …]]
1. [[Note]] — one line on why it's related
2. …
Gaps: … (anything the vault doesn't cover yet, one line)
```

- Up to 10 results, strongest first. Say so plainly if there are none.
- Then offer, in one line: add links between these notes, and/or write a Dataview query into a note for a list that stays up to date. Do neither unless I say yes.
