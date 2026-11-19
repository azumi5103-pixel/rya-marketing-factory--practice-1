---
name: email
description: Factory station 6 (content line). Writes review-ready client emails from the content calendar, in the client's voice. Newsletters and one-off sends by default, welcome or nurture sequences on request. Each email gets one goal, three subject line options, preview text, body copy, one call to action, a footer block, and a guardrail and consent check that covers Canada's anti-spam rules. Use when asked for an email, a newsletter, subject lines, preview text, a welcome or nurture sequence, or "the emails for week N" of the calendar. Not for one-to-one messages to a specific client, social posts or blog articles.
---

# Station: Email

**Line:** Content · **Needs:** content-calendar, positioning-messaging · **Feeds:** performance-report

**Job:** Keep warm leads moving toward a conversation with the client, one honest email at a time.

---

## 1. Inputs

**Required**
- `context/brand-book.md`
- `context/offer.md`
- `context/personas.md` (approved, not a placeholder)
- `context/positioning.md`
- `context/voice-and-tone.md`
- `context/guardrails.md`
- The content calendar: `calendar/content-calendar.csv` (the rows whose channel is email). Not needed for a one-off or sequence the human describes directly.

**Optional**
- `context/marketing-plan.md` (campaign message, call to action and KPIs for the weeks in question)
- The brief from the human: email type, goal, audience, send day
- Details of the list: who is on it, how they joined, and where the consent record is kept
- Results from earlier sends, to learn from

**Run type.** Decide which one applies before writing:
- **Calendar email** (default): one email per calendar email row the human names.
- **One-off**: a single email from the human's brief.
- **Sequence** (only when asked): two or more linked emails sent over time.

If a required file still contains `[PLACEHOLDER`, tell the human which file before drafting. If `personas.md` is a placeholder, stop and recommend `research-personas`.

---

## 2. Steps

1. **Confirm the run.** State the run type, the calendar rows (or brief) and the number of emails. If the human named no rows and the calendar has several email rows, list them and ask which to write.
2. **Establish the list.** Ask who will receive the email and how they joined (sign-up form, event sign-in, client list, partner list). Write the answer in the run summary. If it is unknown, write `[NEEDS CLIENT INPUT: how this list joined and where consent is recorded]` and mark the run NOT READY TO SEND. The draft can still be reviewed.
3. **Fix one reader and one goal per email.** From the calendar row (and `marketing-plan.md` if present) take the persona, content pillar, key message, call to action and specs. Choose one goal: read, download, reply or book. The call to action must come from the approved list in `voice-and-tone.md`. Specs in the calendar row override the defaults below.
4. **Choose the tone.** Use the situation, audience and channel tables in `voice-and-tone.md`. For grief or estate readers, follow the quiet tone and leave out promotion.
5. **Write the body.** Open on the reader's situation, not on the business. Give one idea (a tip, a story or an update), then one call to action. Use "we" for the business and "you" for the reader. Default length is 150 to 250 words unless the calendar Specs say otherwise.
6. **Write three subject lines.** Make them different angles (a question, a plain statement, a benefit). Keep each within the limit in the Specs (default 50 characters or fewer) and make each one match what is inside the email. Follow the emoji, punctuation and word rules in `voice-and-tone.md`.
7. **Write the preview text.** Add something the subject line does not say. Default 40 to 90 characters.
8. **Use only facts from the context pack.** Every price, service, name, credential and claim must appear in `offer.md`, `brand-book.md` or `guardrails.md`. List each one in "Facts used". Anything missing becomes `[NEEDS CLIENT INPUT: ...]`.
9. **Handle stories and proof with care.** Use a real client story, quote or photo only if `guardrails.md` allows it and permission is on file. Otherwise use a generic scenario labelled as an example, or a story written by the team.
10. **Set the sender and sign-off.** Sign off as the business, using the name exactly as it appears in `brand-book.md`. Do not sign as, or write as a letter from, a named person. If `voice-and-tone.md` describes the email as a letter from a named person, use the business sign-off and list the conflict under "Conflicts with the context pack".
11. **Add the footer block.** Write the sender identification line (business name and mailing address) and an unsubscribe line. If the mailing address is not in the context pack, mark it `[NEEDS CLIENT INPUT: mailing address for the footer]`. The sending tool supplies the live unsubscribe link.
12. **Sequences only: map before writing.** Fill in the sequence map first: number of emails (default 3 to 5, ask before going beyond 5), send gaps (default at least 3 days apart), one goal per email, and exit conditions (for example booked, replied or unsubscribed). Email 1 delivers whatever the reader signed up for. Write each email only after the map is agreed.
13. **Run the guardrail check** (section 4), fix what fails, and list what you could not fix.
14. **Save and present.** Save to `outputs/<client-slug>/<Asset ID>/<Asset ID>-copy-vN.md`, plus `<Asset ID>-sources.md` (rules: `outputs/README.md`), never overwriting an existing file (use `-v2`). Show the review checklist (section 5) and wait for approval.

---

## 3. Output template

Save as `outputs/<client-slug>/<Asset ID>/<Asset ID>-copy-vN.md`, plus `<Asset ID>-sources.md` (rules: `outputs/README.md`)

Use every heading and field below, in this order. If a field does not apply, write `N/A` and a few words why. Do not add, rename or reorder fields. Every email has exactly three subject options.

