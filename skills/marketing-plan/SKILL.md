name: marketing-plan
description: Checks a client's 12-week marketing plan against the factory's plan structure, flags gaps, unsourced claims and conflicts with the context pack, then writes the plan-to-calendar hand-off block that the calendar import and the content-calendar station use. Can also draft a new plan from the context pack. Use when a team uploads or updates a marketing plan, when asked to check, review or tidy a plan, when the content calendar needs campaigns, KPIs or budget from the plan, or when asked to draft a plan for a new client or the next 12-week cycle.
---

# Marketing plan station

Sits on the strategy line before content-calendar. When a team brings in an existing plan, run this station first: the calendar import needs its campaign IDs. It uses personas.md and positioning.md when they exist, but doesn't need them. Its main job is the hand-off: turning a plan into a short, structured block that the rest of the factory can use.

**Two modes**
- **Check mode** (default): a plan already exists. Read it, map it to the 15-part structure below, flag what's missing or weak, and produce the hand-off block. Do not rewrite the team's strategy.
- **Draft mode**: no plan exists yet (new client or next cycle). Draft one from the context pack in the same structure, mark every assumption [TBC], and stop for human review before the hand-off is used.

If it isn't clear which mode is needed, ask once.

## 1. Inputs

**Required**
- The plan: an uploaded plan document (Word, PDF or markdown) or `marketing-plan.md`
- `offer.md`: services, prices, service area, capacity
- `guardrails.md`: claims, privacy and sensitivity rules

**Use if available**
- `brand-book.md`, `voice-and-tone.md`
- `personas.md`, `positioning.md`
- Insights from the last cycle (`insights-summary` output) in draft mode

If `offer.md` or `guardrails.md` is missing, say so and continue, but flag every client fact as unverified.

## 2. Steps

1. **Confirm the mode** and the client name.
2. **Map the plan to the structure.** Find each part, even if the team used different headings:
   0 Plan information · 1 Executive summary · 2 Situation analysis (client snapshot, SWOT, competitors, market data, insights) · 3 Priority audiences · 4 Positioning and messaging (statement, differentiators, content pillars, words to use and avoid) · 5 Objective and KPIs (SMART objective, funnel assumptions, KPI table) · 6 Strategies (S1 to S3) · 7 Tactics and media mix · 8 Campaign roadmap (campaign IDs C1, C2...) · 9 Asset mix · 10 Budget · 11 Measurement and review schedule · 12 Risks · 13 Assumptions to confirm · 14 References
3. **Check completeness.** For each part, mark Present, Partial or Missing.
4. **Check the logic.**
   - Does the objective have a number, a definition and a deadline?
   - Do the funnel numbers add up (inquiries to consultations to clients)?
   - Does every KPI link to the objective? Flag vanity metrics.
   - Does every tactic link to a strategy, and every campaign to a phase (Introduce, Build trust, Invite action)?
   - Does the asset mix total match the campaign roadmap?
   - Does the budget add up by month, and stay within the stated monthly budget?
5. **Check facts against the context pack.** Compare every price, service, time, area and capacity claim with `offer.md`. List each conflict side by side. Never pick a winner; the client confirms.
6. **Check sources.** Every statistic needs a source and a date checked. Flag any figure with no source as UNSOURCED. Flag figures that look like AI estimates (round numbers, no date, no named source).
7. **Assign IDs** if the plan has none: campaigns C1, C2...; strategies S1, S2, S3. Tell the team which IDs you assigned.
8. **Write the hand-off block** (output template, part B).
9. **Draft mode only:** write the full plan in the 15-part structure, then do steps 3 to 8 on your own draft.
10. **Save.** Check report and hand-off to `outputs/<client-slug>/strategy/marketing-plan/YYYY-MM-DD-marketing-plan-check.md`. Once a human approves the hand-off, save the clean plan with the hand-off at the end in the same folder as `YYYY-MM-DD-marketing-plan-vN.md`.

