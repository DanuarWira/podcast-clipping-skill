---
name: podcast-clipping
description: "Analyze, score, edit, and verify podcast short-form clips."
version: 0.2.0
author: Danuar Wiranata, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [video, clipping, podcast, shorts, subtitles, editing, scoring]
    related_skills: []
---

# Podcast Clipping Skill

End-to-end workflow for turning long podcasts into short-form clips for TikTok, Reels, and YouTube Shorts. It covers ingest, transcript alignment, moment discovery, clip scoring, hook writing, narrative shaping, crop and camera direction, subtitles, audio, color, graphics, rendering, QA, publishing metadata, and post-publication learning.

Treat source media as evidence. Never invent quotes, timestamps, speaker intent, performance numbers, or claims. A style reference is a hypothesis, not proof that an edit will perform.

## When to Use

Use for podcast, interview, webinar, livestream, or long-form conversation clipping.

Do not use for invented source footage, generic social copy without media, or final mastering when no source and no measurable target exist.

## Required Inputs

- Source video or audio.
- Timestamped transcript, or enough access to generate one.
- Target platform, language, audience, and desired duration.
- Brand rules, logo, fonts, colors, and rights constraints when available.
- Optional: examples, previous performance data, and speaker names.

If an input is unknown, mark it `UNKNOWN`. Do not silently assume it.

## Deliverables

Create one project folder with:

- `01-source-report.md`: media metadata, rights notes, speakers, transcript coverage, and source defects.
- `02-transcript.json` or timestamped transcript.
- `03-moment-map.md`: all notable moments, not only selected clips.
- `04-clip-plan.md`: ranked candidates and rejection reasons.
- `05-edit-decision-list.md`: executable timeline instructions per clip.
- `06-caption-pack.md`: hooks, titles, descriptions, CTAs, and hashtags.
- `07-qa-report.md`: technical, editorial, accessibility, and policy checks.
- `08-learning-log.md`: post-publish metrics and changes for the next batch.
- Rendered preview and final files per selected clip.

Templates live in `templates/`. Rules live in `references/`.

## Pipeline

### 1. Ingest and source audit

Inspect duration, codec, resolution, frame rate, variable-frame-rate status, audio channels, loudness, orientation, camera angles, and missing sections. Extract representative frames and identify speakers, shot boundaries, and screen content.

Completion: metadata table exists and every source defect is logged.

### 2. Transcript and alignment

Generate or import a transcript with word or phrase timestamps. Correct names, jargon, numbers, slang, code-switching, and negations. Mark uncertain words with `[UNCLEAR]`. Keep speaker turns, laughter, pauses, interruptions, and overlap.

Completion: every selected phrase maps to source time and corrected text is traceable to audio.

### 3. Moment discovery

Scan the whole source. Label moments by type:

- revelation, contrarian view, conflict, story, failure, transformation;
- practical framework, checklist, mistake, warning, prediction;
- emotional vulnerability, humor, surprise, reaction, quotable line;
- visual demonstration, before/after, object, screen, or audience interaction.

Mark setup, tension, turn, payoff, and exit for each moment. Also mark dead air, repetition, low-context references, and claims needing review.

Completion: moment map covers full source and includes rejected moments with reasons.

### 4. Candidate construction

Build clips around one idea. Start as late as possible without losing context and end after payoff, reaction, or useful final beat. Prefer 20 to 60 seconds for first pass; use 60 to 90 seconds only when narrative value clearly justifies it.

Test each candidate without the full podcast: who is speaking, what is the question, why should a viewer continue, and what changes by the end? Reject clips that need misleading cropping, missing qualifiers, or unrelated context.

### 5. Scoring and selection

Score every candidate using `references/scoring.md`. Keep raw dimension scores, penalties, confidence, and rejection reason. Score editorial potential, not guaranteed views.

Create three hook variants per selected candidate: curiosity, conflict, and utility. Select based on source tone, audience, and promise supported by the footage.

Completion: every selected clip has score breakdown, source quotes, hook, risk flags, and a decision.

### 6. Narrative and retention pass

Map the first two seconds, context beat, escalation, payoff, and final frame. Remove greetings and filler only when meaning stays intact. Preserve qualifiers and speaker intent. Use a cold open only when the edit can return to enough context.

Run a spoken-only test and a muted test. Spoken-only must make sense; muted test must communicate speaker changes, hook, and emotional direction through captions and framing.

### 7. Visual edit design

Choose a style from `references/editing-style.md` and record why it fits. Define:

