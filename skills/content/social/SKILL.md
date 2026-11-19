---
name: social
description: Factory station 4 (content line). Writes platform-ready social posts from the content calendar, in the client's voice, with captions, hooks, hashtags and visual briefs. Use when asked for social posts, captions, a week of social content or platform-specific copy.
---

# Station: Social

**Line:** Content · **Needs:** content-calendar · **Feeds:** performance-report

**Job:** Turn calendar slots into posts that are ready to schedule.

**Boundaries.** Every client fact (audiences, wording rules, CTAs, prices, hashtags, platforms, photos, colours and fonts) comes from the context files at run time. This file contains none. Check the files on every run; don't rely on memory.

---

## 1. Inputs

Load these before writing. If something is missing, mark it `[NEEDS CLIENT INPUT: ...]` rather than guessing.

- **Context files:**
  - `context/voice-and-tone.md`: tone by situation, audience and channel, language guide, words to use and avoid, approved CTAs, local hashtag
  - `context/positioning.md`: audiences, default audience, core promise, current focus area and the rules for using the positioning
  - `context/personas.md`: each audience's pressures, fears and words
  - `context/offer.md`: services, pricing and booking wording
  - `context/brand-book.md`: imagery, photo library, colour, typography, confirmed platforms and handles
  - `context/guardrails.md`: claims, privacy, permissions, AI disclosure and audience sensitivity
- **Calendar rows:** the rows to cover (date, topic, pillar, audience, funnel stage) from `context/content-calendar.csv`. One post per row unless the calendar says otherwise.
- **Platforms the client actually uses:** write only for platforms and handles the context files confirm. For any other platform, write `[NEEDS CLIENT INPUT: confirm platforms and handles]`.
- **Source material (optional):** the "Repurposing notes" from a blog post made by the blog-seo-geo station (one-sentence takeaway, pull quote or tip, best audience). Link back to the article when the post is built from one.
- **Approved visuals:** the photo library listed in `brand-book.md`. Check each file's permission status in `guardrails.md`.
- **Target area:** the current focus area from `positioning.md`, and the service area wording from `voice-and-tone.md`.

## 2. Steps

1. **Read the calendar row.** Identify one audience and one content pillar. Use the default audience in `positioning.md` unless the row names another. Each post carries one audience and one pillar, never a mix.
2. **Lead with the audience's real pressure.** Start from the pressure `positioning.md` and `personas.md` name for this audience. A line those files mark as supporting is used as support, never as the hook.
3. **Write the hook (first line).** It must work alone, before "more" or the cut-off. Use a specific, true, gentle observation or question. No fear, urgency, guilt or clickbait.
4. **Write the caption in the social tone.** Use the social channel row and the audience row in `voice-and-tone.md`. Follow its rules for pronouns, spelling, reading level, exclamation marks and emoji.
5. **Protect the decision-maker's control.** Follow the rules in `positioning.md` and `guardrails.md` on who decides, and use their approved example wording. Never imply the business decides for anyone, takes things from them or rushes them.
6. **Frame belongings the way the context files do.** Use the framing in `positioning.md` and `voice-and-tone.md`. Reassure rather than pressure.
7. **Adapt to the platform.** Match length, format and hashtag practice to each confirmed platform (for example, Instagram: strong first line, short paragraphs, 3–6 hashtags; carousel or Reel for step-by-step tips). Do not copy-paste one caption across platforms.
8. **Add hashtags.** Use the local hashtag `voice-and-tone.md` names as the anchor. Add a few topical tags built from the primary and secondary terms in its language guide, and local tags that fit the post. Skip any area name or term the context files say to avoid.
9. **Add one call to action.** Choose from the approved CTA list in `voice-and-tone.md`, matched to the funnel stage. Awareness posts may use a soft CTA (save, share, read more). No urgency CTAs.
10. **Write the visual brief.** Describe the image, carousel or short video for the creative line. Follow the imagery section of `brand-book.md` (what to choose and what to avoid), its palette and its typography. Give any on-image text. Name the exact photo file when one fits and `guardrails.md` shows its permission is confirmed.
11. **Write alt text.** One or two plain sentences describing what is shown, with no keyword stuffing and no names of private individuals.
12. **Run the guardrail check** (section 4), fix issues, then save.

## 3. Output template

Save to: `outputs/<client-slug>/<Asset ID>/<Asset ID>-copy-vN.md`, plus `<Asset ID>-sources.md` (rules: `outputs/README.md`)

Start every output with the status line `DRAFT – awaiting review`. A human changes it to `APPROVED – YYYY-MM-DD` after review.

Fill every field. If a value is unknown, write `[NEEDS CLIENT INPUT: ...]` instead of leaving it blank or guessing.

