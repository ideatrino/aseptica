# Aseptica

**A free, offline-first sterility-assurance toolkit.** Plan a sterilization cycle, read the sterility assurance level (SAL) it actually achieves, and keep a local, exportable record of every run — all in a single HTML file that runs in any browser, with no install, no account, and no data leaving your machine.

> **Not a medical device.** Aseptica is a planning and record-keeping aid. It does not sterilize anything and is not validated for clinical, pharmaceutical, or regulatory use. Always confirm with a biological indicator and your facility's validated protocol.

---

## Why this exists

Sterilization is governed by simple, well-understood mathematics — microbes die logarithmically, so survivors follow `N(t) = N₀ · 10^(−t/D)`. Yet the practical tools tend to fall into two camps: expensive validated enterprise systems aimed at regulated manufacturers, or one-off web calculators that show a number and forget it.

Aseptica aims at the gap between them:

- **The math is open and visible**, not hidden behind a paywall or a black box.
- **It keeps a record.** Most free calculators don't — Aseptica logs each cycle with a timestamp and lets you export to CSV or JSON.
- **It runs fully offline** in a single file, so it works in a lab with no internet and keeps your records private to your own browser.

It won't replace a validated system where regulations demand one. It's built for students, makers, small clinics, home labs, food-preservation hobbyists, and anyone who wants to understand and document the cycle they're running.

## What it does

- **Cycle calculator** — enter the method (with typical D-value presets), exposure time, starting bioburden, and target SAL; get the log reductions, the achieved SAL, the expected survivors, and a clear PASS / FAIL verdict.
- **Solve for time** — one click tells you the exposure needed to reach your target SAL.
- **Live survivor curve** — a log-scale plot redraws as you type, showing the cycle against the "1 organism" line and your target SAL.
- **Cycle log** — save runs to a local log, then export to CSV or JSON for your records.

## Use it

Open `index.html` in any modern browser. That's the whole install.

To put it online for free, enable **GitHub Pages** on this repository (Settings → Pages → deploy from the `main` branch). Your tool will be live at `https://<your-username>.github.io/aseptica/`.

## The math, briefly

- `LR = t / D` — log reductions from exposure time `t` and D-value `D`.
- `achieved SAL = N₀ · 10^(−LR)` — expected survivors; below 1 it reads as the probability a unit is non-sterile.
- `time to target = D · log₁₀(N₀ / target SAL)`.

The standard target for terminal sterilization is a SAL of `1e-6` (a one-in-a-million chance of a non-sterile unit). D-value presets are typical illustrative figures — **always use the validated D-value for your own indicator, organism, and load.**

## Privacy

All records live in your browser's local storage. Nothing is uploaded anywhere. Clearing your browser data or using the "Clear log" button removes them.

## License

Licensed under the Apache License 2.0 — see [LICENSE](LICENSE). You're free to use, modify, and distribute it, including commercially, provided you keep the attribution and license notice.

## Author

**Ideatrino** · ideatrino@proton.me · 2026
