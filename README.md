# 🪐 MindOrbit — Galaxy of Ideas

> **Your ideas as a living solar system.**  
> You are the Sun. Your Ideas orbit as Planets. Steps are Satellites. Modules are Sub-satellites.

![MindOrbit Banner](Galaxy_of_Idea_banner.png)

---

## ✨ What is MindOrbit?

MindOrbit is a free, offline-first **Progressive Web App** for visual fractal mind-mapping. No account, no server, no ads — your data lives entirely on your device.

Built with vanilla HTML/CSS/JS + D3.js. Installable on Android, iOS, and desktop.

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
├── MindOrbit_Splashscreen_1.png # Splash image (used internally)
├── Galaxy_of_Idea_banner.png   # Brand banner (export header)
└── README.md
```

---

## 🧭 Hierarchy

| Level | Metaphor | Default Name | Colour |
|-------|----------|-------------|--------|
| **Level 0** | ☀️ Sun — central node | Me | Gold `#FFD166` |
| **Level 1** | 🌍 Planet — orbits the Sun | Idea | Teal `#06D6A0` |
| **Level 2** | ⭐ Satellite — orbits a Planet | Step | Cyan `#AEFEFF` |
| **Level 3** | 🚀 Module — orbits a Satellite | Module | Violet `#b47fff` |

All four level names and glow colours are **fully customisable** in Settings → Hierarchy.

---

## 📱 Navigation

| Gesture / Action | Result |
|-----------------|--------|
| **Tap a node (unfocused)** | Focus that node — children orbit around it |
| **Tap focused node** | Open Edit sheet |
| **Tap ☀️ Me icon (topbar)** | Shuffle fractal layout (unfrozen) or restore saved Home (frozen) |
| **Drag canvas** | Pan the view |
| **Pinch / scroll** | Zoom in / out |
| **Drag a node (frozen)** | Move node freely — all children follow |
| **← Back (Android)** | Dismiss top panel, or navigate up one edit level |
| **← Back × 2 (home)** | Toast warning, second press closes app |
| **+ NodeName button (bottom)** | Add a child to the focused node |

---

## 🏠 Home & Freeze

| Button | Action |
|--------|--------|
| **☀️ Me icon** | Shuffle fractal layout & reset zoom (unfrozen) |
| **❄️ Freeze** | Lock all node positions — free drag mode, children follow parent |
| **💾 Save Positions** | Commit current layout as permanent Home (appears only when frozen) |
| **☀️ Me icon (frozen)** | Restore last saved Home positions |

The **saved Home layout** is included in JSON exports and restored on import.

---

## ⚙️ Settings Panel

Accessible via the 👽 button (top-left). Opens as a floating panel with a zoom-from-corner animation.

| Item | Description |
|------|-------------|
| 📖 **User Manual** *(Multilingual)* | In-app guide in 12 languages |
| **Hierarchy table** | Rename each level · Set individual glow colour via colour picker |
| 📄 **Export PDF** | Printable hierarchy with banner header |
| 🖼 **Export PNG** | Shareable snapshot |
| ⬆ **Export JSON** | Full data backup (nodes, positions, finance, colours, Home layout) |
| ⬇ **Import JSON** | Restore full state from backup |
| ⚠️ **Full Reset** | Leaves only Me — blank slate on screen and after reload |

---

## 💾 Data & Storage

- All data stored in **localStorage** key `mindorbit-v2`
- **No cloud sync**, no account required
- **First launch** (no data): demo graph is shown
- **After Full Reset**: only the Me node remains, on screen and after page reload
- **User data**: any saved node clears the demo/reset state; reloads restore your data
- **Export JSON** includes everything: node hierarchy, custom names, glow colours, finance fields, icon/photos, saved Home positions, and freeze state
- **Offline**: once visited, the Service Worker caches the app HTML and CDN assets — fully functional without internet

---

## 💰 Finance

Each node optionally tracks four numeric fields, revealed by tapping **＋ Finance**:

| Field | Direction | Colour |
|-------|-----------|--------|
| **Budget** | Money Out (planned) | 🔴 Red |
| **Cost** | Money Out (actual) | 🔴 Red |
| **Expected** | Money In (forecast) | 🟢 Green |
| **Income** | Money In (actual) | 🟢 Green |

When both sides have data, a **P&L row** (Planned and Real) appears automatically.  
The 💰 Finance panel shows totals, per-node rows, and a treemap with Real P&L badges.

---

## 🌐 Multilingual User Manual

The in-app manual supports **12 languages**, selectable via a flag dropdown in the manual header:

🇬🇧 English · 🇫🇷 Français · 🇪🇸 Español · 🇩🇪 Deutsch · 🇮🇹 Italiano · 🇵🇹 Português · 🇷🇺 Русский · 🇨🇳 中文 · 🇯🇵 日本語 · 🇻🇳 Tiếng Việt · 🇹🇭 ภาษาไทย · 🇰🇭 ភាសាខ្មែរ

Each language includes a dedicated **Installation** section with platform-specific instructions.

---

## 📤 Export (PDF / PNG)

Both exports open a new browser tab with:

- **Galaxy of Ideas** banner header
- **Your name** (Me node) + optional description
- Export date · idea count · step count
- Full hierarchy: Ideas → Steps → Modules with descriptions and emojis

---

## 📲 PWA Installation

MindOrbit is a fully installable **Progressive Web App** — no app store, no account, 100% offline after first load.

### Android (Chrome / Edge)
1. Open the app in Chrome
2. Tap **Settings → Install App** inside MindOrbit, or use the banner at the bottom
3. Tap **Install** in the browser prompt
4. MindOrbit appears on your home screen and works fully offline

### iOS (Safari)
1. Open the app in Safari *(Chrome on iOS cannot install PWAs)*
2. Tap the **↑ Share** button at the bottom of the screen
3. Scroll down and tap **«Add to Home Screen»**
4. Tap **Add** — done

### Desktop (Chrome / Edge / Brave)
1. Open the app in the browser
2. Click the **install icon** (⊕) in the address bar — or go to **Settings → Install App**
3. Click **Install**

> Once installed, the app opens in its own window with no browser UI, caches all assets for offline use, and behaves like a native app.

---

## 🛠 Tech Stack

| | |
|--|--|
| **Graph engine** | [D3.js v7](https://d3js.org/) — force-directed + fractal layout |
| **Fonts** | Orbitron + Inter (Google Fonts) |
| **Storage** | localStorage (`mindorbit-v2`) |
| **PWA** | Inline manifest (data URI) · Inline Service Worker (Blob URL) · Offline cache |
| **Export** | html2canvas (PNG) · window.print (PDF) |
| **Framework** | None — vanilla HTML/CSS/JS |

---

## 🗺 Layout Engine

MindOrbit uses a **fractal radial layout** rather than standard force physics:

- Ideas distribute evenly around Me on a circle sized to prevent overlap
- Each subtree fans out in a cone pointing away from the Sun
- A seeded PRNG ensures a different arrangement on every shuffle
- A post-placement separation pass pushes any remaining overlaps apart
- Curved quadratic bezier synapses reduce visual crossings
- A soft ripple/wave chimes animation breathes life into the graph at rest

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

All assets must be at the **root** of the repo alongside `index.html`.

---

## 🤝 Credits & Support

Created by **Ced Racine** · [cedracine.com](https://cedracine.com)

If MindOrbit brings value to your life, consider supporting free development:  
💚 [donate.cedracine.com](https://donate.cedracine.com)

---

*MindOrbit is part of the [cedracine.com/appz](https://cedracine.com/appz) free PWA suite.*
