---
name: multilingual-subtitling
description: "Create accurate mixed-language subtitles for podcast clips."
version: 0.1.0
author: Danuar Wiranata, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [subtitles, transcription, Indonesian, English, code-switching, ASR]
    related_skills: [podcast-clipping]
---

# Multilingual Subtitling Skill

Use for accurate subtitles on mixed Indonesian and English podcast speech, including formal Indonesian, slang, abbreviations, pronunciation variants, code-switching, names, numbers, and technical terms. The skill separates transcription from subtitle styling: never rewrite spoken language during transcription, and never use a language model to guess inaudible words without marking uncertainty.

## When to Use

Use when audio contains Indonesian, English, or rapid switching between them. Use for burned-in captions and SRT/VTT sidecars.

Do not use translation mode unless explicitly requested. Default output is faithful same-language transcription.

## Accuracy Contract

Every subtitle token must be one of:

- heard and verified from audio;
- supported by context but marked `[UNCLEAR]`;
- a proper noun or technical term verified against a source glossary;
- intentionally omitted as non-speech noise, with the omission rule recorded.

Never normalize slang into formal Indonesian, translate English automatically, or replace a speaker's grammar with polished copy. Preserve meaning, code-switches, repeated words, fillers that affect meaning, and laughter or relevant reactions.

## Inputs and Outputs

Inputs:

- source video/audio;
- optional transcript, speaker list, glossary, and reference links;
- target format, font, reading speed, and safe area.

Outputs:

- word- or phrase-timestamped master transcript;
- reviewed SRT or VTT;
- subtitle render preview;
- glossary of names, slang, acronyms, and technical terms;
- `subtitle-qa.md` with confidence, corrections, and unresolved audio.

## Procedure

1. Inspect audio channels, sample rate, duration, background noise, overlap, and speaker turns. Completion: source audio report exists.
2. Run ASR with language detection or a multilingual model. Keep word timestamps, per-segment confidence, and speaker diarization when available. Do not trust one-pass output.
3. Detect language per word or phrase. Label `id`, `en`, `mixed`, or `unknown`. Treat language detection as a review aid, not truth.
4. Build a glossary before correction. Add speaker names, brands, places, acronyms, slang, Indonesian-English terms, and likely homophones. Verify against audio and available source context.
5. Perform a correction pass against audio. Replay every low-confidence segment, language boundary, number, name, negation, punchline, and technical term at normal and reduced speed. Correct only what is audible.
6. Perform a context pass. Check pronouns, tense, negation, turn-taking, and whether a cut removed the phrase needed to understand the sentence. Mark unresolved words `[UNCLEAR]`, never silently invent them.
7. Segment captions for reading. Prefer phrase boundaries, maximum two lines, and avoid splitting names, noun phrases, numbers, or a word with its negation. Use target reading speed from `references/segmentation.md`.
8. Assign speaker labels only when useful and reliable. Keep label styling distinct from spoken text. Never attribute overlap with low confidence.
9. Export SRT/VTT, then render a burned-in preview. Inspect sync at speech onset, pauses, interruptions, laughter, cuts, and final word.
10. Run QA using `references/qa.md`. A subtitle is not approved when unresolved words affect the hook, claim, punchline, name, number, or negation.

## Mixed-Language Rules

- Keep English words as spoken: `deadline`, `mindset`, and `feedback` remain English unless translation is requested.
- Preserve Indonesian slang: `nggak`, `gak`, `kepo`, `gue`, `lu`, ` banget`, and repeated forms remain faithful to the recording.
- Do not force one spelling when the speaker's form is clear and intentional.
- For unclear slang, replay audio and consult context, then use `[UNCLEAR]` if still uncertain.
- Keep code-switch boundaries natural. Do not split a caption immediately before or after a short switched phrase unless readability requires it.
- Verify English names, acronyms, and technical terms with a glossary, not phonetic guessing.
- Preserve numbers exactly when audible. If `15` versus `50` is unclear, mark it and flag human review.

## Accuracy Tiers

- `A`: audio reviewed, glossary checked, no unresolved material words.
- `B`: audio reviewed, minor uncertain filler or low-impact word remains.
- `C`: ASR-only or substantial overlap/noise remains. Not ready for final publication.

Selected social clips require Tier A for hooks, claims, names, numbers, negations, punchlines, and calls to action. Tier B may ship only when uncertainty is clearly outside meaning. Tier C is preview-only.

## Subtitle Style

- Two lines maximum by default.
- Break at phrase boundaries, not arbitrary character counts.
- Keep text inside vertical-video safe margins.
- Use high contrast and a readable outline or shadow.
- Highlight semantic words sparingly; never recolor every language switch automatically.
- Do not change text to create a hook. Hooks belong in a separate overlay and must be source-faithful.
- Use burned-in subtitles plus SRT/VTT when downstream editing needs accessibility or searchability.

## Verification

For every final clip, record:

- ASR model and language mode;
- audio and transcript versions;
- number of segments manually reviewed;
- unresolved tokens and their timestamps;
- glossary entries checked;
- maximum reading speed;
- sync spot checks;
- subtitle file format and render settings;
- final accuracy tier.

Run a self-check: assert each subtitle has start < end, non-empty text, valid timestamp format, no accidental double spaces, and no unresolved token in hook, claim, name, number, negation, or punchline.

## Pitfalls

- ASR confidence is not word truth, especially at Indonesian-English boundaries.
- Diarization can swap speakers after interruptions; inspect every speaker label.
- Automatic punctuation can reverse meaning around `nggak`, `not`, and `bukan`.
- Translation hides whether the original was transcribed correctly. Keep source-language master first.
- Subtitle readability and transcription accuracy are separate QA gates.
