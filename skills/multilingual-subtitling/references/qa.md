# Subtitle QA

## Audio review gates

Replay every hook, claim, number, name, negation, punchline, language switch, and low-confidence segment. Compare subtitle against audio at normal speed and 0.75x.

## Technical gates

- start and end timestamps valid;
- no overlaps unless intentional speaker overlap is represented;
- no empty cues or duplicate cues;
- subtitle stays inside safe margins;
- two lines maximum;
- reading speed within project target;
- font contrast passes visual inspection;
- SRT/VTT opens in a second player;
- burned-in render matches sidecar text;
- final frame contains no truncated subtitle.

## Accuracy report

Record total cues, reviewed cues, corrected cues, unresolved cues, language labels, glossary checks, and final tier. List unresolved timestamps. If a material token is uncertain, block final approval until a human reviews it.
