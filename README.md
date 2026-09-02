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
- **Class tabs**: All (55) / Class 10 (19) / Class 11 (7) / Class 12 (29) — full NCERT lech1+lech2 (Class 12 Part II) coverage
  - Class 10: H₂, O₂, N₂, Cl₂, HCl, H₂O, CO₂, NH₃, NaCl, H₂SO₄, HNO₃, CaCO₃, CH₄, C₂H₆, C₂H₄, C₂H₂, CH₃OH, C₂H₅OH, CH₃COOH
  - Class 11: BeCl₂ (linear), BF₃ (trigonal planar), O₃, CH₂O, C₆H₆ (benzene), PCl₅, SF₆ (octahedral)
  - Class 12 — Haloalkanes/Arenes: CH₃Cl, C₂H₅Br, C₆H₅Cl, CH₂Cl₂, CHI₃, C₆H₅CH₂Cl, CHCl₃, CCl₄
  - Class 12 — Alcohols/Phenols/Ethers: C₆H₅OH, p-Cresol, C₆H₅OCH₃, C₂H₅OC₂H₅, C₃H₈O₃ (glycerol)
  - Class 12 — Aldehydes/Ketones/Acids: HCHO, CH₃CHO, C₆H₅CHO, CH₃COCH₃, CH₃COC₂H₅, C₆H₅COCH₃, C₆H₅COC₆H₅, HCOOH, CH₃COOH, C₆H₅COOH, (COOH)₂, NH₂CONH₂
  - Class 12 — Amines: CH₃NH₂, C₂H₅NH₂, C₆H₅NH₂ (aniline)
  - Class 12 — Biomolecules: C₆H₁₂O₆ (glucose, pyranose), C₂H₅NO₂ (glycine), C₁₂H₂₂O₁₁ (sucrose, α-glucose+β-fructose)
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
