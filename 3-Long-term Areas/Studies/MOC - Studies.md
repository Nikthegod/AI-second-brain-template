---
tags: [example, studies]
created: 2026-01-12
status: growing
---

# MOC - Studies

Courses, study notes, and exam prep. Each course gets a subfolder with `Notes/` (study notes) and `Originals/` (lecture PDFs and slides, kept untouched).

> [!example] Example MOC
> Created once the area reached 3 notes. Replace with your own areas.

## Key notes

- [[Corporate Finance L1 - Time Value of Money]] — full example of a study note
- [[Exam Prep Plan]] — tasks with due dates, collected by the Tasks plugin
- [[Why Start Investing Early]] — a processed inbox capture

## All notes

```dataview
LIST FROM "3-Long-term Areas/Studies"
WHERE file.name != this.file.name
SORT file.folder ASC, file.name ASC
```
