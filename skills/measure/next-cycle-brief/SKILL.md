---
name: next-cycle-brief
description: Factory station 12 (measure line). Writes the client brief for the next campaign cycle from approved insights, the marketing plan's KPIs, the offer and the client's confirmed priorities, dates and budget. Use when asked for a next-cycle brief, next campaign brief, or the plan for the next period, or to start the next loop after a performance report and insights summary. Requires an approved insights summary and period dates from the user. Stops and lists gaps if either is missing.
---

# Station: Next-cycle brief

**Line:** Measure · **Needs:** insights-summary (approved), marketing-plan hand-off · **Feeds:** content-calendar (next loop) and every content and creative station

**Job:** Start the next cycle with a brief every station can run from, built only from approved evidence and confirmed client decisions.

---

## 1. Inputs

**Required (context files, read exactly as named)**
- `context/marketing-plan.md`: objective, KPI table, campaign IDs, spending controls, hand-off block
- `context/offer.md`: services, prices, service area
- `context/positioning.md`: core message and content pillars
- `context/personas.md`: audiences
- `context/voice-and-tone.md`
- `context/guardrails.md`
- `templates/client-brief.md`: the section structure in section 3

**Required (outputs, from the client's folder in `outputs/`)**
- The most recent insights file whose status line reads `APPROVED – <date>`
- The most recent approved performance report that covers the period the insights describe

**Use if available**
- `context/brand-book.md`
- `context/content-calendar.csv`: to confirm what was produced and its status
- The most recent approved client brief in `outputs/<client-slug>/reports/`, for "what changed since last cycle"

**Supplied at run time (ask in one message if not given)**
- Period start and end dates. The brief sets its own period; do not assume a length.
- Confirmed monthly marketing budget, and whether it has changed
- Client priorities for the period, one sentence each
- Dates or channels the client cannot use (blackouts, events, holidays)
- Approvals or constraints added since the last cycle

**Stop conditions:** no approved insights file, insights status not `APPROVED`, no approved performance report for the covered period, or period dates not supplied. List what is missing and stop. A provisional brief is produced only when the user explicitly asks for one. In that case every section is labelled `PROVISIONAL` and the status stays `DRAFT`.

---

## 2. Steps

1. Confirm the client slug and name from `context/marketing-plan.md`. Find the approved insights file. If there is none, stop (section 1).
2. Ask for the period start and end dates and the run-time inputs above, in one message. Do not assume a 12-week cycle.
3. Read the approved insights. List each insight ID with its evidence row and recommended change. Use only insights whose status is `APPROVED`.
4. Write one objective for the period: a single measurable sentence with a deadline inside the period. Take the metric from KPI rows in `context/marketing-plan.md`.
5. Set targets for the period. For each KPI row used: target = plan target × (period days ÷ 84), rounded as in the performance-report station. Write the formula in the Target method note. If the plan's Week 1 date is still TBC and the period is not confirmed, mark targets `[NEEDS CLIENT INPUT]`.
6. Choose audience and message. Name the personas from `context/personas.md`, priority persona first. Name the pillar or pillars from `context/positioning.md`. Use only claims that appear in the context files or approved insights.
7. Plan deliverables. Each row names a station as listed in `skills/README.md`, a quantity and a due date inside the period. Add a deliverable only when an approved insight or the client's stated priority supports it.
8. Write one test: tied to one insight ID, with a success measure and a review date inside the period.
9. Record constraints from client input and the guardrails: blackouts, approvals, budget limits, consent requirements.
10. Write the Evidence table: one row per change or deliverable that differs from the last cycle, citing its insight ID and evidence row.
11. Run the guardrail check (section 4), then show the brief with the review checklist (section 5).

---

## 3. Output template

**File name:** `outputs/<client-slug>/reports/YYYY-MM-DD-brief-<period-label>.md`
**Period label:** `<start>-to-<end>` in `YYYY-MM-DD` form. Never overwrite an existing brief. Save a new version with `-v2`, `-v3`.

**Structure:** use these headings in this order. Do not delete or reorder sections. If a section is empty, write `None`.

```markdown
Station: next-cycle-brief
Date: YYYY-MM-DD
Context used: [each file read, named as in section 1]
Insights used: [insight IDs, file name, approval date]
Performance report used: [file name, period covered]
Status: DRAFT – awaiting review

# Client brief: [client name from marketing-plan.md]

**Client:** [name]
**Brief title:** [cycle name, period label]
**Date:** YYYY-MM-DD · **Approved by client on:** [date or TBC]

## Objective
[One measurable sentence with a deadline inside the period.]

## Goals and measures
| Goal | Metric | Target | How we'll measure it |
|---|---|---|---|

**Target method:** [formula, period days, 84-day base, rounding rule]

## Audience
**Personas:** [names from personas.md]
**Priority:** [one persona]

## Message
**Pillar(s):** [from positioning.md]
**Core message for this cycle:** [one sentence from positioning.md or an approved insight]

## Deliverables
| Station | Deliverable | Quantity | Due |
|---|---|---|---|

## Budget and tools
**Monthly marketing budget:** [amount] ([confirmed by client / TBC])
**Paid tools:** [from playbook/tool-register.md]
**Paid ads:** [amount, or none]

## Timeline
**Period:** [start] to [end] ([n] days)
**Review dates:** [dates]
**Approval points:** [list]
**Launch date:** [date or TBC]

## What we're testing
[One test, its insight ID, success measure and review date.]

## Constraints
[Each item sourced to a context file or client input.]

## Evidence
| Change in this brief | Insight ID | Evidence row (performance report) | Why |
|---|---|---|---|
```

---

## 4. Guardrail check

- [ ] Every insight used has status `APPROVED`, and its evidence row exists in the performance report.
- [ ] Targets use the KPI names in `context/marketing-plan.md` and the stated pro-rating formula. No new targets without a source.
- [ ] No budget, price, service or area claim that is absent from `context/offer.md`, `context/marketing-plan.md` or client input. Gaps are marked `[NEEDS CLIENT INPUT: ...]`.
- [ ] No outcome guarantees, and no fear, urgency or guilt framing (`context/voice-and-tone.md`, `context/guardrails.md`).
- [ ] No client, family member or partner named. No testimonial or photo added without written permission.
- [ ] No partner organization named as referring or endorsing the client without written agreement.
- [ ] Every deliverable traces to an insight ID or a stated client priority.
- [ ] Follows `context/guardrails.md`.

---

## 5. Review checklist (human)

- [ ] Is every change in the brief traceable to an approved insight?
- [ ] Do the period dates match what the client confirmed?
- [ ] Is the objective measurable, with a deadline inside the period?
- [ ] Are targets pro-rated with the stated formula and consistent with `context/marketing-plan.md`?
- [ ] Is the budget confirmed, or clearly marked TBC?
- [ ] Is there one test, with a review date?
- [ ] Would the client recognize their priorities in the brief?

When approved, change the status line to `APPROVED – <date>`, suggest a commit message, and propose any context changes to the team context repo. Do not edit `/context` or other station files directly.

---

## 6. Tool slot

**Job:** planning.
**Current tool:** see `playbook/tool-register.md` → next-cycle-brief.
**Default:** Claude, using `templates/client-brief.md` as the only planning template.
