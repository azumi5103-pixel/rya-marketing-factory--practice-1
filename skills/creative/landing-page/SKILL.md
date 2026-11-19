---
name: landing-page
description: Factory station 9 (creative line). Writes one conversion-focused landing page for one campaign, one audience and one action. Section-by-section copy in a fixed order, headline options matched to the traffic source, objection handling from the personas, a short form with privacy and consent wording, the confirmation message, metadata, tracking and a build brief for the page tool. Check mode reviews an existing page against the same structure and the context pack without rewriting it. Use when asked for a landing page, campaign page, consultation or booking page, sign-up or download page or page copy, or to review a page before ads, posts or partners send traffic to it. Needs positioning; uses ad-creative output when traffic is paid.
---

# Station: Landing page

**Line:** Creative · **Needs:** marketing-plan (its hand-off block), positioning-messaging, ad-creative (if paid traffic) · **Feeds:** performance-report

**Job:** Give campaign traffic one clear place to take one clear action.

**Two modes**
- **Build mode** (default): write a new page from the context pack and the campaign.
- **Check mode**: an existing page will receive traffic. Review it against this station's structure and the context pack, and produce a check report. Do not rewrite the page.

If it isn't clear which mode is needed, ask once.

**Boundaries.** One page, one audience, one action. This station writes page copy, the form, the confirmation and the build brief. Ads belong to ad-creative, emails to email, and articles to blog-seo-geo. Every client fact (services, prices, areas, CTAs, proof, colours, fonts, images, wording rules) comes from the context files at run time. This file contains none.

---

## 1. Inputs

**Required**
- `context/brand-book.md`
- `context/offer.md`
- `context/personas.md` (approved, not a placeholder)
- `context/positioning.md`
- `context/voice-and-tone.md`
- `context/guardrails.md`
- `context/marketing-plan.md`, including its hand-off block (campaign IDs, phases, audiences, key messages, lead CTAs, KPIs, spending controls)

**Required when traffic is paid**
- The approved ad-creative output for this campaign (`outputs/<client-slug>/<ad Asset ID>/<Asset ID>-copy-vN.md`)

**Required for Check mode**
- The existing page: pasted text, an exported file or a public URL, plus screenshots of the desktop and mobile views if available

**Optional (use if present)**
- `context/content-calendar.csv`: the rows whose CTA or link points to this page
- `playbook/tool-register.md`: the current page, form and analytics tools
- A filled-in `templates/client-brief.md` for this campaign

