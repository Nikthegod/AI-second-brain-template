# Home

Start here. Each link opens a Map of Content (MOC) for one project or area; projects with fewer than 3 notes link their notes directly.

## Projects

- [[Investment Advisor Agent - Project Plan]] · [[How to Use the Investment Advisor Agent]] *(example — under 3 notes, so no MOC yet)*

## Long-term areas

- [[MOC - Studies]] *(example)*

## Resources

- [[The Art of War]] *(example book note)*
- [[Passport Renewal]] *(example Life-Admin note)*

## Latest briefings

```dataview
LIST FROM "Daily_Briefings"
SORT file.name DESC
LIMIT 3
```

## Latest research briefs

```dataview
LIST FROM "4-Research_Briefs"
SORT file.name DESC
LIMIT 5
```

## Inbox

```dataview
LIST FROM "0-Inbox"
```

## Recently changed

```dataview
TABLE file.mtime AS "Modified"
FROM -"6-Archive" AND -"0-Inbox" AND -"5-Resources/Claude Rules" AND -"5-Resources/Templates" AND -"4-Research_Briefs" AND -"Daily_Briefings"
WHERE !contains(file.folder, "Agent Output")
SORT file.mtime DESC
LIMIT 10
```
