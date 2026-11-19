---
name: insights-summary
description: Factory station 11 (measure line). Reads the approved performance report, the approved marketing plan and client feedback, then turns the results into rated learnings (what worked, what didn't, and why), exact proposed edits to /context files and station SKILL.md files, and a hand-off block for the next-cycle-brief station. It only proposes changes; a human approves them. Use after a performance report is approved, when asked what we learned from a campaign or period, how to improve the factory, what to keep, change, stop or test next, or how to update the context pack after results or client feedback.
---

# Station: Insights summary

**Line:** Measure · **Needs:** performance-report, marketing-plan · **Feeds:** next-cycle-brief and the `/context` pack

**Job:** Close the loop. Turn results into changes that make the next cycle better.

This station judges evidence and proposes changes. It never edits `/context` or a station file itself, and it never adds new facts about the client.

---

## 1. Inputs

**Required**
- The approved performance report: `outputs/<client-slug>/reports/YYYY-MM-DD-report-<period>.md`, with status `APPROVED – <date>`
- `context/marketing-plan.md`: the objective, KPI names and targets, content pillar names, audiences and campaign IDs (C1, C2…) from its hand-off block
- `context/personas.md`
- `context/positioning.md`
- `context/voice-and-tone.md`
- `context/offer.md`
- `context/brand-book.md`
- `context/guardrails.md`

**Optional (use if present)**
- Client feedback for the period: meeting notes, emails or comments (paraphrase, don't paste)
- Our own review notes and Decision Trail entries from the period
- The outputs the report covers, in `outputs/<client-slug>/`, to link a result to a specific asset
- The last insights summary, `outputs/<client-slug>/reports/YYYY-MM-DD-insights-<period>.md`, to see whether its changes were accepted and whether they held up
- The station SKILL.md files the evidence points to, in `skills/<line>/<station>/SKILL.md`

**Stop conditions**
- If the performance report is not marked `APPROVED`, stop and tell the user to finish the `performance-report` station first.
- If `context/marketing-plan.md` is missing, stop and recommend running the `marketing-plan` station first.
- If any context file still contains `[PLACEHOLDER` text, name the file, continue, and do not propose changes to that file.

---

## 2. Steps

1. **Confirm the inputs.** State the client slug, the period label (copied exactly from the performance report's file name), the report file used, and which optional inputs you have. Ask the user to add any client feedback before you continue.
2. **Build the KPI scorecard.** List every KPI from the hand-off block in `context/marketing-plan.md`, in the same order and with the same names. Copy the target from the plan and the actual from the report. Set the status to one of: `Ahead`, `On track`, `Behind`, `Too early`, `No data`. Do not create or estimate numbers. Do every calculation in code or a spreadsheet and show it under the scorecard.
   **Pace rule (mid-point reviews).** When the report covers part of the 12-week cycle, judge each KPI against its pace, not its full target:
   - **Pace** = 12-week target × weeks covered by the report ÷ 12. For a range target (e.g. 8 to 10), work out the pace for both ends. For counts, round each end to the nearest whole number.
   - **Ahead:** the actual is above the top of the pace. **On track:** the actual is within the pace (equal to it, or inside the range). **Behind:** the actual is below the bottom of the pace.
   - **Too early:** use instead of `Behind` when `context/marketing-plan.md` says the KPI comes mostly later in the cycle (for example, it names a later campaign or phase as the one that drives it). Quote or cite the plan section in the Source column.
   - **Limits (cost or ceiling KPIs):** don't pace a limit such as a maximum cost. Compare the actual with the limit directly, or use `No data` if it can't be worked out yet.
   - **Final review:** at the week 12 review, compare actuals with the full target, and don't use `Too early`.
3. **Log the observations.** Go through the report's wins and misses, the client feedback and the review notes. Write each as one numbered line (O1, O2…) with its source: report section, feedback date or note date. An observation says what happened, not why.
4. **Group the observations into learnings.** Write 3 to 7 learnings (L1, L2…). Use this sentence pattern: *When we [did what] for [persona / pillar / channel / campaign], [result], likely because [reason].* List the observation IDs each learning rests on. Mark the reason as `(hypothesis)` unless the evidence itself shows the cause.
5. **Classify each learning.** Set its result to `Worked`, `Didn't work` or `Unclear`.
6. **Rate the evidence.** Give each learning one strength rating, using these rules:
   - **Strong:** the same pattern across two or more assets or two or more periods, or a KPI marked `Ahead` or `Behind` in the scorecard, with no small-sample flag in the report. A `Too early` KPI is not evidence that something failed.
   - **Moderate:** one clear result with no small-sample flag, or the same point made by the client and supported by the data.
   - **Weak:** a single post or one-off result, anything the report flags as a small sample, or client feedback with no supporting data.
7. **Tag each learning.** Name the persona, pillar, channel, campaign ID and format it concerns, using the exact names from `context/marketing-plan.md` and `context/personas.md`. Write `—` where a tag doesn't apply.
8. **Decide the action.** For each learning, choose one: `Keep`, `Change`, `Stop` or `Test`. A Weak learning can only be `Test`.
9. **Draft context changes.** For each Strong or Moderate learning that should change a context file, write one proposed change (CC1, CC2…): file, section heading, change type (`Add`, `Replace`, `Remove`), the current text quoted word for word from the file (or `—` for an Add), the new text, and the learning ID. New wording follows `context/voice-and-tone.md`. If a learning suggests a client fact has changed (a service, price, area, capacity, credential), don't write the fact; write `[NEEDS CLIENT INPUT: ...]` and add it to the client questions.
10. **Draft station changes.** For each learning that points to how a station works rather than what we know about the client, write one proposed change (SC1, SC2…): file path, section number, current text quoted word for word, new text, and the learning ID. A station change can instead come from a **run note**: a problem you hit while running this or another station (for example, an input that was missing, a rule you had to guess, or a file name that doesn't match). Write the run note in one sentence instead of the learning ID. A run note can only change files in `/skills`, `/templates` or `/playbook`, never `/context`.
11. **Review the last cycle.** If a previous insights summary exists, list each change it proposed with its status (`Accepted`, `Rejected`, `Pending`, `Unknown`) and whether this period's evidence `Supports`, `Contradicts` or is `Silent` on it. If there is no previous summary, write `First cycle: no previous insights.`
12. **Write the tests.** For every `Test` learning, write one test (T1, T2…): hypothesis, what changes and what stays the same, the KPI it should move, and the station that produces it.
13. **Write the hand-off block** (output template, part B).
14. **Run the guardrail check** (section 4), fix what fails, then present the output with the review checklist (section 5).
15. **Save** to `outputs/<client-slug>/reports/YYYY-MM-DD-insights-<period>.md`. Never overwrite; a revision gets `-v2`.

---

## 3. Output template

Use every heading below, in this order, even when a section is empty. Write `None this period.` in an empty section. Order learnings by strength (Strong, then Moderate, then Weak); within the same strength, follow the order of the KPIs in the plan.

Save as `outputs/<client-slug>/reports/YYYY-MM-DD-insights-<period>.md`

**A. Insights summary**

```markdown
Station: insights-summary
Date: YYYY-MM-DD
Context used: [list files]
Source report: outputs/<client-slug>/reports/YYYY-MM-DD-report-<period>.md
Status: DRAFT – awaiting review
AI-drafted for review

# Insights summary: [Client], [period]

## Summary
[3 sentences: the strongest learning, the biggest miss, the one change we recommend most]

## KPI scorecard
Pace calculation: [one line per KPI, or "Final review: full targets used"]

| KPI | Target | Actual | Pace (weeks covered: N) | Status (Ahead / On track / Behind / Too early / No data) | Source |
|---|---|---|---|---|---|

## Observations
| ID | What happened | Source |
|---|---|---|
| O1 | | |

## Learnings
| ID | Learning | Result (Worked / Didn't work / Unclear) | Evidence (observation IDs) | Strength (Strong / Moderate / Weak) | Persona | Pillar | Channel | Campaign | Format | Action (Keep / Change / Stop / Test) |
|---|---|---|---|---|---|---|---|---|---|---|
| L1 | When we ..., ..., likely because ... | | | | | | | | | |

## Proposed context changes
Proposals only. Changes go through the team context repo (see context/README.md).

### CC1
- **File:** context/<file>.md
- **Section:**
- **Change type:** Add / Replace / Remove
- **Current text:** "<quoted word for word, or — for Add>"
- **New text:** "<proposed wording>"
- **From learning:** L#

## Proposed station changes
### SC1
- **File:** skills/<line>/<station>/SKILL.md
- **Section:** <number and heading>
- **Current text:** "<quoted word for word>"
- **New text:** "<proposed wording>"
- **From:** Learning L# / Run note: <one sentence on what happened in the run>

## Last cycle's changes
| Change ID (last cycle) | What it changed | Status (Accepted / Rejected / Pending / Unknown) | This period's evidence (Supports / Contradicts / Silent) |
|---|---|---|---|

## Tests for next cycle
| ID | Hypothesis | What changes / what stays | KPI it should move | Station |
|---|---|---|---|---|

## Questions for the client
1.
```

**B. Insights to next-cycle hand-off** (the next-cycle-brief station reads this block)

```markdown
## Hand-off: insights to next-cycle brief
Client:
Period covered:
Source report:
Next period: [from context/marketing-plan.md, or TBC]

### KPI status
| KPI | Target | Actual | Pace | Status |
|---|---|---|---|---|

### Keep
| Learning ID | What to keep | Persona | Pillar | Channel |
|---|---|---|---|---|

### Change
| Learning ID | What to change | Persona | Pillar | Channel |
|---|---|---|---|---|

### Stop
| Learning ID | What to stop | Persona | Pillar | Channel |
|---|---|---|---|---|

### Test next
| Test ID | Hypothesis | KPI | Station |
|---|---|---|---|

### Context and station changes awaiting approval
| ID | File | Status (Proposed / Approved / Rejected) |
|---|---|---|

### Open questions for the client
1.
```

Reuse the exact KPI names, pillar names, persona names and campaign IDs from `context/marketing-plan.md` and `context/personas.md`. The next-cycle brief and content calendar match on them.

---

## 4. Guardrail check

Before showing the output, confirm each item and fix anything that fails:

- [ ] **No new numbers.** Every figure comes from the approved performance report or `context/marketing-plan.md`. Any calculation is shown.
- [ ] **Evidence before change.** No context or station change is based on a Weak learning. One-off results go to Tests, not to `/context`. Station changes from a run note touch only `/skills`, `/templates` or `/playbook`.
- [ ] **Pace is applied the same way.** Mid-point statuses follow the pace rule in step 2, and every `Too early` cites the plan.
- [ ] **Causes are labelled.** Any reason the data doesn't show is marked `(hypothesis)`.
- [ ] **No invented client facts.** Proposed changes don't add or alter services, prices, areas, credentials, testimonials or results. Gaps are marked `[NEEDS CLIENT INPUT: ...]`.
- [ ] **Current text is exact.** Every "current text" is quoted word for word from the file it names.
- [ ] **Proposals only.** No file in `/context` or `/skills` was edited. Context changes go through the team context repo.
- [ ] **Privacy.** Client feedback is paraphrased. No customer, client or family names, contact details, identifiable stories or individual-level analytics data.
- [ ] **Audience sensitivity.** New wording adds no fear, urgency or loss framing unless `context/brand-book.md` allows it, and describes personas without stereotypes.
- [ ] **Voice matches** `context/voice-and-tone.md` in any proposed customer-facing wording.
- [ ] **AI disclosure.** The output is labelled "AI-drafted for review" until a human approves it.
- [ ] **Follows `context/guardrails.md`.**

---

## 5. Review checklist (human)

- [ ] Is every learning backed by evidence we would be comfortable showing the client, and is each strength rating fair?
- [ ] Have we mistaken a one-off result for a pattern anywhere?
- [ ] Do the "likely because" reasons match what we actually saw, or are some of them guesses?
- [ ] Is the client's feedback represented fairly, including what they didn't like?
- [ ] Would each proposed context change still be right in the next cycle, and is it worth asking the team to change shared context?
- [ ] Could we write the next brief from the hand-off block alone, without reopening the report?

When approved: change status to `APPROVED – <date>`, remove "AI-drafted for review", and commit. Propose the approved context changes to your team context repo. Commit approved station changes in this repo. Record what you changed and why in a Decision Trail entry.

---

## 6. Tool slot

**Job:** synthesis.
**Current tool:** see `playbook/tool-register.md` → insights-summary. (Fill in that row; it is empty in the template.)
**Default:** Claude (this skill), with a spreadsheet or code for any calculation.
**Optional add-on:** a second AI model, given the same report, to challenge the learnings and strength ratings before human review.
