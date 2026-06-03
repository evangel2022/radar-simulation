<p align="center">
  <strong>English</strong> |
  <a href="README_CN.md">简体中文</a>
</p>

<h1 align="center">AN/SPY-6(V) Aegis Combat System — Phased Array Radar Simulation</h1>

<p align="center">
  <strong>HTML5 Canvas · Web Audio API · Pure JavaScript · Zero Dependencies</strong>
  <br>
  Naval Air & Missile Defense | Multi-Target Tracking | Fire Control | SM-6 Intercept | PPI Display
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
  <a href="https://evangel2022.github.io/radar-simulation/"><img src="https://img.shields.io/badge/demo-GitHub%20Pages-brightgreen" alt="Live Demo"></a>
  <a href="https://github.com/evangel2022/radar-simulation/actions/workflows/ci.yml"><img src="https://github.com/evangel2022/radar-simulation/actions/workflows/ci.yml/badge.svg" alt="CI Status"></a>
  <a href="#"><img src="https://img.shields.io/badge/dependencies-zero-success" alt="Zero Dependencies"></a>
  <a href="#"><img src="https://img.shields.io/badge/vanilla-js-yellow.svg" alt="Vanilla JavaScript"></a>
  <a href="CONTRIBUTING.md"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome"></a>
</p>

---

A pure-frontend, interactive **Aegis Combat System** simulator built entirely with web standards. It models the U.S. Navy's **AN/SPY-6(V) phased array radar** with end-to-end visualization of multi-target detection, tracking, classification, threat assessment, fire-control lock, weapon assignment, and SM-6 missile intercept. Rendered with **HTML5 Canvas**, sound effects synthesized via **Web Audio API**, zero dependencies — runs as a single HTML file.

---

## Table of Contents

- [Features](#features)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Contributing](#contributing)
- [License](#license)
- [Disclaimer](#disclaimer)

---

## Features

### Radar Simulation
| Feature | Description |
|---------|-------------|
| **PPI Display** | 360° rotating sweep line, multi-level range rings, bearing tick marks |
| **Multi-Target Engine** | Air targets (fighters, cruise missiles, UAVs), ballistic missiles (IRBM/MRBM/SRBM), surface vessels — each with independent kinematic models |
| **Four Radar Modes** | Volume Search / Surveillance / Precision Track / Fire Control Support |
| **Adaptive Resource Allocation** | SEARCH / TRACK / ENGAGE three-channel power bar with dynamic rebalancing |
| **Adjustable Parameters** | Detection range (50–2000 km), scan rate (0.5–4.0 rpm), sector scan angle |

### Fire Control & Engagement
| Feature | Description |
|---------|-------------|
| **11-Step Workflow** | SEARCH → DETECT → TRACK → CLASSIFY → LOCK → FIRE CONTROL → WEAPON ASSIGNMENT → ENGAGE → MIDCOURSE GUIDANCE → INTERCEPT → KILL ASSESSMENT |
| **DESIGNATE for Engagement** | Two-phase confirmation: Select Target → Assign Engagement, mirroring real Aegis tactical logic |
| **Weapon System** | SM-6 missile launch, midcourse guidance, terminal intercept — full visualization |
| **Predicted Intercept Point (PIP)** | Real-time intercept geometry computation and rendering |

### Visual & Interaction
| Feature | Description |
|---------|-------------|
| **Dark Navy-Themed UI** | Military console design with a CSS custom properties theme system |
| **Target Lock Animation** | Pulsing lock box, historical track trail, predicted flight path vector |
| **Threat Alert Panel** | Scrolling top banner + tiered alert list + threat-level color coding |
| **Target Status Dashboard** | Four-segment panel (Track Info / Kinematics / Engagement / Threat Assessment) |

### Audio Feedback
| Feature | Description |
|---------|-------------|
| **Procedural Synthesis** | Real-time Web Audio API OscillatorNode synthesis — zero audio files |
| **5 Core Sound Types** | Alert Beep · Lock Tone · Missile Launch · Intercept Explosion · Radar Pulse |
| **Performance Guard** | Single AudioContext, 3-channel concurrency cap, global mute control |

---

## Quick Start

### Prerequisites

- **Modern browser** — Chrome 90+ / Firefox 90+ / Edge 90+
- No Node.js, Python, or build tools required

### Run

```bash
# Option 1: Open directly (recommended)
# Double-click index.html or open in browser

# Option 2: Python HTTP server
python -m http.server 8080 --directory .
# Open http://localhost:8080

# Option 3: Node.js
npx serve .
```

> **Note:** Browser autoplay policies may require a user click anywhere on the page to activate AudioContext. Sound effects will work after the first interaction.

---

## Usage

| Action | Result |
|--------|--------|
| Click a target on radar canvas | Select target, show full details in right panel |
| Click **LOCK TARGET** | Lock target, enter fire control tracking mode |
| Click **DESIGNATE** | Designate target for engagement, assign SM-6 missile |
| Click **FIRE** | Launch missile, begin intercept sequence |
| Toggle **SEARCH / TRACK / ENGAGE** | Switch radar operating mode |
| Drag **Range** slider | Adjust detection range (50–2000 km) |
| Drag **Scan Rate** slider | Adjust scan rate (0.5–4.0 rpm) |
| Toggle type filters | Filter targets by category (air/ballistic/surface) |
| Click 🔊 (top-right) | Toggle global sound on/off |

---

## Tech Stack

| Layer | Technology | Notes |
|-------|------------|-------|
| **Rendering** | Canvas 2D API | 60fps PPI radar sweep, target trails, particle effects |
| **Audio** | Web Audio API | OscillatorNode + GainNode procedural synthesis |
| **Styling** | CSS3 | Custom Properties, Grid, Flexbox |
| **Logic** | Vanilla JavaScript | ES5-compatible, no framework, no build, no transpilation |
| **Deployment** | Static HTML | Single file, host on GitHub Pages or any static server |

---

## Project Structure

```
radar-simulation/
├── index.html                  # Main application (HTML + CSS + JS, self-contained)
├── README.md                   # 项目文档 (Chinese)
├── README_EN.md                # Project Documentation (English)
├── LICENSE                     # MIT License
├── CONTRIBUTING.md             # Contribution guidelines
├── package.json                # Project metadata & npm scripts
├── .gitignore                  # Git ignore rules
└── .github/
    └── workflows/
        └── ci.yml              # CI/CD: HTML validation + GitHub Pages deploy
```

---

## Contributing

Issues and pull requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution workflow, branch strategy, coding standards, and commit message conventions.

---

## License

This project is open-sourced under the [MIT License](LICENSE).

---

## Disclaimer

This project is a simulation system built for **educational and demonstration purposes only**. It contains no classified or real-world military data. All visual representations, behavioral parameters, and technical specifications are simulated and do not reflect the actual performance or combat capability of any real weapon system.

---

<p align="center">
  <sub>
    Keywords: radar simulation, phased array radar, Aegis combat system, AN/SPY-6, missile defense, naval radar, PPI display, fire control system, HTML5 Canvas, Web Audio API, vanilla JavaScript, military simulation, air defense, ballistic missile defense, SM-6 interceptor
  </sub>
</p>