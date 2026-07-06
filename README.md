# TETRACUBE '86 — 3D Tetris

A 3-dimensional Tetris with retro 80s arcade graphics: neon vector wells,
synthwave sun, CRT scanlines, and square-wave bleeps. Pieces fall into a
6×6×14 well — fill an entire 6×6 floor layer to clear it.

**Zero dependencies.** The 3D renderer is hand-rolled (perspective projection
+ painter's algorithm on a 2D canvas), so nothing to install and no network
needed.

## Run it locally

Just open the file:

```
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Or serve it (recommended for some browsers):

```
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Controls

| Key | Action |
|---|---|
| ← ↑ ↓ → | Move piece horizontally (camera-relative) |
| Q / E | Spin around vertical axis |
| W / S | Pitch toward/away from you |
| A / D | Roll left/right |
| Space | Hard drop |
| Shift (hold) | Soft drop |
| Mouse drag / `[` `]` | Orbit the camera · scroll wheel zooms |
| P | Pause |
| M | Toggle sound |
| R | Quit to menu |

## 50 levels of difficulty

Pick any start level (1–50) on the title screen. Gravity accelerates every
level (≈1.1 s per row at level 1 down to 70 ms at level 50). You level up by
clearing layers or surviving pieces (2 layers or 12 placed pieces per level).

## Shapes — new geometry unlocked as you climb

| Unlocks | Tier | Shapes |
|---|---|---|
| Level 1 | Flat classics | I-BEAM, CUBE, ELL, TEE, ESS |
| Level 5 | True 3D tetracubes | TRIPOD, SCREW-L, SCREW-R, TOWER |
| Level 12 | Pentacubes | STARFISH, ZIGGURAT, VIPER |
| Level 20 | Alien geometry | HELIX (a closed 6-cube loop), HYPERSTAR (3D plus, 7 cubes) |
| Level 30 | Endgame monsters | MEGACUBE (2×2×2), SERPENT (6-cube 3D zigzag) |
| Level 15+ | Mercy piece | MONOCUBE (rare single cube) |

Shapes like TRIPOD, SCREW, HELIX and HYPERSTAR only exist in 3D — they have
no flat equivalent.

## Scoring

- Layer clears: 100 / 300 / 800 / 2000 / 5000+ × level for 1/2/3/4/5+
  simultaneous layers
- Hard drop: 2 pts per row · soft drop: 1 pt per row · 2 pts per cube placed
- Hi-score persists in `localStorage`
