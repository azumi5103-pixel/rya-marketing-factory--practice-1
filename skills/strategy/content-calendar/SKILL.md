---
name: content-calendar
description: Factory station 3 (strategy line). Builds the 12-week content calendar from the marketing-plan hand-off block and the context pack. Every asset gets a week, day, campaign, content pillar, audience, funnel phase, channel, format, call to action, owner role and measurement method, saved as a review-ready markdown calendar plus a CSV in the factory's 21-column layout. Also checks an existing calendar against the hand-off and guardrails (Check mode). Use when asked for a content calendar, content plan, posting schedule or asset list, when a marketing plan needs to become dated content slots, or before the social, blog-seo-geo, email, ad-creative or video-short-form stations run from a calendar.
---

# Station: Content calendar

**Line:** Strategy · **Needs:** marketing-plan (its hand-off block), research-personas, positioning-messaging · **Feeds:** social, blog-seo-geo, email, ad-creative, video-short-form, performance-report

**Job:** Turn the approved plan into a dated, owned, checkable list of assets that every content station can run from.

**Two modes**
- **Build mode** (default): no calendar exists for this cycle. Create the full 12-week calendar from the hand-off block.
- **Check mode**: a calendar already exists. Compare it with the hand-off block and the context pack, flag gaps and conflicts, and produce a check report. Do not rewrite the team's calendar.

If it isn't clear which mode is needed, ask once.

**Boundaries.** This station plans slots, not copy. It writes a one-line key message and a call to action per asset. Captions, scripts, emails and ad copy belong to the content and creative stations. Every client fact (campaign names, pillar names, channels, publishing days, prices, wording rules) comes from the hand-off block or the context files at run time. This file contains none.

---

## 1. Inputs

**Required**
- `context/marketing-plan.md`, including its hand-off block (objective, KPIs, content pillars, audiences, campaigns with IDs, asset mix totals, budget, spending controls, assumptions to confirm)
- `context/brand-book.md`
- `context/offer.md`
- `context/personas.md` (approved, not a placeholder)
- `context/positioning.md`
- `context/voice-and-tone.md`
- `context/guardrails.md`

**Required for Check mode**
- The existing calendar: `context/content-calendar.csv` or the file the user names

**Optional (use if present)**
- Output from `insights-summary` or `next-cycle-brief` for a later cycle
- `templates/client-brief.md` or `templates/client-intake.md` for this client
- Dated events or key dates the user wants the calendar to respect

