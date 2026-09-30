# Study notes (Claude Rules)

Read this before writing a study note from a lecture, reading, case study, or other source file.

The structure combines four proven learning methods:
- **Cornell method** — a summary plus cue questions, so the note can be reviewed in minutes.
- **Active recall** — questions to test yourself, rather than re-reading.
- **Feynman technique** — each concept explained in plain words, as if to a non-specialist.
- **Zettelkasten linking** — reusable ideas live in their own notes and are linked, not repeated.

## Template

Use these sections in this order. Leave out a section only if the source has nothing for it.

````markdown
---
tags: [finance]
created: YYYY-MM-DD
status: seedling
source: "[[CorpFin L1 - Time Value of Money.pdf]]"
---

# Corporate Finance L1 – Time Value of Money

## Summary
- 3–5 bullets giving 90% of the value in 20% of the reading time.
- Lead with the main conclusion of the lecture.

## Key concepts
### Present value
- **In plain words:** one or two sentences a non-specialist would understand.
- **Why it matters:** the decision or problem it helps with.
- Formula, if any: $PV = \dfrac{FV}{(1+r)^n}$
- See [[Discount Rate]] for the reusable concept note.

## Frameworks and models
> [!tip] Framework name
> Steps or components, one line each. When to use it, and when not to.

## Worked examples
- One example from the source, step by step, with the numbers.

## Cue questions
Questions to test recall. Answer from memory before re-reading the note.
- What does a higher discount rate do to present value, and why?
- When would you use an annuity formula instead of discounting each cash flow?

## Connections
- Builds on: [[Note]] — one line on how.
- Contrasts with: [[Note]] — one line on the difference.
- Appears again in: [[MOC - Topic]]

## So what for me
- How this helps with the goals in `goals.md` (interviews, projects, decisions).
- Links to related projects or notes, where relevant.

## Claude's additions
- Explanations or examples not in the source. Leave empty if none.

## Open questions
> [!question] Anything unclear, unreadable, or worth asking in class.
````

## Rules
- **Content:** only what the source says, outside `## Claude's additions`. Keep the source's terms and numbers exactly.
- **Length:** aim for one to two screens per lecture. Cut detail rather than cram it in; the original is one click away.
- **Formulas:** LaTeX with `$...$` inline or `$$...$$` on its own line. Define every symbol once.
- **Callouts:** `> [!tip]` for frameworks, `> [!example]` for worked examples if long, `> [!question]` for open questions. No other callout types.
- **Cue questions:** 3–6 per note. Ask for reasoning ("why", "when", "what happens if"), not just definitions.
- **Reusable concepts:** if a concept will matter beyond this source, give it its own `1-Notes/` note in the same plain-words format and link to it here.
- **So what for me:** 2–4 bullets, specific to the goals in `goals.md`. Skip generic statements like "useful for work".
- **Case studies:** add a `## Case facts` section after the Summary (company, situation, decision, numbers), and make `## Frameworks and models` show how the framework applies to the case.

## Books

Use this instead of the template above when the inbox item is a book: usually exported highlights plus a short reflection. Save as `5-Resources/Books/<Title>.md`, with `source:` set to the book title and author.

````markdown
---
tags: [books]
created: YYYY-MM-DD
status: evergreen
source: "<Title> — <Author>"
---

# <Title> — <Author>

## Summary
- 5–7 bullets giving 90% of the value in 20% of the reading time.

## Plot / Core argument
- Fiction: the story in 5–10 bullets. Non-fiction: the argument, step by step.

## Key concepts / characters
- **Name:** one or two plain-words sentences each.

## My highlights
> Exported quotes, exactly as written, with chapter or location if given.

## My takeaways
- From my reflection, in my words.

## So what for me
- 2–4 bullets linking to my goals or related notes.

## Claude's additions
- Anything from general knowledge rather than my highlights or reflection, labelled "general knowledge — verify".
````

- Highlights and reflection are the source. Keep them exactly as written.
- Summary, plot, and concepts may draw on general knowledge for well-known books, but anything not supported by my highlights or reflection goes under `## Claude's additions`.
- Never process a whole book file unless I ask. If only a book file is dropped in, ask for highlights and a reflection instead.
