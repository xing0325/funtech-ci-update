# FUNTECH CI — Page 03 「CI UPDATE」 clone spec

Source: https://ci.funtech.inc/en/ci-update (slide 03 of a 14-page CI manual)
Multi-session parallel clone effort — this session owns **page 3**. Standalone single-file build.

## Interaction model
Single non-scrolling screen (`main` is `overflow:hidden`). Continuous JS/CSS animations
(marquee scroll, odometer roll, red grain noise, gear spin). No page scroll. Menu opens on click.

## Design tokens
- Background: `#1C1D1E` (charcoal)
- Foreground / cream: `#F2EEEB`
- Brand red: `#FF481B` (rgb 255,72,27)

## Fonts
- `elevon` — Adobe Typekit kit `pfl7wcw` — display: marquee (900), headline (900), numbers (400)
- `proxima-nova` — Typekit `pfl7wcw` — UI labels, weight 600, ~12–16px, letter-spacing 0.3–0.75px
- `Zen Kaku Gothic Antique` — Google Fonts, weights 400/500/700/900 — JP/body

## Layout (reference frame 1425×675, 8px padding)
- Left rail  x8–208 (~200px, full stage height): vertical thumbnail nav, current (03) highlighted
- Stage      x208–1417, y8–611 (1209×603): the animated content stage
- Bottom bar y611–667 (~52px, full width): prev/next nav + corporate/wantedly + PDF/JP/EN

## Stage layers (back → front)
1. Charcoal base
2. **6-row red `CIUPDATE` marquee wall** — elevon 900, `#FF481B`,
   font-size `clamp(96px, max(22cqw, calc(100cqh/6)), 360px)` (≈266px → 22cqw wins → giant),
   line-height 1, 6 rows stacked & vertically centered (overflows → ~2–3 rows visible),
   each row scrolls horizontally seamless, alternating direction
3. Diagonal repeating-linear-gradient stripes (-135deg), low opacity
4. Radial-gradient vignette (ellipse at center → dark edges)
5. Red grain noise `<canvas>` + animated noise border (keyframes noise-border-h/v-cycle, noise-illustration-cycle)
6. **Crisp cream headline** `FUNTECH CI / FOR / NEXT / YEARS` — elevon 900, ~75px, `#F2EEEB`,
   kinetic scattered placement, stagger fade-up on load

## HUD chrome
- Top-left (in stage): `03.` rolling odometer (elevon red) + `CI UPDATE` label (proxima cream) + spinning gear ⚙ (keyframe `spin`)
- Top-right: ⚡️ 🏆 🎉 emoji toggle buttons (32px) + sound icon (keyframe `sound-bar-pulse`) + MENU
- Bottom bar: `← 02 BRAND MESSAGE` (prev) · CORPORATE SITE · WANTEDLY · PDF · JP/EN · `04 VISION VISUAL →` (next)
- Menu overlay: grid of 14 page thumbnails (downloaded to /thumbnails), `NN LABEL` red+cream, faint red marquee behind

## Deck index (for nav + menu)
01 HOME · 02 BRAND MESSAGE · **03 CI UPDATE** · 04 VISION VISUAL · 05 FUNTECH WAY ·
06 A MILLION-VOLT CREATIVE · 07 BREAKERS OF VICTORY · 08 ALL FOR FUN · 09 LOGO DETAILS ·
10 LOGO VARIATION · 11 10th SPECIAL ITEM · 12 ENDING MESSAGE · 13 WE ARE FUNTECH · 14 FIN

## Notes / gotchas
- Original site freezes rAF/canvas in background tabs → screenshots time out (not a bug). Verify via DOM/eval or clone locally.
- Chrome auto-translate polluted text extraction; all copy above is the pre-translation English.
- Prev/next/menu links point to the live ci.funtech.inc pages (other slides owned by other sessions).
- Marquee scroll speed is approximated (original is bundled rAF, unreadable while frozen).
