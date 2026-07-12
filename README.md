# jakobkessler.dev

Personal portfolio site. Interactive flow-field particle system built with vanilla JavaScript and the Canvas 2D API — no libraries, no framework, no build step.

**Live:** https://jkobks.github.io/portfolio/

## What it does

Roughly 1,500 particles drift through a procedurally generated vector field, leaving colored trails. The field is driven by layered sine waves that shift over time, so the flow never repeats exactly.

- **Cursor repulsion** — particles are pushed away from the pointer, with force falling off quadratically over a 220px radius
- **Click shockwaves** — each click spawns an expanding ring that displaces particles as it passes through them, decaying over time
- **Trail rendering** — instead of clearing the canvas each frame, a semi-transparent fill is drawn over it, so previous positions fade out gradually
- **Additive blending** (`globalCompositeOperation = 'lighter'`) so overlapping trails build up light rather than covering each other

## Stack

- Vanilla JavaScript (ES5-compatible, no transpilation)
- Canvas 2D API
- CSS custom properties, `backdrop-filter` for the glass panels
- Zero dependencies

## Notes

- Particle count scales down on narrow viewports for performance
- Handles `prefers-reduced-motion`
- Retina-aware via `devicePixelRatio` scaling, capped at 2x

## Running locally

Just open `index.html` in a browser. That's it.

```bash
git clone https://github.com/jkobks/portfolio.git
cd portfolio
open index.html
```

---

Jakob Kessler — Munich
