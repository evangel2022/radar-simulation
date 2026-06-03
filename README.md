<div align="center">

[![中文](https://img.shields.io/badge/README-%E4%B8%AD%E6%96%87-red?style=flat-square)](README_CN.md)

</div>

<br>

# AN/SPY-6(V) Aegis Combat System — Radar Simulation

> Web-based Naval Air & Missile Defense Radar Simulator

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-brightgreen)](https://evangel2022.github.io/radar-simulation/)
[![CI](https://github.com/evangel2022/radar-simulation/actions/workflows/ci.yml/badge.svg)](https://github.com/evangel2022/radar-simulation/actions/workflows/ci.yml)

An interactive, pure-frontend radar simulation system built with web technologies. Models the U.S. Navy Aegis Combat System and AN/SPY-6(V) phased array radar with full visualization of multi-target detection, tracking, classification, and the lock-designate-engage-intercept engagement workflow.

---

## Features

### Radar Simulation Core
- **PPI Display** — 360° rotating sweep line, multi-level range rings, bearing tick marks
- **Multi-Target Generation** — Air targets (fighters, cruise missiles, UAVs), ballistic missiles (IRBM/MRBM/SRBM), surface vessels
- **Dynamic Radar Modes** — Volume Search / Surveillance / Precision Track / Fire Control Support
- **Adaptive Resource Allocation** — SEARCH / TRACK / ENGAGE three-channel power bar with dynamic adjustment

### Fire Control & Engagement
- **11-Step Engagement Workflow** — SEARCH → DETECT → TRACK → CLASSIFY → LOCK → FIRE CONTROL → WEAPON ASSIGNMENT → ENGAGE → MIDCOURSE GUIDANCE → INTERCEPT → KILL ASSESSMENT
- **Designate for Engagement** — Two-phase confirmation process mirroring real Aegis combat logic
- **Weapon Assignment & Intercept** — SM-6 missile launch, midcourse guidance, terminal intercept visualization
- **Predicted Intercept Point (PIP)** — Real-time calculation and display of predicted intercept points

### Visual & Interaction
- **Dark Navy-Themed UI** — Professional military console visual design
- **Target Lock Animation** — Pulsing lock box, track history trails, predicted flight path
- **Threat Alert System** — Top threat banner, tiered alert list, threat-level color coding
- **Target Status Dashboard** — Four-panel display: track info, kinematics, engagement, threat assessment

### Audio Feedback
- **Procedural Sound Generation** — Web Audio API OscillatorNode based, zero audio files required
- **5 Core Sound Types** — Alert beep, lock tone, missile launch, intercept explosion, radar pulse
- **Global Mute Control** — One-click mute toggle in the top-right corner

---

## Quick Start

### Prerequisites

- A modern browser (Chrome / Firefox / Edge latest version). No backend or build tools required.

### Running

```bash
# Option 1: Open directly (recommended)
# Open index.html in your browser

# Option 2: Local HTTP server
python -m http.server 8080 --directory .
# Visit http://localhost:8080

# Option 3: Node.js
npx serve .
```

> **Note:** Due to browser autoplay policies, you may need to click anywhere on the page first to activate the AudioContext for sound effects.

---

## Usage

| Action | Description |
|--------|-------------|
| Click a target on the radar canvas | Select target, details shown in right panel |
| Click **LOCK TARGET** | Lock target, enter fire control tracking mode |
| Click **DESIGNATE** | Designate target for engagement, assign weapons |
| Click **FIRE** | Launch missile, begin intercept process |
| Toggle **SEARCH / TRACK / ENGAGE** | Switch radar operating mode |
| Drag **Range / Scan Rate** sliders | Adjust detection range and scan rate |
| Toggle filters | Filter targets by type (air/ballistic/surface) |
| Click 🔊 top-right | Toggle sound on/off |

---

## Tech Stack

| Category | Technology |
|----------|------------|
| Rendering | Canvas 2D API |
| Audio | Web Audio API (OscillatorNode) |
| Styling | Pure CSS (CSS Variables, Grid, Flexbox) |
| Logic | Pure JavaScript (ES5-compatible, no framework) |
| Dependencies | **Zero external dependencies** — single self-contained HTML file |

---

## Project Structure

```
radar-simulation/
├── index.html              # Main application (HTML + CSS + JS)
├── README.md               # Project documentation (English)
├── README_CN.md            # Project documentation (Chinese)
├── LICENSE                 # Open source license
├── CONTRIBUTING.md         # Contribution guidelines
├── package.json            # Project metadata
├── .gitignore              # Git ignore rules
└── .github/
    └── workflows/
        └── ci.yml          # CI/CD workflow
```

---

## Contributing

Issues and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed contribution guidelines and coding standards.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

## Disclaimer

This project is a simulation system for educational and demonstration purposes only. It contains no classified or real military data. All visuals, parameters, and behaviors are simulated and do not represent the actual performance of any real-world weapon system.