**Ask the user before starting** (one message, only what the files don't already answer)
1. The campaign ID from the hand-off block.
2. Traffic sources that will send people to the page (paid ad, organic post, email, partner, print or QR code).
3. The one action: book, download, register or contact.
4. Who receives form submissions, and how fast they can reply.
5. The page URL, if it already exists or is reserved.

If a required file still contains `[PLACEHOLDER`, name the file. If `personas.md` or `positioning.md` is a placeholder, stop and recommend running research-personas or positioning-messaging first.

---

## 2. Steps

### Build mode

1. **Confirm the run.** State the mode, campaign ID and name, the one audience, the traffic sources and the one action. If the request carries two actions (for example book and download), ask which one this page serves. The other gets its own page.
2. **Pull the campaign facts.** From the hand-off block in `context/marketing-plan.md`, copy the campaign ID, name, weeks, phase, audience, key message, lead CTA and KPI names exactly. From `context/content-calendar.csv`, list the asset IDs that link here.
3. **Set the page goal.** Write one sentence: *[audience] arriving from [source] [takes action] because [promise].* Define what counts as a conversion (for example, a submitted form). The button text comes from the approved CTA list in `voice-and-tone.md` and must match the hand-off's lead CTA. If they differ, list the conflict and use the hand-off's wording until a human decides.
4. **Match the message.** For each traffic source, record the promise the visitor clicked: the ad headline from the ad-creative output, the calendar key message, or the partner's wording. The hero headline repeats that promise in its first words. If two sources promise different things, recommend one page per promise and stop for a decision.
5. **Write three headline options.** A is the closest match to the traffic promise and is the recommendation. B and C each change one thing (angle, length or the fear addressed). Record what each one tests.
6. **Build the fear-to-answer map.** From `personas.md`, take every fear (practical, emotional, social) and every reassurance listed for this audience. For each fear, write the answer using only facts from `offer.md`, `positioning.md` and `brand-book.md`, and assign the section where the page answers it. A fear the page cannot answer goes under "Gaps and assumptions" with the reason.
7. **Write the sections in this fixed order.** Never add, drop or reorder sections. Default lengths apply unless the calendar row's Specs say otherwise.
   1. **Hero:** eyebrow (6 words or fewer), headline (10 words or fewer), subheadline (25 words or fewer), button, one supporting line under the button (15 words or fewer) that removes one barrier, hero image.
   2. **Problem:** 40 to 80 words in the reader's situation and words, drawn from the persona's "in their words" lines. Name the pressure calmly; never amplify it.
   3. **Solution:** 60 to 100 words on what the client does for this reader, following the positioning file's instructions for this audience, then 3 benefit bullets of 12 words or fewer.
   4. **Proof:** see step 8.
   5. **How it works:** 3 or 4 numbered steps, each a heading of 6 words or fewer plus one sentence. Use only the process described in `offer.md`.
   6. **FAQ:** see step 9.
   7. **Final call to action and form:** a heading of 10 words or fewer, one reassurance line, the form, the privacy notice and the button.
   8. **Footer:** business name exactly as in `brand-book.md`, contact details from `brand-book.md`, privacy policy link, service area wording from `voice-and-tone.md`.

   Use the tone row in `voice-and-tone.md` that fits this audience and situation, and the closest channel row. Use "we" for the business and "you" for the reader unless `voice-and-tone.md` says otherwise.
8. **Add proof.** Use only proof that `guardrails.md` allows and whose permission is confirmed there. Use this order: cleared testimonials, word for word with the name format the guardrails require; founder background and community roles as written in `brand-book.md`; process facts from `offer.md`. Never shorten or reword a testimonial unless the guardrails allow it. If nothing is cleared, build the section from process facts and list the missing proof under "Gaps and assumptions."
9. **Write the FAQ.** Write 4 to 6 questions, in this order: fears from step 6 that the page hasn't answered yet, then cost, what happens after the form is sent, service area, and who will come. Answers are 1 to 3 sentences, using facts from `offer.md` only. Prices appear exactly as written there.
10. **Design the form.** Start from the fields the action can't happen without, and stop there. At most 5 fields. For each field, record the label, type, required or optional, and why it is asked. Rules:
    - Labels are visible above each field, not placeholder text only.
    - No field asks for health, financial, family-conflict or ID details. A free-text field says what kind of answer is wanted and carries a short note not to include private details.
    - If the client will send marketing email beyond replying to this request, add a separate, unticked consent checkbox, worded to meet the consent rules in the email station's guardrail check.
    - Under the form, write a privacy notice of 50 words or fewer: what is collected, why, who sees it, and how to ask for it to be deleted, with a link to the privacy policy. If the context pack has no privacy policy URL, write `[NEEDS CLIENT INPUT: privacy policy URL]` and set Publish readiness to NOT READY TO PUBLISH.
    - Write error messages that say how to fix the problem.
11. **Write the confirmation.** On-screen message (40 words or fewer): thank the visitor, say what happens next and when. Auto-reply email, if the form tool sends one: subject line of 50 characters or fewer, and a body of 80 words or fewer. State a reply time only if the user or the context pack gave one; otherwise write `[NEEDS CLIENT INPUT: reply time]`. Offer one optional next step. No second sales pitch.
12. **Choose images.** Take images only from the library listed in `brand-book.md`, and check each one's permission status in `guardrails.md`. Write alt text that describes what is in the image. Generic AI images follow the AI rules and disclosure table in `guardrails.md`. If no cleared image fits, write a brief for one and mark it `[NEEDS CLIENT INPUT: image]`.
13. **Write the metadata.** Meta title of 60 characters or fewer with the key phrase near the front. Meta description of 150 to 160 characters. Lowercase hyphenated slug. Social share title and image. Indexing: `noindex` for a page that only receives paid or campaign traffic, `index` if the hand-off names search as a source for this campaign.
14. **Set up tracking.** Name the conversion event and the confirmation URL or on-page event. Write one UTM-tagged link per traffic source: `utm_source` (platform or partner), `utm_medium` (paid-social, social, email, referral, print), `utm_campaign` (campaign ID and name in lowercase with hyphens), `utm_content` (asset ID from the calendar). Use KPI names exactly as in the hand-off.
15. **Write the build brief.** Fill in the build brief table in the output template so someone can build the page in the registered tool without asking questions. Colours and text pairings: use only pairs that `brand-book.md` lists as passing WCAG AA for that text size. If it gives no list, check each pair (4.5:1 for normal text, 3:1 for large text) and record the ratio. Fonts and minimum sizes come from `brand-book.md`. Hide the site's main navigation on this page if the tool allows it.
16. **Run the guardrail check** (section 4), fix what fails, list what you couldn't fix, then save and show the review checklist (section 5).

### Check mode

1. **Read the page.** Record where the text came from (paste, file or URL) and the date checked. If a URL can't be read, ask for pasted text or screenshots.
2. **Map it to the eight sections** from Build step 7. Mark each one Present, Partial or Missing, in the fixed order, even if the page uses other headings.
3. **Check the message match** for each traffic source, as in Build step 4.
4. **Check the one action.** Count every button and link that leads off the page or to a different action. Each one is an issue, apart from the privacy policy and contact details.
5. **Check the form** against the rules in Build step 10, one row per field.
6. **Check facts against the context pack.** Compare every price, service, area, time, CTA and proof point with `offer.md`, `brand-book.md`, `voice-and-tone.md` and `guardrails.md`. List each conflict side by side. Never pick a winner; the client confirms.
7. **Check accessibility:** text and background pairs as in Build step 15, alt text on every image, visible labels, button text that describes the action, and a readable mobile view.
8. **Check tracking:** conversion event, confirmation URL or event, and UTM links for each traffic source.
9. **Write the check report** (section 3, part B). Give a suggested fix for each issue. Do not rewrite the page. Then run the guardrail check and show the review checklist.

---

## 3. Output template

Save as:
- Build mode: `outputs/<client-slug>/<Asset ID>/<Asset ID>-copy-vN.md`, plus `<Asset ID>-sources.md` (rules: `outputs/README.md`)
- Check mode: `outputs/<client-slug>/<Asset ID>/<Asset ID>-check-vN.md`

Lowercase, hyphens, no spaces. `<description>` is the campaign ID plus the action, for example `c2-consultation`. Never overwrite an existing file; save a revision as `-v2`, `-v3`. Images and exports from the page tool go in the same client folder with the same date-first naming.

Start every output with the header block below. A human changes the status to `APPROVED – YYYY-MM-DD` after review.

Fill every field. If a value is unknown, write `[NEEDS CLIENT INPUT: ...]` instead of leaving it blank or guessing. Keep every heading and table, even when a row says "none."

### A. Build mode

```markdown
Station: landing-page
Date: YYYY-MM-DD
Mode: Build
Context used: [each file with its version line]
Campaign source: context/marketing-plan.md (hand-off block, version line)
Status: DRAFT – awaiting review
Publish readiness: READY TO BUILD | NOT READY TO PUBLISH – [reason]

# Landing page: [Client], [Campaign ID] [Campaign name], [action]

## 1. Page brief
| Field | Value | Source |
|---|---|---|
| Campaign | | hand-off |
| Phase | | hand-off |
| Audience (one) | | hand-off |
| Traffic sources | | user |
| Calendar assets linking here | | context/content-calendar.csv |
| The one action | | user |
| Conversion counted as | | |
| Button text | | voice-and-tone.md, hand-off |
| Page URL | | |
| Submissions go to | | user |

**Page goal:** [audience] arriving from [source] [takes action] because [promise].

## 2. Message match
| Traffic source | Promise the visitor clicked | Where the page repeats it |
|---|---|---|

## 3. Headline options
| Option | Headline | Subheadline | What it tests |
|---|---|---|---|
| A (recommended) | | | |
| B | | | |
| C | | | |

## 4. Fear-to-answer map
| Fear (from personas.md) | Type | Answer on the page | Section | Source of the answer |
|---|---|---|---|---|

## 5. Page copy

### Section 1: Hero
- **Eyebrow:**
- **Headline:** (option A)
- **Subheadline:**
- **Button:** [button text] → links to #form
- **Line under the button:**
- **Image:** [file name] · **Alt text:**

### Section 2: Problem
[40–80 words]

### Section 3: Solution
[60–100 words]
- [benefit]
- [benefit]
- [benefit]

### Section 4: Proof
| Proof item | Exact wording | Source | Permission status |
|---|---|---|---|

### Section 5: How it works
1. **[Step heading]:** [one sentence]
2. **[Step heading]:** [one sentence]
3. **[Step heading]:** [one sentence]

### Section 6: FAQ
**[Question]**
[Answer, 1–3 sentences]

(4 to 6 questions)

### Section 7: Final call to action and form
- **Heading:**
- **Reassurance line:**
- **Form:** see part 6
- **Button:** [button text]

### Section 8: Footer
- **Business name:**
- **Contact:**
- **Service area line:**
- **Privacy policy link:**

## 6. Form
| # | Label | Field type | Required | Why we ask | Help text |
|---|---|---|---|---|---|

- **Marketing consent checkbox:** [exact wording, unticked] or "Not used: no marketing email planned"
- **Privacy notice:** [50 words or fewer, with link]
- **Error messages:** [one per required field]
- **Notifications:** [who receives each submission, and how]

## 7. Confirmation
- **On-screen message:**
- **Auto-reply subject:**
- **Auto-reply body:**

## 8. Metadata
| Field | Value |
|---|---|
| Meta title (≤60 characters) | |
| Meta description (150–160 characters) | |
| URL slug | |
| Social share title | |
| Social share image and alt text | |
| Indexing | index / noindex, and why |

## 9. Tracking
- **Conversion event:**
- **Confirmation URL or event:**

| Traffic source | Asset ID | UTM-tagged link |
|---|---|---|

| KPI (from hand-off) | How this page feeds it |
|---|---|

## 10. Build brief
**Tool:** [from playbook/tool-register.md]
**Page settings:** URL · meta title · meta description · indexing · navigation hidden (yes/no)

| # | Block | Layout (desktop / mobile) | Copy | Text colour on background (contrast ratio) | Fonts and sizes | Image |
|---|---|---|---|---|---|---|
| 1 | Hero | | Part 5, section 1 | | | |
| 2 | Problem | | Part 5, section 2 | | | |
| 3 | Solution | | Part 5, section 3 | | | |
| 4 | Proof | | Part 5, section 4 | | | |
| 5 | How it works | | Part 5, section 5 | | | |
| 6 | FAQ | | Part 5, section 6 | | | |
| 7 | Final CTA and form | | Part 5, section 7 | | | |
| 8 | Footer | | Part 5, section 8 | | | |

**Form setup:** fields, required flags, consent checkbox, notification recipients, spam protection
**Confirmation setup:** on-screen message or confirmation page, auto-reply
**Tracking setup:** conversion event, UTM links tested
**Before publishing:**
- [ ] Mobile view checked
- [ ] Test submission sent and received by the right person
- [ ] Auto-reply received
- [ ] Every link and button works
- [ ] Keyboard-only run through the form works
- [ ] Privacy policy link works

## 11. Facts used
| Fact | Where on the page | Source file and section |
|---|---|---|

## 12. Tools used
| Role | Tool | Notes |
|---|---|---|

## 13. Guardrail result
| Check | Pass / Fixed / Open | Note |
|---|---|---|

## 14. Gaps and assumptions
- [every `[NEEDS CLIENT INPUT: ...]` item and anything the reviewer must confirm]

## 15. Questions for the client
1.
```

### B. Check mode

```markdown
Station: landing-page
Date: YYYY-MM-DD
Mode: Check
Context used: [each file with its version line]
Page checked: [URL or file name, date checked]
Status: DRAFT – awaiting review
Publish readiness: READY FOR TRAFFIC | NOT READY FOR TRAFFIC – [reason]

# Landing page check: [Client], [page name]

## 1. Summary
[Three sentences: overall readiness, the biggest gap, the biggest strength.]

## 2. Structure
| # | Section | Status (Present / Partial / Missing) | Note |
|---|---|---|---|
| 1 | Hero | | |
| 2 | Problem | | |
| 3 | Solution | | |
| 4 | Proof | | |
| 5 | How it works | | |
| 6 | FAQ | | |
| 7 | Final CTA and form | | |
| 8 | Footer | | |

## 3. Message match
| Traffic source | Promise the visitor clicked | On the page? | Fix |
|---|---|---|---|

## 4. Competing actions
| Element | Where | Leads to | Fix |
|---|---|---|---|

## 5. Form
| Field | Needed for the action? | Issue | Fix |
|---|---|---|---|

Privacy notice: present / missing · Consent checkbox: correct / missing / pre-ticked / not needed

## 6. Conflicts with the context pack
| Fact | On the page | In the context file | Action |
|---|---|---|---|

## 7. Accessibility
| Item | Issue | Fix |
|---|---|---|

## 8. Tracking
| Item | Status | Fix |
|---|---|---|

## 9. Guardrail result
| Check | Pass / Fail | Note |
|---|---|---|

## 10. Questions for the client
1.
```

---

## 4. Guardrail check

Before showing anything, confirm each item and fix what fails:

- [ ] **Follows `context/guardrails.md`.** Claims, privacy, AI disclosure and audience sensitivity apply to every line, image and form field.
- [ ] **No invented facts.** Every price, service, area, time, credential, statistic and proof point is in "Facts used" with its source file. Gaps are marked `[NEEDS CLIENT INPUT: ...]`. Missing information is never filled with a similar-sounding claim.
- [ ] **Proof is real and cleared.** Testimonials are word for word, with the name format and permission status `guardrails.md` requires. No invented or AI-written reviews, quotes, client stories or results.
- [ ] **No outcome promises.** No guaranteed results, savings, timelines or superlatives the context pack can't back up.
- [ ] **Wording rules.** Every word on the page respects the use and avoid lists in `voice-and-tone.md` and `guardrails.md`. Check the files on each run; don't rely on memory.
- [ ] **Audience sensitivity.** No fear, urgency, guilt or pressure framing, no countdowns, no "spots left." Tone matches the audience and situation rows in `voice-and-tone.md`.
- [ ] **One action.** One button text throughout, and no links off the page apart from the privacy policy and contact details.
- [ ] **Message match.** The hero repeats the promise of every traffic source.
- [ ] **Form collects only what is needed.** At most 5 fields, each with a reason. No health, financial, family-conflict or ID fields.
- [ ] **Privacy and consent.** A privacy notice and policy link sit next to the form. Marketing consent is a separate, unticked box, or isn't asked for.
- [ ] **Images.** Every image is from the brand book library with permission confirmed, or is a generic AI image the guardrails allow, with any disclosure they require. Every image has accurate alt text.
- [ ] **Accessible.** Text and background pairs pass WCAG AA for their size, labels are visible, button and link text say what happens, and the page reads in order on mobile.
- [ ] **Paid rules.** If traffic is paid, the page matches the approved ad and stays within the hand-off's spending controls and paid start week.
- [ ] **AI disclosure.** The file is labelled `DRAFT – awaiting review`, and nothing is published or treated as approved.

---

## 5. Review checklist (human)

- [ ] Would someone who clicked the ad, post or partner link recognize in the first five seconds that they're in the right place?
- [ ] Is there exactly one thing to do on this page, and is it the action the campaign needs?
- [ ] Does the page answer this audience's biggest fears without leaning on them?
- [ ] Is every fact, price and proof point something the client has confirmed and cleared?
- [ ] Would you fill in this form yourself, and does the privacy wording tell you plainly what happens to your details?
- [ ] Could someone build and test this page from the build brief without asking us a single question?

When approved: change the status to `APPROVED – <date>`, commit, and suggest a commit message (for example `Add <client> C2 consultation landing page (approved)`). After launch, give the page URL, conversion event and UTM links to performance-report.

---

## 6. Tool slot

**Job:** page copy and page building.

Take tool names from `playbook/tool-register.md` (row: landing-page). Don't hard-code them here, so this station stays correct when the register changes.

| Role | Used for | Tool (from register) |
|---|---|---|
| Copy drafting | Write the copy, form and confirmation from the context files, then apply the guardrail check | `[NEEDS CLIENT INPUT: tool from register]` |
| Page building | Build the page from the build brief | `[NEEDS CLIENT INPUT: tool from register]` |
| Forms and notifications | Collect submissions, send the auto-reply, notify the right person | `[NEEDS CLIENT INPUT: tool from register]` |
| Analytics | Record the conversion event and UTM sources | `[NEEDS CLIENT INPUT: tool from register]` |

**Rules for using tools:**
- Never paste real client names, contact details or form submissions into an AI tool.
- Nothing is published, and no traffic is sent to the page, until a human approves it.
- Log what you used in "Tools used" in the output file.
- If no tool is registered for a role, write the build brief anyway, do that step by hand, and say so in "Gaps and assumptions."
