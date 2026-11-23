---
name: zoom-shake
description: "Apply purposeful zoom, shake, and tracking motion."
version: 0.1.0
metadata:
  hermes:
    tags: [video editing, zoom, shake, tracking, transitions]
    related_skills: [podcast-clipping, motion-typography]
---
# Zoom and Shake

## When to Use
Use when a clip needs subject-following zoom, impact shake, or motivated zoom transitions.

Motion follows reveal, punchline, completed thought, reaction, shot boundary, or audio beat. Track face/object and record confidence plus fallback crop.

## Defaults
- Punch-in: 100% to 106–112% over 300–900 ms.
- Pull-out: return to base crop after payoff.
- Impact shake: 80–180 ms, low amplitude, only on impact or comedy beat.
- Transition zoom: compatible shots only; do not hide a hard cut.
- Follow crop: re-center per shot, not every frame unless required.

Do not shake continuously or zoom into eyes, mouths, or cropped limbs. Check softness when exceeding source resolution. Disable shake for reduced-motion exports. Pass only when tracking stays attached, no edge reveal or warp appears, subtitles remain readable, and low-confidence tracking has human review or static fallback.
