---
name: video-short-form
description: Factory station 8 (creative line). Writes short-form video concepts, scripts, shot lists and on-screen text for Reels, TikTok, Shorts and similar, plus prompts for AI video tools. Use when asked for a video, script, Reel, TikTok, short-form content or storyboard.
---

# Station: Video and short-form

**Line:** Creative · **Needs:** content-calendar, positioning-messaging · **Feeds:** social, ad-creative, performance-report

**Job:** Plan videos that can be shot on a phone or produced with AI tools, ready to film or generate.

**Boundaries.** Every client fact (audiences, wording rules, CTAs, prices, hashtags, platforms, people, photos, colours, fonts and wardrobe) comes from the context files at run time. This file contains none. Check the files on every run; don't rely on memory.

---

## 1. Inputs

Load these before writing. If something is missing, mark it `[NEEDS CLIENT INPUT: ...]` rather than guessing.

- **Context files:**
  - `context/voice-and-tone.md`: tone by situation, audience and channel, language guide, words to use and avoid, approved CTAs, local hashtag
  - `context/positioning.md`: audiences, default audience, core promise, current focus area and the rules for using the positioning
  - `context/personas.md`: each audience's pressures, fears and words
  - `context/offer.md`: services, pricing and booking wording
  - `context/brand-book.md`: founder, imagery, photo library, colour, contrast, typography, wardrobe, confirmed platforms and handles
  - `context/guardrails.md`: claims, privacy, permissions, AI likeness and disclosure, audience sensitivity
- **Calendar row:** date, topic, pillar, audience, funnel stage, from `context/content-calendar.csv`. One video per row unless the calendar says otherwise.
- **Platform and length:** write only for platforms the context files confirm; the first confirmed platform is the default. Do not write for any other platform until it is confirmed. Mark it `[NEEDS CLIENT INPUT: confirm platforms and handles]`.
- **Who is on camera:** the founder named in `brand-book.md`, voiceover only, or nobody (hands, objects and text only). Confirm the founder is willing and available before writing a script that needs them on camera.
- **Existing footage and photos:** the photo library listed in `brand-book.md` and any video on file. Check each file's permission status in `guardrails.md`.
- **Source material (optional):** "Repurposing notes" from a blog post made by the blog-seo-geo station, or a post from the social station. Link back to the source when the video is built from one.
- **Target area:** the current focus area from `positioning.md`, and the service area wording from `voice-and-tone.md`.

## 2. Steps

1. **Read the calendar row.** Identify one audience and one idea. Use the default audience in `positioning.md` unless the row names another. One idea per video.
2. **Lead with the audience's real pressure.** Start from the pressure `positioning.md` and `personas.md` name for this audience. A line those files mark as supporting is used as support, never as the hook.
3. **Write the hook for the first 2 seconds.** It must work with the sound off: a spoken line plus on-screen text, or a strong visual in the brand look. Use a true, gentle observation or question. No fear, urgency, guilt or clickbait.
4. **Choose the format and length.** Pick the simplest format that carries the idea (talking to camera, voiceover over B-roll, text and keepsakes, step-by-step tip). Aim for the shortest length that delivers the idea, usually 15–30 seconds, and match the platform.
5. **Write the script beat by beat.** Use a table of time, visual, audio and on-screen text. Follow the short-video channel row and the audience row in `voice-and-tone.md`, and its rules for pronouns, spelling and reading level. Write for the ear. Calm and reassuring pace, not hype.
6. **Protect the decision-maker's control.** Follow the rules in `positioning.md` and `guardrails.md` on who decides, and use their approved example wording. Never imply the business decides for anyone, takes things from them or rushes them.
7. **Frame belongings the way the context files do.** Use the framing in `positioning.md` and `voice-and-tone.md`. Reassure rather than pressure.
8. **Write on-screen text and captions.** Short lines, large and readable. Use the minimum sizes and fonts in the typography section of `brand-book.md`, and only text and background pairs its contrast list marks as passing. Include open captions or a subtitle file so the video works without sound.
9. **Write the shot list.** For each shot: framing, location, props, light and who is in frame. Follow the imagery section of `brand-book.md`: what to choose, what to avoid and the wardrobe for anyone on camera.
10. **Add music and sound notes.** Calm, warm and unhurried. Use only licensed or platform-cleared music and record the source. No hype tracks, no urgency effects.
11. **Add the call to action.** One CTA from the approved list in `voice-and-tone.md`, matched to the funnel stage. Awareness videos may use a soft CTA (save, share, follow). No urgency CTAs.
12. **Write the caption and hashtags.** Caption follows the social channel row in `voice-and-tone.md`. Use its local hashtag as the anchor plus a few topical tags. Skip any area name or term the context files say to avoid.
13. **Write the AI video prompt (only if an AI tool is used).** Describe scene, subject, setting, light, camera movement, mood and duration in plain terms. Use generic people, never a real person's likeness. List what must not appear: everything the imagery section of `brand-book.md` says to avoid, plus logos and text rendered by the tool.
14. **Plan for reuse.** Note which cut-downs, stills or quotes can feed the social and ad-creative stations.
15. **Run the guardrail check** (section 4), fix issues, then save.

