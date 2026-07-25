---
name: Dwell
description: A warm, offline worship backing pad for iPad
colors:
  bg-void: "#07070d"
  bg-rise: "#101022"
  surface: "rgba(255,255,255,0.045)"
  surface-strong: "rgba(255,255,255,0.09)"
  border: "rgba(255,255,255,0.09)"
  text: "#F5F5F7"
  text-muted: "#9597a6"
  accent: "#F97316"
  accent-soft: "rgba(249,115,22,0.16)"
  accent-glow: "rgba(249,115,22,0.38)"
  danger: "#EF4444"
  danger-soft: "rgba(239,68,68,0.13)"
typography:
  body:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", system-ui, sans-serif"
    fontSize: "13.5px–15px"
    fontWeight: 500
    lineHeight: 1.5
  title:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", system-ui, sans-serif"
    fontSize: "17px"
    fontWeight: 700
  display:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", system-ui, sans-serif"
    fontSize: "22px"
    fontWeight: 700
    letterSpacing: "-0.01em"
  label:
    fontFamily: "-apple-system, BlinkMacSystemFont, \"SF Pro Text\", system-ui, sans-serif"
    fontSize: "9px–12px"
    fontWeight: 700
    letterSpacing: "0.04em–0.08em"
rounded:
  sm: "10px"
  md: "14px"
  lg: "22px"
  pill: "999px"
spacing:
  xs: "6px"
  sm: "10px"
  md: "16px"
  lg: "18px"
components:
  chord-pad:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    rounded: "{rounded.md}"
    padding: "0"
  chord-pad-active:
    backgroundColor: "{colors.accent-soft}"
    textColor: "{colors.accent}"
    rounded: "{rounded.md}"
  key-pill:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    rounded: "{rounded.sm}"
  key-pill-active:
    backgroundColor: "{colors.accent}"
    textColor: "#1a0f04"
    rounded: "{rounded.sm}"
  preset-chip:
    backgroundColor: "{colors.surface}"
    textColor: "{colors.text}"
    rounded: "{rounded.pill}"
  preset-chip-active:
    backgroundColor: "{colors.accent-soft}"
    textColor: "{colors.accent}"
    rounded: "{rounded.pill}"
  stop-btn-playing:
    backgroundColor: "{colors.danger-soft}"
    textColor: "{colors.danger}"
    rounded: "{rounded.sm}"
---

# Design System: Dwell

## Overview

**Creative North Star: "The Booth at Dusk"**

Dwell reads like the tech booth at the edge of a darkened sanctuary a few minutes before a live set: near-black ambient light, a few frosted-glass panels catching a low glow, and one warm ember-orange signal that tells the operator exactly where the sound is pointed. Everything at rest is quiet and low-contrast; the interface has no urgency until something is actually playing, and then the accent color and its glow become the entire visual vocabulary for "this is live."

The system is deliberately flat and glassy — translucent surfaces, soft blur, no drop shadows — but it earns that flatness through an instrument-panel logic rather than borrowing a generic template look: the fader cap, the RTA cutoff ball, and the pan/breath indicator dots are the one place skeuomorphic weight and specular highlight are allowed, because those are the parts a hand actually turns or drags. Everything else stays flat so those touch points read as the "hardware" against a calm glass chassis.

**Key Characteristics:**
- Near-black void background with a single warm accent — no secondary or tertiary hue competing for attention
- Frosted/blurred glass surfaces at rest; the accent's soft glow — not shadow — is what conveys elevation and "live" state
- A handful of touch primitives (fader cap, knob dot, RTA ball) carry deliberate specular/hardware rendering as the sole departure from flat
- Tactile, immediate feedback: pads and buttons scale down on press; nothing waits to confirm a touch landed

## Colors

A near-black stage lit by exactly one warm signal color; everything else is neutral glass and muted gray text.

### Primary
- **Ember Orange** (`#F97316`): the single accent — active keys, active chords, active preset chips, the fader glow, knob fill, RTA cutoff marker. Never used as a background color on its own; always paired with `accent-soft` (16% tint) as the resting-active background or `accent-glow` (38% alpha) as a glow/shadow color, never a flat fill outside small hardware elements (fader glow line, knob dot, RTA ball core).

