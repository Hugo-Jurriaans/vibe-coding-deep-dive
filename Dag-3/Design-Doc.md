Web-Hooked — Design Manual
1. Project Overview

Platform: Web (Frontend only)
Tech: HTML, CSS, JavaScript
Rendering: Canvas (2D)
Target Experience: Relaxing, satisfying, replayable fishing gameplay
Core Pillar: Feel > Features

This game should be:
Easy to start
Hard to master (if skill-based)
Pleasant even when nothing “big” happens

2. Core Design Pillars
These pillars should guide every decision.

1. Simplicity
Mechanics should be learnable in under 1 minute
One main interaction at a time
Avoid stacking systems early

2. Atmosphere
Fishing is about patience and calm
Sound, color, and motion matter as much as mechanics

3. Readability
Player should always understand:
What is happening
What they did right or wrong
Clear visual and audio feedback

4. Replayability
Short loops (1–3 minutes per session)
Progression visible immediately
---------------------------------------------------------------------
3. Risks of Frontend-Only Web Development
Performance Constraints

Risk

Browser-based rendering can struggle with:
Performance Constraints
Heavy animations
Complex physics
Many entities
Design Choice
Use 2D Canvas
Fake physics (timers, curves, tension bars)
Limit particles and effects
Different screen sizes
Mobile browsers are weaker
Audio issues on some platforms
Design Choice
Fixed aspect ratio canvas
Scaled rendering
Touch-first interaction design
Test early on mobile

⚠️ No Backend / Server

Risk
No cloud saves
No multiplayer
Saves can be cleared
Design Choice
Offline-first design

Use localStorage or IndexedDB
Optional export/import saves

4. Recommended Technical Choices
Rendering

✅ Canvas only
❌ DOM-heavy animations

One canvas
All visuals drawn in JS
CSS only for menus and UI overlays
Architecture
Single Game State Object
Systems read from state, don’t mutate randomly
Renderer never changes game data
Suggested systems

Input

Game State

Fishing Logic

Progression

Renderer

Audio

Save/Load

Data-Driven Design

Fish defined in JSON-like objects

Locations defined by data, not code

Easier balancing and expansion

5. Gameplay Design Choices
Fishing Mechanics

Best web-friendly options:

Timing bars

Tension meters

Click-and-hold interactions

Pattern recognition

Avoid:

Twitch-heavy reactions

Physics-heavy line simulation

Progression

Recommended:

Content-based progression

Light stat upgrades

Collection-driven motivation

Examples:

Fish journal

Rare fish chances

Gear with simple modifiers

Session Length

One fishing attempt: ~20–40 seconds

One session: ~2–5 minutes

Always allow “one more cast”

6. Visual & Styling Direction
🎨 Best-Fit Style: Stylized 2D (Cozy / Indie)
Why this works:

Low performance cost

Timeless look

Forgiving on low-res screens

Fits fishing emotionally

Art Direction Recommendations
Color Palette

Blues, teals, greens

Warm highlights (sunset orange, soft yellow)

Low contrast, calm saturation

Shapes

Rounded UI elements

Soft silhouettes

Avoid sharp, aggressive angles

UI Style

Large readable buttons

Minimal text

Icon + text where possible

Subtle animations (fade, slide, bob)

Animation Style

Slow, looping water motion

Gentle bobbing of objects

No sudden camera movement

Fonts

Friendly sans-serif

Optional handwritten style for titles

Avoid ultra-thin fonts

7. Audio Design Guidelines

Ambient water sounds

Soft reel clicks

Clear bite sound

Audio feedback is more important than visuals for fishing

Rule

If you close your eyes, the game should still feel good.

8. Scope Control Rules (Very Important)
Always Ask:

Does this improve the fishing loop?

Does this add calm or stress?

Is this readable in 1 second?

Never Add:

Features that only add complexity

Systems you can’t test easily

Content before the core loop is fun

9. Definition of “Done”

The game is ready when:

The first fishing attempt feels good

Progress saves correctly

Visual style is consistent

Players understand it without explanation

10. Final Design Rule (The Big One)

Fishing games succeed on feel, not realism.

If something feels good but isn’t realistic — keep it.
