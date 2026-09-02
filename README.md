# Gesture Molecule Lab — Class 10/11/12 Smart Board AR

Upgraded prototype for INSPIRE MANAK / smart-board chemistry lessons.
Webcam hand-tracking + mouse/touch fallback. Single-file `index.html`.

## Folder
`D:\Projects\Chem-AR\`

## Run
Double-click `index.html` or serve via HTTPS/localhost for camera:
```powershell
# PowerShell — start local server on http://localhost:8080
Set-Location -LiteralPath "D:\Projects\Chem-AR"
python -m http.server 8080
# then open http://localhost:8080
```

Camera requires **HTTPS or localhost** (browser security). If camera is blocked, mouse/touch still works.

## Features
- **Class tabs**: All / Class 10 (16) / Class 11 (7+) / Class 12 (8) — 34 curated NCERT molecules
  - Class 10: H₂, O₂, N₂, Cl₂, HCl, H₂O, CO₂, NH₃, NaCl, H₂SO₄, HNO₃, CaCO₃, CH₄, C₂H₆, C₂H₄, C₂H₂, CH₃OH, C₂H₅OH, CH₃COOH
  - Class 11: BeCl₂ (linear), BF₃ (trigonal planar), O₃, CH₂O, C₆H₆ (benzene), PCl₅, SF₆ (octahedral)
  - Class 12: CHCl₃, CCl₄, C₆H₅OH (phenol), C₆H₅NH₂ (aniline), C₆H₅CHO, CH₃COCH₃ (acetone), NH₂CONH₂ (urea), C₃H₈O₃ (glycerol)
- **Search** by name/formula/category
- **Info panel** with formula, class, category, description
- **3D**: Three.js r128, atom labels always facing camera, bonds
- **Hand gestures (MediaPipe Hands + CameraUtils via CDN)**:
  - Move hand → rotate (palm landmark 9 delta * 4.6)
  - Pinch thumb(4)-index(8) distance → zoom (smoothed, mapped 5→14)
  - Open palm (4-5 fingers extended) hold 1.2s → reset view
  - Skeleton overlay + fps
- **Fallback**: mouse drag rotate, wheel zoom, 1-finger touch drag + 2-finger pinch, reset button
- **Responsive**: desktop smart-board grid (left cam / center 3D / right library), mobile single column

## Tech
- `Three.js` + `MediaPipe Hands` + `CameraUtils` (CDN)
- No build step, offline-capable after first CDN load

## Replace/Deploy
Copy `D:\Projects\Chem-AR\index.html` over your `Chem-AR` repo's `index.html` and push to GitHub Pages.

## License
Prototype — same as original Chem-AR.
