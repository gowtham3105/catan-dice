# Catan Dice

A beautiful, feature-rich dice roller built for Settlers of Catan. Runs entirely in the browser as a single HTML file — no build step, no dependencies.

**[Live Demo](https://gowtham3105.github.io/catan-dice/)**

## How It Works

### 1. Set Up Players
When you first open the app (or tap **New Game**), the **"Who Goes First?"** screen appears. Here you can:
- Edit player names by tapping the text fields
- Tap the color circles to cycle through 6 Catan player colors (red, blue, orange, white, green, brown)
- Adjust player count (2-6) via the Players panel

### 2. Pick First Player
Tap **"Pick First Player"** — the app automatically rolls for every player with staggered dice animations. The highest total wins and goes first. Ties are automatically re-rolled until a clear winner emerges. The player order is reordered so the winner starts.

### 3. Roll Dice
Tap **Roll Dice**, press Space/Enter, tap the dice directly, or shake your phone. The 3D dice animate, land on a result, and the turn automatically advances to the next player.

### 4. Special Rolls
- **Robber (7)** — a full-screen overlay appears with a pulsing pirate flag. Dismiss it to continue.
- **Snake Eyes (2)** — dice glow red with a sad descending chord
- **Boxcars (12)** — rainbow cycling glow with a triumphant fanfare
- **Doubles** — green highlight with a sparkle chime

### 5. Track the Game
- The **header** shows roll count, average, rolls since last robber, and total game time
- The **turn bar** shows who's rolling, a live turn timer, and who's up next
- **Roll history** displays the last 10 rolls as chips with mini dice faces and player colors
- The **Catan probability reference strip** highlights the current roll against expected pip counts

### 6. Review Stats
Expand **Session Statistics** to see:
- Total rolls, average, highest, lowest
- Robber count vs expected, doubles, boxcars
- Frequency distribution chart (actual vs expected)
- Per-player time stats: turns taken, total time, average time, longest turn
- Slowest player highlighted in red, fastest in green

### 7. New Game
Tap **New Game** at the bottom to reset everything. A styled confirmation modal appears. Stats, history, and timers are cleared, but your player setup is preserved. The first-roll selection starts again.

## Features

### Dice & Animation
- **3D CSS dice** with `transform-style: preserve-3d` and 4 roll animation variants
- **Cryptographic RNG** using `crypto.getRandomValues()` mixed with high-resolution timing
- **Particle effects** — earth-toned bursts on every roll, dark for robber, rainbow for boxcars
- **Ocean wave** animated background with aurora gradients

### Sound Engine
- Fully synthesized audio using the Web Audio API — no sound files
- **Unique musical motif per roll total** (2-12):
  - High-probability numbers (6, 8) — bright major arpeggios
  - Low-probability numbers (3, 11) — single tones
  - Robber (7) — ominous tritone with deep rumble
  - Boxcars (12) — triumphant C major fanfare
- Dice clatter on roll start (bandpass-filtered noise bursts)
- Toggle on/off with the speaker button

### Game Timer
- **Total game time** in the header, ticking live
- **Per-turn timer** in the turn bar — turns gold at 30s, pulses red at 60s
- **Per-player time stats** in the stats panel with slowest/fastest highlights

### Controls
- **Roll button** with ripple animation
- **Keyboard** — Space or Enter to roll, Escape to dismiss robber
- **Mobile shake** — `DeviceMotionEvent` with threshold > 30
- **Tap dice** directly to roll

### Persistence & PWA
- Full session state saved to `localStorage` — refresh and pick up where you left off
- **Installable as a PWA** — add to home screen on iOS/Android, works offline
- Saves: roll stats, distribution, history, player setup, timers, and current turn

### Design
- **Catan-themed** color palette: ocean blue background, parchment surfaces, warm gold accents
- Ivory dice with dark red dots matching real Catan dice
- Catan red roll button, earth-toned particles and charts
- Fully responsive — adapts for screens under 480px (iPhone 12 Pro tested)
- Single `index.html` file, zero external dependencies

## Install

Open `index.html` in any modern browser, or visit the [live demo](https://gowtham3105.github.io/catan-dice/).

**As a phone app:** Visit the live demo in Safari (iOS) or Chrome (Android), then add to home screen. It works offline and opens fullscreen.

## License

MIT
