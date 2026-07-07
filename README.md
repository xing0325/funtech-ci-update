# FUNTECH CI — 03 CI UPDATE (clone)

Pixel-faithful, single-file clone of **slide 03「CI UPDATE」** from the FunTech Brand Identity
CI manual — https://ci.funtech.inc/en/ci-update

Part of a multi-session parallel cloning effort (this repo = **page 3**). Standalone, zero-build,
deploys to GitHub Pages.

## What it is
A single non-scrolling HUD screen:
- 6-row giant red **`CIUPDATE`** kinetic marquee wall (elevon 900, `#FF481B`)
- Cream headline **`FUNTECH CI / FOR / NEXT / YEARS`** (elevon 900)
- Layered stage: diagonal stripes + radial vignette + animated red grain `<canvas>` + noise border
- HUD chrome: rolling `03.` odometer + spinning gear, ⚡🏆🎉 toggles, sound bars, MENU
- Left rail thumbnail nav (14 slides) + full-screen menu overlay
- Bottom nav: ◄ 02 BRAND MESSAGE · CORPORATE SITE · WANTEDLY · PDF · EN/JP · 04 VISION VISUAL ►

## Tokens / fonts
`#1C1D1E` charcoal · `#F2EEEB` cream · `#FF481B` brand red ·
`elevon` + `proxima-nova` (Adobe Typekit kit `pfl7wcw`) · `Zen Kaku Gothic Antique` (Google Fonts)

## Run
Just open `index.html`, or serve statically:
```
python -m http.server 8178
```
Append `?freeze` to the URL for a static (no-animation) render — handy for screenshots / reduced motion.

## Notes
- Prev/next/menu links point to the live ci.funtech.inc pages (other slides owned by sibling sessions).
- Marquee scroll speed is a tasteful approximation (original is bundled rAF).
- See `SPEC.md` for the full reverse-engineering spec.

Cloned with the `clone-website` skill. Not affiliated with FunTech.
