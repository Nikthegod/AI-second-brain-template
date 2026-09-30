---
tags: [example, ai, finance]
created: 2026-01-08
status: growing
---

# Investment Advisor Agent – Project Plan

> [!example] Example project
> Shows how a project lives in the vault: notes and plans here, **code in its own git repository outside the vault**. `Profile/` holds files you write for the agent; `Agent Output/` holds what it writes back. Delete once you have your own projects.

## Summary
- An AI agent that reviews a sample portfolio against a written risk profile and produces a plain-English monthly report.
- Research and education only: it explains and flags, it never buys, sells, or moves money.
- Portfolio piece: public repo with a demo on made-up data; the real version runs locally.

## Scope
- **v1:** read `Profile/Risk Profile.md`, read a holdings CSV, compare allocation to targets, flag drift and high fees, write a report to `Agent Output/`.
- **Later:** news summaries per holding, what-if projections using [[Compound Interest]], a small dashboard.

## Guardrails
- Every report starts with "Not investment advice."
- Code enforces folder access: read only `Profile/`, write only `Agent Output/`.
- No brokerage connections, no account numbers anywhere.

## Where things live
- Code: `~/Projects/investment-advisor-agent/` (separate git repo, pushed to GitHub)
- Plan and notes: this folder
- Agent input: [[Risk Profile]]
- Agent output: `Agent Output/`, e.g. [[2026-01-31 Monthly Portfolio Review]]

## Next steps
- [ ] Write the holdings CSV format
- [ ] Build the folder-access helper with tests
- [ ] Generate the first report on sample data

## Related
- [[How to Use the Investment Advisor Agent]]
- [[2026-01-10 Index Funds vs Active Funds]] — background research brief
- [[Corporate Finance L1 - Time Value of Money]] — the maths behind projections
