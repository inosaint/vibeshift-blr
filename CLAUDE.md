# CLAUDE.md - Project Context

## Project
Chaos Typewriter — a wordle-like game with a p5.js step-sequencer grid and Tone.js audio. Single-file app (`chaos-typewriter.html`).

## Architecture
- `chaos-typewriter.html` is the entire app in one file
- CSS styles: lines 1–672
- Audio engine (vanilla JS): lines ~678–1030 — VIBES, DREAMY_VOICES, AudioEngine
- App logic: lines ~1032–2485 — currently React inside `<script type="text/babel">`, pending conversion to vanilla JS

## In-Progress Work
- **Convert React to vanilla JS** — drop React, ReactDOM, and Babel (~2MB). Plan at `.claude/plans/glistening-noodling-barto.md`
- Keep p5.js and Tone.js (they're needed)

## Audio Engine Details
- Dreamy vibe: multi-instrument — 5 voices (pad, bell, pluck, keys, perc), one per letter group (3 cols each)
- Glitchy: AMSynth + BitCrusher (whole-tone scale)
- Calm: FMSynth (pentatonic minor)
- Tense: MonoSynth + distortion (phrygian)
- `playNote(row, chaos, col)` — col determines instrument in multi-voice vibes
- Lydian scale for dreamy, rows map to pitches (row 0 = highest, row 4 = lowest)

## Preferences
- True vanilla HTML/CSS/JS — no frameworks or compile steps
- Keep it simple, avoid over-engineering
- **Prompt to commit often** — after completing a meaningful chunk of work, proactively ask the user if they want to commit
