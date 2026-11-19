---
name: performance-report
description: Factory station 10 (measure line). Turns client campaign data, supplied as CSV exports, into a plain-language performance report against the targets in the marketing plan. Covers results, the three numbers that matter, wins, misses, data notes, next-cycle changes and context conflicts. Use when asked for a performance report, campaign results, a review-week report (weeks 4, 8 or 12), a monthly recap or analysis of marketing data. Accepts CSV only, for any reporting period.
---

# Station: Performance report

**Line:** Measure · **Needs:** marketing-plan hand-off, content calendar, campaign data (CSV) · **Feeds:** insights-summary

**Job:** Show the client what happened in a period, measured against the targets in the marketing plan, and say what to change next.

---

## 1. Inputs

**Required**
- `context/marketing-plan.md`: KPI table, 12-week targets, monthly budget, spending controls, review weeks (4, 8 and 12), and the hand-off block. Targets and KPI names come only from this file.
- `context/offer.md`: prices, services and service area. Used to check price and service statements in the data.
- `context/guardrails.md`: rules on claims, privacy, AI disclosure and audience sensitivity.
- `context/content-calendar.csv`: asset IDs, campaign IDs, and the measurement method for each asset.
- `templates/reporting-template.md`: the base structure. This station extends it; section order is fixed in section 3.
- **Campaign data:** one or more CSV files exported for the period. Required columns: `metric`, `date`, `value`, `source`. Optional columns: `campaign_id`, `asset_id`, `channel`. Each row is one metric, on one date, from one source.

**Use if available**
- `context/voice-and-tone.md`: every word in the report is client-facing.
- `context/brand-book.md`: checking names, claims and tone.
- `context/positioning.md` and `context/personas.md`: explaining results by audience only. They never supply results.
- The most recent `performance-report` output in `outputs/<client-slug>/reports/`: for "since last report" comparisons only.

**Not accepted:** XLSX files, pasted figures and screenshots. If the person supplies one of these, ask for CSV exports before continuing.

**Stop conditions:** If a required file is missing, or a context file contains `[PLACEHOLDER` or `[NEEDS CLIENT INPUT` text that affects a target or a claim, stop and list what is missing. Missing data is reported as `Not measured`. It is never estimated.

---

## 2. Steps

1. **Set the period and report type.** Use the period label rules in section 3. A period that ends on plan week 4, 8 or 12 is a review report and covers plan weeks 1 to 4, 1 to 8 or 1 to 12. Any other period is an ad hoc report. If the period is unclear, ask one question before continuing.

2. **Check the CSV files.** Confirm the required columns are present, dates fall inside the period, values are numeric, currency is CAD, and no rows are duplicated (same metric, date, source, campaign_id and asset_id). Record every problem in section 7.4. Never fix a value silently.

3. **Remove personal data.** Drop any column or free-text field that contains names, email addresses, phone numbers, street addresses or customer notes. Report counts and totals only. Record the removed columns in section 7.4.

4. **Map metrics to KPI rows.** Match each metric to a row in the KPI table of `context/marketing-plan.md`. Metrics with no matching row go under "Other measures (no target)" in section 2. Do not create targets for them.

5. **Calculate every figure in code.** Do not estimate. For each figure, record the formula, numerator, denominator and result in section 7.2. Rounding: counts as whole numbers, rates to one decimal place, dollars as whole CAD.

6. **Set the status for each KPI row.**
   - *Pro-rated target* = plan target × (days in period ÷ 84). For review weeks, days in period are counted from the plan's Week 1 start date.
   - If the plan's Week 1 date is still `TBC` in `context/marketing-plan.md`, do not pro-rate. Show actuals only and set status to `No target yet`.
   - *On track*: actual is at or above the pro-rated target.
   - *Behind*: actual is below the pro-rated target.
   - *Not measured*: no data row exists for the KPI.
   - *Cost metrics* (such as cost per paid client) are not pro-rated. Compare with the plan's stated target. On track if at or below the target. If there are zero paid clients and spend is above zero, status is `Behind (no paid clients yet)`.
   - Add `(small sample)` to any rate built from fewer than 10 underlying counts.
   - Write the status rules used in section 7.3.

7. **Choose the three numbers that matter.** Rank KPI rows that have data by the size of their gap from the pro-rated target, as a percentage of that target, in either direction. Take the top three. Ties go to the row with more direct business impact, in this order: new paid clients, complimentary consultations, qualified inquiries, then the remaining rows. Write one sentence per number on why it matters. If fewer than three KPI rows have data, show the rows that exist and say so.

8. **Write wins and misses.** Each point must cite a row in section 2. A possible reason must be marked "We think" and name the evidence used. Do not state a cause as proven from one period.

9. **Propose changes for next cycle.** Each change needs an action, the evidence row it comes from, an owner and a check date (a review week). Changes are proposals. They never edit `/context`.

10. **Flag context conflicts.** Compare every price, service, time, service-area and capacity statement found in the data (for example ad copy or page text supplied with the exports) against `context/offer.md` and `context/brand-book.md`. List each conflict side by side in section 8. Do not choose which version is right.

