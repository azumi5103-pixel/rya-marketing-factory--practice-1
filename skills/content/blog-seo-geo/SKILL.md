---
name: blog-seo-geo
description: Factory station 5 (content line). Writes search-optimized blog articles built to rank in search engines and be cited by AI answer engines (GEO), from the content calendar and positioning. Use when asked for a blog post, article, SEO content, GEO content, FAQ content or a pillar page.
---

# Station: Blog, SEO and GEO

**Line:** Content · **Needs:** content-calendar, positioning-messaging · **Feeds:** email, social, performance-report

**Job:** Publish content that people find through search and that AI tools quote when answering questions.

**Boundaries.** Every client fact (audiences, wording rules, CTAs, prices, areas, office location, founder background, testimonials, pages and guides) comes from the context files at run time. This file contains none. Check the files on every run; don't rely on memory.

---

## 1. Inputs

Load these before writing. If something is missing, mark it `[NEEDS CLIENT INPUT: ...]` rather than guessing.

- **Context files:**
  - `context/voice-and-tone.md`: tone by situation, audience and channel, language guide, words to use and avoid, approved CTAs, service area wording
  - `context/positioning.md`: audiences, default audience, core promise, current focus area and the rules for using the positioning
  - `context/personas.md`: each audience's pressures, fears, words and where they look for help
  - `context/offer.md`: services, pricing, booking wording and resources offered at no cost
  - `context/brand-book.md`: founder background, testimonials, office location, imagery, keyword decisions
  - `context/guardrails.md`: claims, privacy, permissions, AI disclosure and audience sensitivity
- **Content calendar entry:** topic, publish date, funnel stage, from `context/content-calendar.csv`.
- **Audience:** one audience named in `positioning.md` per article. Use its default audience unless the calendar names another.
- **Target question:** the exact question that audience types into a search engine or asks an AI tool, in their words. Start from the searches and "in their words" lines in `personas.md`.
- **Keywords:** primary phrase plus 2–4 secondary phrases. Use the primary and secondary terms as the language guide in `voice-and-tone.md` says, including where the secondary term may appear. Check the keyword plan if `brand-book.md` says one exists.
- **Location to target:** the current focus area from `positioning.md`, the service area wording from `voice-and-tone.md`, and the office location from `brand-book.md`. Never imply an office anywhere else.
- **Internal pages to link to:** 2–4 service pages, the consultation page and any no-cost resource listed in `offer.md`. Ask for live URLs; do not invent them.
- **Sources:** client facts from the context files, plus named third-party sources for any statistic.

## 2. Steps