```markdown
# Social: <description, for example "<focus area> week 1">

DRAFT – awaiting review

## Brief
- **Client:** <business name exactly as in brand-book.md>
- **Date:** YYYY-MM-DD
- **Context used:** <each file with its version line>
- **Calendar rows covered:** <dates or row numbers>
- **Platforms:** <confirmed platforms and handles>
- **Positioning version used:** <version line from positioning.md>
- **Source article (if any):** <blog title and link, or "none">

---

## Post 1
- **Platform:** <Instagram | Facebook | LinkedIn | other confirmed platform>
- **Format:** <single image | carousel | Reel | text post | story>
- **Scheduled date and time:** <YYYY-MM-DD, time, time zone>
- **Audience:** <one audience named in positioning.md>
- **Pillar:** <from the calendar>
- **Funnel stage:** <awareness | consideration | decision>

**Hook (first line):**
<text>

**Caption:**
<full caption, including the hook>

**Hashtags:**
<local hashtag from voice-and-tone.md plus topical and local tags>

**Call to action:**
<one CTA from the approved list in voice-and-tone.md>

**Link:** <URL or "none">. Add UTM parameters if the performance report needs them.

**Visual brief:**
- **Concept:** <what the image, carousel or video shows>
- **Photo file or shot:** <file name from the library, or description for a new shot>
- **On-image text:** <exact text, or "none">
- **Colours and type:** <palette and fonts from brand-book.md>
- **Permission:** <confirmed | NEEDS CLIENT INPUT>

**Alt text:**
<one or two plain sentences>

---

## Post 2
<repeat the block above for every post>

---

## Measurement (for the performance report)
| Post | Primary goal | Metric to track |
|---|---|---|
| 1 | <consultation enquiries | guide downloads | link clicks | saves and shares> | <metric> |

## Tools used
| Role | Tool | Used for |
|---|---|---|

## Guardrail check result
- [ ] Section 4 checklist completed
- <list any items that failed and how they were fixed>

## Gaps and assumptions
- <every [NEEDS CLIENT INPUT: ...] item and anything the reviewer must confirm>
```

## 4. Guardrail check

Follows `context/guardrails.md`. Also confirm:

- [ ] One audience and one pillar per post; the default audience from `positioning.md` unless told otherwise.
- [ ] The core promise in `positioning.md` is present or implied.
- [ ] The decision-making rules in `positioning.md` and `guardrails.md` are respected; nothing suggests the business decides, takes or rushes.
- [ ] Primary and secondary terms are used as the language guide in `voice-and-tone.md` says.
- [ ] Consultation, pricing and booking wording matches `voice-and-tone.md` and `offer.md` exactly. No word from the avoid lists in `voice-and-tone.md` or `guardrails.md`.
- [ ] No fear, urgency or guilt selling.
- [ ] No invented testimonials, prices, services, credentials, statistics or results. Testimonials only as `guardrails.md` allows, word for word. Prices only as written in `offer.md`; otherwise `[NEEDS CLIENT INPUT]`.
- [ ] No identifiable client stories, names, homes or photos without the written permission `guardrails.md` requires. This includes any photo it lists as still awaiting permission.
- [ ] No claim that a context file marks `[NEEDS CLIENT INPUT]` until the client confirms it.
- [ ] No legal, financial, medical or real-estate advice; point to the right professional instead.
- [ ] Alt text included on every image and accurate to the image.
- [ ] AI disclosure added wherever the platform or guardrails require it for AI-generated or AI-edited images.
- [ ] Spelling, reading level, exclamation marks and emoji follow `voice-and-tone.md`.
- [ ] Hashtags are relevant, not stuffed, and include the local hashtag from `voice-and-tone.md`.
- [ ] Platform and handle confirmed before scheduling.

## 5. Review checklist (human)

1. Does the first line stop the scroll for this specific audience, without fear, guilt or urgency?
2. Does the post speak to one audience and one pillar, and ease their pressure while respecting who decides?
3. Does it sound like the client as `voice-and-tone.md` describes them: warm, capable, never syrupy or alarmist?
4. Is every claim, testimonial and price confirmed, and is every photo and story cleared for public use?
5. Does the visual brief match the brand look, and could the creative line build it without asking questions?
6. Is the CTA calm and right for the funnel stage, and are the link, hashtags and alt text correct?

## 6. Tool slot

**Job:** social copy and scheduling.

Take tool names from `playbook/tool-register.md`. Do not hard-code them here, so this station stays correct when the register changes.

| Role | Used for | Tool (from register) |
|---|---|---|
| Copy drafting | Draft hooks and captions from the calendar row and context files, then apply the guardrail check in section 4 | `[NEEDS CLIENT INPUT: tool from register]` |
| Scheduling | Load approved posts with dates, times, links and alt text | `[NEEDS CLIENT INPUT: tool from register]` |

**Rules for using tools:**

- Never paste client details beyond what the context files allow, and never paste client photos or names into a tool without confirmed permission.
- Nothing is scheduled or published until a human has approved it.
- Log what you used in "Tools used" in the output file.
- If no tool is registered for a role, do that step manually and say so in "Gaps and assumptions."
