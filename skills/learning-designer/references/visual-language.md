# Visual Language Library

Read this in full before building any HTML explainer. The goal: every training gets a design born from its content, not a reskin of the last one.

## Step 0: The metaphor comes from the content's shape

Before writing any code, name the underlying structure of what you're teaching. The structure picks the metaphor, the metaphor picks the layout and motion. Never default to "pipeline on dark green" because it worked last time.

| Content shape | Metaphor options | Signature visual/motion |
|---|---|---|
| Sequence / flow (money, data, a process) | Pipeline, river, subway line, relay race | A pulse/traveler animating along a path; stations reveal |
| Hierarchy / taxonomy | Map, city districts, tree, solar system | Zoom from overview into detail; pan between regions |
| Trade-off / tension | Balance scale, slider, tug-of-war, dial | Draggable slider where moving one side visibly costs the other |
| States and transitions | Machine with modes, traffic lights, doors | The scene itself changes state; buttons flip the machine |
| Composition (parts of a whole) | Anatomy diagram, exploded product view, layer cake | Parts separate on scroll, hover isolates one part |
| Comparison (us vs them, before/after) | Split screen, mirror, side-by-side race | Synchronized panels; a scrubber wipes between them |
| Accumulation / compounding | Snowball, stacking blocks, filling vessel | Counter + growing shape driven by scroll or time |
| Timeline / history | Road, filmstrip, geological strata | Horizontal scroll; milestones light up as you pass |
| Network / relationships | Constellation, web, city grid | Nodes attract/repel; clicking a node highlights its links |
| Scale (big numbers, tiny margins) | Zoom-out sequence, unit comparison | Progressive zoom: one order, a day, a year |
| Risk / uncertainty | Weather, minefield, radar | Probabilistic dots, heat zones, sweep animation |
| A journey with decisions | Chose-your-path map, branching trail | The learner picks a branch and the route draws itself |

Rule: pick the metaphor, then write one sentence justifying it ("payments is a sequence, so Maria's money rides a rail"). If you can't justify it, pick again.

## Aesthetic direction: rotate, never repeat

Pick ONE direction per training. Check the design log (below) and do not use the same direction twice in a row.

| Direction | Palette | Type | Feel |
|---|---|---|---|
| Night lab | Near-black + one neon accent | Grotesk sans, huge | Technical, cinematic |
| Editorial | Paper white/cream, ink text, one warm accent | Serif headlines, sans body | NYT feature, calm authority |
| Field notes | Kraft/warm neutrals, hand-drawn accents | Rounded sans or mono labels | Sketchbook, approachable |
| Blueprint | Deep blue, white linework, grid visible | Mono/condensed | Engineering drawing |
| Pop / arcade | Bright saturated shapes on light ground | Chunky rounded type | Playful, game-like |
| Brutalist | Raw black/white, hard edges, oversized type | Ultra-bold, tight leading | Confident, no decoration |
| Organic | Soft gradients, blobs, natural hues | Humanist sans | Story-like, gentle |

Shopify green is an accent option, not a requirement. It must never make every page look the same.

## Motion and interaction patterns (pick 2-3, not all)

- **Scrollytelling**: the graphic stays pinned while scroll advances the story (IntersectionObserver + sticky). Best for narratives.
- **The traveler**: something animates along a path (SMIL animateMotion or offset-path). Best for flows.
- **Direct manipulation**: a slider/drag input changes the diagram live. Best for trade-offs and "what if".
- **Scene state machine**: clicking changes the whole scene, not a text panel. Best for modes/configurations.
- **Progressive zoom**: overview first, click/scroll dives into a region. Best for hierarchies and scale.
- **Reveal on interrogation**: hover/tap a part of a drawing and it explains itself. Best for anatomy.
- **Simulation toy**: a tiny live system the learner pokes (canvas particles, simple physics). Best for emergent concepts (fraud patterns, network effects).
- **Scrubber/wipe**: drag to compare before/after. Best for comparisons.

Motion must teach. If an animation could be removed without losing meaning, remove it.

## Craft bar (visual acuity checklist)

