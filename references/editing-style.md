# Editing style system

## Default vertical format

- Canvas: 1080x1920, 9:16.
- Crop: speaker eyes near upper-middle safe region; never hide captions behind platform UI.
- Captions: two lines maximum, high contrast, strong outline or shadow, phrase-synced.
- Emphasis: highlight one or two semantic words per phrase, not every word.
- Pace: remove dead air, but keep breaths and reactions that carry emotion.

## Speaker-aware motion

- Solo speaker: gentle punch-in on claim, reveal, or emotional peak; return to base crop after payoff.
- Two speakers: alternate framing only at speaker changes or reaction moments; keep spatial orientation stable.
- Fast debate: shorter cuts and tighter crops, but preserve turn-taking.
- Storytelling: hold shots longer; use reaction or detail cutaways only when they add context.

## Color and audio

- Correct exposure and white balance first.
- Keep skin tones natural and match cameras before adding a look.
- Use restrained contrast and saturation. Log the reason for any stylized grade.
- Dialogue remains foreground. Duck music and effects under speech.
- Normalize only after cleanup; inspect clipping and room noise.

## Style selection

- Confessional: warm-neutral grade, stable crop, minimal effects, breathing room.
- Debate: cooler neutral grade, quicker speaker changes, emphasis on reactions.
- Educational: clean grade, diagram or keyword overlays only when source supports them.
- Comedic: reaction cuts and timing accents, no effect that hides the joke.
- Story: slower rhythm, motivated cutaways, strongest visual on emotional turn.

Every chosen style must state: audience, source tone, pacing target, caption treatment, motion rule, and why the style fits.

## Reference-derived creator format

The supplied Instagram references expose a consistent educational/AI-tools editing pattern through their public captions: one strong promise, rapid proof, tool or workflow steps, animated text, B-roll or screen capture, and a comment CTA. Treat this as a format reference, not a frame-by-frame copy.

Use this preset when source content is educational, technical, or tool-focused:

- Open with a concrete result or contrast in the first 0.5 to 1 second: `Satu kalimat. Game langsung bisa dimainin.` or an equivalent source-backed line.
- Use kinetic typography for keywords and numbers. Animate by phrase or semantic unit, not every character.
- Change visual evidence with the sentence: screen recording, repository, product UI, terminal, diagram, or relevant B-roll. Do not show unrelated stock footage.
- Build a proof ladder: claim, mechanism, visible demonstration, limitation or caveat, then CTA.
- For lists, use numbered overlays with one item per beat. Keep item text short and let narration carry detail.
- Use quick cuts and subtle punch-ins on transitions between steps. Avoid transition effects between every shot.
- Keep caveats visible when source includes them, such as unofficial status, requirements, attribution, or unverified claims.
- End with a specific comment CTA tied to the topic, not a generic `follow for more`.
- Use captions as the primary reading layer and typography overlays as secondary emphasis. Never let decorative text compete with speech captions.

### Reference style profiles

**AI tool demo**

Hook: result first. Visual: screen capture or output before explanation. Rhythm: fast, one visual change per meaningful sentence. Text: large keyword overlay plus compact phrase captions. Proof: show the actual workflow. Risk: label unofficial tools, dependencies, and author claims.

**Tutorial or setup**

Hook: specific outcome or learner promise. Visual: numbered steps, command or UI close-up, and a clear completion state. Rhythm: medium-fast, pause long enough to read commands. Text: preserve exact package names, versions, and commands. Risk: verify platform and installation requirements.

**Clipper/editor showcase**

Hook: before/after or raw-to-final contrast. Visual: split-screen or sequential comparison, typography, B-roll, and motivated motion graphics. Rhythm: fast at the opening, slower on the payoff. Text: show editing decisions, not unsupported performance claims.

**Podcast insight**

Hook: strongest source quote or contradiction. Visual: speaker-first crop, reaction cut, restrained keyword graphics. Rhythm: follow argument beats, not a fixed effect count. Text: faithful multilingual subtitles from `multilingual-subtitling`; never rewrite slang or English switches.

### Mandatory style log

For each clip, record:

