# Nova Patrol

A single-file arcade space shooter that runs in the browser. Shoot waves of aliens, grab power-ups, and beat a boss every 5th wave. No build step, no dependencies.

## Play

Open `index.html` in any modern browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

To host it free on GitHub Pages: push the repo, then go to **Settings → Pages**, choose the `main` branch and the `/ (root)` folder.

## Controls

| Input | Action |
|---|---|
| Arrow keys / A, D | Move |
| Mouse or touch | Steer toward pointer |
| P / Esc | Pause |
| M | Mute / unmute sound |
| Enter / Space | Start or restart |

The cannon fires automatically.

## Game details

| Item | Behaviour |
|---|---|
| Grunt (pink) | 1 hit, 10 pts |
| Tank (amber, wave 3+) | 3 hits, 30 pts |
| Weaver (green, wave 6+) | 2 hits, 20 pts, weaves side to side when diving |
| Boss (every 5th wave) | Spread shots, 500 pts, restores 1 life. From wave 10 it alternates with aimed triple shots; from wave 15 the spread widens to 7 |
| Triple shot (cyan T) | 10 s |
| Shield (green S) | Absorbs 1 hit, lasts 8 s |
| Bomb (amber B) | Clears enemy bullets, 2 damage to every enemy on screen (10 to a boss) |
| Extra life (pink +) | +1 life, max 3 |
| Combo | Kills within 2 s of each other build a multiplier: x2 at 4 kills, up to x5 at 16. Taking a hit resets it |
| Diving aliens | From wave 2 |
| Aimed enemy shots | From wave 4 |

High score is stored in `localStorage` under `nova-best`; the mute setting under `nova-mute`. The game-over screen shows kills and best combo.

## Tech

Plain HTML, CSS and JavaScript on a `<canvas>`. Sound effects are synthesized with the Web Audio API, so there are no audio files. Alien sprites are mirrored pixel grids defined in code. Fonts (Bungee, Space Mono) load from Google Fonts, with system fallbacks.

## License

MIT