## 3. Output template

Save to: `outputs/<client-slug>/<Asset ID>/<Asset ID>-copy-vN.md`, plus `<Asset ID>-sources.md` (rules: `outputs/README.md`). The MP4 goes to OneDrive; the repo folder holds `<Asset ID>-video-link.md`, a thumbnail and captions.

Lowercase, hyphens, no spaces. Never overwrite an existing file; save a revision as `-v2`, `-v3`. Save video, images, subtitle files and other files from external tools in the same client folder with the same date-first naming (for example, `YYYY-MM-DD-video-<description>-1.mp4` and `YYYY-MM-DD-video-<description>-1.srt`).

Start every output with the status line `DRAFT – awaiting review`. A human changes it to `APPROVED – YYYY-MM-DD` after review.

Fill every field. If a value is unknown, write `[NEEDS CLIENT INPUT: ...]` instead of leaving it blank or guessing.

```markdown
# Video: <description, for example "<focus area> week 1 Reel">

DRAFT – awaiting review

## Brief
- **Client:** <business name exactly as in brand-book.md>
- **Date:** YYYY-MM-DD
- **Context used:** <each file with its version line>
- **Calendar rows covered:** <dates or row numbers>
- **Platforms:** <confirmed platforms and handles>
- **Positioning version used:** <version line from positioning.md>
- **Source (if any):** <blog or social post title and link, or "none">

---

## Video 1
- **Platform:** <first confirmed platform | other confirmed platform>
- **Length:** <seconds>
- **Aspect ratio:** <9:16 | other>
- **Production method:** <phone shoot | AI video tool | mixed>
- **On camera:** <founder (name from brand-book.md) | voiceover only | no one>
- **Audience:** <one audience named in positioning.md>
- **Pillar:** <from the calendar>
- **Funnel stage:** <awareness | consideration | decision>
- **Scheduled date and time:** <YYYY-MM-DD, time, time zone>

**Hook (first 2 seconds):**
<spoken line, on-screen text and opening visual>

**One idea:**
<the single idea this video carries>

**Script:**
| Time | Visual | Audio (voice, sound) | On-screen text |
|---|---|---|---|
| 0:00–0:02 | | | |
| 0:02–0:08 | | | |
| 0:08–0:15 | | | |
| 0:15–0:20 | | | |

**Shot list:**
| # | Framing | Location and props | Light | Who is in frame | Source (new shoot or file name) |
|---|---|---|---|---|---|
| 1 | | | | | |

**Captions and subtitles:**
- **Open captions or subtitle file:** <open captions | .srt file>
- **Subtitle file name:** YYYY-MM-DD-video-<description>-<n>.srt
- **Full transcript:** <text>

**Music and sound:**
- **Track or style:** <style that fits the tone row in voice-and-tone.md>
- **Source and licence:** <platform library | licensed | NEEDS CLIENT INPUT>

**Post caption:**
<full caption in the social tone from voice-and-tone.md>

**Hashtags:**
<local hashtag from voice-and-tone.md plus topical and local tags>

**Call to action:**
<one CTA from the approved list in voice-and-tone.md>

**Link:** <URL or "none">. Add UTM parameters if the performance report needs them.

**Cover image:**
- **Frame or concept:** <what it shows>
- **On-image text:** <exact text, or "none">
- **Alt text:** <one or two plain sentences>

**AI video prompt (if used):**
<scene, subject, setting, light, camera movement, mood, duration, and what must not appear>

**Permissions and disclosure:**
- **Everyone on camera has given written consent:** <confirmed | NEEDS CLIENT INPUT>
- **Client photos, footage or stories used:** <none | file names and permission status>
- **AI-generated or AI-edited content:** <none | description and disclosure wording>

**Output file names:**
- Video: YYYY-MM-DD-video-<description>-<n>.<ext>
- Subtitles: YYYY-MM-DD-video-<description>-<n>.srt
- Cover image: YYYY-MM-DD-video-<description>-<n>-cover.<ext>

**Reuse notes (for social and ad-creative stations):**
- **Cut-downs or stills:** <list>
- **Best line or quote:** <short, standalone, in brand voice>

---

## Video 2
<repeat the block above for every video>

---

## Measurement (for the performance report)
| Video | Primary goal | Metric to track |
|---|---|---|
| 1 | <consultation enquiries | guide downloads | link clicks | saves and shares> | <metric, for example 3-second views, watch time, saves> |

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

- [ ] One audience and one idea per video; the default audience from `positioning.md` unless told otherwise.
- [ ] The core promise in `positioning.md` is present or implied.
- [ ] The decision-making rules in `positioning.md` and `guardrails.md` are respected; nothing suggests the business decides, takes or rushes.
- [ ] Primary and secondary terms are used as the language guide in `voice-and-tone.md` says.
- [ ] Consultation, pricing and booking wording matches `voice-and-tone.md` and `offer.md` exactly. No word from the avoid lists in `voice-and-tone.md` or `guardrails.md`.
- [ ] No fear, urgency or guilt selling.
- [ ] No invented testimonials, prices, services, credentials, statistics or results. Testimonials only as `guardrails.md` allows, word for word. Prices only as written in `offer.md`; otherwise `[NEEDS CLIENT INPUT]`.
- [ ] Written consent on file for everyone filmed, as `guardrails.md` requires. This includes any photo or footage it lists as still awaiting permission.
- [ ] No identifiable client stories, names, homes or belongings shown without written permission on file.
- [ ] No AI-generated likeness of a real person: the founder, anyone named in `brand-book.md`, any client or family member. Follow the AI rules in `guardrails.md`; AI visuals use generic, non-identifiable people only.
- [ ] AI disclosure added wherever the platform or guardrails require it for AI-generated or AI-edited video, voice or images.
- [ ] Captions or subtitles included so the video works without sound.
- [ ] Music is licensed or platform-cleared, and the source is recorded.
- [ ] No claim that a context file marks `[NEEDS CLIENT INPUT]` until the client confirms it.
- [ ] No legal, financial, medical or real-estate advice; point to the right professional instead.
- [ ] Imagery follows the choose and avoid lists in `brand-book.md`.
- [ ] Spelling, reading level, exclamation marks and emoji follow `voice-and-tone.md`.
- [ ] Platform and handle confirmed before scheduling.

## 5. Review checklist (human)

1. Does the first 2 seconds stop the scroll for this audience, even with the sound off, without fear, guilt or urgency?
2. Does the video carry one idea for one audience, and ease their pressure while respecting who decides?
3. Does it sound and look like the client as `voice-and-tone.md` and `brand-book.md` describe them: warm, capable, unhurried, never syrupy or alarmist?
4. Is everyone on camera, every photo, every story and every music track cleared, and is any AI use disclosed?
5. Could the founder or the creative line film or generate it from the script and shot list without asking questions?
6. Are the captions, CTA, link and hashtags correct, and does the primary term from `voice-and-tone.md` lead?

## 6. Tool slot

**Job:** scripting and video production.

Take tool names from `playbook/tool-register.md`. Do not hard-code them here, so this station stays correct when the register changes.

| Role | Used for | Tool (from register) |
|---|---|---|
| Scripting | Draft the hook, script, shot list and captions from the calendar row and context files, then apply the guardrail check in section 4 | `[NEEDS CLIENT INPUT: tool from register]` |
| Video production | Edit phone footage or generate AI video from the prompt in the output file | `[NEEDS CLIENT INPUT: tool from register]` |
| Captions | Create open captions or the subtitle file | `[NEEDS CLIENT INPUT: tool from register]` |

**Rules for using tools:**

- Never upload client photos, footage, names or voices to a tool without confirmed written permission.
- Never use a tool to clone or imitate a real person's face or voice.
- Check the AI tool's licence terms for commercial use before publishing.
- Nothing is scheduled or published until a human has approved it.
- Log what you used in "Tools used" in the output file.
- If no tool is registered for a role, do that step manually and say so in "Gaps and assumptions."