- Typography does the heavy lifting: strong scale contrast (hero type 3-5x body), tight line-height on big type, generous on body. Max 2 typefaces.
- One accent color used with intent; everything else neutral. Color means something (each stage/actor owns a hue) or it's decoration, cut it.
- Whitespace is a feature. If a section feels full, split it into two screens.
- Draw real graphics: SVG paths, custom shapes, illustrated scenes. Emoji are not illustration. Boxes are not diagrams.
- Ease everything (cubic-bezier, 200-600ms). Nothing snaps, nothing bounces gratuitously.
- 60fps: animate transform/opacity only, never layout properties.
- Works at laptop width first; degrades gracefully on mobile.

## The wow pass (final polish, always)

After the page works, do one dedicated pass to juice it. Add depth and celebration without adding a single word:

- **Celebrate wins physically.** Correct answers, reveals, and commitments earn a canvas confetti burst or equivalent. Reward moments are the emotional anchor of the learning.
- **Numbers count up.** Any big stat animates from 0 with an ease-out (odometer effect). A number that just appears is a wasted reveal.
- **Dialogue types itself.** Questions and quotes appear character by character with a blinking caret. Tension is a teaching tool.
- **Real 3D, not fake.** Card flips use perspective + backface-visibility. Key surfaces tilt subtly toward the cursor (max ~5deg).
- **Everything idles alive.** Ambient drift on background shapes, gentle bobbing on icons, staggered delays so nothing moves in sync.
- **Springy easings on interactions** (cubic-bezier with overshoot, e.g. .2,1.8,.4,1) for pips, stamps, and pop-ins. Linear easing is dead motion.
- **Texture.** A film-grain or noise overlay at ~4-6% opacity kills the flat vector look.
- Still bound by the craft bar: transform/opacity only, 60fps, and every effect maps to a meaning (reward, attention, depth). Juice that distracts gets cut.

## Design log (anti-repetition system)

After every build, append one line to the design log. Default location: `~/.learning-designer/design-log.md` (create it if missing). If the user keeps a notes repo, prefer `Resources/Learning-Design/design-log.md` there instead.

```
| date | training | metaphor | aesthetic direction | motion patterns | file |
```

Before every build, read the log. New build must differ from the previous entry in at least metaphor AND aesthetic direction.

## Study list: where this craft comes from

When asked to level up, or before an important build, study these (fetch and read where possible, otherwise apply the noted lesson):

| Source | What to steal |
|---|---|
| **Bartosz Ciechanowski** (ciechanow.ski: "Mechanical Watch", "Internet", "GPS") | The gold standard for teaching mechanisms. Every diagram is manipulable. Concepts build strictly one at a time. Sliders let you feel the system. |
| **The Pudding** (pudding.cool) | Scrollytelling structure: data becomes a story with a protagonist. Pinned graphics that transform as you scroll. |
| **Nicky Case** ("Parable of the Polygons", "The Evolution of Trust") | Playable explanations. The learner runs the simulation and discovers the conclusion themselves. Friendly, zero jargon. |
| **R2D3** ("A Visual Introduction to Machine Learning") | One continuous scroll where a single dataset transforms through every concept. The running-example principle, perfected. |
| **Distill.pub** | Rigor + interactivity. Marginal notes, hover definitions, figures readers can interrogate. |
| **NYT "Snow Fall" and NYT Graphics** | Full-bleed immersion, media woven into text, restraint: long quiet stretches make the big moments land. |
| **Bret Victor** ("Explorable Explanations", "Up and Down the Ladder of Abstraction") | The philosophy: a reader should be able to ask "what if" and get an answer by doing, not by trusting. |
| **Stripe landing pages / docs** | Production polish: gradient craft, restrained motion, typography hierarchy, code-as-graphic. |
| **Josh Comeau** (joshwcomeau.com) | Micro-interactions in teaching: springy widgets, delightful controls that reinforce the concept. |
| **Neal.fun** ("The Deep Sea", "Wealth Shown to Scale") | Scale made visceral through committed scrolling. One idea, executed totally. |
| **Setosa** (setosa.io: "Conditional probability", "Pi visualized") | Small, perfect single-concept interactives. Proof you don't need a long page to teach one thing well. |

The shared DNA across all of these: a single running example, direct manipulation, one idea per screen, and graphics drawn for the idea rather than decorated around it.
