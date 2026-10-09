# The Lucky Drum

A fun way to pick numbers for UK National Lottery draw games. Choose a game, press **Draw**, and watch
numbered 3D balls tumble around a glass draw machine. Your numbers are pulled out one at a time and
bounce into a tray at the front.

It's a single web page with no build step and no install.

## Games

| Game | What you get | Jackpot odds |
| --- | --- | --- |
| Lotto | 6 numbers from 1–59 | 1 in 45,057,474 |
| EuroMillions | 5 numbers from 1–50 + 2 Lucky Stars from 1–12 | 1 in 139,838,160 |
| Set For Life | 5 numbers from 1–47 + 1 Life Ball from 1–10 | 1 in 15,339,390 |
| Thunderball | 5 numbers from 1–39 + 1 Thunderball from 1–14 | 1 in 8,060,598 |
| Lotto HotPicks | 1–5 numbers from 1–59 (you choose how many) | depends on picks |
| EuroMillions HotPicks | 1–5 numbers from 1–50 (you choose how many) | depends on picks |

The page works out the odds for the game and number of picks you choose.

## How to use it

1. Pick a game from the row of buttons at the top.
2. For a HotPicks game, choose how many numbers you want (1–5).
3. Press **Draw**. The drum mixes the balls, then draws your numbers one by one.
4. Your numbers appear under **Your numbers**, sorted from lowest to highest.
5. Press **Copy numbers** to copy them, ready to paste into the National Lottery app or website.

Other controls:

- **Quick Dip ×5** makes five extra lines instantly, without the animation.
- **Your lines** keeps your last 30 lines. Use **Copy all lines** or **Clear lines**.
- **Sound on / Sound off** switches the sound effects.

The page remembers your chosen game, your saved lines and your sound setting in your browser.

## Running it

**Open the file:** download or clone this repository and open `index.html` in any modern browser.

**Run a local server:**

```bash
npx http-server .
```

Then open the address it prints (usually http://localhost:8080).

**Host it on GitHub Pages:**

1. In the repository on GitHub, go to **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Pick the branch that contains `index.html` and the `/ (root)` folder, then save.
4. After a minute or two, the site appears at `https://<your-username>.github.io/<repository-name>/`.

You need an internet connection, because the page loads Three.js and its fonts from CDNs.

## How it works

- **3D scene:** [Three.js](https://threejs.org) (r128) draws the glass drums, brass rings, stand, tray and balls,
  with studio-style lighting, reflections and soft shadows.
- **Ball physics:** a small physics loop moves each ball, with gravity, an air blast during mixing, bounces off the
  drum wall and collisions between balls.
- **Ball faces:** each ball's number is drawn onto a canvas and wrapped round the ball. Main balls are coloured by
  number range. Lucky Stars are gold stars, Life Balls are teal and Thunderballs are purple.
- **Sound:** the Web Audio API makes the mixing rumble, the whoosh and the plink sounds, so there are no audio files.
- **Phones and accessibility:** the layout fits phone screens. If your device is set to reduce motion, the
  animation speeds up and the mixing is skipped.

## Fair randomness

Numbers come from `crypto.getRandomValues`, the browser's cryptographic random number generator. Rejection
sampling removes bias, so every ball in a pool has exactly the same chance of being picked, and no number repeats
within a line.

No way of choosing numbers changes your chances of winning. Every combination is equally likely.

## Project files

| File | What it is |
| --- | --- |
| `index.html` | The whole app: page layout, styles, 3D scene, physics and draw logic |
| `README.md` | This file |

## Play responsibly

You must be 18 or over to play National Lottery games. Check the rules, prices and draw times at
[national-lottery.co.uk](https://www.national-lottery.co.uk). For support, visit
[BeGambleAware](https://www.begambleaware.org).

This project isn't affiliated with or endorsed by the National Lottery or its operator.
