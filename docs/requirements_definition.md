# Pendulum Wave Requirements Definition

## 1. Project Overview

- Project name: `Pendulum Wave`
- Format: Interactive 3D browser artwork
- Core concept: A live 3D mobile composed of 900 chrome balance balls suspended from the ceiling
- Technical base: `HTML`, `JavaScript`, `Three.js`, `Web Audio API`

## 2. Artistic Definition

This work must not be treated as a pre-rendered AI-style visual loop.

It is an interactive 3D system in which 900 spheres continuously update their behavior through algorithmic rules. The visual result must emerge from ongoing local interaction, not from a simple parameter-offset animation such as arranging many `sin(t + offset)` motions in parallel.

The work should be perceived as:

- a persistent live mobile
- an algorithmic sculpture
- a system where order and chaos coexist
- a sound-generating structure whose rhythm emerges from the state of the spheres

## 3. Artistic Goals

- Create a visual language inspired by Newton's cradle, but expanded into a large 3D field of suspended chrome balls
- Preserve the beauty of thin aligned wires and metallic reflections
- Express a balance between discipline and instability
- Allow viewers to sense that the work is continuously "active", not simply replaying
- Generate sound as a consequence of system behavior, not as background music

## 4. Core Identity Of The Work

The work must satisfy all of the following:

- It is interactive 3D, not a flat rendered movie
- Sphere motion is governed by algorithmic activity
- Sphere positions are not determined only by pre-written coordinate offsets
- Sound emerges from proximity events and rhythm structures
- The system keeps running over time without a fixed ending
- The visual and sonic behavior should suggest a living computational object

## 5. Visual Requirements

### 5.1 Spheres

- Total count: `900`
- Layout: `30 x 30`
- Material: chrome / steel-like reflective spheres
- Quality: reflections and shading must feel intentional, not generic CG

### 5.2 Wires

- Every sphere must be connected to the ceiling by a thin wire
- Wires must remain visually elegant and structurally aligned
- Wires are part of the composition, not only technical helpers
- Optional event glow may appear on activated wires, but must remain subtle

### 5.3 Lighting And Environment

- Use a restrained studio-like environment
- Reflections should enhance material realism without excessive glare
- Lighting must support a calm, sculptural atmosphere

### 5.4 Interface Presence

- UI must remain minimal
- Any visible data overlay must not break the world of the piece
- Controls for debugging and tuning must be separated from the artwork version when necessary

## 6. Motion Algorithm Requirements

### 6.1 Motion Model

Each sphere must have its own internal state, including at least:

- position
- velocity
- local energy
- local timing deviation or tempo variation

### 6.2 Behavioral Logic

Sphere motion must be updated through a rule-based process that includes:

- attraction toward a larger wave structure
- local alignment with neighboring spheres
- local avoidance or distance constraint
- energy recovery and loss over time

### 6.3 Non-Collision Rule

- Neighboring spheres must not visually penetrate each other
- Distance constraints must actively prevent overlap
- Collision handling should appear as local negotiation, not abrupt teleportation

### 6.4 Long-Term Activity

- The system must continue running indefinitely while the page remains open
- It must not feel like a short seamless loop
- Recurring states may appear, but the work should maintain the impression of ongoing activity

## 7. Sound Requirements

### 7.1 Sound Identity

- Sound must use a shared minimal tone family across all modes
- The sonic character should be restrained, sculptural, and art-installation appropriate
- The sound should lean toward bowl-like or resonant metallic tones rather than percussive pop effects

### 7.2 Pitch System

- Use a common one-octave scale as the base pitch set
- Notes should not be precomposed into a fixed melody
- Melody-like moments may emerge from the system, but must arise from behavior

### 7.3 Trigger Logic

Sound must be generated through a hybrid structure:

- sphere proximity creates sound candidates
- rhythm logic determines when candidates are allowed to sound

This means:

- sound is not independent background audio
- sound is not triggered by simple random timing
- sound is not a fixed musical timeline

### 7.4 Density Control

- Sound output must be limited to a perceptually meaningful amount
- The system may select only part of all possible events to avoid sonic overload
- Audio density should preserve clarity and musical emergence

## 8. Mode Requirements

The project must support multiple behavioral themes. Current themes include:

- `wave`
- `accelerate`
- `breathe`
- `cascade`

Future themes may include:

- `waltz`
- `canon`
- `heartbeat`
- `hototogisu`

Each mode must:

- share the same core system identity
- differ through timing structure and behavioral emphasis
- avoid becoming just a cosmetic preset

## 9. Data / Live Metrics Requirements

- A discreet live metrics panel may be shown for observation
- Metrics should reflect ongoing algorithmic state rather than static configuration
- Suitable values include motion energy, proximity, collision activity, and per-frame sound event count
- The display must remain visually secondary to the artwork

## 10. Interaction Requirements

- Camera orbit and viewing control are allowed
- Sound activation may require user interaction for browser audio policies
- The viewer should be able to watch the system without needing to constantly manipulate it

## 11. Non-Functional Requirements

- Must run in modern desktop Chrome on macOS
- Must remain stable during long observation sessions
- Visual update and audio generation must not degrade excessively over time
- Performance must remain acceptable with 900 spheres active

## 12. Approved Direction

The approved direction for this project is:

- algorithm-driven sphere behavior
- one-octave shared sound palette
- sound generated from proximity plus rhythm gating
- subtle wire glow on activated events
- discreet live metrics display

## 13. Explicitly Rejected Direction

The project should avoid the following:

- purely pre-scripted motion made only from offset sine waves
- presentation as a fake "AI video"
- over-designed UI inside the artwork view
- overly bright or decorative wire effects
- excessive sound density that masks the structure
- conventional soundtrack behavior detached from sphere activity

## 14. Deliverable Definition

The approved artwork file at the current stage is:

- [pendulum_wave_ordered_chaos_resonance.html](/Users/sawor/Dev/Pendulum_Wave/output/approval/pendulum_wave_ordered_chaos_resonance.html)

This file represents the current accepted direction and should be treated as the main approval reference for future refinement.
