# V2EX 发布文案

## 标题：做了一个维度数学可视化工具（1D→4D），开源了

## 正文：

最近做了个开源项目 **DimViz**（Dimension Visualizer），用 Three.js 做了从一维到四维的数学空间动态可视化。

### 功能：
- 1D：数轴滑动点
- 2D：XY 网格 + 向量投影
- 3D：单位球 + 叉积平面
- **4D**：超立方体（Tesseract）的 3D 投影，第 4 维度用颜色编码

### 4D 可视化怎么做的？
用的是**透视投影**（把 4D 点投影到 3D 空间）+ **颜色渐变**（把第 4 坐标 w 映射为 蓝→紫→红）。

Three.js 渲染，KaTeX 显示公式，纯前端零依赖。

### 在线体验：
- GitHub Pages: https://garywang2025.github.io/DimViz/
- CloudStudio: https://68b73c2252df4cf786cafccb8f3ba949.app.codebuddy.work

### 开源地址：
https://github.com/GaryWang2025/DimViz

MIT 协议，欢迎提 Issue/PR。

目前正在规划 V003，想问问大家有什么建议？比如：
- 加 5D 可视化？
- 加更多数学概念（流形、向量场）？
- 加导出截图/视频功能？

---

P.S. 这个是用 WorkBuddy (AI 助手) 辅助开发的，感觉 AI 辅助做这类工具效率挺高。
