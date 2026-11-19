---
name: ad-creative
description: Factory station 7 (creative line). Turns the paid-ad rows of the content calendar into test-ready ads. Each ad gets one concept tied to a content pillar and one audience, three headlines, two primary texts and one description within platform limits, one CTA, a visual brief and a ready-to-paste image prompt that follows the AI rules, a test plan saying what each variant tests, targeting notes and UTM links. Check mode reviews ads someone else drafted or ads already running against the context pack and the landing page, without rewriting them. Use when asked for ads, ad copy, ad variations, a paid social or search campaign, display ads, image prompts for ads, or to check ads before they launch. Needs the marketing-plan hand-off and the content calendar; feeds landing-page and performance-report.
---

# Station: Ad creative

**Line:** Creative · **Needs:** marketing-plan (its hand-off block), positioning-messaging, content-calendar · **Feeds:** landing-page, performance-report

**Job:** Create ads worth testing, with enough variation to learn what works.

**Two modes**
- **Build mode** (default): write new ads for the calendar rows named.
- **Check mode**: ads already exist (drafted by someone else, or live). Review them against this station's structure, the context pack and the landing page, and produce a check report. Do not rewrite the ads.

If it isn't clear which mode is needed, ask once.

**Boundaries.** This station writes ads: copy, visual brief, image prompt, test plan and tracking. The page the ad sends people to belongs to landing-page, and organic posts belong to social. Every client fact (audiences, pillars, CTAs, prices, areas, budget, platforms, photos, colours, fonts and wording rules) comes from the context files at run time. This file contains none. Check the files on every run; don't rely on memory.

---

## 1. Inputs

**Required**
- `context/brand-book.md`: imagery, photo library, colour, contrast, typography, logo rules
- `context/offer.md`: services, pricing and booking wording
- `context/personas.md` (approved, not a placeholder): each audience's pressures, fears, words and where they look for help
- `context/positioning.md`: audiences, default audience, core promise, current focus area and the rules for using the positioning
- `context/voice-and-tone.md`: paid-ads channel row, tone by audience and situation, language guide, words to use and avoid, approved CTAs
- `context/guardrails.md`: claims, privacy, permissions, AI visuals in advertising and disclosure, audience sensitivity
- `context/marketing-plan.md`, including its hand-off block: campaign IDs and names, phases, audiences, key messages, lead CTAs, KPIs, paid budget and spending controls
- `context/content-calendar.csv`: the rows marked Paid for the campaign or asset IDs named (key message, pillar, audience, platform, specs, CTA, KPI, notes)

**Required for Check mode**
- The existing ads: pasted copy, an export from the ad platform, or screenshots, with the destination URL of each

**Optional (use if present)**
- The landing page output for the same campaign: `outputs/<client-slug>/<landing page Asset ID>/<Asset ID>-copy-vN.md`
- `playbook/tool-register.md`: the current copy, image and ad-platform tools
- An earlier ads file or performance report for this campaign, to avoid repeating a losing variant

