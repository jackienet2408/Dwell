# Dwell

**A warm, offline worship backing pad for iPad.**

Dwell is a touch-first ambient pad synth built for worship teams who need a reliable, no-fuss "hold a chord" instrument during a live service — no laptop, no subscription, no internet connection required once installed.

Tap a key, tap a chord, and a warm analog-style pad swells in under your band. Change chords on the fly, shape the tone live with rotary knobs and a real-time spectrum graph, and keep the whole thing running from a home-screen app on the iPad already sitting on your tech booth.

## Why

Most "pad" tools are either expensive iOS apps tied to a subscription, or heavyweight DAW setups that are overkill for a booth operator whose only job is: *pick a key, pick a chord, keep it smooth.* Dwell is built to be exactly that — a single-purpose, distraction-free instrument, installable straight from a browser with no App Store, no Apple Developer account, and no TestFlight in the loop.

## Features

- **Key + chord grid** — tap a root key and a diatonic chord (I–vii°); pads show both the Roman numeral and the actual note name, in Major or Minor
- **Smooth voice-leading** — chord changes crossfade rather than cut, with an adjustable attack/swell time
- **Layered pad engine** — detuned oscillator voices, an ensemble/chorus layer, a sub-drone, filtered noise "air," and optional vinyl crackle + tape hiss for character
- **Live sound design** — rotary knobs (drag to turn) organized into swipeable pages: Tone, Movement, and Space & Vinyl
- **Real-time spectrum graph** — see the pad's actual frequency content and drag directly on the graph to set the filter's warmth/cutoff
- **PA-style master fader** — an always-visible vertical fader with a live signal level meter, independent of whatever sound-design page is open
- **Presets** — four built-in starting points (Warm & Soft, Bright Chapel, Vintage Tape, Wide Ambient) plus save-your-own custom presets, stored on-device
- **Built for the booth** — screen wake lock while playing, a Stop button that only lights up when something's actually sounding, and a background glow that quietly follows whatever key/chord/preset is active
- **Fully offline** — installs as a Home Screen PWA and runs with no network connection; no Apple Developer Program, no TestFlight

## Getting started

1. Open the app URL in Safari on iPad.
2. Tap the Share button → **Add to Home Screen**.
3. Launch it like any other app — from then on it works fully offline, even in Airplane Mode.

## Tech

Plain HTML/CSS/JavaScript and the Web Audio API — no build step, no framework, no dependencies. A service worker (`sw.js`) caches the app shell on first load so it keeps working with no connection, and `manifest.json` makes it installable as a Home Screen app. Hosted as static files (e.g. GitHub Pages), which is all a PWA like this needs.

## Status

Actively evolving — the sound engine and UI are still being refined session to session.

## License

TBD.