11. **Run the guardrail check (section 4)**, fix any failures, then show the report with the review checklist (section 5).

---

## 3. Output template

**File name:** `outputs/<client-slug>/reports/YYYY-MM-DD-performance-report-<period-label>.md`

**Period label:**
- Review reports: `review-wk4`, `review-wk8` or `review-wk12`
- Ad hoc reports: `adhoc-YYYY-MM-DD-to-YYYY-MM-DD`

Never overwrite an existing report. Save a new version with `-v2`, `-v3` and so on.

**Structure:** Every report uses these headings, in this order, with no additions before section 1. Use the status values exactly as written in step 6.

```markdown
Station: performance-report
Date: YYYY-MM-DD
Context used: [each context file from section 1 that was read]
Data sources: [one line per CSV file: file name, row count, date range]
Status: DRAFT – awaiting review

# Performance report: [client name from marketing-plan.md], [period label]

**Period:** YYYY-MM-DD to YYYY-MM-DD (plan weeks X to Y of 12)
**Report type:** Review week 4 / Review week 8 / Review week 12 / Ad hoc

## 1. The headline
[Two sentences: what happened, and what it means for the business.]

## 2. Results against goals

| KPI (plan row) | 12-week target | Pro-rated target | Actual | Status | Calc ref |
|---|---|---|---|---|---|
| [row name from plan] | [target] | [value or n/a] | [value or Not measured] | [status] | [7.2 line number] |

### Other measures (no target)

| Measure | Actual | Source | Calc ref |
|---|---|---|---|

## 3. The three numbers that matter

1. **[KPI name]:** [actual] against [pro-rated target], status [status]. [One sentence on why it matters.]
2. **[KPI name]:** ...
3. **[KPI name]:** ...

## 4. What worked
- [Result with number from section 2, then the likely reason marked "We think", with the evidence used.]

## 5. What did not, and why we think so
- [Result with number from section 2, then the likely reason marked "We think", with the evidence used.]

## 6. What we will change next cycle

| # | Change | Evidence (section 2 row) | Owner | Check at |
|---|---|---|---|---|

## 7. Data notes

### 7.1 Sources
[File name, date range, row count, and the export tool or platform named in the file if known.]

### 7.2 Calculations
[One line per figure: KPI, formula, numerator, denominator, result.]

### 7.3 Status rules applied
[Pro-rating method and the plan Week 1 date used, or "No target yet" reason. Small-sample threshold. Any exceptions.]

### 7.4 Excluded or changed rows and removed columns
[Rows dropped and why. Columns removed for personal data. Duplicates found. Values questioned but not changed.]

### 7.5 Small samples and missing data
[List each rate with fewer than 10 counts, and each KPI with no data.]

## 8. Context flags (for the context owner; no edits made)

| Item | Found in data or copy | Context file says | Action needed |
|---|---|---|---|

## 9. Questions for the client
1. [Question]
```

---

## 4. Guardrail check

Before showing any report, confirm each item and fix anything that fails:

- [ ] Every number traces to a row in a file supplied for this period. Nothing is estimated or taken from memory.
- [ ] Every KPI row with a target appears in section 2, including misses.
- [ ] No personal data about individual customers, clients, partners or staff. Counts and totals only.
- [ ] Rates built from fewer than 10 underlying counts are marked `(small sample)`.
- [ ] No cause is stated as proven from one period. Every reason is marked "We think."
- [ ] No outcome guarantees, projections presented as results, or superlatives ("best," "only," "#1").
- [ ] Price, service and area statements match `context/offer.md`, or appear in section 8.
- [ ] No partner organization is named as referring or endorsing Rya unless it has agreed in writing.
- [ ] Voice follows `context/voice-and-tone.md`: plain language, grade 7 to 8, Canadian spelling, no emoji, "we" for Rya and "you" for the reader.
- [ ] Follows `context/guardrails.md`.

---

## 5. Review checklist (human)

- [ ] Does every KPI row in the plan have either a result or a stated reason it is `Not measured`?
- [ ] Would the client understand the headline without reading the rest?
- [ ] Do the three numbers follow the selection rule in step 7, and do the reasons hold?
- [ ] Are the data notes enough to re-check any figure from its formula?
- [ ] Is each change specific, with an owner and a check date?
- [ ] Are the context flags in section 8 listed for the context owner, with nothing in `/context` edited?

When approved, change the status line to `APPROVED – <date>`, suggest a commit message, and propose any section 8 fixes to the team context repo. Do not edit `/context` directly.

---

## 6. Tool slot

**Job:** data analysis and reporting.
**Current tool:** see `playbook/tool-register.md` → Performance report.
**Default:** Claude reads the CSV files and calculates in code, showing each formula in section 7.2. No spreadsheet is created unless the person asks for one.
**Limit:** this station does not connect to live advertising or analytics accounts. Data arrives only as CSV exports.
