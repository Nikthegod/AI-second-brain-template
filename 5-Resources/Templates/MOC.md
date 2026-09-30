---
tags: []
created: <% tp.date.now("YYYY-MM-DD") %>
status: growing
---

# <% tp.file.title %>

One line on what this project or area covers.

## Key notes

- [[Note Name]] — why it matters, one line

## All notes

```dataview
LIST FROM "<% tp.file.folder(true) %>"
WHERE file.name != this.file.name
SORT file.name ASC
```
