RX100 Dodge 🏍️
A tiny, dependency-free browser game: steer a retro two-stroke-inspired bike
across a three-lane highway and dodge oncoming traffic for as long as you
can. Built with plain HTML, CSS, and JavaScript — no frameworks, no
build tools, no external libraries, no image assets. Everything you see is
drawn live on an HTML5 `<canvas>`.
![status](https://img.shields.io/badge/status-prototype-orange)
![stack](https://img.shields.io/badge/stack-HTML%2FCSS%2FJS-blue)
What it is
An endless, lane-based dodging game with a dark, high-speed road-racer
vibe.
The player's bike is "RX100-inspired" in feel only — a simple original
silhouette (no logos, no traced or copied artwork).
Vehicles spawn ahead and race toward the player; both their speed and
spawn rate increase the longer you survive.
Score is tracked continuously (distance survived + points per vehicle
dodged), with a persistent best score saved in your browser.
Full start screen with instructions, and a game-over screen with a
restart flow.
Keyboard controls plus on-screen touch buttons for mobile.
Project structure
```
rx100-dodge/
├── index.html   # Page structure: canvas, HUD, overlays, touch controls
├── style.css    # Dark road-racer theme, layout, responsive sizing
├── game.js      # All game logic: rendering, input, physics, difficulty
└── README.md    # This file
```
Running it locally
No installation, no dependencies, no build step. Pick any one of these:
Option A — just open it
Double-click `index.html` (or right-click → Open With → your browser).
Option B — a tiny local server (recommended)
Some browsers restrict certain features for files opened directly from
disk, so serving the folder is a bit more reliable:
```bash
# from inside the rx100-dodge folder
python3 -m http.server 8000
```
Then visit `http://localhost:8000` in your browser.
Any other static server works too (`npx serve`, VS Code's "Live Server"
extension, etc.) — there's nothing to install or compile.
Controls
Action	Keyboard	Touch / mobile
Move left	`←` or `A`	Tap the left arrow button
Move right	`→` or `D`	Tap the right arrow button
Start game	`Space` or `Enter`, or click/tap the start screen	Tap Start Ride
Restart after crash	`Space` or `Enter`, or click/tap the game-over screen	Tap Ride Again
How the difficulty scales
Speed ramps up smoothly the longer you survive, capped so the game
never becomes literally impossible.
Spawn rate increases over time, and past a certain point there's a
growing chance of a second vehicle spawning in a different lane —
never every lane at once, so there's always a gap to aim for.
Deploying to GitHub Pages
Create a new GitHub repository and push this folder's contents to it:
```bash
   git init
   git add .
   git commit -m "Initial commit: RX100 Dodge prototype"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
On GitHub, go to Settings → Pages.
Under Build and deployment → Source, choose Deploy from a
branch.
Pick the `main` branch and the `/ (root)` folder, then save.
GitHub will publish the site at
`https://<your-username>.github.io/<your-repo>/` within a minute or
two — no build step required, since it's static HTML/CSS/JS.
Notes on the art
There are no external image, font, or sound files — every shape (bike,
vehicles, road, lane markings) is drawn directly with Canvas 2D drawing
calls. This keeps the project genuinely dependency-free and easy to fork,
re-skin, or extend (new vehicle colors, new bike shapes, sound effects,
etc. can all be added directly in `game.js`).
Ideas for extending this prototype
Add power-ups (shields, score multipliers, slow-motion).
Add a simple sound engine using the Web Audio API.
Add a pause button / `Escape` key handling.
Save a small history of recent runs instead of just the single best
score.
Add background scenery (buildings, trees) scrolling behind the road for
extra depth.
