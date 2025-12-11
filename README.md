# WebGL Train Scene Demo

**Interactive 3D train simulation built with pure WebGL and JavaScript**

Full-stack computer graphics project demonstrating real-time 3D rendering, procedural generation, and physics simulation. Built from scratch using WebGL 1.0 without external 3D libraries.

[View Live Demo](#) <!-- Add your GitHub Pages link here -->

---

## 🎮 Features

### Real-Time 3D Graphics

### Interactive Environment

### User Controls

## 🎯 Controls Reference

| Action | Key(s) |
|--------|--------|
| **Camera Mode 1** - Follow Train | `1` |
| **Camera Mode 2** - Side View | `2` |
| **Camera Mode 3** - Top-Down | `3` |
| **Camera Mode 4** - Orbital | `4` |
| **Camera Mode 5** - Free Camera | `5` |
| **Increase Speed** | `↑` Arrow |
| **Decrease Speed** | `↓` Arrow |
| **Move Forward** (Free Cam) | `W` |
| **Move Backward** (Free Cam) | `S` |
| **Strafe Left** (Free Cam) | `A` |
| **Strafe Right** (Free Cam) | `D` |
| **Move Up** (Free Cam) | `E` |
| **Move Down** (Free Cam) | `Q` |
| **Look Around** (Free Cam) | Mouse Drag |
| **Pause/Resume** | `Spacebar` |

---


## 💻 Technical Stack

- **glMatrix 3.4.3** - Efficient matrix mathematics for 3D transformations

- **Alpha Blending** - Transparency for particle effects

- **High-DPI Support** - Device pixel ratio scaling for retina displays
---

## 🚀 Implementation Highlights
- Manual vertex buffer object (VBO) management
- Element buffer object (EBO) indexing with Uint32 support for large models
- Attribute pointer configuration and shader uniform management

### Shader Programming
**Vertex Shaders**: Transform 3D geometry with model-view-projection matrices, calculate world-space normals, compute fog depth

**Fragment Shaders**: 
- Procedural texture generation (wood grain, metal noise, gradient patterns)
- Multi-light Phong shading with spotlight attenuation
- Distance fog blending
- Particle alpha compositing

### Scene Management
- **Scene Graph**: Parent-child transform hierarchies for complex animations
- **Object Pooling**: Reuse terrain tiles, track segments, and environmental objects
- **State Synchronization**: Coordinate camera, train position, and world objects

### Performance Optimizations
- Geometry instancing for repeated objects (sleepers, pillars)
- Compressed vertex data with interleaved attributes
- Efficient matrix operations with pre-allocated buffers
- Delta-time animation for frame-rate independence

---

## 🎓 Learning Outcomes

This project demonstrates proficiency in:
- **Computer Graphics Fundamentals**: Coordinate systems, projection matrices, lighting models
- **WebGL API Mastery**: Buffer management, shader compilation, texture handling
- **3D Mathematics**: Matrix transformations, vector operations, quaternions
- **Game Development Patterns**: Game loop, input handling, state management
- **Code Architecture**: Modular design, separation of concerns, maintainable structure

Developed as part of **CptS 442 - Computer Graphics** coursework at Washington State University, showcasing practical application of theoretical concepts in real-time rendering.

---

## 📂 Project Structure

```
WebGL-Train-Scene-Demo/
├── index.html              # Main application file
├── train_v1_L3.../         # 3D train model assets
│   ├── 11709_train_v1_L3.obj
│   └── textures/
├── *.jpg                   # Terrain and material textures
└── README.md
```

---

## 🎯 Controls Reference

| Action | Key(s) |
|--------|--------|
| **Camera Mode 1** - Follow Train | `1` |
| **Camera Mode 2** - Side View | `2` |
| **Camera Mode 3** - Top-Down | `3` |
| **Camera Mode 4** - Orbital | `4` |
| **Camera Mode 5** - Free Camera | `5` |
| **Increase Speed** | `↑` Arrow |
| **Decrease Speed** | `↓` Arrow |
| **Move Forward** (Free Cam) | `W` |
| **Move Backward** (Free Cam) | `S` |
| **Strafe Left** (Free Cam) | `A` |
| **Strafe Right** (Free Cam) | `D` |
| **Move Up** (Free Cam) | `E` |
| **Move Down** (Free Cam) | `Q` |
| **Look Around** (Free Cam) | Mouse Drag |
| **Pause/Resume** | `Spacebar` |

---

## 🔧 Running Locally

```bash
# Clone the repository
git clone https://github.com/SpidersSuck/Portfolio.git
cd Portfolio/WebGL-Train-Scene-Demo

# Start a local HTTP server (required for texture loading)
python -m http.server 8000

# Open in browser
# Navigate to http://localhost:8000
```

**Note**: Must be served via HTTP/HTTPS due to CORS restrictions on texture loading. Cannot run directly from `file://` protocol.

---

## 📚 Technical Documentation

### Coordinate System
- **Right-handed**: +X right, +Y up, +Z toward camera
- **Train motion**: Positive Z-axis (toward camera)
- **World units**: Arbitrary scale (train ~6 units tall)

### Lighting System
- 10 dynamic point lights with spotlight cone
- Positioned at street lamp locations
- Sorted by distance to train for nearest-light culling
- Intensity: 35 units with quadratic attenuation

### Camera Specifications
- **FOV**: 45° (π/4 radians)
- **Near plane**: 0.1 units
- **Far plane**: 500 units
- **Aspect ratio**: Viewport-dependent

---

## 🎨 Asset Attribution

- **Train Model**: Custom-textured 3D model with wood, metal, and painted materials
- **Textures**: Procedural generation + sourced texture maps for realism
- **Skybox**: Fully procedural gradient with mathematical cloud generation

---

## 📖 Code Quality

- **Student-friendly comments**: Clear explanations for educational purposes
- **Attribution**: References to course material sources (Week 6-10 examples)
- **Modular structure**: Separate sections for shaders, geometry, scene management
- **Readable formatting**: ~1240 lines with logical organization

---

## 🌐 Browser Compatibility

Tested and optimized for:
- ✅ Chrome 90+
- ✅ Edge 90+
- ✅ Safari 14+ (WebGL support required)

Requires WebGL 1.0 support and `OES_element_index_uint` extension for large models.

---

*Built with passion for computer graphics and real-time rendering techniques. Part of an ongoing portfolio demonstrating full-stack development capabilities.*
