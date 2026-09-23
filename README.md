# H-Bot Math

A video-game style algebra tutorial built for one 8th grader who was stuck on slope.

Everything lives in a single file, `index.html`. No build step, no dependencies, no network calls. Open it and it runs. Fonts come from Google Fonts and fall back to system fonts offline.

**Live:** https://jonesco.github.io/hbot/

## What's in it

Five worlds, each opening with a Big Idea card that states the one concept the world runs on:

1. **What slope means** — rise over run, read left to right. Drag two points and watch the numbers change.
2. **The slope formula** — y's on top, same order both times. Includes missing-coordinate problems.
3. **y = mx + b** — m is the step, b is the spawn point. Sliders, spot-the-m-and-b cards, and two points to a full equation.
4. **Intercepts** — to find one, zero out the other. Slope-intercept form, standard form (the cover-up method), and graphing from two intercepts.
5. **Boss battle** — the Gradient Golem. Eight questions, three hearts, and a finisher when it goes down.

## How the practice works

Problems are built one step at a time instead of asking for a final answer. She tags the points, taps numbers into the formula, computes the top, computes the bottom, then divides. A running board shows the work stacking up line by line, the way you'd write it on paper, with a short note under each line. Every step has a hint, and missing a step twice shows the answer with the reasoning.

Wrong answers get diagnosed where possible: a flipped sign, an upside-down fraction, a swapped point order.

## Other bits

- Arcade intro with a chiptune written in the Web Audio API. Sound toggle in the top bar; click the logo to replay the intro.
- XP, ranks and streaks, saved in `localStorage`.
- Works on phones.
- Respects `prefers-reduced-motion`.

## Editing

`index.html` is one file: styles at the top, markup in the middle, script at the bottom. Question generators are functions named `gen*` (`genSlope`, `genMB`, `genFromPoints`, `genMissing`, `genIntSI`, `genIntStd`, `genIntPlot`). Each returns a list of steps, a board, and a draw function for the graph. Homework problem sets are the `HW_*` and `IXL` arrays.
