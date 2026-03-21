# Pendulum Wave Development Specification

## 1. Purpose

This document defines the implementation structure for the `Pendulum Wave` project so that the current approved artwork can be maintained, extended, and later converted into a reusable Codex skill.

This specification is not a concept memo. It is a development-facing description of:

- system boundaries
- runtime behavior
- state model
- rendering model
- sound generation model
- event rules
- approved file direction

## 2. Current Approved Artifact

- Main approved file:
  [pendulum_wave_ordered_chaos_resonance.html](/Users/sawor/Dev/Pendulum_Wave/output/approval/pendulum_wave_ordered_chaos_resonance.html)

This file is the baseline implementation reference for future revisions.

## 3. Runtime Platform

- Runtime: browser
- Primary browser target: desktop Chrome on macOS
- Rendering: `Three.js`
- Audio: `Web Audio API`
- Delivery format: standalone `.html`

## 4. System Definition

The artwork is a persistent real-time system with three coupled layers:

1. Motion layer
   900 spheres update through local rule-based motion.
2. Audio layer
   Sound events are derived from sphere proximity and rhythm gating.
3. Trace layer
   Subtle visual traces such as wire glow and live metrics expose system activity.

The system must remain active continuously while the page is open.

## 5. Scene Specification

### 5.1 Object Count

- Sphere count: `900`
- Grid: `30 x 30`

### 5.2 Geometry

- Sphere geometry: high-resolution enough to support reflective chrome appearance
- Wire geometry: one line per sphere from ceiling anchor to current sphere position
- Optional glow geometry: one secondary line per sphere, used only during event traces

### 5.3 Layout

- Each sphere has a stable base anchor position in the grid
- Sphere movement is expressed relative to its base position
- Wires always connect base anchor to live sphere position

## 6. Sphere State Model

Each sphere instance must hold at least the following fields:

- `row`
- `col`
- `baseX`
- `baseZ`
- `x`
- `vx`
- `energy`
- `targetX`
- `swingBias`
- `localTempo`
- `soundCooldown`
- `wirePulse`
- `wirePulseHue`

These fields define the minimum persistent state required for approved behavior.

## 7. Motion Update Model

### 7.1 Motion Loop

Each animation frame must:

1. advance time
2. compute target positions
3. simulate local forces
4. apply distance constraints
5. update visual transforms
6. update trace systems
7. render

### 7.2 Target Motion

Target motion is not final motion. It is a higher-level attractor.

Target position must be influenced by:

- mode-specific phase function
- global phase progression
- local tempo deviation
- cross-axis bias
- breathing or slow modulation
- energy-scaled amplitude

### 7.3 Local Motion Forces

Per-sphere acceleration must combine:

- target attraction
- neighbor alignment
- local flow correction
- damping

This creates ordered-chaotic motion rather than simple direct sine playback.

### 7.4 Distance Constraint

Neighboring spheres in each row must enforce a minimum spacing.

Constraint behavior must:

- prevent visible overlap
- preserve smoothness
- avoid hard snapping where possible
- support repeated iterative correction in a single frame

## 8. Timing And Mode Structure

### 8.1 Required Modes

Current supported modes:

- `wave`
- `accelerate`
- `breathe`
- `cascade`

### 8.2 Mode Definition Rule

A mode must not only change appearance. A mode must change at least one of:

- phase structure
- temporal cadence
- rhythm window pattern
- propagation behavior
- sound profile timing

### 8.3 Future Mode Direction

Future themes such as `waltz`, `canon`, `heartbeat`, and `hototogisu` should be implemented as temporal-behavioral systems, not as cosmetic presets.

## 9. Audio System Specification

### 9.1 Audio Activation

- Audio must be disabled by default until user interaction
- Audio context must initialize only after explicit user action

### 9.2 Shared Tone Family

All modes must use one shared tone family.

The tone family should remain:

- minimal
- resonant
- metallic or bowl-like
- suitable for gallery-style listening

### 9.3 Pitch Set

- Base pitch system: one octave
- Current implementation direction: base scale `C4` to `C5`, with some modes allowed to shift the active register downward
- Pitch assignment is derived from spatial structure, not a prewritten melody file

### 9.4 Event Trigger Model

Sound event generation must follow this logic:

1. evaluate local proximity between neighboring spheres
2. derive candidate event strength from gap, compression, and relative velocity
3. pass candidate through rhythm gate
4. trigger sound only if budget and cooldown conditions allow

### 9.5 Density Limiting

Per-frame sound event count must be intentionally constrained.

This limit exists for:

- perceptual clarity
- prevention of sonic overload
- runtime stability

Sound selection does not need to represent every physical near-contact event.

## 10. Wire Glow Trace Specification

### 10.1 Trigger Source

Wire glow must only activate from actual emitted sound events, not from all near-contact candidates.

### 10.2 Visual Character

Wire glow must remain:

- thin
- brief
- low intensity
- secondary to the wire itself

### 10.3 Motion Character

The glow should read as a short pulse traveling from ceiling anchor toward the sphere.

It should behave like an event trace, not a decorative persistent light source.

## 11. Metrics Overlay Specification

### 11.1 Role

The live metrics overlay is observational, not interactive.

### 11.2 Approved Metrics

Current approved metrics include:

- mode
- tempo drift
- wave energy
- proximity
- collisions
- per-frame sound events

### 11.3 Visual Constraint

The metrics overlay must:

- stay visually quiet
- avoid bright dashboard aesthetics
- remain subordinate to the artwork

## 12. UI Specification

### 12.1 Approved Controls

Artwork-view controls may include:

- mode switching
- auto orbit toggle
- sound on/off

### 12.2 Restricted Controls

Debug sliders and tuning UIs are not part of the approved artwork view.

If needed, they must live in separate development-only files.

## 13. File Organization Guidance

Current project-relevant outputs are organized under:

- [output](/Users/sawor/Dev/Pendulum_Wave/output)
- [output/approval](/Users/sawor/Dev/Pendulum_Wave/output/approval)

Recommended future structure:

- approved artifact in `output/approval/`
- exploratory variants in `output/`
- documentation in project root

## 14. Skill Conversion Guidance

This project is a strong candidate for a future Codex skill. To support that conversion:

- keep the approved artifact as the canonical runtime example
- keep the development spec separate from concept notes
- describe the system in terms of state, rules, and outputs
- avoid embedding long artistic essays inside the future skill body

When converted into a skill, recommended decomposition is:

1. `SKILL.md`
   concise workflow and rules for extending the artwork
2. `references/algorithm.md`
   motion, proximity, and sound logic
3. `references/art-direction.md`
   visual and experiential constraints
4. `assets/`
   optional base template files if a reusable starter is needed

## 15. Change Rules For Future Development

Any future revision should preserve all of the following unless intentionally replaced:

- 900-sphere architecture
- algorithmic local motion rather than offset-only animation
- one-octave shared sound palette
- proximity plus rhythm-gated sound triggering
- subtle wire glow event traces
- quiet live metrics display

## 16. Non-Goals

The system should not drift toward:

- a pre-rendered video aesthetic
- a conventional music sequencer
- a generic screensaver
- a debug-heavy interface
- a physically exact simulation at the cost of artwork quality

## 17. Implementation Reference Summary

The approved implementation should continue to communicate the following identity:

- live
- algorithmic
- spatial
- sonic
- sculptural

This identity is the primary development constraint.
