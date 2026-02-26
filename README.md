# Renew — Local Dev Setup

A two-page website: portfolio showcase + interactive room simulator.

## Quick Start

You only need Node.js (v14+). No npm install required — zero dependencies.

```bash
node server.js
```

Then open your browser to:

| Page | URL |
|------|-----|
| Portfolio | http://localhost:3000 |
| Room Simulator | http://localhost:3000/simulator.html |

Press `Ctrl+C` to stop the server.

---

## Project Structure

```
renew-app/
├── server.js          ← Static file server (pure Node, no deps)
├── start.js           ← Alias for server.js
├── README.md
└── public/
    ├── index.html     ← Portfolio / showcase page
    └── simulator.html ← 2D/3D room designer
```

## Adding Your Photos

In `public/index.html`, find the two `.slider-wrap` blocks and replace the
placeholder `<div>` elements with real `<img>` tags:

```html
<!-- BEFORE — replace this div: -->
<div class="placeholder-before" id="before1">Your "before" photo here</div>

<!-- With: -->
<img id="before1" src="/images/kitchen-before.jpg" alt="Kitchen before">

<!-- AFTER — same pattern: -->
<img id="after1" class="after-img" src="/images/kitchen-after.jpg" alt="Kitchen after">
```

Place your images in `public/images/` and they'll be served automatically.

## Customising Content

| What | Where |
|------|-------|
| Business name | Search/replace `Renew` in both HTML files |
| Contact details | `index.html` → `#contact` section |
| Project names & descriptions | `index.html` → `.project` blocks |
| Colour scheme | `index.html` → `:root` CSS variables |

## Deploying

Since this is plain HTML/CSS/JS + a lightweight Node server, you can deploy to:
- **Render / Railway / Fly.io** — push the folder, set start command to `node server.js`
- **Any static host (Netlify, Vercel, GitHub Pages)** — just upload the `public/` folder (no server needed for static hosting)
