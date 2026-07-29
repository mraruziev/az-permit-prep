# Arizona Permit Prep

Interactive study app for the **Arizona MVD Class G written knowledge test** — the permit test.
Eight narrated animated lessons, 166 practice questions, full-length mock exams, road sign drills
and a cheat sheet. One HTML file, no build step, no dependencies, no tracking.

> **Study aid, not the official test.** Questions here are written from Arizona traffic law and MVD
> practice, but rules change. Confirm anything you are unsure about against the current
> [Arizona Driver License Manual](https://azdot.gov/mvd) before test day.

## Try it

Open `index.html` in any browser. That is the whole install.

If GitHub Pages is enabled for this repo, it is also live at
`https://<your-username>.github.io/az-permit-prep/`.

## What's in it

### Animated lessons — 8 lessons, 28 scenes, ~6 minutes

Each lesson plays like a video: play/pause, a scrubber, chapter jumps, and 0.75×/1×/1.5× speed.
The visuals are drawn live on a `<canvas>`, and there is an optional **voice-over** that reads the
narration aloud using the browser's built-in speech synthesis. Every lesson has a full text
transcript underneath and a button that drops you straight into that topic's quiz.

| Lesson | Covers |
|---|---|
| Signs, Signals & Markings | Sign shapes and colors, signal states including flashing and dark signals, pavement lines |
| Right-of-Way | Four-way stops, unprotected left turns, roundabouts, school buses and the median exception |
| Speed, Lanes & Space | Arizona's limits, the two-second rule, why braking distance grows with speed squared |
| Sharing the Road | The 3-foot bicycle law, truck No-Zones, motorcycle lane rights, crosswalks |
| Alcohol, Drugs & the Law | BAC thresholds, implied consent, the point system, insurance minimums |
| Arizona Rules & Licensing | Permit to Class G, curfew and passenger restrictions, headlight and signal distances |
| Emergencies & Arizona Weather | Dust storm procedure, flooded washes, skid and blowout recovery |
| Parking & Vehicle Basics | Curb clearances, hill parking wheel direction, ABS braking |

### Practice modes

- **Practice Exam** — 30 questions drawn evenly across all eight topics, scored at the end with no
  hints. 24 correct to pass, matching the real test's 80% threshold.
- **Quick Quiz** — 10 random questions with the answer explained immediately.
- **Road Signs Drill** — all 27 signs, one at a time.
- **Missed Questions** — automatically collects questions you get wrong more often than right.
- **Topic drills** — any one of the eight topics on its own.

### Reference

- **Sign Chart** — all 27 signs as hand-drawn SVG, with shape, color class and meaning.
- **Cheat Sheet** — the numbers worth memorizing, grouped for a last look before the test.
- **Progress** — per-topic accuracy, test history, and overall stats.

## Arizona-specific content

The question bank leans on the things Arizona actually tests and other states do not:

- **Dust storms** — pull fully off the road, lights **off** including hazards, foot off the brake
- **Flooded washes** — and the Stupid Motorist Law that bills you for your own rescue
- **3-foot minimum** clearance when passing a bicycle
- **Hands-free law** — you may not hold or support a phone while driving
- **Class G restrictions** — one passenger under 18, no driving midnight to 5 a.m.
- **Permit at 15½** with a licensed driver 21 or older in the front seat
- Speed limits of 15 / 25 / 65 / 75, and the basic speed law that overrides all of them

## Keyboard shortcuts

**In a quiz:** `1`–`4` answer · `Enter` next question · `Esc` exit

**In a lesson:** `Space` or `K` play/pause · `←` `→` seek 5 seconds · `Esc` back to the lesson list

## Notes for anyone reading the source

- **Single file, zero dependencies.** All CSS and JS are inline. Nothing is fetched at runtime, so
  it works fully offline.
- **Progress is local.** Scores, topic accuracy and watched lessons live in `localStorage` under
  `az-permit-prep/v1`. Nothing leaves your browser.
- **Themes.** Light and dark are both designed, driven by `prefers-color-scheme` with
  `[data-theme]` overrides available on the root element.
- **Road signs are SVG,** generated from a catalog in the source. That catalog doubles as the sign
  quiz bank, so a sign only has to be described once.
- **Lessons are canvas animations.** Each scene is a `draw(g, p)` function where `p` runs 0 to 1
  across the scene, drawn through a small set of primitives (`car`, `bike`, `truck`, `bus`, `ped`,
  `road`, `signpost`). Adding a scene means adding one object to the `LESSONS` array.
- **Sign colors are deliberately not themed.** A stop sign is red on any background.

## License

MIT — see [LICENSE](LICENSE).
