# Reddit 发布文案

## Title: I built a browser-based math visualizer (1D→4D), now open source

## Subreddits: 
- r/math
- r/visualization
- r/javascript
- r/threejs

## Body:

Hi everyone! I'd like to share a project I've been working on: **DimViz** (Dimension Visualizer).

It's a browser-based tool that visualizes mathematical spaces from 1D to **4D**. No installation needed — just open the HTML file or visit the live demo.

### What it does:

| Dimension | Visualization | Math Concepts |
|-----------|---------------|----------------|
| ℝ¹ (1D) | Number line, sliding point | Space definition, basis, norm |
| ℝ² (2D) | XY grid, basis vectors, projection | Linear transform, rotation matrix |
| ℝ³ (3D) | 3-axis, unit sphere, cross product plane | Dot product, eigenvalues, $S^2$ |
| ℝ⁴ (4D) | **Tesseract** wireframe, w→color gradient | Perspective projection, 4D rotation, $SO(4)$ |

### How 4D visualization works:

Since we can't "see" 4D directly, the project uses two techniques:

1. **Perspective projection**: Project 4D points to 3D space (like 3D→2D projection in games)
3. **Color encoding**: Map the 4th coordinate (w) to a **color gradient** (blue→purple→red)

So even though the screen is 2D, you can "perceive" the 4th dimension through color!

### Try it online:

- **GitHub Pages**: https://garywang2025.github.io/DimViz/
- **CloudStudio**: https://68b73c2252df4cf786cafccb8f3ba949.app.codebuddy.work

### Tech stack:
- Three.js r128 (3D rendering)
- KaTeX (LaTeX formula rendering)
- Pure HTML/CSS/JS (zero dependencies)

### Open source:
https://github.com/GaryWang2025/DimViz

MIT license. PRs and feedback welcome!

I'm currently planning **V003**. What features would you like to see?
- 5D visualization?
- More math concepts (manifolds, vector fields)?
- Export screenshots/videos?
- Mobile-friendly UI?

Would love to hear your thoughts!

---

**Demo screenshot** (if allowed):
[Insert screenshot of 4D tesseract here]

**GitHub repo**: https://github.com/GaryWang2025/DimViz
