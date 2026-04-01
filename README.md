# 3D Particle System ✨

<p align="center">
  <img src="Screenshot.png" alt="3D Particle System preview" width="100%">
</p>

A polished single-file interactive particle experience built with **HTML**, **CSS**, **JavaScript**, and **Three.js**. It combines text morphing, procedural particle shapes, theme controls, font switching, audio-reactive motion, magnetic interaction, export/import presets, fullscreen mode, and a responsive settings panel designed for desktop and mobile devices.

**Live branding:** [@SudhirDevOps1](https://github.com/SudhirDevOps1)

---

## 🌈 Overview

This project renders a high-density 3D particle field that can:

- morph into multiple procedural shapes
- morph into user-entered text
- switch between multiple color themes and custom gradients
- react to mouse, touch, gravity, ripple motion, and microphone input
- be configured through a modern responsive side panel

Everything runs from a single `index.html` file, making it easy to host on **GitHub Pages**, **Netlify**, **Vercel**, or any static web server.

---

## ✨ Highlights

- **40,000 particles** rendered with Three.js
- **9 built-in shapes**
- **10 switchable fonts** for text morphing and input styling
- **Theme presets + custom color mixer**
- **Responsive settings panel** with mobile-friendly interactions
- **Fullscreen mode**
- **Screenshot export**
- **Preset export/import** via JSON
- **Audio-reactive mode** using microphone input
- **Magnetic field interaction**
- **Particle life cycle effect**
- **Background starfield**
- **Smooth OLED-black UI**

---

## 🎨 Visual Preview

The image below is loaded from the same folder as this `README.md`.

![Screenshot preview](Screenshot.png)

---

## 🧩 Feature Breakdown

### 1) Particle Morphing
The particle system can morph between default shapes or typed text.

**Available shapes:**
- Heart
- Sphere
- Torus
- Galaxy
- DNA
- Cube
- Wave
- Star
- Spiral

### 2) Font Switching
Text morphing is not limited to a single style. The app includes 10 fonts:

- Inter
- Playfair Display
- Bebas Neue
- Dancing Script
- Orbitron
- Pacifico
- Righteous
- Lobster
- Cinzel
- Monoton

Selected font applies to:
- the text input field
- particle text rendering on canvas sampling

### 3) Themes and Custom Colors
Built-in themes:
- Fire
- Ocean
- Aurora
- Sunset
- Cyber
- Gold
- Candy
- Custom gradient

Custom theme uses 3 color pickers and updates the preview instantly.

### 4) Motion and Physics
Included interactive behaviors:
- Mouse repel
- Drag rotation
- Touch rotation
- Gravity
- Ripple wave
- Auto rotate
- Magnetic attractors
- Particle life / respawn behavior
- Audio-reactive movement

### 5) Utility Actions
The action panel supports:
- Explode
- Save screenshot as PNG
- Randomize shape/theme/settings
- Export current preset as JSON
- Import saved preset JSON
- Reset application

---

## 🖥️ UI Structure

### Top Left
- Particle count indicator
- FPS counter
- Audio activity indicator

### Top Right
- Fullscreen button
- Settings button

### Bottom Center
- Compact text input field for morphing text

### Bottom Left
- Small clickable branding
- **@SudhirDevOps1** opens GitHub in a new tab

### Right Panel
Responsive settings drawer containing:
- Shapes
- Font style selector
- Particle type selector
- Colors
- Custom color mixer
- Parameters
- Effects
- Presets
- Actions

---

## 🎮 Controls

### Mouse / Touch
- **Move cursor** → repels particles when enabled
- **Mouse drag** → rotate particle view
- **Touch drag** → rotate on mobile and tablet
- **Mouse wheel** → zoom in/out

### Keyboard
- **Escape** while typing → clear text
- **Escape** while panel is open → close settings panel

### Settings Panel Close Methods
- close button inside panel
- click overlay outside panel
- press `Esc`
- swipe right on panel header on touch devices

---

## ⚙️ Parameters

The settings panel includes these live controls:

- **Size** - particle point size
- **Speed** - motion intensity over time
- **Spread** - scale of the target shape/text
- **Force** - mouse interaction strength
- **Gravity** - vertical pull or lift
- **Links** - line connections between particles

---

## 🌟 Effects Toggles

- **Auto Rotate**
- **Mouse Repel**
- **Ripple Wave**
- **Audio React**
- **Magnetic**
- **Life Cycle**
- **Starfield**

---

## 🎛️ Presets

The project includes quick presets:

- **Default**
- **Neon**
- **Calm**
- **Chaos**

These adjust theme and motion parameters without removing the rest of the functionality.

---

## 🧠 Technical Notes

### Stack
- HTML5
- CSS3
- Vanilla JavaScript
- [Three.js r128](https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js)

### Rendering Notes
- Additive blending is used for glow-like particle intensity
- BufferGeometry is used for efficient particle updates
- Animation loop uses `requestAnimationFrame`
- Delta time is clamped for smoother frame stability
- Responsive panel and touch-safe interactions are included

### Browser Support
Recommended modern browsers:
- Chrome
- Edge
- Firefox
- Safari
- Mobile Chrome / Safari

For best performance:
- use hardware acceleration
- keep other heavy tabs closed if running on low-end mobile devices

---

## 📁 Project Structure

```text
.
├── index.html   # Complete single-page app
├── README.md    # Project documentation
└── Screenshot.png
```

---

## 🚀 Running Locally

### Option 1: Open directly
Open `index.html` in your browser.

### Option 2: Use a local static server
Examples:

```bash
python -m http.server 8000
```

or

```bash
npx serve
```

Then open the shown localhost URL.

---

## 🌍 Deploying to GitHub Pages

1. Create a GitHub repository
2. Upload `index.html`, `README.md`, and `Screenshot.png`
3. Commit and push
4. Open repository **Settings**
5. Go to **Pages**
6. Set source to your main branch
7. Save and wait for deployment

Because this is a static single-file app, it works well with GitHub Pages.

---

## 🛠️ Customization Guide

### Change default shape
In `index.html`, update:

```js
shape:'heart'
```

### Change default theme
Update:

```js
theme:'fire'
```

### Change particle count
Update:

```js
N:40000
```

### Add a new theme
Extend the `THEMES` object with RGB arrays in 0-1 range.

### Add a new font
1. Import the font in the CSS `@import`
2. Add a `.font-item` block in the settings panel
3. Use the same name in the `data-font` attribute

### Add a new shape
Extend the `SHAPES` object with a function returning `[x, y, z]`.

---

## ⚡ Performance Notes

This project is tuned to feel smooth while preserving visual density. Still, performance may vary based on:

- GPU power
- browser implementation
- mobile device thermal limits
- whether microphone mode is enabled
- whether link connections are enabled

If performance drops on low-end devices:
- keep **Links** low
- disable **Audio React**
- disable **Life Cycle** if not needed
- reduce browser zoom

---

## 🔧 Recent Improvements

The current version includes stability improvements such as:

- safer fullscreen handling
- safer audio initialization fallback
- improved touch and panel behavior
- responsive safe-area support for mobile devices
- more reliable import/export UI syncing
- corrected particle life color handling
- line rendering sync with particle rotation
- cleaner close behavior for settings panel

---

## 👤 Credits

Built with Three.js and custom UI/interaction logic.

Branding and profile link:
- **@SudhirDevOps1**
- GitHub: https://github.com/SudhirDevOps1

---

## 📜 License

You can use and modify this project for personal or portfolio use.
If you publish a modified version, keeping visible credit is appreciated.
