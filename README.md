# 🦋 Fly In Chaos

> **The butterfly effect, made playable — and you can hear it.**

[![Play](https://img.shields.io/badge/▶_play-flyinchaos.com-ff4081?style=for-the-badge)](https://flyinchaos.com)
[![License](https://img.shields.io/badge/license-MIT-69f0ae?style=for-the-badge)](#license)
[![Single file](https://img.shields.io/badge/one%20file-no%20build-39d0ff?style=for-the-badge)](#tech-notes-for-the-curious)

A one‑tap arcade game where the thing that beats you isn't bad luck, a hidden difficulty spike, or a designer being cruel — **it's a law of nature.** You steer a butterfly through a chaotic wind, and a twin that starts **3 pixels** from you, with the *same* inputs and the *same* wind, peels away in real time. That divergence *is* the butterfly effect — drawn as a live graph and a rising tone you can actually hear.

> *One flap. Infinite outcomes.*

🔗 **Play free, no install:** [flyinchaos.com](https://flyinchaos.com) — works on desktop and mobile (rotate to landscape).

---

## The science (it's real, not a skin)

Every concept below is tied to a real mechanic — no marketing fiction. Physicists read this, and precision is the whole reason it goes viral, so the on‑screen curve is presented honestly as a *signature*, not an overclaim.

| Chaos concept | What you **see / do** in the game |
|---|---|
| **Sensitive dependence on initial conditions** | A magenta twin launches **3 px** from your gold butterfly with identical flaps and identical wind, then diverges exponentially. The orange scope plots the gap on a **log axis**; a tone climbs in pitch as it grows. |
| **Determinism ≠ predictability** | The world is fully **deterministic** — a seeded daily puzzle, identical for everyone on Earth — yet you can't *compute* the solution; you have to *feel* it. Same rules, no foresight. |
| **Chaotic advection** | Your butterfly is a tracer in a smooth‑but‑chaotic 2D flow. The ambient streaks look calm; your path through them does not. |
| **Blinking / impulsive vortices** | Your taps inject **real, decaying vortices** into the wind field (the classic stirring mechanism). You don't just endure chaos — you *stir* it. The butterfly perturbs the atmosphere. |
| **Lyapunov signature** | The straight log‑climb on the scope *is* e^{λt}; the plateau is the bounded strange attractor (the screen) doing exactly what the math says. |
| **Fractal basin boundaries** | The line between "win" and "lose" as a function of your taps is fractal — nudge one tap a pixel and your fate flips. That's why "one more try" is mathematically honest. |

> *Integrity note:* the on‑screen curve is a finite‑ε, single‑run **signature** of exponential divergence — a faithful fingerprint of chaos — not a numerically converged Lyapunov exponent. Honesty is part of the design.

## How to play

- **Tap / click to flap.** The butterfly is pushed *away* from your finger — tap **behind** it to fly forward, **below** to rise, **above** to brake the climb.
- Land on the flower before you drift off‑screen or run out of flaps. Clear **12 levels**.
- **V** chaos view (divergence replay) · **M** mute · **R** restart level · **S** share run · **A** assist (menu).

## Features

- **12 levels** with a fair, bounded difficulty curve and a victory screen.
- **Deterministic daily world** — the same puzzle for everyone each day (UTC), so it's raceable and reproducible.
- **Divergence replay + sonification** — watch *and hear* your run and its 3 px twin tear apart.
- **PNG share card** — export your run's divergence fan as an image.
- **Fair budget‑relative stars** — ★★★ always means "efficient flight," at every level.
- **Assist mode** (excluded from records) and **prefers‑reduced‑motion** support.
- **Installable PWA** with offline play.
- **Fair playfield** — a fixed logical resolution letterboxed to any device, so difficulty is identical on every screen, orientation, and zoom.
- **Fully synthesized audio** — wind hum, tap whoosh, the divergence tone, win/lose/victory stingers. No audio files, no licensing.

## Why it's not "Flappy with a coat of paint"

Flappy's pipes are obstacles you dodge; here the "obstacle" is a deterministic chaotic field you can read and stir. The divergence isn't decoration — it's the *receipt* that the thing you're fighting is real sensitive dependence. And the daily seed makes it a shared puzzle, not a solo grind. Failing is gorgeous: a death is a fractal ribbon of every way that run could have gone, with a tone that tells the story of how it fell apart.

## Tech notes for the curious

This is intentionally a **single self‑contained `index.html`** — no build step, no framework, no external assets, no network calls during play:

- **Physics:** fixed‑timestep integrator (frame‑rate independent) over a 2D time‑dependent flow + sum‑of‑vortices ripple field.
- **Determinism:** a seeded PRNG (`mulberry32`) drives the daily world; `Math.random` is used *only* for cosmetics, never gameplay.
- **Audio:** 100% Web Audio API synthesis (no samples).
- **Fairness:** all gameplay math runs in a fixed logical playfield and is letterboxed to the device — same geometry on every phone, tablet, monitor, orientation, and zoom.
- **Offline:** a service worker + web manifest make it installable and playable offline.

## Run it locally

It's a single static file. Open `index.html` in a browser, or serve the folder:

```bash
npx serve .
```

### Deploy

Drop the folder (`index.html`, `manifest.webmanifest`, `icon.svg`, `sw.js`, `og.png`, `netlify.toml`) onto [Netlify Drop](https://app.netlify.com/drop), or push to GitHub and connect Netlify / Vercel / Cloudflare Pages (build command: *empty*; publish directory: `.`).

## Support

Fly In Chaos is **free, forever.** If it made you feel something, you can support development (UPI / cards via Razorpay):

🔗 **[razorpay.me/@kumarankit5563](https://razorpay.me/@kumarankit5563)**

## License

Released under the **MIT License** — fork it, learn from it, build on it. See [`LICENSE`](LICENSE).

## Contributing

Contributions welcome — open an issue or a PR. Areas I'd especially love help with:

- **Translations** (real global reach).
- A **screen‑space UI layer** (crisp HUD / 44 px‑tappable pills on phones).
- The **global daily leaderboard** (server‑side replay‑verified, anti‑bot scoring).
- An **Android** build (Capacitor).
- A **classroom edition** — a "predict‑then‑reveal" lesson mode for teaching chaos theory.

## Roadmap

- Global **daily leaderboard** with replay‑verified, anti‑bot scoring.
- **Android** (Capacitor) + portal distribution.
- **Classroom edition** for teaching sensitive dependence / chaos theory.

---

*Fly In Chaos — one flap. Infinite outcomes.* 🦋
