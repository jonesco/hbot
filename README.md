# H-Bot Academy

Study games built for one 8th grader. Two so far.

- **H-Bot Math (Slope Quest)**, in `math/`: slope, the slope formula, y = mx + b, intercepts.
- **H-Bot Music (Note Quest)**, in `music/`: bass clef reading, ledger lines, rhythm, and the bass neck.

Each game is a single HTML file. No build step, no dependencies, no network calls beyond Google Fonts, which fall back to system fonts offline. The root page is a lobby that reads each game's saved XP out of `localStorage` and shows it on the cabinet.

**Live:** https://jonesco.github.io/hbot/

## H-Bot Math

Five worlds, each opening with a Big Idea card stating the one concept the world runs on.

1. **What slope means.** Rise over run, read left to right. Drag two points and watch the numbers change.
2. **The slope formula.** Y's on top, same order both times. Includes missing-coordinate problems.
3. **y = mx + b.** m is the step, b is the spawn point. Sliders, spot-the-m-and-b cards, and two points to a full equation.
4. **Intercepts.** To find one, zero out the other. Slope-intercept form, standard form (the cover-up method), and graphing from two intercepts.
5. **Boss battle.** The Gradient Golem.

## H-Bot Music

Seven worlds, same shape, with sound. Notes play through the Web Audio API, pitched an octave up so laptop speakers can carry them.

1. **The staff.** Five lines, four spaces, and a note she can walk up and down while listening.
2. **Landmarks.** The two dots hug the F line. G B D F A and A C E G, tappable, with a drill.
3. **Reading notes.** Line or space, which one, then the letter. Built in steps, then a speed round.
4. **Ledger lines.** Middle C above, open E below.
5. **Rhythm.** Note values, counting, and a tap-along bar that scores each note hit or missed.
6. **On the bass.** Read the note, tap it on a fretboard. Any correct position counts.
7. **Boss battle.** The Sour Note.

## How the practice works

Problems are built one step at a time instead of asking for a final answer. In math that means tagging the points, tapping numbers into the formula, working out the top, the bottom, then dividing. In music it means line or space, which one, then the letter. A running board shows the work stacking up line by line, the way you'd write it on paper, with a short note under each line. Every step has a hint, and missing a step twice shows the answer with the reasoning.

Wrong answers get diagnosed where possible: a flipped sign, an upside-down fraction, a swapped point order, or a fretboard spot that is actually some other note.

## Shared engine

Both games run on the same code: worlds and steps, a Big Idea card per world, step-by-step problem building, drills with combo counters, XP and ranks in `localStorage`, an arcade intro with a chiptune written in the Web Audio API, and a boss fight with a finisher. Both work on phones and respect `prefers-reduced-motion`.

## Editing

Each `index.html` is one file: styles at the top, markup in the middle, script at the bottom.

Question generators are functions named `gen*`. Math has `genSlope`, `genMB`, `genFromPoints`, `genMissing`, `genIntSI`, `genIntStd`, `genIntPlot`. Music has `genLineSpace`, `genNameSteps`, `genNameQuick`, `genLedger`, `genFret`, `genTap`. Each returns a list of steps, a board, and a draw function for the graph or staff. Homework problem sets live in the `HW_*` and `IXL` arrays; rhythm patterns live in `BARS`.