- format and safe margins;
- base crop for each speaker;
- shot changes and punch-ins;
- subtitle style and emphasis rules;
- b-roll, screenshots, diagrams, and overlays;
- transitions, SFX, music, and silence;
- grade, skin-tone target, and contrast;
- end card and CTA behavior.

Every effect needs a purpose: comprehension, emphasis, continuity, rhythm, or brand identity. Remove decoration without a purpose.

### 8. Subtitle and accessibility pass

Use phrase-synced captions, two lines maximum by default, readable contrast, and safe placement above platform UI. Emphasize meaning-bearing words, not every word. Verify names, numbers, negations, punctuation, and speaker changes.

Provide burned-in captions for the short-form render unless the user requests sidecar captions. Keep an SRT/VTT sidecar when possible.

### 9. Audio and color pass

Clean dialogue before loudness normalization. Reduce noise without metallic artifacts. Keep speech intelligible above music and effects. Inspect peaks and channel balance. Correct exposure and white balance before applying a restrained look; match cameras and preserve natural skin tones.

Do not claim loudness compliance unless measured. Record the tool, target, and result.

### 10. Render and QA

Render a low-resolution review first, then final. Inspect first second, every cut, captions, punch-ins, graphics, transitions, audio, final payoff, and export dimensions. Use `vision_analyze` on sampled frames and `terminal` for media probes.

Completion: `07-qa-report.md` has pass/fail per check, evidence, and unresolved items. A clip with a failed hard check is not deliverable.

### 11. Publish package and learning loop

Generate platform-specific title, description, CTA, and hashtags from the selected hook and source. Keep claims factual. After publication, record impressions, 1-second and 3-second hold, average watch time, completion rate, rewatches, shares, saves, comments, profile visits, and follows when available.

Compare performance by hook, topic, duration, opening frame, subtitle treatment, speaker, and style. Do not infer causality from one clip. Update `08-learning-log.md` with repeated patterns and the next test.

## Hard Editorial Rules

- No fabricated quote, timestamp, statistic, reaction, or performance claim.
- No edit that changes a speaker's meaning by removing a qualifier.
- No unsupported medical, financial, political, legal, defamatory, or dangerous claim without human review.
- No copyrighted music, b-roll, logo, or image without permission or a documented license decision.
- No fake urgency, fake controversy, or `you won't believe this` without a specific source-backed reason.
- Never disclose private information visible in frames unless authorized.
- Keep faces, captions, and important graphics within safe areas.
- Never use constant zoom, random SFX, or word-by-word emphasis as a substitute for story.

## Candidate Schema

```yaml
id: C001
source_in: 00:12:34.500
source_out: 00:13:21.000
speakers: [Host, Guest]
category: contrarian_view
setup: "Exact source-backed setup"
tension: "What creates forward motion"
payoff: "Exact source-backed payoff"
opening_quote: "Exact source wording"
payoff_quote: "Exact source wording"
score: 0
score_breakdown: {hook: 0, payoff: 0, emotion: 0, clarity: 0, replay: 0, visual: 0, audio: 0}
penalties: []
confidence: medium
hook_variants: {curiosity: "", conflict: "", utility: ""}
recommended_style: educational
risk_flags: []
decision: select
```

## Scoring Formula

Use the rubric in `references/scoring.md`. Keep both raw and adjusted scores:

`adjusted_score = raw_score - penalties`

Do not compare scores across different audiences without recording audience and platform. Confidence reflects evidence quality, not predicted virality.

## Verification Checklist

A clip passes only when:

- source timestamps and transcript evidence match;
- opening hook is source-faithful;
- setup, tension, and payoff survive trimming;
- subtitles match speech and stay readable in safe margins;
- no black frames, accidental dead air, jump cuts, or broken graphics remain;
- speech is intelligible and audio is not clipped;
- grade is consistent and skin tones are natural;
- export matches requested aspect ratio, frame rate, and resolution;
- rights and sensitive-content flags are recorded;
- final frame preserves the payoff or intentional CTA;
- every unknown is explicitly listed.

Run the self-check for every candidate: timestamps, opening quote, payoff quote, score, confidence, decision, and risk flags must be non-empty. Use an assert-based check or a small standard-library script; no test framework is needed.

## Pitfalls

- High emotion with low clarity usually creates comments but poor completion.
- High clarity with no tension often becomes useful but scrollable content.
- A strong quote can fail if the first frame does not visually identify the speaker or topic.
- Automatic face tracking can jump across cuts and must be reviewed.
- Automatic captions commonly corrupt names, numbers, slang, and negations.
- TikTok reference pages may be blocked. Never claim visual analysis without retrieved evidence.
- One viral clip is not a reliable style rule. Learn from batches.
