# Morphing Sphere

A playful browser-based generative art experiment where a dense particle cloud forms a rotating sphere and then morphs into user-defined text. Built as a single-page HTML project, it turns plain words into floating point clusters, animates them into a stylized 3D form, and lets you export the result as a PNG.

This project is a visual experience as much as a code demo: the sphere is generated with a golden-angle distribution, text is sampled into particles, and GSAP animates the positions to create a smooth morphing transition.

## Overview

Morphing Sphere is a static front-end experience that runs entirely in the browser. It uses:

- HTML for structure
- CSS for the dark-glass UI and responsive layout
- JavaScript for the particle engine and animation logic
- Three.js for the 3D point-cloud rendering
- GSAP for interpolated motion

The result is an art piece that feels like a word becoming a constellation, then collapsing back into an orbiting sphere.

## Key features

- Real-time particle sphere generation
- Text-driven morph animation using canvas sampling
- Interactive input field for custom words
- Auto-return to sphere after a short display interval
- Mouse wheel / trackpad pinch zoom control
- Mobile-friendly touch interactions
- PNG export button for saving the current composition
- Minimal dependencies, no framework build step

## Tech stack

- HTML5
- CSS3
- JavaScript (ES6+)
- Three.js r128
- GSAP 3.7.1

## Project structure

```text
.
├── index.html        # Complete project: markup, styles, logic, and animation
├── README.md         # Project documentation
└── .gitignore        # Optional repository metadata if present in your fork
```

In this repository, the app is intentionally compact: nearly all of the logic lives in a single `index.html` file, including the UI, styling, animation code, and the WebGL scene setup.

## How it works

The project is built around a particle system:

1. A set of particles is initialized on a spherical shell using a Fibonacci-like distribution.
2. These particles are stored in a `THREE.BufferGeometry` and rendered with `THREE.Points`.
3. When the user submits text, the app renders the text onto an offscreen canvas.
4. Pixel alpha values from that canvas are sampled to create a new set of target coordinates.
5. GSAP smoothly interpolates the particle positions from the sphere to the text layout.
6. After a delay, the particle positions animate back toward the sphere.

The motion is not a true 3D text mesh; instead, it is a point-cloud illusion that uses placement density and timing to suggest readable letters.

## Controls

### Text input

- Type any word or short phrase in the input box
- Press Enter or click the arrow button to trigger transformation
- The input is limited to a short phrase for readability and visual impact

### Camera / zoom

- Use the mouse wheel or trackpad gesture to zoom in and out
- On touch devices, pinch gestures adjust the same zoom value
- This provides a cinematic feel and gives the particle field more depth

### Export

- Click the `↓ PNG` button to export the current visual state
- The exported output is generated from the canvas renderer and saved as a PNG file

## Run locally

Because this is a static front-end app, there is no package install or compile step required.

### Option 1: open directly in a browser

Open `index.html` directly in any modern browser.

### Option 2: serve it locally

From the project directory:

```bash
cd morphing-sphere
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

This is the recommended method because some browsers handle local assets and external CDN resources more predictably when served from an HTTP server.

## Browser notes

- Works best in modern desktop browsers with WebGL enabled
- Mobile browsers are supported, including touch gestures
- If the page appears blank, verify that WebGL is enabled and that network access to the external CDN libraries is available

## Customization points

If you want to adapt the project, the most useful values are in the main script inside `index.html`:

- `particleCount` controls how many points are used
- `radius` defines the initial sphere size
- `size` in the `THREE.PointsMaterial` changes the particle size
- `sampleRate` controls how densely text is sampled into points
- `zoom` and min/max zoom values define the camera framing

These values make it easy to tune the aesthetic between a dense, airy cloud and a more compact, readable particle field.

## Performance considerations

The project scales particle counts depending on viewport size:

- Smaller screens use fewer particles to maintain responsiveness
- Larger screens and high-resolution displays increase particle density for extra detail

This variability keeps motion smooth across desktop and mobile devices while preserving the visual complexity of the artwork.

## Art direction

The visual design uses a dark background and a glowing purple palette, with a soft glassmorphism panel for the controls. This creates a futuristic, minimal aesthetic that complements the generative motion and provides a quiet contrast to the bright particle text.

## Limitations

- The text effect is optimized for short strings rather than long paragraphs
- It relies on browser WebGL support
- The repository currently contains a single static HTML demo; it is not a full application with backend services or persistent storage

## License

No explicit license file is present in this repository at the moment, so the codebase does not currently declare a license in the repository metadata. If you plan to reuse, modify, or redistribute the project, it is best to confirm the intended usage terms with the repository owner before publishing or commercializing it.

## Acknowledgements

This project relies on:

- Three.js for 3D rendering and particle geometry
- GSAP for smooth animation interpolation

## Summary

Morphing Sphere is a compact, elegant browser demo that turns a simple text input into a living particle sculpture. It combines 3D geometry, generative art, and animation to produce a memorable effect without requiring a build system or complex architecture.

If you want to explore the project further, the best place to start is the `index.html` file, where the full rendering loop, particle generation, text sampling, and UI behavior are all defined.

---

Created for the `PeppermintGrave/morphing-sphere` repository.



