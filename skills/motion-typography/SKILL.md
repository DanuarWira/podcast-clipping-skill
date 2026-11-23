---
name: motion-typography
description: "Design motion typography and visual presets for clips."
version: 0.1.0
author: Danuar Wiranata, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [motion graphics, typography, captions, presets, video editing]
    related_skills: [podcast-clipping, multilingual-subtitling]
---

# Motion Typography Skill

Use this skill to design text supers, kinetic typography, background treatments, sound accents, and reusable motion presets for short-form clips. Keep subtitles separate from decorative text. Every animation must improve hook clarity, explanation, rhythm, or payoff.

## Workflow

1. Read transcript, audience, platform, and brand direction. Completion: style profile selected.
2. Mark hook, semantic keywords, list steps, proof moments, payoff, and CTA. Completion: every motion event has a source timestamp.
3. Choose one profile: `classic-motion`, `technical-ui`, `podcast-insight`, `tutorial`, `before-after`, or `comedy`. Completion: reason recorded.
4. Build a motion map with text, layer, in/out time, animation, easing, color, background, and SFX. Completion: no unassigned animation.
5. Render a low-resolution preview. Check readability, overlap, timing, safe margins, and attention load. Completion: QA passes.
6. Export reusable preset data and final render settings. Completion: another clip can reuse preset structure.

## Profiles

### Classic motion

Use large short supers, restrained textured or solid background, preset timing, one accent color, and subtle whoosh, click, or pop accents. Keep six words or fewer per visual where possible. Do not stack multiple large animated text blocks.

### Technical UI

Use screen recording, repository, terminal, chart, or product UI as evidence. Highlight the exact region with a mask, box, cursor path, or controlled zoom. Preserve commands and package names exactly.

### Podcast insight

Keep speaker and faithful multilingual subtitles primary. Use keyword supers only on claims, emotional turns, or payoff. Do not rewrite slang, English switches, or qualifiers.

### Tutorial

Use numbered step cards, active-state emphasis, focused screen crops, and completion confirmation. Keep commands on screen long enough to read. One step per beat.

### Before-after

Show raw state, transition marker, final state, and concise callouts explaining changes. Never imply measured performance improvement without evidence.

## Motion primitives

- `hook_hit`: 120 to 280 ms reveal, scale, or directional entrance.
- `masked_reveal`: reveal phrase or UI region from a meaningful edge.
- `scale_pop`: 100% to 106%, then return to baseline.
- `word_stagger`: reveal semantic words in phrase order, not every character by default.
- `underline_reveal`: draw one emphasis line under one keyword.
- `step_enter`: introduce a numbered item and reduce prior items.
- `proof_callout`: box, arrow, cursor, or crop around source evidence.
- `payoff_hold`: reduce motion for 300 to 700 ms after key line.
- `cta_exit`: short exit animation with one specific action.

## Guardrails

- Maximum two attention devices at once.
- Maximum two subtitle lines; supers must not cover subtitles or faces.
- Use one main text animation per visual.
- No fake scarcity, fake numbers, fake testimonials, or unsupported claims.
- Do not use stock footage as decoration when source-backed visual exists.
- Avoid constant shake, RGB split, glitch, lens flare, particle overlays, and transition packs without recorded purpose.
- Keep dialogue and captions readable throughout every animation.
- Respect safe margins and reduced-motion requests.

## Preset schema

```yaml
id: classic-motion-v1
profile: classic-motion
canvas: 1080x1920
font: ""
accent: ""
background: ""
text_layers:
  - id: hook
    text: ""
    in: 0.0
    out: 1.8
    primitive: hook_hit
    easing: ease_out
    purpose: "communicate source-backed promise"
sfx:
  enabled: false
  events: []
qa:
  max_simultaneous_attention_devices: 2
  subtitle_safe_margin: true
  claim_source_checked: true
```

## Verification

Pass only when each motion event has timestamp, purpose, source basis, duration, easing, and readability check. Verify first second, every text entrance, keyword emphasis, transition, payoff hold, and CTA. Remove any effect whose purpose cannot be stated in one sentence.