### Secondary
- **Alert Red** (`#EF4444`): reserved for the Stop button's "something is playing" state (`danger-soft` background, red glow). The only other hue permitted in the system; never used decoratively.

### Neutral
- **Void Black** (`#07070d`): base background.
- **Rise Indigo** (`#101022`): the radial-gradient lift at the top-left of the screen — never a flat fill, only the gradient's far end.
- **Glass Surface** (`rgba(255,255,255,0.045)`): resting background for pads, chips, knob wells, viz panels.
- **Glass Surface Strong** (`rgba(255,255,255,0.09)`): fader track, tray handle bar, unselected page dot — anything needing slightly more presence than a resting surface.
- **Hairline Border** (`rgba(255,255,255,0.09)`): the only border color in the system, at 1px, on every surface that needs an edge.
- **Signal White** (`#F5F5F7`): primary text.
- **Muted Slate** (`#9597a6`): secondary text, labels, sharps/flats, inactive icons.

### Named Rules
**The One Ember Rule.** Ember Orange is the only color allowed to signal "this is active/live." If a control isn't currently doing something, it stays neutral glass — no decorative accent color on idle elements.

## Typography

**Body Font:** -apple-system, BlinkMacSystemFont, "SF Pro Text", system-ui, sans-serif (no distinct display or mono face — one system stack throughout)

**Character:** Native-feeling and utilitarian by design — this is a booth tool, not an editorial surface, so type carries information density (Roman numeral + note name, knob value, dB-style label) rather than personality. Weight, not size, does most of the hierarchy work.

### Hierarchy
- **Display** (700, 22px, tight -0.01em tracking): the Roman numeral on a chord pad — the single largest, most important glanceable value on screen.
- **Title** (700, 17px): the "Now Playing" key + chord readout in the top bar.
- **Body** (600, 13.5–15px): preset chip labels, mode toggle labels, hint text.
- **Label** (700, 9–12px, 0.04–0.08em uppercase tracking): fader label, knob labels, brand wordmark, chord pad's note-name subtext — the small uppercase caption layer under every control.

### Named Rules
**The Weight-Over-Size Rule.** Hierarchy is built mostly with font-weight (500 body vs. 700 emphasis) and muted-vs-signal color, not a wide type scale — sizes stay clustered between 9px and 22px across the entire app.

## Layout

Single-column "stage" (max-width 720px, centered) stacked vertically: top bar → horizontally-scrolling preset strip → key/chord grid → stop button, with a fixed-width 50px master-fader rail docked to the right edge of the whole app shell, independent of scroll. Below the stage, a bottom "studio tray" slides open (max-height transition, not a modal) to reveal a horizontally swipeable, scroll-snapped pager of knob pages (Tone / Movement / Space & Vinyl), with dot indicators.

Density is adaptive: a `.compact` state (triggered when the tray opens, shrinking the stage) tightens gaps, pad heights, and font sizes on the key/chord grid so the chord grid and the open tray can coexist without the page needing to scroll. Spacing runs on an approximate 6/8/10/16/18px rhythm; horizontally-scrolling strips (presets, keys) hide their native scrollbars.

## Elevation & Depth

Flat by default — no drop shadows on cards, pads, or panels. Depth and "aliveness" are conveyed by glow (radial `accent-glow` blur), opacity shift, and blur (`backdrop-filter`) on the fader rail and studio tray, not by elevation shadows. The few real box-shadows in the system are deliberately reserved for the hardware-style touch primitives (fader cap, knob glow ring, RTA cutoff ball, install card) to give just those elements physical weight against the flat chassis.

### Shadow Vocabulary
- **Ember glow** (`0 0 22px rgba(249,115,22,0.38)` variants): active chord pad, fader cap accent line, knob glow ring, RTA handle/ball — the system's only "this is active" depth cue.
- **Hardware cap shadow** (`0 2px 5px rgba(0,0,0,0.5), inset 0 1px 0 rgba(255,255,255,0.12)`): fader cap and RTA ball only — the deliberate skeuomorphic exception.
- **Panel lift** (`0 8px 24px rgba(0,0,0,0.35)`): install card and modals only, to separate them from the stage below.

### Named Rules
**The Flat-Chassis Rule.** Surfaces are flat glass at rest. Shadow only appears on the small set of elements a hand actually drags or turns (fader cap, knobs, RTA ball) — never on static containers like pads, chips, or panels.

