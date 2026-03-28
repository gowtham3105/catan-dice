# Catan Dice

A beautiful, feature-rich dice roller built for Settlers of Catan. Runs entirely in the browser as a single HTML file — no build step, no dependencies.

**[Live Demo](https://gowtham3105.github.io/catan-dice/)**

## Features

### Dice Rolling
- **3D animated dice** with CSS `transform-style: preserve-3d` and multiple roll animations
- **Cryptographic RNG** using `crypto.getRandomValues()` mixed with high-resolution timing for fair rolls
- **Particle effects** — color-coded bursts on every roll (orange for robber, rainbow for boxcars, red for snake eyes)
- **Animated starfield** background with aurora gradient

### Special Roll Detection
- **Robber (7)** — dramatic full-screen overlay with pulsing pirate flag, shows rolls since last robber
- **Snake Eyes (2)** — red glow, descending minor chord
- **Boxcars (12)** — rainbow cycling glow, triumphant fanfare with confetti burst
- **Doubles** — cyan highlight with sparkle chime

### Sound Engine
- Fully synthesized audio using the Web Audio API — no sound files needed
- **Unique musical motif for each roll total** (2-12), reflecting Catan probability:
  - High-probability numbers (6, 8) get bright major arpeggios
  - Low-probability numbers (3, 11) get single tones
  - Robber (7) plays an ominous tritone with deep rumble
  - Boxcars (12) triggers a triumphant C major fanfare
- Dice clatter sound on roll start (bandpass-filtered noise bursts)
- Toggle on/off with the speaker button

### Multiplayer Turn Tracking
- **2-6 players** with customizable names and 6 color options (red, blue, orange, white, green, brown)
- Color-coded turn bar showing current roller and who's up next
- Player colors appear as dots in the roll history
- Turn automatically advances after each roll

### Statistics & Probability
- **Header stats** — roll count, running average, rolls since last 7 (highlights orange when overdue at 7+)
- **Catan probability reference strip** — shows pip dots for each number (2-12) matching the board tile dots, highlights the current roll
- **Session statistics panel** — total rolls, average, high/low, robber count, expected robbers, doubles, boxcars
- **Frequency distribution chart** — actual rolls vs expected probability (ghost bars), color-coded by number

### Roll History
- Last 10 rolls shown as chips with mini dice faces, player color dots, and totals
- Special styling for robber (orange) and boxcars (purple) rolls

### Controls
- **Roll button** with ripple animation
- **Keyboard** — Space or Enter to roll, Escape to dismiss robber overlay
- **Mobile shake** — uses `DeviceMotionEvent` to detect phone shaking (threshold > 30)
- **Click dice** directly to roll

### Persistence
- Full session state saved to `localStorage` — refresh the page and pick up where you left off
- Saves: roll stats, distribution, history, player setup, and current turn

### Design
- Dark theme with glassmorphism-style surfaces
- Animated aurora background with drifting starfield
- Fully responsive — adapts dice size and layout for screens under 480px
- Single `index.html` file (~1200 lines), zero external dependencies

## Usage

Open `index.html` in any modern browser, or visit the [live demo](https://gowtham3105.github.io/catan-dice/).

1. Tap **Roll Dice** (or press Space/Enter, or shake your phone)
2. Set up players via the **Players** panel — customize names and colors
3. Expand **Session Statistics** to see distribution charts and detailed stats
4. Robber overlay auto-dismisses on click/tap or press Escape

## License

MIT
