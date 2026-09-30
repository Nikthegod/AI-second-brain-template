---
tags: [example, finance, studies]
created: 2026-01-12
status: growing
source: "[[CorpFin L1 - Time Value of Money.pdf]]"
---

# Corporate Finance L1 – Time Value of Money

> [!example] Example study note
> Shows what `/study-note` produces from a lecture deck. The original PDF would sit in `../Originals/`. Delete this once you have your own notes.

## Summary
- Money today is worth more than the same amount later, because it can be invested to earn a return.
- Present value converts a future amount into today's money by discounting at the required rate of return.
- The higher the discount rate or the longer the wait, the lower the present value.
- Every valuation later in the course (bonds, projects, companies) is built on this one idea.

## Key concepts
### Present value (PV)
- **In plain words:** what a future payment is worth if you had it today instead.
- **Why it matters:** lets you compare cash arriving at different times on equal terms.
- Formula: $PV = \dfrac{FV}{(1+r)^n}$, where $FV$ is the future amount, $r$ the rate per period, and $n$ the number of periods.
- See [[Present Value]].

### Discount rate
- **In plain words:** the return you could earn elsewhere for similar risk — the "price" of waiting.
- **Why it matters:** small changes in the rate move valuations a lot over long periods.
- See [[Discount Rate]].

### Compounding
- **In plain words:** earning returns on your past returns, not just on the original amount.
- Formula: $FV = PV \times (1+r)^n$ — the reverse of discounting.
- See [[Compound Interest]].

## Frameworks and models
> [!tip] Comparing cash flows at different times
> 1. Pick one point in time (usually today). 2. Discount or compound every cash flow to that point. 3. Compare the totals. Don't add cash flows from different dates without converting them first.

## Worked examples
- **Question:** what is $1,000 received in 3 years worth today at 5% a year?
- $PV = \dfrac{1000}{(1.05)^3} = \dfrac{1000}{1.157625} \approx 863.84$
- **Reading it:** you should be indifferent between $863.84 today and $1,000 in three years, at a 5% required return.

## Cue questions
- Why is $1,000 today worth more than $1,000 in five years, even with zero inflation?
- What happens to present value when the discount rate doubles — and why is the effect bigger for distant cash flows?
- When would you compound instead of discount?

## Connections
- Builds on: [[Compound Interest]] — discounting is compounding in reverse.
- Used in: [[Investment Advisor Agent - Project Plan]] — the agent's return projections rely on the same maths.
- Part of: [[MOC - Studies]]

## So what for me
- Case interviews and finance roles expect quick PV reasoning without a spreadsheet.
- The agent project's projections are only as good as the discount-rate assumptions behind them.

## Claude's additions
- Rule of 72 (general knowledge): at r% a year, money roughly doubles in 72 ÷ r years — handy for sanity-checking answers.

## Open questions
> [!question] How is the discount rate chosen for a real project, rather than given in the question? (Probably covered in a later lecture on WACC.)