## Shapes

Rounded throughout, scaled to the control's role: chord pads and knob wells use a medium 14px radius, small utility controls (stop button, RTA canvas, viz panels) use 10px, large containers/modals use 22px, and anything chip- or pill-shaped (presets, mode segments' inner buttons) goes fully pill (999px). Circles are reserved for touch/drag primitives — knobs, the fader cap's rounded ends, page dots, the breath/pan indicator dot. Borders are a single 1px hairline (`rgba(255,255,255,0.09)`) on nearly every surface; no double borders or heavier strokes.

## Components

### Buttons
- **Shape:** pill (999px) for presets and the add-preset circle button; 12px/9px rounded rectangle for mode-toggle segments; 10px for the square stop button.
- **Primary/Active:** `accent-soft` background + 1px `accent` border + `accent` text — the shared "selected" recipe used across preset chips, mode buttons, and chord pads.
- **Hover/Press:** no hover state (touch-first); press feedback is a `scale(0.94–0.96)` transform on `:active`, near-instant (0.12s), giving the "tactile and immediate" feel — controls compress physically rather than fading or glowing on touch-down.
- **Danger:** the Stop button switches to `danger-soft` background, `danger` border/text, and a red glow only while audio is actually sounding.

### Chips (Preset chips)
- **Style:** glass background, hairline border, pill shape, 38px height.
- **State:** `active` swaps to the shared accent-soft/accent-border/accent-text recipe; the `add` variant uses a dashed border and muted text to read as a secondary action.

### Cards / Containers (chord pads, key pills, viz panels)
- **Corner Style:** 14px (chord pads, knob wells) or 10px (viz/RTA panels, key pills).
- **Background:** glass surface at rest; accent-soft when active.
- **Shadow Strategy:** none at rest; ember glow ring + 1px accent border ring when active (see Elevation & Depth).
- **Border:** 1px hairline at rest, 1px accent when active.
- **Internal Padding:** content-centered flex, not a fixed padding scale — pads size by `min-height` (88px, 52px compact) rather than padding.

### Inputs / Fields
- **Style:** pill shape, `surface-strong` background, 1px accent border (inputs are always in an "active editing" state visually, unlike other idle controls).
- **Focus:** no separate focus ring; the accent border is already present on open.

### Navigation (mode toggle, page dots, tray pager)
- Mode toggle: a segmented pill control, transparent idle segments, `accent-soft`/`accent` active segment.
- Page dots: 6px circles, `surface-strong` idle, accent + 1.4× scale when active.
- Tray pager: horizontal scroll-snap, no visible scrollbar, controlled entirely by swipe — no arrow/chevron nav controls.

### The Knob (signature component)
A 68px (56px in Movement's grouped rows) circular touch target with an SVG-drawn dial and a radial `accent-glow` halo behind it whose opacity scales continuously with the knob's current value (`--val` custom property) — the knob visually brightens as it's turned up, with no numeric readout required to sense intensity at a glance. A short `scale(1.09)` bump animation fires on programmatic value snaps (e.g. preset recall) to make silent state changes still feel touched.

## Do's and Don'ts

### Do:
- **Do** keep Ember Orange as the only color that means "active/live" — every other surface stays neutral glass.
- **Do** use glow + opacity, not box-shadow, to show elevation on ordinary panels and pads.
- **Do** reserve real skeuomorphic shading (gradients, inset highlights, drop shadows) for parts the user physically drags or turns — fader cap, knobs, RTA ball.
- **Do** give touch feedback via an immediate scale-down transform, not color fade or delay.
- **Do** keep type hierarchy driven by weight and muted/signal color contrast rather than a wide size scale.

### Don't:
- **Don't** introduce a second accent hue; red is reserved solely for the Stop-while-playing state.
- **Don't** add generic glassmorphism flourishes (extra gradient sheens, rainbow blurs, decorative frosted cards) beyond the system's existing surface/border/blur recipe — this should read as a purpose-built instrument panel, not a templated "AI app" look.
- **Don't** put a drop shadow on a static container (pad, chip, panel) that isn't currently active or being touched.
- **Don't** add hover-only affordances; every interactive state must work with touch-press alone.