- profile selected and source reason;
- hook timestamp and exact wording;
- visual evidence used for each claim;
- typography animation triggers;
- B-roll source and rights status;
- CTA wording and source basis;
- caveats retained;
- effects deliberately skipped and why.

Observed public metadata is enough to infer format patterns, not enough to certify exact font, color, transition, timing, or audio choices. Inspect downloaded source footage before setting those values.

## Motion and visual treatment system

Choose motion from the narrative beat. Every animation must have one job: attract attention, explain structure, show change, maintain continuity, or create a payoff.

### Animation map

- **Hook hit**: quick text reveal, scale-in, or directional movement during the first phrase. Duration 120 to 280 ms. Use once, not on every caption.
- **Keyword emphasis**: scale 100% to 106%, color change, underline, or short position shift on one meaningful word. Return to baseline before the next phrase.
- **Punch-in**: gradual crop from 100% to 106% or 112% over 300 to 900 ms on a claim, reaction, or reveal. Add ease-out; never zoom continuously without a beat.
- **Release**: return to the base crop after payoff so the viewer feels a completed beat.
- **Topic transition**: wipe, slide, match cut, or shape transition only when the topic or section changes. Prefer a clean cut when no transition is needed.
- **List progression**: number or step enters, active item gains contrast, completed items reduce emphasis. Keep previous items visible only when comparison matters.
- **Proof reveal**: mask, crop, cursor path, or highlight reveals the exact UI, repository line, chart, or object being discussed.
- **Reaction accent**: brief freeze frame, outlined face, arrow, or callout when a reaction itself carries meaning. Remove immediately after the beat.
- **Payoff hold**: reduce motion for 300 to 700 ms after the key line. The viewer must have time to process the conclusion.

### Visual modules

Select only modules supported by the source:

- speaker cutout or outline for contrast against a relevant background;
- screen recording with cursor emphasis and zoomed region;
- repository, terminal, product UI, or document callout;
- before/after split screen or wipe comparison;
- progress bar or chapter marker for a multi-step explanation;
- diagram, arrow, bracket, or highlight box for relationships;
- keyword card for a definition or central concept;
- reaction crop or freeze frame for humor and surprise;
- masked B-roll, object close-up, or detail crop when it adds evidence;
- end card with one specific CTA.

Do not add an overlay when the source already communicates the idea clearly. Do not use stock footage as decoration. Do not use a chart, number, logo, UI, or product screenshot unless it is source-backed or clearly labeled as illustrative.

### Motion presets by content

**Technical explanation**: screen proof first, cursor highlight, controlled zoom, diagram or callout, then static takeaway. Avoid glitch effects unless the subject is explicitly digital error or disruption.

**Tutorial**: numbered step card, focused screen crop, cursor path, short confirmation state, then next step. Hold commands and package names long enough to read.

**Debate or strong opinion**: speaker-first crop, cut on turn-taking, subtle push-in on the claim, reaction shot on response, no distracting overlays over faces.

**Story or confession**: slower crop movement, restrained text, reaction or detail B-roll only at emotional turns, payoff hold before the end card.

**Comedy**: cut on the joke, reaction frame, subtitle timing accent, occasional freeze or speed change only when it improves timing. Never cover the punchline with graphics.

**Before/after showcase**: raw frame, transition marker, final frame, then callouts explaining what changed. Do not imply performance improvement without measured evidence.

### Visual quality limits

- Maximum two simultaneous attention devices: for example, punch-in plus keyword highlight. A third device usually lowers clarity.
- Never animate captions, logo, B-roll, background, and UI at the same time by default.
- Keep decorative motion below speech priority. Dialogue and captions remain readable during every effect.
- Avoid constant shake, RGB split, glitch, lens flare, particle overlays, heavy blur, fake camera movement, and transition packs unless the source or brand explicitly requires them.
- Use motion blur only when it improves a fast transition; preserve text edges.
- Respect reduced-motion and accessibility exports when requested.
- Maintain consistent easing, speed language, corner radius, stroke width, and accent color across one clip.

### Motion decision log

For each animated element, record:

- timestamp and source beat;
- module or preset;
- visual purpose;
- duration and easing;
- attention devices already active;
- accessibility or readability check;
- reason for not using a stronger effect, when relevant.

If purpose is empty, remove animation.
