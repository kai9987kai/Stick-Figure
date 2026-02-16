# Stick-Figure Alive

A browser-based **stick figure rig lab** focused on animation systems: **IK**, **keyframes**, clip playback, terrain interaction, balance/COM tooling, and simple “beat-reactive” automation hooks. ([GitHub][1])

---

## What it does

* **Rig + IK + playback**

  * Play / Pause / Reset / Step (**+1/60s**) ([GitHub][1])
  * Clips: `idle`, `walk`, and `custom (JSON timeline)` ([GitHub][1])
* **“Alive” motion controls**

  * IK strength, foot planting, bob, lean ([GitHub][1])
  * **Possess mode**: drag hands/feet/head targets with the mouse ([GitHub][1])
  * Foot snapping: hold **Shift** while dragging feet to snap to terrain ([GitHub][1])
* **Advanced systems**

  * Terrain modes: `flat`, `wave`, `steps`, `noise` ([GitHub][1])
  * Auto balance
  * Trails: length + alpha
  * Beat controls: BPM + intensity
  * Toggles: **Beat Reactor**, **COM Overlay**, “Generate style clip” ([GitHub][1])
* **Record / Export**

  * Record toggle, add keyframe, clear keys, “Use as Custom Clip”
  * Timeline JSON export/import (export/import/copy/paste) ([GitHub][1])

---

## Quick start

1. Clone:

   ```bash
   git clone https://github.com/kai9987kai/Stick-Figure.git
   cd Stick-Figure
   ```
2. Open `index.html` in a browser (or serve locally):

   ```bash
   # optional: quick static server
   python -m http.server 8000
   ```
3. Visit:

   * `http://localhost:8000/`

> If your browser blocks some features when opening files directly (`file://`), use the local server method.

---

## Controls

### Keyboard shortcuts

* `Space` — play / pause ([GitHub][1])
* `R` — reset ([GitHub][1])
* `K` — add keyframe ([GitHub][1])
* `P` — toggle possess mode ([GitHub][1])
* `M` — mirror pose ([GitHub][1])
* `B` — beat toggle / beat reactor control ([GitHub][1])
* `C` — COM overlay ([GitHub][1])
* `G` — generate style clip ([GitHub][1])

### Mouse

* In **Possess mode**, drag targets (hands/feet/head). ([GitHub][1])
* Hold **Shift** while dragging feet to **snap** to terrain. ([GitHub][1])

---

## JSON automation files

This repo includes small JSON “action scripts” that look like input macros (buttons pressed for N frames):

* `actions-beat.json` ([GitHub][2])
* `actions-test.json` ([GitHub][3])

### Format (observed)

```json
{
  "steps": [
    { "buttons": ["space"], "frames": 2 },
    { "buttons": ["b"], "frames": 2 },
    { "buttons": [], "frames": 10 },
    { "buttons": ["left_mouse_button"], "frames": 2, "mouse_x": 420, "mouse_y": 420 }
  ]
}
```

([GitHub][3])

* `buttons`: array of symbolic inputs like `"space"`, `"b"`, `"left_mouse_button"`. ([GitHub][2])
* `frames`: how many frames to hold/apply that step. ([GitHub][2])
* optional mouse fields: `mouse_x`, `mouse_y` for click targeting. ([GitHub][3])

---

## Repository layout

* `index.html` — entry point / UI ([GitHub][4])
* `actions-beat.json` — minimal beat toggle loop ([GitHub][2])
* `actions-test.json` — sample multi-step input script ([GitHub][3])
* `output/` — output assets/exports (folder present) ([GitHub][4])
* `LICENSE` (MIT), `CODE_OF_CONDUCT.md`, `SECURITY.md` ([GitHub][4])

---

## License

MIT. ([GitHub][4])

---

## Contributing

Issues/PRs welcome—especially for:

* new terrain presets
* better foot plant & balance heuristics
* richer timeline JSON schema (curves, easing, constraints)
* deterministic replay + exportable clips

Please follow the project Code of Conduct. ([GitHub][4])

[1]: https://raw.githubusercontent.com/kai9987kai/Stick-Figure/main/index.html "Stick Figure Alive - Advanced Rig Lab"
[2]: https://raw.githubusercontent.com/kai9987kai/Stick-Figure/main/actions-beat.json "raw.githubusercontent.com"
[3]: https://raw.githubusercontent.com/kai9987kai/Stick-Figure/main/actions-test.json "raw.githubusercontent.com"
[4]: https://github.com/kai9987kai/Stick-Figure/tree/main "GitHub - kai9987kai/Stick-Figure"
