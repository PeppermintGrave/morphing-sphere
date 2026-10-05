# PeppermintGrave // Morphing Sphere

> Particles become whatever you type.

**Morphing Sphere** is a small experimental web project by **PeppermintGrave**.

It starts as a sphere made from thousands of particles. Type something, and the particles smoothly leave their formation and become the shape of your text.

Then, after a moment, everything returns to the sphere.

No accounts. No backend. No database. Just particles, text, and a little bit of math.

---

## Live Demo

**[Open Morphing Sphere](https://peppermintgrave.github.io/morphing-sphere/)**

Works directly in the browser on desktop and mobile.

---

## What it does

The project begins with a smooth particle sphere generated using a Fibonacci distribution.

When you enter text:

```text
hello
```

the particles calculate positions based on the shape of the characters and smoothly morph into the word.

After a few seconds, they return to their original spherical formation.

The cycle is:

```text
SPHERE
   ↓
MORPHING
   ↓
TEXT
   ↓
RETURNING
   ↓
SPHERE
```

---

## Features

- Thousands of particles
- Fibonacci-distributed sphere
- Smooth text morphing
- Dynamic text sampling
- Unicode text support
- Emoji input filtering
- Automatic return to the sphere
- Smooth camera zoom
- Mouse wheel zoom
- Touch pinch zoom
- Responsive desktop/mobile layout
- Animated status indicators
- PNG export
- No backend required
- Single HTML file
- Works entirely in the browser

---

## The idea

The project is intentionally simple.

There is something interesting about taking something mathematically organized, like a sphere, and turning it into something readable.

The particles don't actually become a 3D model of the letters.

Instead, the text is drawn onto an invisible canvas, sampled for its visible pixels, and converted into thousands of particle positions.

Those positions become the destination of the morph.

```text
Text
 ↓
Canvas
 ↓
Pixel sampling
 ↓
Particle positions
 ↓
Smooth interpolation
 ↓
Text
```

---

## Technology

Morphing Sphere is built with:

- HTML
- CSS
- JavaScript
- [Three.js](https://threejs.org/)
- [GSAP](https://gsap.com/)

Three.js handles the particle scene and rendering.

GSAP handles the smooth transitions between particle positions.

The text shape is generated dynamically in JavaScript rather than using pre-made models for individual words.

---

## Particle sphere

The starting sphere uses a Fibonacci-style distribution.

This allows thousands of points to be spread across the surface of a sphere without simply stacking them into obvious rows or rings.

The result is a clean, evenly distributed particle formation.

The number of particles also adjusts depending on the screen size so the experience can remain usable on smaller devices.

---

## Text morphing

The text system works with arbitrary input rather than a fixed list of words.

The entered text is rendered to an offscreen canvas and sampled to find visible areas.

Those sampled positions are then converted into 3D particle targets.

If there are more particles than sampled text points, the points are reused with small variations so the entire particle system can still participate in the morph.

---

## Unicode

Morphing Sphere supports normal Unicode characters.

For example:

```text
Hello
বাংলা
日本語
Γειά
é
Ω
★
```

Emoji input is intentionally filtered out.

This keeps the text-particle system focused on characters that can be represented cleanly by the current rendering system.

---

## PNG Export

The `↓ PNG` button creates a PNG image of the current text formation.

The export uses a separate Three.js scene and renderer so the exported image can be composed independently from the live interactive scene.

The output is rendered at:

```text
1600 × 900
```

The export also works while the sphere is morphing, using the calculated text target positions.

---

## Controls

### Desktop

- **Mouse wheel** — zoom
- **Text field** — enter text
- **Enter** — morph
- **↓ PNG** — export the current text formation

### Mobile

- **Pinch** — zoom
- **Text field** — enter text
- **Enter / submit** — morph
- **↓ PNG** — export

---

## Project structure

The project is intentionally lightweight.

```text
morphing-sphere/
│
├── index.html
├── favicon.png
└── README.md
```

Most of the project lives inside `index.html`.

There is no build system required.

There is no package installation step.

There is no server required.

---

## Running locally

Clone the repository:

```bash
git clone https://github.com/PeppermintGrave/morphing-sphere.git
```

Then open the project in a browser.

You can also use a simple local server if your browser environment requires one.

For example:

```bash
python -m http.server
```

Then open:

```text
http://localhost:8000
```

---

## Why I made it

This started as a small visual experiment.

I wanted to see how far a simple collection of particles could go without turning the project into something unnecessarily complicated.

A sphere.

Some particles.

A text field.

And then the sphere stops being a sphere.

---

## Credits

**Created by PeppermintGrave**

Concept, visual direction, implementation, particle system, text morphing system, interface, and project design by PeppermintGrave.

Built with Three.js and GSAP.

---

## License

This project is published for personal and educational use.

You are welcome to explore the code and learn from it.

Please do not present the original project or its assets as your own.

---

## PeppermintGrave

More experiments and projects:

**YouTube:**  
https://www.youtube.com/@PeppermintGraveYT

**GitHub:**  
https://github.com/PeppermintGrave

---

> Some things are easier to understand when you watch them disappear.