1. **Choose one audience and one question.** Write the target question as that person would ask it. Confirm intent (informational, comparison, ready to book) and match the article to it.
2. **Lead with the direct answer.** In the first 40–60 words, answer the question plainly in a self-contained paragraph an AI tool could quote without extra context. Use the primary term from `voice-and-tone.md` in it where natural.
3. **Lead with the audience's real pressure.** Open on the pressure `positioning.md` and `personas.md` name for this audience. A line those files mark as supporting is used as support, never as the headline.
4. **Outline with question-style headings.** One H1, H2s phrased as questions, H3s only where they help. Short paragraphs (2–4 sentences), lists and steps where useful.
5. **Protect the decision-maker's control throughout.** Follow the rules in `positioning.md` and `guardrails.md` on who decides, and use their approved example wording. Never imply the business decides for anyone, takes things from them or rushes them.
6. **Frame belongings the way the context files do.** Use the framing in `positioning.md` and `voice-and-tone.md`. Reassure, don't pressure.
7. **Show expertise without unsupported claims.** Use the founder's background and community roles exactly as `brand-book.md` states them, and practical guidance on the client's process from `offer.md`. Use testimonials only as `guardrails.md` allows, word for word.
8. **Add local signals.** Mention the focus area (or the topic's target area) naturally, with the full service area stated once, in the wording `voice-and-tone.md` gives. Skip any area name it says to avoid. Hashtags belong to social repurposing only.
9. **Write the FAQ block.** 3–6 questions from related searches and real family questions, each answered in 1–3 standalone sentences.
10. **Write metadata.** Meta title (≤60 characters, key phrase near the front) and meta description (150–160 characters, benefit plus a calm reason to click). Lowercase hyphenated slug.
11. **Add the call to action.** Use the primary CTA from the approved list in `voice-and-tone.md`, or another CTA from that list that fits the funnel stage. No urgency CTAs.
12. **Add internal links and schema notes** (see template).
13. **Run the guardrail check** (section 4), fix issues, then save.

## 3. Output template

Save to: `outputs/<client-slug>/<Asset ID>/<Asset ID>-copy-vN.md`, plus `<Asset ID>-sources.md` (rules: `outputs/README.md`)

Start every output with the status line `DRAFT – awaiting review`. A human changes it to `APPROVED – YYYY-MM-DD` after review.

```markdown
# Blog: <working title>

DRAFT – awaiting review

**Client:** <business name exactly as in brand-book.md>
**Date:** YYYY-MM-DD
**Context used:** <each file with its version line>
**Audience:** <one audience named in positioning.md>
**Funnel stage:** <awareness | consideration | decision>
**Target area:** <focus area from positioning.md | wider service area>
**Positioning version used:** <version line from positioning.md>

## Target question
<exact question the audience types or asks an AI>

## SEO metadata
- **Primary keyword:**
- **Secondary phrases:**
- **Meta title:** <≤60 characters>
- **Meta description:** <150–160 characters>
- **URL slug:** /<slug>

## Article

# <H1 matching the target question>

<Direct answer paragraph, 40–60 words, quotable on its own>

## <H2 as a question>
<body>

## Frequently asked questions

### <Question>
<Answer, 1–3 sentences>

<Call to action, calm, no urgency>

## Sources
- <Source, link, claim it supports>

## Suggested internal links
| Anchor text | Target page | Placement |
|---|---|---|

## Schema notes
- BlogPosting (author: the founder or the business, names as in brand-book.md; publish and updated dates)
- FAQPage for the FAQ block
- LocalBusiness: office location from brand-book.md; areaServed from the service area in voice-and-tone.md

## Gaps and assumptions
- <every [NEEDS CLIENT INPUT: ...] item and anything the reviewer must confirm>
```

## 4. Guardrail check

Follows `context/guardrails.md`. Also confirm:

- [ ] One clear audience; the default audience from `positioning.md` unless told otherwise.
- [ ] The core promise in `positioning.md` is present.
- [ ] The decision-making rules in `positioning.md` and `guardrails.md` are respected; nothing suggests the business decides, takes or rushes.
- [ ] Primary and secondary terms are used as the language guide in `voice-and-tone.md` says.
- [ ] Consultation, pricing and booking wording matches `voice-and-tone.md` and `offer.md` exactly. No word from the avoid lists in `voice-and-tone.md` or `guardrails.md`.
- [ ] No fear, urgency or guilt selling.
- [ ] No invented prices, services, credentials, testimonials, statistics or results. Prices only as written in `offer.md`; otherwise `[NEEDS CLIENT INPUT]`.
- [ ] No claim that a context file marks `[NEEDS CLIENT INPUT]` until the client confirms it.
- [ ] Every outside fact is sourced. No legal, financial, medical or real-estate advice; point to estate lawyers, advisors, doctors or realtors instead.
- [ ] No keyword stuffing. Spelling, reading level, pronouns, exclamation marks and emoji follow `voice-and-tone.md`.
- [ ] No client photos or names used without the permission `guardrails.md` requires.

## 5. Review checklist (human)

1. Would an AI tool quote the first paragraph as a complete, correct answer to the target question?
2. Does it speak to one audience and open on their real pressure?
3. Are the decision-making rules respected in every step, and are belongings framed the way the context files say?
4. Does the primary term lead, with the secondary term used only where the language guide allows?
5. Is every claim sourced or confirmed, and every gap marked?
6. Does it sound like the client as `voice-and-tone.md` describes them: warm, capable, never syrupy or alarmist? Is the CTA calm?

## 6. Tool slot

**Job:** search research and long-form writing.

Record the actual tools in `playbook/tool-register.md`: keyword tool, AI-search check (does an AI tool answer or cite this page for the target question?) and writing tool. If none is registered for a role, list that in "Gaps and assumptions."
