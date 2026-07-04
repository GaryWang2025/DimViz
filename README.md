# DimViz 📐 (V005)

> **Dim**ension **Viz**ualizer — 一维到五维数学空间动态可视化（ℝ¹→ℝ²→ℝ³→ℝ⁴→ℝ⁵）

[![Live Demo](https://img.shields.io/badge/🌐%20GitHub%20Pages-Live%20Demo-blue?style=for-the-badge)](https://garywang2025.github.io/DimViz/)
[![MIT License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)]()
[![GitHub Stars](https://img.shields.io/github/stars/GaryWang2025/DimViz?style=for-the-badge)](https://github.com/GaryWang2025/DimViz)
[![Three.js](https://img.shields.io/badge/Three.js-r128-green?style=for-the-badge)](https://threejs.org/)
[![No Build](https://img.shields.io/badge/Build-No%20Build%20Required-orange?style=for-the-badge)]()

[中文](#中文) | [English](#english)

---

## English

### ✨ Features

#### Core Visualization
- 🎯 **Interactive 1D→5D** — Drag to rotate, scroll to zoom, auto-rotate
- 📐 **Rigorous Math** — KaTeX LaTeX formula panel for each dimension (ℝ¹→ℝ⁵)
- 🎬 **Auto Demo** — Watch dimensions unfold: 1D → 2D → 3D → 4D → 5D

#### 4D Features
- 🌀 **Tesseract (Hypercube)** — Perspective projection ℝ⁴→ℝ³, W encoded as color gradient
- 🔺 **5 Regular 4-Polytopes** — 5-cell, 8-cell, 16-cell, 24-cell, 600-cell (of the 6 convex regular 4-polytopes; 120-cell omitted for performance)
- 🎨 **Cell Coloring** — Each tesseract cell gets a unique color; isolate individual cells
- 🌐 **Stereographic Projection** — Conformal projection with curved (slerp-interpolated) edges
- 🎛️ **Per-Plane Rotation** — All 6 rotation planes (4D) / 10 planes (5D) with independent speed & toggle
- 📦 **Unfold Animation** — Tesseract unfolds into Dalí cross (8 cells → 3D cross)
- 🔪 **4D Slice** — W-axis cross-section showing the true **3D polyhedron** (convex hull)
- 🔀 **Dimension Collapse** — Watch 4D continuously collapse into 3D (paired vertex interpolation)

#### 5D Features
- 🌌 **Penteract (5D Hypercube)** — 32 vertices, 80 edges, double perspective projection 5D→4D→3D
- 🎨 **V-axis Color Gradient** — 5th dimension encoded as color hue

#### UI / UX
- 🌙 **Dark / Light Mode** — Full CSS variable theming, scene background syncs
- 🌐 **i18n** — English / 中文 real-time language toggle
- 📷 **Screenshot Export** — One-click PNG download
- 📚 **Tutorial Mode** — 4-step guided intro (auto-launches on first visit via localStorage, reopenable via ❓)

### 🚀 Live Demo

☛ **[Try DimViz online →](https://garywang2025.github.io/DimViz/)**

No install, no build — click and explore!

### 🚀 Quick Start

No build step required — just open in a browser:

```bash
git clone https://github.com/GaryWang2025/DimViz.git
open output/dimension-visualizer.html
```

Or download `output/dimension-visualizer.html` and double-click it.

### 📐 What's Inside

| Dimension | Object | Vertices | Edges | Key Concepts |
|-----------|--------|----------|-------|-------------|
| **ℝ¹** | Number line, basis arrow | — | — | Space definition, basis, norm, linear map |
| **ℝ²** | XY grid, basis vectors | — | — | Standard basis, rotation matrix, linear transform |
| **ℝ³** | 3-axis, unit sphere, cross product | — | — | Inner product, cross product, eigenvalues, S² |
| **ℝ⁴** | **8-cell** (Tesseract) | 16 | 32 | Perspective projection, SO(4), 6 rotation planes |
| **ℝ⁴** | **5-cell** (Pentachoron) | 5 | 10 | 4-simplex, Schläfli {3,3,3} |
| **ℝ⁴** | **16-cell** (Hexadecachoron) | 8 | 24 | 4D cross-polytope, Schläfli {3,3,4} |
| **ℝ⁴** | **24-cell** (Icositetrachoron) | 24 | 96 | Unique to 4D, Schläfli {3,4,3} |
| **ℝ⁴** | **600-cell** (Hexacosichoron) | 120 | 720 | Golden ratio φ, Schläfli {3,3,5} |
| **ℝ⁵** | **Penteract** | 32 | 80 | Double projection 5D→4D→3D, SO(5), 10 rotation planes |

### 🛠️ Tech Stack

- [Three.js r128](https://threejs.org/) — 3D rendering
- [KaTeX](https://katex.org/) — LaTeX formula rendering
- Pure HTML/CSS/JS — no build step (CDN-based dependencies: Three.js, KaTeX)

### 🤝 Contributing & Feedback

- 🐛 **Bug report** → [Open an Issue](https://github.com/GaryWang2025/DimViz/issues/new?template=bug_report.md)
- 💡 **Feature request** → [Suggest a feature](https://github.com/GaryWang2025/DimViz/issues/new?template=feature_request.md)
- 📢 **Feedback** → [Start a discussion](https://github.com/GaryWang2025/DimViz/issues/new?template=feedback.md)
- 🔧 **Code** → PRs welcome!

### 📄 License

MIT © 2026

---

## 中文

### ✨ 功能特性

#### 核心可视化
- 🎯 **可交互 1D→5D** — 拖动旋转，滚轮缩放，自动旋转
- 📐 **严格数学** — KaTeX LaTeX 公式面板，覆盖 ℝ¹→ℝ⁵
- 🎬 **自动演示** — 观看维度展开：1D → 2D → 3D → 4D → 5D

#### 4D 功能
- 🌀 **超立方体（Tesseract）** — 透视投影 ℝ⁴→ℝ³，第4维（W）编码为颜色渐变
- 🔺 **5种正则4D多胞体** — 5-cell、8-cell、16-cell、24-cell、600-cell（6种凸正则4-多胞体中的5种；120-cell因性能省略）
- 🎨 **胞体着色** — 超立方体每个胞体独立颜色，可单独隔离显示
- 🌐 **立体投影** — 保角映射，棱边显示为弧线（slerp插值）
- 🎛️ **旋转平面独立控制** — 4D全部6平面 / 5D全部10平面，各自独立调速和开关
- 📦 **展开动画** — 超立方体展开为达利十字（8个立方体胞→3D十字形）
- 🔪 **4D 切片** — W轴截面，显示**真正的3D多面体**（凸包算法）
- 🔀 **维度塌陷** — 亲眼看4D连续塌缩为3D（成对顶点插值）

#### 5D 功能
- 🌌 **五维超立方体（Penteract）** — 32顶点80棱，双重透视投影 5D→4D→3D
- 🎨 **V轴颜色渐变** — 第5维编码为色相

#### UI / 体验
- 🌙 **深色/浅色模式** — CSS 变量全套切换，场景背景同步
- 🌐 **中英文切换** — 实时语言切换
- 📷 **截图导出** — 一键下载 PNG
- 📚 **新手教程** — 4步引导（首次加载自动弹出，localStorage记忆，❓随时重开）

### 🚀 在线体验

☛ **[点击体验 →](https://garywang2025.github.io/DimViz/)**

无需安装，无需构建 — 打开即用！

### 📐 内容概览

| 维度 | 对象 | 顶点 | 棱 | 关键概念 |
|------|------|------|-----|---------|
| **ℝ¹** | 数轴、基向量 | — | — | 空间定义、基底、范数、线性映射 |
| **ℝ²** | XY网格、基向量 | — | — | 标准正交基、旋转矩阵、线性变换 |
| **ℝ³** | 三轴、单位球、叉积 | — | — | 内积、叉积、特征值、单位球面 S² |
| **ℝ⁴** | **8-cell**（超立方体） | 16 | 32 | 透视投影、SO(4)、6个旋转平面 |
| **ℝ⁴** | **5-cell**（正五胞体） | 5 | 10 | 4-单纯形、Schläfli {3,3,3} |
| **ℝ⁴** | **16-cell**（正十六胞体） | 8 | 24 | 4D交叉多面体、Schläfli {3,3,4} |
| **ℝ⁴** | **24-cell**（正二十四胞体） | 24 | 96 | 4D独有、Schläfli {3,4,3} |
| **ℝ⁴** | **600-cell**（正六百胞体） | 120 | 720 | 黄金比例φ、Schläfli {3,3,5} |
| **ℝ⁵** | **五维超立方体** | 32 | 80 | 双重投影 5D→4D→3D、SO(5)、10个旋转平面 |

### 🛠️ 技术栈

- [Three.js r128](https://threejs.org/) — 3D 渲染引擎
- [KaTeX](https://katex.org/) — LaTeX 公式渲染
- 纯 HTML/CSS/JS — 无需构建（CDN依赖：Three.js、KaTeX）

### 📄 许可证

MIT © 2026

---

> Made with 🧮 and 🎨 by WorkBuddy
