# 🪐 MindOrbit — Galaxy of Ideas

> **Your ideas as a living solar system.**  
> You are the Sun. Your Ideas orbit as Planets. Steps are Satellites. Modules are Sub-satellites.

![MindOrbit Banner](Galaxy_of_Idea_banner.png)

---

## ✨ What is MindOrbit?

MindOrbit is a free, offline-first **Progressive Web App** for visual mind-mapping in 3D space. No account, no server, no ads — your data lives entirely on your device.

Built with vanilla HTML/CSS/JS + Three.js. Installable on Android, iOS, and desktop.

🔗 **Live app:** [cedracine.github.io/mindorbit](https://cedracine.github.io/mindorbit)  
💚 **Support:** [donate.cedracine.com](https://donate.cedracine.com)

---

## 🗂 File Structure

```
mindorbit/
├── index.html                  # Full app — single file
├── manifest.json               # PWA manifest
├── sw.js                       # Service worker (offline cache)
├── icon-192.png                # App icon
├── icon-512.png                # App icon (large)
├── MindOrbit_Splashscreen_1.png # 3D splash (used internally)
├── Galaxy_of_Idea_banner.png   # Brand banner (export header)
└── README.md
```

---

## 🧭 Hierarchy

| Level | Metaphor | Colour |
|-------|----------|--------|
| **Me** | ☀️ Sun — central node | Gold `#FFD166` |
| **Idea** | 🪐 Planet — orbits the Sun | Custom per idea |
| **Step** | 🛸 Satellite — orbits a Planet | Cyan `#AEFEFF` |
| **Module** | 📦 Sub-satellite — orbits a Step | Violet `#b47fff` |

---

## 📱 Navigation

| Gesture / Action | Result |
|-----------------|--------|
| **Tap ☀️ Sun** | Edit Me (name, photo, emoji, desc) |
| **Tap a Planet** | Enter Idea view |
| **Tap a Satellite** | Enter Step view |
| **Tap centre sphere** | Edit current node |
| **Drag** | Rotate the 3D view |
| **Pinch** | Zoom in / out |
| **← Back** | Navigate up one level |
| **Breadcrumb pills** | Jump directly to any ancestor |
| **❄️ Freeze** | Pause / resume all orbits |
| **Back × 2** | Close app (toast warning on first press) |

---

## ⚙️ Settings Menu

Accessible via the 👽 button (top-left):

- 📖 **User Manual** — in-app guide
- 📄 **Export PDF** — printable hierarchy with banner header
- 🖼 **Export PNG** — shareable snapshot
- ⬆ **Export JSON** — full data backup
- ⬇ **Import JSON** — restore from backup
- ⚠️ **Full Reset** — clears all data, returns to blank orbit immediately; next refresh shows demo data

---

## 💾 Data & Storage

- All data stored in **localStorage** (`mindorbit-v2`)
- **No cloud sync**, no account required
- Demo data shown on first launch and after refresh post-reset
- Saving any node clears the demo state and persists your data

---

## 📤 Export

Both **PDF** and **PNG** exports open a new browser tab with:

- **Galaxy of Ideas** banner header (brand image, no duplicate text)
- **Your name** (Me node) + optional description
- Export date · idea count · step count
- Full hierarchy: Ideas → Steps → Modules with descriptions

---

## 🛠 Tech Stack

| | |
|--|--|
| **Renderer** | [Three.js r128](https://threejs.org/) — WebGL via CDN |
| **Fonts** | Orbitron + Inter (Google Fonts) |
| **Storage** | localStorage |
| **PWA** | Web App Manifest + Service Worker |
| **Export** | html2canvas (PNG) · window.print (PDF) |
| **Framework** | None — vanilla HTML/CSS/JS |

---

## 🚀 Deployment

Hosted on **GitHub Pages** — no build step required.

```bash
# Clone and open locally
git clone https://github.com/cedracine/mindorbit.git
cd mindorbit
# Open index.html in browser, or serve with:
npx serve .
```

All assets must be at the **root** of the repo alongside `index.html`:
- `Galaxy_of_Idea_banner.png` — required for export header
- `MindOrbit_Splashscreen_1.png` — used for internal 3D splash texture

---

## 🤝 Credits & Support

Created by **Ced Racine** · [cedracine.com](https://cedracine.com)

If MindOrbit brings value to your life, consider supporting free development:  
💚 [donate.cedracine.com](https://donate.cedracine.com)

---

*MindOrbit is part of the [cedracine.com/appz](https://cedracine.com/appz) free PWA suite.*