```markdown
Station: email
Date: YYYY-MM-DD
Context used: [list files]
Status: DRAFT – awaiting review

# Email: [Client], [short description]

## Run summary
| Field | Value |
|---|---|
| Run type | Calendar email / One-off / Sequence |
| Emails in this run | [number] |
| Calendar rows | [Asset IDs, or N/A] |
| Recipients | [who is on the list] |
| How they joined and consent basis | [express: how / implied: basis and expiry / NEEDS CLIENT INPUT] |
| Sender name and reply-to | [business name, address] |
| Ready to send? | Yes / NOT READY: [reason] |

## Sequence map
[Sequences only. Otherwise write "N/A: not a sequence."]
| # | Send day | Goal | Exit condition |
|---|---|---|---|

---

## Email [n] of [N]: [working title]

| Field | Value |
|---|---|
| Asset ID or sequence step | |
| Campaign and content pillar | |
| Reader (persona) | |
| Send day | |
| Goal (one) | |
| Call to action (one) | |
| KPI to read afterwards | |

**Subject line options**
| Option | Subject | Characters | Angle |
|---|---|---|---|
| A | | | |
| B | | | |
| C | | | |

**Recommended:** [A/B/C] – [one-sentence reason]

**Preview text:** [text] ([characters])

**Body**
[Greeting]

[Body copy]

**Button label and link:** [label] → [link or NEEDS CLIENT INPUT]

**Sign-off:** [business sign-off]

**Footer block:** [sender identification line] · [mailing address] · [unsubscribe line]

**Image alt text:** [text, or "No images"]

**Word count:** [number] (target: [from Specs or default])

**Facts used**
| Fact | Where it appears in the context pack |
|---|---|

**Gaps:** [NEEDS CLIENT INPUT: ...] items for this email, or "None"

[Repeat the whole "Email [n] of [N]" block for each email.]

---

## Guardrail check results
| Check (section 4) | Result: Pass / Fixed / Open | Note |
|---|---|---|

## Conflicts with the context pack
| Topic | Source A says | Source B says | Action |
|---|---|---|---|

## Questions for the client or the human
1.
```

---

## 4. Guardrail check

Before showing the output, confirm each item and fix anything that fails. These are practical checks, not legal advice.

- [ ] **Follows `context/guardrails.md`.** Claims, privacy, AI disclosure and audience sensitivity all pass.
- [ ] **No invented facts.** Every price, service, credential, result and name is in "Facts used" and traces to the context pack. Gaps are marked `[NEEDS CLIENT INPUT: ...]`.
- [ ] **Consent is stated.** The run summary says how each recipient joined. Express consent needs a positive opt-in (pre-checked boxes and silence do not count). Implied consent has a stated basis and is still within its time limit. The sender must be able to prove consent (Canadian Radio-television and Telecommunications Commission [CRTC], 2016, n.d.). If unknown, the run is marked NOT READY TO SEND.
- [ ] **Sender is identified.** The footer names the business and gives a mailing address that stays valid for at least 60 days after sending (CRTC, n.d.).
- [ ] **Unsubscribe is built in.** Every email has a one-step unsubscribe that stays valid for at least 60 days after sending. Requests are processed without delay and within 10 business days (CRTC, n.d.).
- [ ] **Subject lines are honest.** Each matches the content, has no fake "Re:" or "Fwd:", and has no urgency, scarcity, fear or guilt.
- [ ] **No avoid-list words.** Subject, preview text, body and button are clear of the avoid lists in `voice-and-tone.md` and `guardrails.md`.
- [ ] **One goal and one call to action,** taken from the approved list in `voice-and-tone.md`.
- [ ] **Sender and AI disclosure.** The sign-off is the business, not a named person. Nothing implies a person wrote it personally. The email is not a one-to-one message to a specific client; if it is, stop and tell the human, because `guardrails.md` governs who writes those.
- [ ] **Stories, quotes and images follow the privacy rules.** No real client name, voice, photo or story without written permission on file. Generic scenarios are labelled as examples.
- [ ] **Voice matches** the review checklist in `voice-and-tone.md`.
- [ ] **Accessible.** Images have alt text, link and button text describe the action, and the email reads clearly as plain text.

**Sources**
Canadian Radio-television and Telecommunications Commission. (n.d.). *Frequently asked questions about Canada's anti-spam legislation*. Retrieved November 12, 2026, from https://crtc.gc.ca/eng/com500/faq500.htm

Canadian Radio-television and Telecommunications Commission. (2016, July 27). *Enforcement advisory – Notice for businesses and individuals on how to keep records of consent*. https://www.canada.ca/en/radio-television-telecommunications/news/2016/07/enforcement-advisory-notice-for-businesses-and-individuals-on-how-to-keep-records-of-consent.html

---

## 5. Review checklist (human)

- [ ] Does each email have one goal and one call to action, and is it the action you want this reader to take?
- [ ] Does it pass the one-line test in `voice-and-tone.md`?
- [ ] Is every fact in "Facts used" correct, and is every `[NEEDS CLIENT INPUT]` filled in or on the question list?
- [ ] Do you know who is on the list and how they joined, and is that consent record kept somewhere you can find it?
- [ ] Are the sender name, mailing address and a working unsubscribe set up in the sending tool?
- [ ] Would the client be comfortable with this going out under the business name?

When approved: change status to `APPROVED – <date>`, commit, and suggest a commit message. After sending, give the chosen subject line, send day and results to `performance-report`.

---

## 6. Tool slot

**Job:** email writing and sending.
**Current tool:** see `playbook/tool-register.md` → Email.
**Default:** Claude for writing. No sending tool is chosen in the register yet; this station does not send. Before the first send, the chosen tool must supply the unsubscribe link, the sender identification and a place to keep consent records. Record the pick and the date in `playbook/tool-register.md`.
