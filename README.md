# Aurora

Interactive aurora borealis simulator: solar storms, magnetosphere physics and dancing curtains
over a winter landscape. Pure canvas, one file.

**[Open it →](https://laci141.github.io/aurora/)** · or download `index.html` and double-click it.

Third in the series after [Density Wave](https://github.com/laci141/galaxy) (galaxy) and
[Orrery](https://github.com/laci141/orrery) (solar system). No libraries, no CDN, no WebGL,
no images — one self-contained `index.html` and canvas 2D.

## Two views, one simulation

The whole point: both views are windows onto the *same* running simulation, and you can switch
between them at any time with a 1.5 s eased dissolve.

**Space** — a side-on schematic of the Sun–Earth system. The Sun breathes and throws prominences;
Earth sits inside ~14 dipole field lines that compress on the dayside and stretch into a flapping
magnetotail. Solar wind particles stream across the gap, wrap around the magnetopause instead of
passing through it, and a fraction spiral down the polar cusps and flash out in the atmosphere.
Every flash feeds the precipitation rate.

**Sky** — ground level on a winter night. Curtains of light fold and ripple over snow-covered
hills, a spruce treeline and a cabin with a lit window, mirrored in a frozen lake.

Launch a CME in Space view and watch it arrive: the cloud crosses the gap in 6–14 seconds, the
dayside field lines buckle, and about two seconds later the sky ignites — low arcs first, then
towering curtains that decay back to quiet over 30–90 seconds.

## The physics behind the picture

- **Storm cycle**: quiet → eruption → transit → impact → storm → decay, driven by a Kp-like
  activity index (0–9).
- **Colour by altitude**: bright green (oxygen, ~100–150 km) at the base of every ray, deep red
  (oxygen above ~200 km) creeping into the ray tops during strong storms, purple/blue nitrogen
  fringes at the very bottom edge when activity is high.
- **Surges**: every 10–30 s a bright pulse runs horizontally along a curtain — the real auroral
  surge, and the best thing the sky does.

## Controls

| Key | |
|---|---|
| `V` | switch view |
| `C` | launch a CME |
| `H` | hide / show the UI |
| `F` | fullscreen |
| `P` | photo (PNG) |
| `Space` | projector mode |
| `M` | sound |
| `Esc` | leave projector mode |

The glass panel has three tabs — **Storm** (view, activity, CME, time speed, camera, layers),
**Visuals** (four palettes with a 4.5 s crossfade, colour boost, star density, photo, copy link,
projector, hide UI) and **Sound** (procedural Web Audio: solar wind, deep drone, aurora shimmer,
impact boom, cusp chimes — nothing is downloaded, every sound is generated live).

Interface in **English, Hungarian, Romanian and German**.

## Notes

- Seeded randomness (mulberry32) — the seed and every setting live in the URL, so *Copy link*
  brings back exactly the same sky.
- Pre-rendered sprites on offscreen canvases, flat typed arrays for particles, DPI-aware
  rendering capped at 2×, and a performance guard that thins detail if the frame rate drops.
- `prefers-reduced-motion` starts paused in Sky view on a still, moderate aurora.

Made by laci141. MIT licensed.
