# 🌐 AI in Daily Life — Interactive 3D Website

A single-file, dependency-free website about **AI applications in everyday life**, rendered with
[Three.js](https://threejs.org/) (WebGL). It features a glowing wireframe globe, particle
atmosphere, orbiting satellites and connection arcs — plus a fully interactive UI built with
vanilla JavaScript.

**Everything in it works:** navigation, cards, modal, counters, globe controls, mobile menu,
back-to-top and toasts.

---

## ✨ Features

| Area | What you get |
|------|--------------|
| 3D scene | Rotating wireframe globe, dark core, fresnel glow shell, 700 surface "city" points, 1400 drifting atmosphere particles, 900-star field, 7 connection arcs with travelling pulses, 3 orbiting satellites |
| Controls | `OrbitControls` drag-to-rotate, pause/resume spin, glow colour shuffler |
| Sections | Hero → Applications → Impact → About → Footer, with smooth scrolling and active-link highlighting |
| Cards | Smart Home 🏠, Healthcare 🩺, Education 📚, Transportation 🚗, Finance 💰 — hover to recolour the globe, click to open an accessible modal (`Esc`, backdrop, ✕ and arrow keys all work) |
| Stats | Counters animate when the Impact section enters the viewport |
| Theme | Modern dark theme with glowing accents, glassy panels, pointer-tracking card glow |
| Responsive | Mobile menu, stacked grid, adjusted camera & layout below 760px |
| Resilience | CSS fallback globe if the CDN/WebGL is unavailable; `prefers-reduced-motion` respected |

## 📁 Project structure

```
ai-daily-life-3d/
├── index.html      ← the whole site (inline CSS + JS + importmap)
├── README.md
└── PROMPT.md       ← original build brief
```

## 🚀 Run locally

Because the page uses an `importmap` and ES modules, open it through a web server
(direct `file://` opening is blocked by browser CORS rules for modules):

```bash
# Option A — Python
python3 -m http.server 8080
# → http://localhost:8080

# Option B — Node
npx serve .
```

Then open <http://localhost:8080>.

## 🌍 Deploy to GitHub Pages

1. **Create the repository and push the code**

   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial release: AI in Daily Life 3D site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```

2. **Enable Pages**
   - Open your repo on GitHub → **Settings → Pages**
   - Under *Build and deployment*, set **Source** to **Deploy from a branch**
   - Choose branch **`main`** and folder **`/ (root)`** → **Save**

3. **Wait for the build** (a green check on the *Actions* tab), then visit:

   ```
   https://<your-username>.github.io/<your-repo>/
   ```

   > For a user/organisation site, name the repo `<your-username>.github.io` and it will be
   > served at `https://<your-username>.github.io/`.

### ⚙️ One-time configuration

Set your repository URL **once** — it drives every GitHub link on the page:

```js
var GITHUB_URL = "https://github.com/your-username/ai-daily-life-3d"; // index.html, UI script
```

### 🔁 Redeploy

Any push to `main` redeploys automatically. For a manual redeploy: **Settings → Pages →
“Clear cache” / re-save**, or re-run the workflow from the **Actions** tab.

## 🛠 Customization

- **Colours** — edit the CSS custom properties in `:root` (`--accent`, `--bg`, …).
- **Glow palette** — the `ACCENTS` array in the UI script.
- **Sectors** — the `SECTORS` array (icon, title, colour, description, bullets, stat).
  Adding an entry automatically creates a new card.
- **Three.js version** — the two URLs in the `importmap` block.

## 📦 Tech

- Three.js **r169** via CDN `importmap` (jsDelivr)
- `OrbitControls` from `three/addons`
- Vanilla HTML/CSS/JS — **no frameworks, no build step**

## 📄 License

Free to use for any purpose. Attribution appreciated but not required.
