# 知乎文章文案

## 标题：如何用浏览器"看见"四维空间？我做了一个开源可视化工具

## 正文：

数学中有个有趣的事实：**我们生活在三维空间，但可以用数学描述任意维度的空间**。

从一维到二维到三维，我们都有直观的几何感受。但到了四维，我们的大脑就无法"想象"了 —— 因为我们没有四维的眼睛。

但这并不意味着我们无法**可视化**四维。

最近我做了一个开源项目 **DimViz**（Dimension Visualizer），用 Three.js 实现了从一维到**四维**的数学空间动态可视化。本文分享一下设计思路和技术实现。

---

## 一、为什么需要维度可视化？

线性代数里有很多抽象概念：
- 什么是"空间"？
- 基底到底是什么？
- 线性变换的几何意义是什么？
- 特征值在哪里？

教科书里的公式是一回事，但**几何直觉**是另一回事。

一个好的可视化工具，可以帮学生、研究者快速建立空间直觉。

## 二、从一维到三维：建立基础

### 一维（ℝ¹）
最简单的"空间"：一条数轴。
- 可视化：滑动点 + 基底箭头
- 数学概念：空间定义、基底、范数、线性映射

### 二维（ℝ²）
平面空间，最直观。
- 可视化：XY 网格 + 基向量 + 样本向量 + 投影虚线
- 数学概念：标准正交基、欧氏范数、线性变换、旋转矩阵

### 三维（ℝ³）
我们生活的空间。
- 可视化：三轴 + 单位球（线框）+ 叉积平面 + 样本向量
- 数学概念：内积、叉积、特征值、单位球面 $S^2$

## 三、四维（ℝ⁴）：核心挑战

四维是这个项目最有意思的部分。

### 问题：如何在 2D 屏幕上展示 4D 物体？

答案是：**投影** + **颜色编码**。

#### 1. 透视投影（Perspective Projection）
就像 3D 游戏把三维场景投影到 2D 屏幕一样，我们可以把 4D 物体投影到 3D 空间：

$$
P(v) = \left( \frac{x}{2-w}, \frac{y}{2-w}, \frac{z}{2-w} \right)
$$

其中 $w$ 是第 4 坐标，焦距设为 2。

#### 2. 颜色编码第 4 维度
投影会丢失信息（就像 3D→2D 会丢失深度信息）。为了"找回"第 4 维度，我们把 $w$ 坐标映射为**颜色渐变**：

- $w = -2$ → 蓝色（冷色，表示"远"）
- $w = 0$ → 紫色（过渡）
- $w = +2$ → 红色（暖色，表示"近"）

这样，即使看不见第四维，你也能通过颜色"感知"它。

### 超立方体（Tesseract）

4D 版本的立方体叫做**超立方体**或**Tesseract**：
- 顶点：16 个（每个坐标是 ±1）
- 边：32 条（两个顶点如果只差一个坐标，就连一条边）
- 面：24 个面（每个面是正方形）

在 DimViz 里，你可以：
1. 拖动旋转 3D 视角
2. 开启"4D 旋转"，观察超立方体在 4D 空间中的旋转（投影会实时变化！）
3. 通过颜色变化，感知第 4 维度的"深度"

## 四、技术实现

### 技术栈
- **Three.js r128**：3D 渲染引擎
- **KaTeX**：实时 LaTeX 公式渲染
- **纯 HTML/CSS/JS**：零依赖，无需构建

### 核心代码逻辑

#### 1. 生成超立方体顶点
```javascript
function getTesseractVertices() {
    const verts = [];
    for (let i = 0; i < 16; i++) {
        verts.push([
            (i & 1) ? 1 : -1,
            (i & 2) ? 1 : -1,
            (i & 4) ? 1 : -1,
            (i & 8) ? 1 : -1
        ]);
    }
    return verts; // 16 vertices
}
```

#### 2. 4D 旋转矩阵
4D 空间有 6 个旋转平面（SO(4) 有 6 个自由度）：
- XY, XW, XZ, YW, YZ, ZW

```javascript
function rotate4D(v, aXY, aXW, aYZ, aYW) {
    let [x, y, z, w] = v;
    // XY plane rotation
    let x2 = x*Math.cos(aXY) - y*Math.sin(aXY);
    let y2 = x*Math.sin(aXY) + y*Math.cos(aXY);
    // XW plane rotation
    let x3 = x2*Math.cos(aXW) - w*Math.sin(aXW);
    let w2 = x2*Math.sin(aXW) + w*Math.cos(aXW);
    // ... 其他平面
    return [x3, y3, z3, w2];
}
```

#### 3. 投影 + 颜色映射
```javascript
function project4DTo3D(v4, focalLength) {
    const [x, y, z, w] = v4;
    const scale = focalLength / (focalLength - w);
    return [x * scale, y * scale, z * scale, w]; // 返回 w 用于颜色
}

function colorFromW(w) {
    const t = (w + 2) / 4; // 归一化到 [0, 1]
    const hue = (240 + 120 * t) % 360; // 240(蓝) -> 300(紫) -> 0(红)
    return new THREE.Color().setHSL(hue / 360, 1.0, 0.62);
}
```

## 五、在线体验

- **GitHub Pages**：https://garywang2025.github.io/DimViz/
- **CloudStudio**：https://68b73c2252df4cf786cafccb8f3ba949.app.codebuddy.work

## 六、开源与反馈

项目已开源：https://github.com/GaryWang2025/DimViz

MIT 协议，欢迎：
- ⭐ Star（如果觉得有用）
- 🐛 提 Issue（Bug 反馈或功能建议）
- 🔧 提 PR（一起改进）

目前正在规划 **V003 版本**，如果你有想法，欢迎留言讨论！

---

**参考阅读**：
- Four-dimensional space - Wikipedia
- Visualizing Higher Dimensions - 3Blue1Brown
- Tesseract - Wikipedia

**标签**：#数学 #可视化 #四维空间 #开源 #Three.js #线性代数
