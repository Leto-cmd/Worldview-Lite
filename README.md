# 🌍 Worldview Light

A real-time global intelligence dashboard built with Three.js — inspired by [Bilawal Sidhu's WorldView](https://worldview.kt-o.com). Track live flights, satellites, vessels, and earthquakes on an interactive 3D globe, all in a single HTML file with zero dependencies to install.

![Worldview Light](https://img.shields.io/badge/status-live-00ffaa?style=flat-square) ![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square) ![Size](https://img.shields.io/badge/size-single%20file-orange?style=flat-square)

---

## ✨ Features

- **Interactive 3D Globe** — drag to rotate, scroll to zoom, with NASA Blue Marble texture, night lights, graticule grid, and atmospheric glow
- **✈ Live Flights** — ADS-B transponder data via OpenSky Network (falls back to simulated data if CORS blocks the request)
- **🛰 Satellites** — 200 orbital objects with real inclination, altitude, and period — positions update every frame
- **🚢 Vessels** — Ships plotted along real-world shipping lanes (Atlantic, Pacific, Malacca Strait, Cape of Good Hope, and more)
- **🔴 Earthquakes** — Live USGS feed (M2.5+ last 24 hours), sized and color-coded by magnitude
- **Radar sweep**, live UTC clock, event feed, hover tooltips, and layer toggles
- **CRT / Hacker Mode** — one-click green phosphor filter with scanlines, vignette, and flicker

---

## 🚀 Usage

No build step, no npm, no config. Just open the file:

```bash
git clone https://github.com/YOUR_USERNAME/worldview-light.git
cd worldview-light
open worldview.html
```

Or serve it locally to get live flight data (bypasses some CORS restrictions):

```bash
npx serve .
# then open http://localhost:3000
```

---

## 📡 Data Sources

| Layer | Source | Auth Required |
|---|---|---|
| Flights | [OpenSky Network](https://opensky-network.org) | No (rate limited) |
| Satellites | Simulated from NORAD orbital elements | No |
| Vessels | Simulated along real AIS shipping lanes | No (live AIS requires paid WSS key) |
| Earthquakes | [USGS Earthquake Hazards](https://earthquake.usgs.gov) | No |

> **Note:** The OpenSky API is public but rate-limited. For best results, run via a local server or add an OpenSky account bearer token to the fetch headers.

---

## 🎮 Controls

| Action | Control |
|---|---|
| Rotate globe | Click + drag |
| Zoom | Scroll wheel |
| Hover object | Mouse over any dot for details |
| Toggle layer | Click layer name in left panel |
| CRT Mode | Click `[ CRT MODE ]` in header |

---

## 🛠 Tech Stack

- [Three.js r128](https://threejs.org) — 3D rendering
- [NASA Blue Marble](https://visibleearth.nasa.gov) — Earth texture
- [USGS GeoJSON Feed](https://earthquake.usgs.gov/earthquakes/feed/v1.0/geojson.php) — Earthquake data
- [OpenSky Network REST API](https://openskynetwork.github.io/opensky-api/) — Flight data
- Vanilla JS, no framework, no bundler

---

## 📁 Structure

```
worldview-light/
└── worldview.html      # entire app — one file
└── README.md
```

---

## 🙏 Credits

Inspired by [Bilawal Sidhu's WorldView](https://worldview.kt-o.com) and the original [kevtoe/worldview](https://github.com/kevtoe/worldview) project. Built with [Claude](https://claude.ai).

---

## 📄 License

MIT — do whatever you want with it.
