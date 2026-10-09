# The Lucky Drum

A fun way to choose UK National Lottery numbers. Pick a game, press **Draw**, and watch real 3D balls
tumble in a glass draw machine before your numbers are pulled out one by one and roll into the tray.

## Games

| Game | What you pick |
| --- | --- |
| Lotto | 6 numbers from 1–59 |
| EuroMillions | 5 numbers from 1–50 + 2 Lucky Stars from 1–12 |
| Set For Life | 5 numbers from 1–47 + 1 Life Ball from 1–10 |
| Thunderball | 5 numbers from 1–39 + 1 Thunderball from 1–14 |
| Lotto HotPicks | 1–5 numbers from 1–59 |
| EuroMillions HotPicks | 1–5 numbers from 1–50 |

## Features

- Three.js draw machine with glass drums, brass rings, studio lighting and ball physics (air-mix, collisions, bounces)
- A second drum for Lucky Stars, Life Ball and Thunderball
- Fair picks from `crypto.getRandomValues` with rejection sampling, so every ball is equally likely
- Quick Dip ×5 for instant extra lines, a saved list of your lines, and copy buttons
- Exact jackpot odds for each game, sound effects (toggleable), reduced-motion support, works on phones

## Run it

It's a single file. Open `index.html` in a browser, or serve the folder (e.g. `npx http-server .`).
It also works on GitHub Pages.

No way of picking numbers changes your odds. Play for fun, and only if you're 18 or over.
