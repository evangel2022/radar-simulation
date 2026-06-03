# AN/SPY-6(V) Aegis Combat System — Radar Simulation

> 现代海基防空反导雷达仿真系统 | Web-based Naval Air & Missile Defense Radar Simulator

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GitHub Pages](https://img.shields.io/badge/demo-GitHub%20Pages-brightgreen)](https://evangel2022.github.io/radar-simulation/)
[![CI](https://github.com/evangel2022/radar-simulation/actions/workflows/ci.yml/badge.svg)](https://github.com/evangel2022/radar-simulation/actions/workflows/ci.yml)

基于 Web 技术构建的纯前端交互式雷达仿真系统，模拟美海军宙斯盾作战系统（Aegis Combat System）与 AN/SPY-6(V) 相控阵雷达的功能，具备多目标探测、跟踪、分类、锁定-标定-交战-拦截全流程可视化能力。

A zero-dependency, browser-based interactive radar simulation system that models the U.S. Navy's Aegis Combat System and AN/SPY-6(V) phased array radar, featuring full visualization of multi-target detection, tracking, classification, and the complete lock-designate-engage-intercept workflow.

---

<details open>
<summary><b>中文文档</b></summary>

## 功能特性

### 雷达仿真核心
- **PPI 平面位置指示器** — 360° 旋转扫描线，多级距离环，方位刻度标记
- **多目标生成与运动模拟** — 空中目标（战斗机、巡航导弹、无人机）、弹道导弹（IRBM/MRBM/SRBM）、水面舰艇
- **动态雷达模式切换** — 体搜索模式 / 监视模式 / 精确跟踪模式 / 火控支持模式
- **自适应功率分配** — SEARCH / TRACK / ENGAGE 三通道功率条动态调整

### 火控与交战流程
- **11 步完整交战工作流** — SEARCH → DETECT → TRACK → CLASSIFY → LOCK → FIRE CONTROL → WEAPON ASSIGNMENT → ENGAGE → MIDCOURSE GUIDANCE → INTERCEPT → KILL ASSESSMENT
- **目标标定 (DESIGNATE FOR ENGAGEMENT)** — 贴近真实宙斯盾作战逻辑的双阶段确认流程
- **武器分配与拦截** — SM-6 导弹发射、中段制导、终端拦截可视化
- **预测拦截点 (PIP)** — 实时计算并显示预测拦截点

### 视觉与交互
- **深色海军风格 UI** — 专业军用控制台视觉设计
- **目标锁定动画** — 脉冲锁定框、航迹历史轨迹、预测飞行路径
- **威胁告警系统** — 顶部威胁横幅、分级告警列表、威胁等级颜色编码
- **目标状态仪表板** — 航迹信息、运动学信息、交战信息、威胁评估四段式面板

### 音频反馈
- **程序化音效生成** — 基于 Web Audio API OscillatorNode，无需任何音频文件
- **5 类核心音效** — 告警蜂鸣、锁定提示音、导弹发射音、拦截爆炸音、雷达脉冲音
- **全局静音控制** — 右上角一键静音切换

## 快速开始

### 前置要求
现代浏览器（Chrome / Firefox / Edge 最新版），无需任何后端或构建工具。

### 运行方式

```bash
# 方式一：直接打开（推荐）
# 在浏览器中打开 index.html 即可

# 方式二：本地 HTTP 服务器
python -m http.server 8080 --directory .
# 访问 http://localhost:8080

# 方式三：Node.js
npx serve .
```

> **注意：** 由于浏览器自动播放策略，首次使用音效功能可能需要点击页面任意位置激活 AudioContext。

## 操作指南

| 操作 | 说明 |
|------|------|
| 点击雷达画布上的目标 | 选中目标，右侧面板显示详情 |
| 点击 **LOCK TARGET** | 锁定目标，进入火控跟踪模式 |
| 点击 **DESIGNATE** | 标定目标用于交战，分配武器 |
| 点击 **FIRE** | 发射导弹，开始拦截流程 |
| 切换 **SEARCH / TRACK / ENGAGE** | 切换雷达工作模式 |
| 拖动 **Range / Scan Rate** 滑块 | 调整探测距离和扫描速率 |
| 勾选过滤器 | 按类型筛选目标（空中/弹道/水面） |
| 点击右上角 🔊 | 切换音效开关 |

## 技术栈

| 类别 | 技术 |
|------|------|
| 渲染 | Canvas 2D API |
| 音频 | Web Audio API (OscillatorNode) |
| 样式 | 纯 CSS (CSS Variables, Grid, Flexbox) |
| 逻辑 | 纯 JavaScript (ES5 兼容，无框架) |
| 依赖 | **零外部依赖** — 单个 HTML 文件自包含 |

## 项目结构

```
radar-simulation/
├── index.html              # 主程序（HTML + CSS + JS 单文件）
├── README.md               # 项目说明
├── LICENSE                 # 开源许可证
├── CONTRIBUTING.md         # 贡献指南
├── package.json            # 项目元数据
├── .gitignore              # Git 忽略规则
└── .github/
    └── workflows/
        └── ci.yml          # CI/CD 工作流
```

## 贡献指南

欢迎提交 Issue 和 Pull Request。请参阅 [CONTRIBUTING.md](CONTRIBUTING.md) 了解详细的贡献流程和代码规范。

## 许可证

本项目采用 [MIT License](LICENSE) 开源许可证。

## 免责声明

本项目为教育性和演示性用途的仿真系统，不包含任何机密或真实的军事数据。所有视觉效果、参数和行为均为模拟实现，不代表任何真实武器系统的实际性能。

</details>

<details>
<summary><b>English Documentation</b></summary>

## Features

### Radar Simulation Core
- **PPI Display** — 360° rotating sweep line, multi-level range rings, bearing tick marks
- **Multi-Target Generation & Motion** — Air targets (fighters, cruise missiles, UAVs), ballistic missiles (IRBM/MRBM/SRBM), surface ships
- **Dynamic Radar Modes** — Volume Search / Surveillance / Precision Track / Fire Control Support
- **Adaptive Power Allocation** — SEARCH / TRACK / ENGAGE three-channel power bar

### Fire Control & Engagement
- **11-Step Engagement Workflow** — SEARCH → DETECT → TRACK → CLASSIFY → LOCK → FIRE CONTROL → WEAPON ASSIGNMENT → ENGAGE → MIDCOURSE GUIDANCE → INTERCEPT → KILL ASSESSMENT
- **Designate for Engagement** — Two-stage confirmation process mirroring real Aegis combat logic
- **Weapon Assignment & Intercept** — SM-6 missile launch, midcourse guidance, terminal intercept visualization
- **Predicted Intercept Point (PIP)** — Real-time calculation and display of intercept geometry

### Visual & Interaction
- **Dark Navy-Style UI** — Professional military console visual design
- **Target Lock Animation** — Pulse lock box, track history trail, predicted flight path
- **Threat Alert System** — Top threat banner, tiered alert list, threat-level color coding
- **Target Status Dashboard** — Four-panel layout: Track Info, Kinematics, Engagement, Threat Assessment

### Audio Feedback
- **Procedural Sound Generation** — Web Audio API OscillatorNode, zero audio files required
- **5 Core Sound Types** — Alert beep, lock tone, missile launch, intercept explosion, radar pulse
- **Global Mute Control** — One-click mute toggle in top-right corner

## Quick Start

### Prerequisites
Modern browser (Chrome / Firefox / Edge latest). No backend or build tools required.

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

> **Note:** Due to browser autoplay policy, you may need to click anywhere on the page to activate AudioContext before sound effects work.

## Usage

| Action | Description |
|------|------|
| Click a target on the radar canvas | Select target, details shown in right panel |
| Click **LOCK TARGET** | Lock target, enter fire control tracking mode |
| Click **DESIGNATE** | Designate target for engagement, assign weapon |
| Click **FIRE** | Launch missile, begin intercept sequence |
| Toggle **SEARCH / TRACK / ENGAGE** | Switch radar operating mode |
| Drag **Range / Scan Rate** sliders | Adjust detection range and scan rate |
| Toggle filter checkboxes | Filter targets by type (Air / Ballistic / Surface) |
| Click top-right 🔊 | Toggle sound on/off |

## Tech Stack

| Category | Technology |
|------|------|
| Rendering | Canvas 2D API |
| Audio | Web Audio API (OscillatorNode) |
| Styling | Pure CSS (CSS Variables, Grid, Flexbox) |
| Logic | Vanilla JavaScript (ES5 compatible, no framework) |
| Dependencies | **Zero external dependencies** — self-contained single HTML file |

## Project Structure

```
radar-simulation/
├── index.html              # Main program (HTML + CSS + JS in one file)
├── README.md               # Project documentation
├── LICENSE                 # Open-source license
├── CONTRIBUTING.md         # Contribution guide
├── package.json            # Project metadata
├── .gitignore              # Git ignore rules
└── .github/
    └── workflows/
        └── ci.yml          # CI/CD workflow
```

## Contributing

Issues and Pull Requests are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed contribution workflow and coding standards.

## License

This project is licensed under the [MIT License](LICENSE).

## Disclaimer

This project is an educational and demonstrative simulation system. It contains no classified or real military data. All visuals, parameters, and behaviors are simulated and do not represent the actual performance of any real weapon system.

</details>