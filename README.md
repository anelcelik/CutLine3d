<p align="center">
  <a href="https://3dprinting.celikovic.xyz"><img src="docs/media/banner.png" alt="Cutline: split big 3D prints into parts and add joints that actually fit" width="100%"></a>
</p>

<p align="center">
  <a href="https://3dprinting.celikovic.xyz"><img alt="Try it live" src="https://img.shields.io/badge/try_it-live-f2c43d?style=for-the-badge&labelColor=1b2a23"></a>
  <img alt="Runs in your browser" src="https://img.shields.io/badge/runs_in-your_browser-2f5d4e?style=for-the-badge&labelColor=1b2a23">
  <img alt="Nothing is uploaded" src="https://img.shields.io/badge/uploads-none-2c7a50?style=for-the-badge&labelColor=1b2a23">
  <a href="LICENSE"><img alt="MIT license" src="https://img.shields.io/badge/license-MIT-78aee0?style=for-the-badge&labelColor=1b2a23"></a>
</p>

# Cutline

**Split 3D prints into parts and add joints, right in your browser.**

Cutline cuts a model that's too big for your printer (or just awkward to print) into pieces. It adds a joint so the pieces fit back together, then gives you print-ready files. Everything runs on your own device. Your files are never uploaded anywhere.

**Try it:** https://3dprinting.celikovic.xyz

<p align="center">
  <img src="docs/media/demo.webp" alt="Dropping a 342 mm rocket onto Cutline, cutting it to fit a 256 mm bed, adding a thread joint, splitting it, playing the assembly animation and downloading the parts" width="100%">
</p>

<p align="center"><a href="docs/media/cutline-promo.mp4"><b>▶ Watch the full video (1080p MP4)</b></a></p>

## How it works

1. **Drop in a model.** STL, 3MF or OBJ, dragged onto the mat or picked from disk.
2. **Pick where to cut.** Slide the cut, let it snap to good spots, or press **Cut to fit my bed**.
3. **Choose a joint.** Dovetail, dowel, snap fit, thread, magnets, puzzle cut or jigsaw.
4. **Split and download.** You get a `.zip` with one STL per part, the pins, and a 3MF laid out and ready to slice.

## A joint for every kind of part

<p align="center">
  <img src="docs/media/joints.png" alt="The sample block and sample plate split with each of the 8 joint types: dovetail, angled dovetail, dowel pins, snap fit, thread, magnets, puzzle cut and jigsaw puzzle" width="100%">
</p>

## Jigsaw mode

Flat parts can become a full jigsaw puzzle. Pick the rows, columns, tab size and randomness, then watch it put itself back together.

<p align="center">
  <img src="docs/media/jigsaw.webp" alt="A CUTLINE sign cut into 12 jigsaw pieces that fly into place" width="85%">
</p>

## Look inside before you print

Section view slices through the assembled parts so you can check how a joint engages. X-ray makes every part see-through.

<p align="center">
  <img src="docs/media/inspect.webp" alt="Section view cutting through the rocket's thread joint, then X-ray showing the thread inside the assembled rocket" width="85%">
</p>

## Edit the model first

Scale, rotate, mirror, lay flat on a face, trim, drill screw or magnet holes, or add blocks and cylinders. Every change can be undone.

<p align="center">
  <img src="docs/media/edit.webp" alt="Drilling an 18 mm hole through the sample block and adding a cylinder on top in Edit mode" width="100%">
</p>

## Light and dark

Cutline follows your system theme.

<p align="center">
  <img src="docs/media/themes.png" alt="The Cutline interface split diagonally between the light and dark themes" width="100%">
</p>

## Features

- **Open** STL, 3MF and OBJ files. Drag and drop works.
- **Print bed presets** (Bambu Lab, Prusa, Creality) or a custom build volume. Includes "cut to fit my bed".
- **Cut** along X, Y or Z into any number of pieces. The cut slider snaps to good spots.
- **Joints:**
  - Dovetail and angled dovetail
  - Dowel pins
  - Snap fit
  - Thread
  - Magnet pockets
  - For flat parts: puzzle cut and a full jigsaw puzzle
- **Extras:** seam bevel, glue groove, optional magnets, and a printable clearance test to tune the fit for your printer.
- **Edit the model before cutting:** scale, rotate, mirror, lay flat on a face, trim, screw or magnet holes (M2–M6, countersink), and added blocks or cylinders. Full undo/redo.
- **Inspect the result:** exploded, assembled or print-layout views, X-ray, section view, isolate a part, and an assembly animation.
- **Filament estimate** by material, infill and price per kg.
- **Export** a `.zip` with one STL per part, the pins, and a 3MF with everything laid out, oriented ready to print.

## Running it locally

Cutline is a single self-contained `index.html`. No build step, no server code.

```sh
git clone https://github.com/anelcelik/CutLine3d.git
cd CutLine3d
python3 -m http.server 8000   # then open http://localhost:8000
```

Opening `index.html` straight from disk also works in most browsers. It needs an internet connection the first time, to load three.js, fflate and the font from their CDNs.

## Built with

- [three.js](https://threejs.org/) for 3D rendering (MIT)
- [Manifold](https://github.com/elalish/manifold) for robust mesh booleans, bundled as WebAssembly (Apache-2.0)
- [fflate](https://github.com/101arrowz/fflate) for zip and 3MF packaging (MIT)
- [Barlow Semi Condensed](https://fonts.google.com/specimen/Barlow+Semi+Condensed) (SIL OFL 1.1)

Every image and animation in this README was captured from the real app. The rocket and the sign are ordinary STL files run through Cutline; only the cursor and the captions were added on top.

## License

[MIT](LICENSE) © 2026 Anel Celikovic. The third-party libraries above keep their own licenses.