**Ask the user before starting** (one message, only what the files don't already answer)
1. Which campaign ID or asset IDs to cover.
2. The destination URL for each ad, if the landing page exists.
3. The image tool, if an AI image will be used and the register names none.

If a required file still contains `[PLACEHOLDER`, name the file. If `personas.md` or `positioning.md` is a placeholder, stop and recommend running research-personas or positioning-messaging first. If `context/marketing-plan.md` has no hand-off block, stop and recommend running the marketing-plan station first.

---

## 2. Steps

### Build mode

1. **Confirm the run.** State the mode, campaign ID and name, and the asset IDs covered. One calendar row marked Paid is one ad. If the user names a campaign, cover every Paid row for it, in calendar order.
2. **Pull the facts for each ad.** From the calendar row, copy the asset ID, week, pillar, audience, key message, platform, specs, CTA and KPI exactly. From the hand-off block, copy the campaign phase, lead CTA, paid start week, paid budget and spending controls. If the row and the hand-off disagree, list the conflict and use the hand-off until a human decides.
3. **Set one audience per ad.** If the row lists more than one audience, use the first one listed and record the choice. Take that audience's pressure, main fear and reassurance from `personas.md` and `positioning.md`.
4. **Write the concept.** One sentence: *For [audience] who [pressure], this ad shows [idea] so they [action].* The concept carries the row's key message and pillar. If two ads in the same campaign share a concept, change one so each tests a different angle, and say what differs.
5. **Write three headlines.** H1 states the row's key message most directly and is the recommendation. H2 and H3 each change one thing (the angle, the fear addressed, or a question in place of a statement). Stay within the character limit for the platform (see the limits table in step 9).
6. **Write two primary texts.** P1 opens on the audience's pressure in their own words from `personas.md`, then gives one reassurance and the CTA. P2 opens on the outcome, then gives the same reassurance and CTA. Follow the paid-ads channel row and the audience row in `voice-and-tone.md`: one benefit, one CTA, no urgency, and its rules on emoji, exclamation marks, spelling and reading level.
7. **Write one description** (the short line under the headline on platforms that show one), within the limit.
8. **Set the CTA.** Use the calendar row's CTA, which must be on the approved list in `voice-and-tone.md`. Pick the platform button that matches it most closely (for example, Book now, Learn more, Sign up, Download) and record both.
9. **Check the limits.** Use the calendar row's Specs first. If they give no limit, use the platform's current published limits, and record the source and date checked. Starting defaults for Meta feed ads: primary text 125 characters before it is cut off, headline 40, description 30. For Google responsive search ads: headline 30, description 90. Count characters for every line and record the count.
10. **Write the visual brief.** Use the image the calendar row asks for. Real photos from the library in `brand-book.md` come first when `guardrails.md` confirms their permission and says real photos are preferred. Give the concept, the photo file or shot, any on-image text (as short as the platform allows; check the calendar Specs), the colour and text pairs (only pairs the contrast list in `brand-book.md` marks as passing), fonts, logo use per `brand-book.md`, size and ratio from the Specs, and alt text.
11. **Write the image prompt** (only if an AI image will be used). Write it ready to paste. Describe subject, setting, light, framing, palette, mood and ratio in plain terms. Follow every condition `guardrails.md` sets for AI visuals in advertising. Add a "must not appear" line: everything the imagery section of `brand-book.md` says to avoid, any real person's likeness, logos, and text drawn by the tool. Record the disclosure `guardrails.md` and the platform require.
12. **Write the test plan.** For each ad, list the variant codes (H1 to H3, P1 to P2) and what each one tests. Give the run order: H1 + P1 runs first; then the one change to test next, and the one after that. The human decides how many variants run at the same time within the hand-off's budget and spending controls. Write one hypothesis per ad: *If [change], then [KPI from the row] improves, because [reason from personas.md].*
13. **Write targeting notes.** Copy location, radius, audience and placements from the calendar Specs and the hand-off only. Anything not stated there is `[NEEDS CLIENT INPUT: ...]`. Never add targeting by age, health or other traits the platform or `guardrails.md` restricts.
14. **Set up tracking.** Destination URL for each ad (or `[NEEDS CLIENT INPUT: landing page URL]`). One UTM-tagged link per variant: `utm_source` (platform), `utm_medium` (`paid-social` or `paid-search`), `utm_campaign` (campaign ID and name in lowercase with hyphens), `utm_content` (asset ID and variant code in lowercase, for example `c2-a07-h1-p1`). Use KPI names exactly as in the hand-off.
15. **Check the destination.** If the landing page output exists, confirm its hero repeats each ad's H1 promise and its button matches the ad's CTA. If it doesn't exist yet, say the landing-page station should run next with this file as its ad input.
16. **Run the guardrail check** (section 4), fix what fails, list what you couldn't fix, then save and show the review checklist (section 5).

### Check mode

1. **Read the ads.** Record where they came from (paste, export or screenshots), the date checked, and whether they are live.
2. **Map each ad to its calendar row** by asset ID, or by key message if it has no ID. List ads with no matching row.
3. **Check the structure.** For each ad, mark each part Present, Partial or Missing: concept, headline, primary text, description, CTA, visual, alt text, destination URL, UTM link, test plan.
4. **Check the limits** as in Build step 9, line by line.
5. **Check facts and wording** against `offer.md`, `brand-book.md`, `voice-and-tone.md` and `guardrails.md`. List each conflict side by side. Never pick a winner; the client confirms.
6. **Check visuals** against the imagery, contrast and logo rules in `brand-book.md` and the AI and permission rules in `guardrails.md`.
7. **Check the destination:** does the landing page repeat the ad's promise, and does its button match the ad's CTA?
8. **Check spending** against the hand-off's paid start week, budget and spending controls.
9. **Write the check report** (section 3, part B). Give a suggested fix for each issue. Do not rewrite the ads. Then run the guardrail check and show the review checklist.

---

## 3. Output template

Save as:
- Build mode: `outputs/<client-slug>/<Asset ID>/<Asset ID>-copy-vN.md`, plus `<Asset ID>-sources.md` (rules: `outputs/README.md`)
- Check mode: `outputs/<client-slug>/<Asset ID>/<Asset ID>-check-vN.md`

Lowercase, hyphens, no spaces. `<description>` is the campaign ID plus the platform, for example `c2-meta`. Never overwrite an existing file; save a revision as `-v2`, `-v3`. Images go in the same client folder named `YYYY-MM-DD-ads-<description>-<asset-id>-<variant>.<ext>`, for example `...-c2-a07-i1.png`.

Start every output with the header block below. A human changes the status to `APPROVED – YYYY-MM-DD` after review.

Fill every field. If a value is unknown, write `[NEEDS CLIENT INPUT: ...]` instead of leaving it blank or guessing. Keep every heading and table, even when a row says "none." Repeat the ad block once per calendar row, in calendar order.

### A. Build mode

```markdown
Station: ad-creative
Date: YYYY-MM-DD
Mode: Build
Context used: [each file with its version line]
Campaign source: context/marketing-plan.md (hand-off block, version line)
Status: DRAFT – awaiting review
Launch readiness: READY FOR REVIEW | NOT READY TO LAUNCH – [reason]

# Ads: [Client], [Campaign ID] [Campaign name], [platform]

## 1. Run summary
| Field | Value | Source |
|---|---|---|
| Campaign | | hand-off |
| Phase | | hand-off |
| Platform | | calendar |
| Asset IDs covered | | calendar |
| Paid start week | | hand-off |
| Paid budget and spending controls | | hand-off |
| Limits used and date checked | | calendar Specs or platform |
| Image tool | | playbook/tool-register.md |

---

## Ad [asset ID]: [key message from the calendar row]

### Brief
| Field | Value |
|---|---|
| Week | |
| Pillar | |
| Audience (one) | |
| Audience pressure and main fear | |
| Key message | |
| Concept | For [audience] who [pressure], this ad shows [idea] so they [action]. |
| Format and size | |

### Copy
| Code | Text | Characters / limit | What it tests |
|---|---|---|---|
| H1 (recommended) | | | Baseline: the key message stated directly |
| H2 | | | |
| H3 | | | |
| P1 (recommended) | | | Baseline: opens on the pressure |
| P2 | | | Opens on the outcome |
| D1 | | | |

- **CTA (approved wording):**
- **Platform button:**

### Visual
- **Concept:**
- **Photo file or shot:** [file name from the brand book library, or "AI image: see prompt"]
- **Permission:** confirmed | NEEDS CLIENT INPUT
- **On-image text:** [exact text, or "none"]
- **Colour and text pairs (contrast ratio):**
- **Fonts:**
- **Logo:**
- **Size and ratio:**
- **Alt text:**
- **Output file name:**

### Image prompt
[ready-to-paste prompt, or "Not used: real photo"]

**Must not appear:** [list]
**Disclosure:** [wording required by guardrails.md or the platform, or "none required", with the source]

### Test plan
- **Run first:** H1 + P1
- **Test next:** [one change and why]
- **Then:** [one change and why]
- **Hypothesis:** If [change], then [KPI] improves, because [reason].

### Targeting notes
| Setting | Value | Source |
|---|---|---|
| Location and radius | | |
| Audience | | |
| Placements | | |

### Tracking
- **Destination URL:**
- **KPI (from the row):**

| Variant | UTM-tagged link |
|---|---|
| h1-p1 | |
| h2-p1 | |
| h3-p1 | |
| h1-p2 | |

---

(Repeat the ad block for every row.)

## Landing page match
| Asset ID | H1 promise | On the landing page? | Button matches CTA? | Action |
|---|---|---|---|---|

## Facts used
| Fact | Where in the ads | Source file and section |
|---|---|---|

## Tools used
| Role | Tool | Notes |
|---|---|---|

## Guardrail result
| Check | Pass / Fixed / Open | Note |
|---|---|---|

## Gaps and assumptions
- [every `[NEEDS CLIENT INPUT: ...]` item and anything the reviewer must confirm]

## Questions for the client
1.
```

### B. Check mode

```markdown
Station: ad-creative
Date: YYYY-MM-DD
Mode: Check
Context used: [each file with its version line]
Ads checked: [source, date checked, live or not]
Status: DRAFT – awaiting review
Launch readiness: READY TO LAUNCH | NOT READY TO LAUNCH – [reason]

# Ads check: [Client], [Campaign ID] [Campaign name], [platform]

## 1. Summary
[Three sentences: overall readiness, the biggest gap, the biggest strength.]

## 2. Ads mapped to the calendar
| Ad | Asset ID | Calendar row found? | Note |
|---|---|---|---|

## 3. Structure
| Ad | Concept | Headline | Primary text | Description | CTA | Visual | Alt text | URL | UTM | Test plan |
|---|---|---|---|---|---|---|---|---|---|---|

(Present / Partial / Missing in each cell.)

## 4. Limits
| Ad | Line | Characters / limit | Fix |
|---|---|---|---|

## 5. Conflicts with the context pack
| Ad | In the ad | In the context file | Action |
|---|---|---|---|

## 6. Visuals
| Ad | Issue | Rule (file and section) | Fix |
|---|---|---|---|

## 7. Landing page match
| Ad | Promise | On the page? | Button matches? | Fix |
|---|---|---|---|---|

## 8. Spending
| Item | In the ads or platform | In the hand-off | Action |
|---|---|---|---|

## 9. Guardrail result
| Check | Pass / Fail | Note |
|---|---|---|

## 10. Questions for the client
1.
```

---

## 4. Guardrail check

Before showing anything, confirm each item and fix what fails:

- [ ] **Follows `context/guardrails.md`.** Claims, privacy, AI visuals and disclosure, and audience sensitivity apply to every line, image and prompt.
- [ ] **No invented facts.** Every price, service, area, credential and claim is in "Facts used" with its source file. Gaps are marked `[NEEDS CLIENT INPUT: ...]`. Missing information is never filled with a similar-sounding claim.
- [ ] **No fake proof.** No invented testimonials, reviews, quotes, results or statistics. No AI-generated or staged person, home or scene presented as a real client, the founder, staff or real work.
- [ ] **AI images follow every condition** `guardrails.md` sets for advertising, and carry any disclosure it or the platform requires.
- [ ] **No outcome promises** and no superlatives the context pack can't back up.
- [ ] **Wording rules.** Every line respects the use and avoid lists and the approved CTAs in `voice-and-tone.md` and `guardrails.md`.
- [ ] **Audience sensitivity.** No fear, urgency, guilt or pressure framing, no countdowns, no "last chance." Tone matches the paid-ads channel row and the audience row in `voice-and-tone.md`.
- [ ] **One audience, one message, one CTA per ad**, and the CTA matches the calendar row.
- [ ] **Within limits.** Every line fits the limit used, and the counts are recorded.
- [ ] **Platform ad policies.** The ad meets the platform's current ad policies. Record whether it falls under a special or restricted ad category (for example, housing, credit, employment, or social issues) and why. No targeting by personal traits the platform or `guardrails.md` restricts.
- [ ] **Accessible visuals.** On-image text is short and uses passing contrast pairs; every image has accurate alt text.
- [ ] **Spending.** Ads start no earlier than the hand-off's paid start week and stay within its budget and spending controls.
- [ ] **AI disclosure in the file.** The file is labelled `DRAFT – awaiting review`, and nothing is launched or treated as approved.

---

## 5. Review checklist (human)

- [ ] Would this audience stop on H1 and the image in a busy feed, without fear, guilt or urgency?
- [ ] Does each ad test one clear idea, and would the result teach us something we can use next cycle?
- [ ] Is every fact and price confirmed, every photo cleared, and every AI image within the guardrails?
- [ ] Does it sound like the client as `voice-and-tone.md` describes them, even in so few words?
- [ ] Does the landing page keep the promise the ad makes, with the same CTA?
- [ ] Does the run plan fit the paid budget and spending controls in the hand-off?

When approved: change the status to `APPROVED – <date>`, commit, and suggest a commit message (for example `Add <client> C2 Meta ads (approved)`). Then run landing-page with this file if the page doesn't match yet. After launch, give the live variants, start dates and UTM links to performance-report.

---

## 6. Tool slot

**Job:** ad copy and image generation.

Take tool names from `playbook/tool-register.md` (row: ad-creative). Don't hard-code them here, so this station stays correct when the register changes.

| Role | Used for | Tool (from register) |
|---|---|---|
| Copy drafting | Write concepts, headlines, primary texts and descriptions from the context files, then apply the guardrail check | `[NEEDS CLIENT INPUT: tool from register]` |
| Image generation | Generate images from the prompt in the output file, only where the guardrails allow AI visuals | `[NEEDS CLIENT INPUT: tool from register]` |
| Ad platform | Build, target and launch approved ads; read results | `[NEEDS CLIENT INPUT: tool from register]` |

**Rules for using tools:**
- Never upload client photos, names or stories to a tool without confirmed written permission.
- Never use a tool to create or imitate a real person's face or voice.
- Check the image tool's licence terms for commercial use before an image runs in an ad.
- Nothing launches until a human has approved it.
- Log what you used in "Tools used" in the output file.
- If no tool is registered for a role, do that step by hand and say so in "Gaps and assumptions."