## 3. Output template

**A. Check report**

```
# Marketing plan check: [Client], [date]
Mode: Check / Draft

## Summary
[3 sentences: overall readiness, the biggest gap, the biggest strength]

## Completeness
| Part | Status (Present / Partial / Missing) | Note |
|---|---|---|
| 0 Plan information | | |
... one row per part 0 to 14 ...

## Logic issues
1. [issue] → [suggested fix]

## Conflicts with the context pack
| Fact | In the plan | In offer.md | Action |
|---|---|---|---|

## Unsourced or unverified claims
| Claim | Where | Action |
|---|---|---|

## Questions for the client ([TBC] list)
1.
```

**B. Plan-to-calendar hand-off** (the calendar import uses its campaign IDs and names; the content-calendar station reads the whole block)

```
## Hand-off: plan to calendar
Client:
Planning period: Week 1 starts [date or TBC], 12 weeks
Monthly budget (CAD): [amount] (Confirmed / TBC)

### Objective
[SMART objective in one sentence]

### KPIs
| KPI | 12-week target | Measurement tool | Owner | Review |
|---|---|---|---|---|

### Content pillars
| Pillar name | What it says |
|---|---|

### Audiences
| Audience | Primary / Secondary |
|---|---|

### Campaigns
| ID | Name | Weeks | Phase | Audience | Key message | Lead CTA | Asset mix |
|---|---|---|---|---|---|---|---|

### Asset mix totals
| Format | Count | Default specs |
|---|---|---|
Total assets:

### Budget by campaign and month (CAD)
| Line | Month 1 | Month 2 | Month 3 | Total |
|---|---|---|---|---|

### Spending controls
-

### Assumptions to confirm (TBC)
1.
```

Use the exact pillar names, KPI names and campaign IDs from the plan. The content calendar reuses them.

## 4. Guardrail check

Before you hand anything back:
- Follows `guardrails.md`.
- No invented facts. Every client fact comes from the plan or the context pack, and conflicts are listed, not resolved.
- No statistic without a source; unsourced figures are flagged, not repeated as fact.
- No promises of outcomes the client can't guarantee (results, timelines, savings).
- Audience sensitivity: no fear, urgency or loss framing unless the brand book allows it.
- Privacy: no client, customer or family names, addresses or stories without written consent.
- AI disclosure: in draft mode, label the plan "AI-drafted for review" until a human approves it.

## 5. Review checklist (human)

Approve the hand-off only when you can answer yes to each:
- [ ] Does the hand-off match what our team actually decided, not what the AI suggested?
- [ ] Are the KPI targets realistic for this budget and the client's capacity?
- [ ] Does every campaign have a clear audience, message and call to action?
- [ ] Does the asset total match what we can really produce in 12 weeks?
- [ ] Are all conflicts with `offer.md` either fixed or on the client question list?
- [ ] Would we be comfortable showing this to the client as is?

Record what you changed and why in a Decision Trail entry.

## 6. Tool slot

**Job:** plan checking and plan-to-calendar hand-off (strategy).
**Current tool:** Claude (this skill). Note the model you used in `playbook/tool-register.md`.
**Possible upgrades:** the Marketing plugin's campaign-planning skill for draft mode; a live-research tool for checking market data.

## Breaking this station up later (optional)

Keep it as one station to start. Split a part out into its own station when it needs to be rerun on its own schedule:

| Possible station | Covers parts | Split it when |
|---|---|---|
| situation-analysis | 2 | You add market research or competitor intelligence stations |
| objectives-kpis | 5 | Targets are reset each cycle from performance reports |
| campaign-architecture | 8, 9 | You plan more than one campaign cycle a year |
| media-mix-budget | 7, 10 | The budget changes monthly or a paid test is running |
| risk-register | 12, 13 | The client wants a standing risk review |

When you split a part out, this station keeps the hand-off block and reads the new station's output instead of doing that part itself.