**Ask the user before building** (one message, only what the files don't already answer)
1. Week 1 start date, or "not confirmed".
2. Publishing days per week, if the hand-off doesn't state them.
3. The channels in use, if the hand-off doesn't state them.
4. Who owns each format (role names are enough) and how many assets a week they can produce.
5. How much approval time the client has each week, and which assets, if any, the client records or appears in.
6. Any dates to avoid or plan around.

**Stop conditions**
- If `context/marketing-plan.md` has no hand-off block, stop and recommend running `marketing-plan` first.
- If `personas.md` or `positioning.md` is a placeholder, stop and recommend `research-personas` or `positioning-messaging`.
- If the hand-off has no campaign table or no asset mix totals, stop and ask for them. Do not invent a split.
- If any other file still contains `[PLACEHOLDER`, tell the user which file and continue, marking every fact that depends on it as unverified.

---

## 2. Steps

### Build mode

1. **Confirm the mode and the client.** Say in one line which mode you are running.
2. **Check the inputs** against section 1. Report placeholders and missing files before producing anything.
3. **Get the run settings** from the user (section 1, "Ask the user before building"). Record each answer and where it came from. Anything unanswered is `[NEEDS CLIENT INPUT: ...]`, never a guess.
4. **Lock the plan's vocabulary.** Copy campaign IDs, campaign names, campaign weeks, phases, pillar names, audience names, KPI names and the asset mix exactly from the hand-off. Never rename or re-ID. If a name looks wrong, list it as a question for the human.
5. **Set the grid.** Weeks run from 1 to 12. Use the publishing days from step 3, in calendar order, as the day slots in each week.
6. **Allocate assets to campaigns.** The number of assets per campaign and per format comes from the hand-off's campaign table and asset mix. Totals must equal the hand-off total.
7. **Deal assets to weeks.** For each campaign, list its assets in the order of the formats in the hand-off's asset mix table. Deal them one at a time to the campaign's weeks (first week, second week, and so on, then back to the first). If the number of assets doesn't divide evenly, the extra assets land in the earliest weeks of the campaign. Paid assets are never placed before the paid start week in the hand-off's spending controls; move them to the earliest allowed week of their campaign.
8. **Assign days.** Within each week, order the assets by the format order in the hand-off's asset mix table, then assign them to the publishing days in order. No two assets share a channel and day. If a week has more assets than days, say so in the capacity check and do not drop an asset.
9. **Assign pillars.** Rotate through the hand-off's pillar list in its listed order across each campaign's assets, skipping any pillar that would repeat the pillar of the previous asset in the same campaign. If the hand-off ties pillars to campaigns, use that mapping instead and rotate within it. Report pillar counts in the reconciliation.
10. **Tag audience and phase.** Audience comes from the campaign's audience in the hand-off. If the campaign lists more than one, tag each asset with one or both. Never tag an audience the campaign doesn't list. Phase comes from the campaign. Where a campaign spans two phases, tag by week and mark `[TBC]`.
11. **Set channel and Paid / Earned / Owned.** Use only channels named in the hand-off's media mix or in the user's answers. Paid, earned or owned comes from the hand-off.
12. **Write the key message and call to action.** One line for the key message, in the client's voice, taken from the campaign's key message and persona angle. One call to action per asset, taken from the campaign's lead CTA or the call-to-action section of `offer.md`. Use soft actions (save, share, download) in early phases and the lead CTA in the final phase. Match the wording rules in `guardrails.md` and `voice-and-tone.md`. A key message or CTA marked `[TBC]` in the hand-off stays `[TBC]`.
13. **Fill the production fields.** Creative assets required and specs come from the hand-off's default specs. If they are missing, write `[NEEDS CLIENT INPUT: specs]`. Owner is a role from step 3, written `TBD: <role>` unless the user named a person. Status for every new row is `Not started`, and the Notes column carries `Approval: Not submitted`.
14. **Fill measurement and cost.** KPI or measurement method comes only from KPI names in the hand-off. Estimated cost comes only from the hand-off's budget lines; leave it blank if none applies. Never estimate.
15. **Reconcile with the hand-off.** Compare totals by format, campaign, week, pillar, audience, channel and paid share with the hand-off. Fix every mismatch. Do not just report it.
16. **Check capacity.** Count assets per week and per owner role against the capacity the user gave. Flag any week or role over that number, and any asset the client has to record or approve beyond the approval time given.
17. **Set dates.** If a Week 1 start date is confirmed, each date is the start date plus (week − 1) × 7 days plus the day's offset. Check the dates against the key dates the user gave, and say if Week 1 has already passed. If it is not confirmed, leave the date column blank and list it as an open item. Never invent a start date or a holiday.
18. **Run the guardrail check** (section 4), fix what you can, list what you couldn't, then save the files and show the review checklist (section 5).

### Check mode

1. **Read the existing calendar** and the hand-off block. Note the file names and dates.
2. **Compare with the hand-off.** Check campaign IDs and names, weeks, phases, pillar names, audiences, channels, formats, paid start week, call to action, KPI names and totals.
3. **Check every row.** Look for missing fields, duplicate IDs, an audience the campaign doesn't list, a pillar not in the hand-off, a paid asset before the paid start week, more than one call to action, and wording that conflicts with `offer.md`, `guardrails.md` or `voice-and-tone.md`.
4. **Check capacity and dates** as in Build mode steps 16 and 17.
5. **Write the check report** (section 3, part B). For each issue, give a suggested fix. Do not edit the calendar or the hand-off.
6. **Run the guardrail check**, then show the review checklist.

---

## 3. Output template

### A. Build mode

Save two files. Never overwrite an existing file; use `-v2` for a new version.
- `outputs/<client-slug>/strategy/content-calendar/YYYY-MM-DD-content-calendar-12-week.md`
- `outputs/<client-slug>/strategy/content-calendar/YYYY-MM-DD-content-calendar-12-week.csv` (the live work order is `calendar/content-calendar.csv`)

**Markdown file**

```markdown
Station: content-calendar
Date: YYYY-MM-DD
Mode: Build
Context used: [list files]
Hand-off source: context/marketing-plan.md (hand-off block, date or version)
Status: DRAFT – awaiting review

# Content calendar: [Client], 12 weeks from [Week 1 start date or TBC]

## 1. Summary
[Three sentences: what the calendar contains, the biggest risk, the biggest open item.]

## 2. Run settings
| Setting | Value | Source |
|---|---|---|
| Week 1 start | | |
| Publishing days | | |
| Channels | | |
| Owner roles | | |
| Capacity per week | | |
| Client approval time per week | | |
| Dates to plan around | | |

## 3. Campaign overview
| ID | Name | Weeks | Phase | Audience | Assets | Lead CTA |
|---|---|---|---|---|---|---|

## 4. Calendar by week
### Week [n]: [Campaign ID and name], [Phase]
| Asset ID | Day | Date | Pillar | Audience | Channel | Paid / Earned / Owned | Format | Key message | CTA | Owner | Status |
|---|---|---|---|---|---|---|---|---|---|---|---|

(One block per week, weeks 1 to 12, in order.)

## 5. Reconciliation with the hand-off
| Check | Calendar | Hand-off | Match |
|---|---|---|---|
| Total assets | | | |

| Format | Calendar | Hand-off | Match |
|---|---|---|---|

| Campaign | Calendar | Hand-off | Match |
|---|---|---|---|

| Pillar | Count | Share of total |
|---|---|---|

| Audience | Count |
|---|---|

| Channel | Count | Paid / Earned / Owned |
|---|---|---|

## 6. Capacity and dates check
| Week | Assets due | Over capacity? | Client records or approves | Note |
|---|---|---|---|---|

[Dates: confirmed or TBC. Weeks already passed, if any. Clashes with dates to plan around.]

## 7. Open items ([NEEDS CLIENT INPUT])
1. ...

## 8. Guardrail check result
[Each item in section 4 of the SKILL.md: pass, fixed, or open.]

## 9. Files
- Markdown: [path]
- CSV: [path]
```

**CSV file.** One header row, then one row per asset, in week and day order. The header is exactly these 21 columns in this order:

```
Asset ID,Campaign ID,Campaign name,Week,Day,Proposed publication date,Content pillar,Target audience,Key message / storyline,Platform / distribution channel,Paid / Earned / Owned,Content format,Creative assets required,Specs,Intended call to action (CTA),Responsible group member,Asset status,Brief ID / link to asset or brief,KPI / measurement method,Est. cost (CAD),Notes
```

Rules for the columns:
- **Asset ID:** `<Campaign ID>-A<NN>`, numbered from 01 within each campaign in week and day order.
- **Campaign ID, Campaign name:** exactly as in the hand-off.
- **Week:** a number from 1 to 12. **Day:** the day name from the run settings.
- **Proposed publication date:** `YYYY-MM-DD`, or blank if Week 1 is not confirmed.
- **Paid / Earned / Owned:** one of those three words.
- **Asset status:** `Not started` for every new row.
- **Brief ID / link to asset or brief:** `Link TBD.` plus a one-line brief note.
- **Notes:** `Approval: Not submitted`, plus any `[NEEDS CLIENT INPUT: ...]` or `[TBC]` for that row.
- Any cell with a comma is wrapped in double quotes. The file is UTF-8.

### B. Check mode

Save as `outputs/<client-slug>/strategy/content-calendar/YYYY-MM-DD-content-calendar-check.md`

```markdown
Station: content-calendar
Date: YYYY-MM-DD
Mode: Check
Context used: [list files]
Calendar checked: [file name and date]
Status: DRAFT – awaiting review

# Content calendar check: [Client], [date]

## Summary
[Three sentences: overall readiness, the biggest gap, the biggest strength.]

## Reconciliation with the hand-off
(The same tables as Build mode section 5, with a Match column.)

## Row-level issues
| Asset ID | Field | Issue | Suggested fix |
|---|---|---|---|

## Capacity and dates
(The same table as Build mode section 6.)

## Conflicts with the context pack
| Where | In the calendar | In the context file | Action |
|---|---|---|---|

## Questions for the client ([TBC] list)
1. ...
```

---

## 4. Guardrail check

Before showing anything, confirm each item and fix what fails:

- [ ] **Follows `context/guardrails.md`.** Claims, privacy, AI disclosure and audience sensitivity all apply to every key message, CTA and note.
- [ ] **No invented facts.** Prices, services, areas, times, partners, testimonials and statistics appear only if they are in the hand-off or the context pack. Gaps are marked `[NEEDS CLIENT INPUT: ...]`.
- [ ] **Wording matches the rules.** Words the offer and guardrails files say to use or avoid are respected in every key message and CTA. Check the files each run; do not rely on memory.
- [ ] **No outcome promises.** No row promises results, savings, timelines or guarantees.
- [ ] **No invented dates.** Dates exist only if the user confirmed Week 1. No holiday, anniversary or event is assumed.
- [ ] **Sensitive moments.** Nothing is scheduled to sound cheerful, urgent or promotional against the audience-sensitivity and tone rules. Flag any date the user marked sensitive.
- [ ] **Privacy and consent.** No client names, faces, stories or testimonials unless the guardrails say written permission is on file. No named organizations unless the guardrails allow it. Flag any asset that needs recording consent.
- [ ] **Sustainable volume.** No week or owner role goes over the capacity the user gave, and the client's approval time is not exceeded.
- [ ] **Paid rules.** Paid assets start no earlier than the hand-off allows and stay within its budget lines.
- [ ] **Totals match.** The calendar's counts equal the hand-off's counts.
- [ ] **AI disclosure.** The file is labelled `DRAFT – awaiting review` and nothing is treated as approved.

---

## 5. Review checklist (human)

- [ ] Does every campaign, pillar, audience and CTA match what our team agreed in the plan, not what the AI suggested?
- [ ] Do the asset counts match the hand-off, and can we really produce them in 12 weeks with the owners and hours we have?
- [ ] Can the client approve and record what is asked of them in the time they have each week?
- [ ] Is each row's audience, phase and call to action sensible for the week it sits in?
- [ ] Are the dates confirmed, and does anything land on a date we should avoid?
- [ ] Would we be comfortable giving this calendar to the content stations, and to the client, as it is?

When approved: change the status line to `APPROVED – <date>`, commit, and suggest a commit message. Then propose copying the approved CSV to `context/content-calendar.csv` for your team to approve. Do not edit `/context` until they say yes.

---

## 6. Tool slot

**Job:** planning and scheduling.
**Current tool:** see `playbook/tool-register.md` → content-calendar.
**Default:** Claude (this skill) to build and check, and a spreadsheet to open and edit the CSV. Optional add-ons: a project or scheduling tool to track owners and approvals, and the Marketing plugin's campaign-planning skill for a second view of the campaign weeks.
