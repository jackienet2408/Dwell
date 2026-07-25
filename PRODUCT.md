# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Primary: a worship team's live-service tech booth operator, running Dwell on an iPad during a service to hold ambient pad chords under the band — no laptop, no subscription, no internet required once installed. Secondary: musicians and worship leaders using it for personal practice or rehearsal outside of a live service, not just booth operation.

## Product Purpose

Dwell is a touch-first ambient pad synth: tap a root key and a diatonic chord, and a warm analog-style pad swells in and holds under the band. It exists to be a single-purpose, distraction-free "hold a chord" instrument for worship contexts. Success is a booth operator (or practicing musician) being able to pick a key, pick a chord, and keep the pad smooth through chord changes without needing DAW-level setup or attention.

## Positioning

Most pad tools are either subscription-tied iOS apps or heavyweight DAW setups that are overkill for someone whose only job is picking keys and chords. Dwell's mechanism: a free, installable-from-browser PWA (no App Store, no Apple Developer account, no TestFlight) that runs fully offline once added to the Home Screen, purpose-built around a key/chord grid plus live knob-based sound design — nothing a subscription app or DAW setup can match on simplicity + zero-friction install + offline reliability together.

## Operating Context

- Runs on iPad, installed via Safari "Add to Home Screen" as a PWA; used fully offline including Airplane Mode.
- Live-service booth use: audio must keep playing when the operator switches to another app (e.g. sheet music) or the screen locks — handled via a real media element + Media Session metadata for lock-screen "now playing" controls.
- Screen wake lock while playing, since the booth operator needs the display active during a live set.
- Also used in lower-stakes personal practice/rehearsal settings, not only under live-service pressure.
- Interaction model: tap key/chord pads, drag rotary knobs, drag directly on a real-time spectrum graph to shape filter warmth/cutoff; swipeable knob pages (Tone, Movement, Space & Vinyl).
- Presets (4 built-in + user-saved custom) stored on-device.

## Capabilities and Constraints

- Plain HTML/CSS/JavaScript + Web Audio API — no build step, no framework, no dependencies.
- Service worker (`sw.js`) caches the app shell for offline use; `manifest.json` makes it installable.
- Hosted as static files (e.g. GitHub Pages) — no backend.
- Key + chord grid covers diatonic chords I–vii° in Major or Minor, showing both Roman numeral and actual note name.
- Chord changes crossfade (adjustable attack/swell) rather than cutting.
- Pad engine: detuned oscillator voices, ensemble/chorus layer, sub-drone, filtered noise "air," optional vinyl crackle + tape hiss.
- Always-visible PA-style master fader with live signal level meter, independent of the open sound-design page.
- Stop button only lights up when audio is actually sounding.
- Background glow follows the active key/chord/preset.
- No named accessibility requirement established yet.

## Brand Commitments

Name: Dwell. Voice: warm, no-fuss, booth-practical — copy elsewhere should stay in that register (e.g. "hold a chord," not technical DSP jargon) unless the user changes it.

## Evidence on Hand

No testimonials, case studies, press, or user-facing marketing copy exist yet beyond the README. Do not fabricate any.

## Product Principles

1. Single-purpose over feature-creep: it's a "pick a key, pick a chord, keep it smooth" instrument, not a DAW.
2. Zero friction to install and run: browser install, no App Store/Developer account/TestFlight, fully offline.
3. Booth-reliable: must keep sounding through app switches and screen lock; wake lock while playing.
4. Live, direct sound design: knobs and the spectrum graph are real-time and touch-first, not menu-driven.
5. Character over sterility: pad engine favors warm/analog imperfection (detune, ensemble, tape hiss, vinyl crackle) over a clean synthetic tone.

## Accessibility & Inclusion

No product-specific accessibility requirement established yet.
