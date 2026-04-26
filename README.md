# 🌾 Windmill Countryside

An animated 2D countryside scene built with **C++ and OpenGL (GLUT/GLU)**. The scene features spinning windmills, moving cars, animated clouds, a day/night cycle, rain, and more — all rendered using OpenGL primitives.

---

## 📸 Scene Preview

| Day Mode | Night Mode |
|----------|------------|
| ![Day Mode](https://drive.google.com/uc?export=view&id=14cLsdcCnwFmeT6_u1uwRrNhtv9CRW44u) | ![Night Mode](https://drive.google.com/uc?export=view&id=1YoB6nZ3UwYXDb9YRTFPH9WcHKXj5D-J1) |

---

## 📋 Scene Overview

The scene includes:

- **4 Windmills** with rotating three-blade fans
- **2 Cars** (red and blue) moving in opposite directions on a road
- **5 Houses** with roofs, walls, doors, and windows
- **Hills** (2 large, 3 small) with shadow shading
- **Trees** and **bushes** scattered across the landscape
- **5 Animated clouds** drifting across the sky
- **Sun** that rises and sets, triggering a day-to-night transition
- **Moon** and **stars** visible at night
- **Rain** effect (toggleable)
- **Day/Night color theming** applied across all scene elements

---

## 🛠️ Built With

| Tool | Purpose |
|------|---------|
| C++ | Core programming language |
| OpenGL | 2D rendering via `GL_POLYGON`, `GL_TRIANGLES`, etc. |
| GLUT (FreeGLUT) | Window creation, event loop, keyboard & timer callbacks |
| GLU | Orthographic projection setup |
| Code::Blocks | IDE (`.cbp` project file included) |

---

## 📁 Project Structure

```
Windmill/
├── main.cpp           # Full source code
├── Windmill.cbp       # Code::Blocks project file
├── Windmill.depend    # Dependency tracking file
├── Windmill.layout    # IDE layout preferences
└── README.md
```

---

## ⚙️ Prerequisites

- A C++ compiler (MinGW/GCC recommended on Windows)
- OpenGL libraries: `opengl32`, `glu32`
- GLUT / FreeGLUT: `freeglut` or `glut`
- [Code::Blocks IDE](http://www.codeblocks.org/) (optional, for `.cbp` project)

### Installing FreeGLUT on Windows (MinGW)

1. Download FreeGLUT from [freeglut.sourceforge.net](http://freeglut.sourceforge.net/)
2. Copy headers to your MinGW `include/GL/` directory
3. Copy `.lib`/`.a` files to your MinGW `lib/` directory
4. Copy `freeglut.dll` to your project directory or `System32`

---

## 🚀 Building & Running

### Using Code::Blocks
1. Open `Windmill.cbp` in Code::Blocks
2. Ensure the linker settings include: `-lglut32 -lglu32 -lopengl32`
3. Press **Build & Run** (`F9`)

### Using g++ (Command Line)
```bash
g++ main.cpp -o windmill -lglut32 -lglu32 -lopengl32
./windmill
```

> **Note:** On Linux, replace `-lglut32 -lglu32 -lopengl32` with `-lglut -lGLU -lGL`

---

## 🎮 Controls

### Scene Controls
| Key | Action |
|-----|--------|
| `D` | Switch to **Day** mode |
| `N` | Switch to **Night** mode |
| `A` | Start **Rain** |
| `C` | Stop **Rain** |

### Red Car Controls
| Key | Action |
|-----|--------|
| `F` | Speed up |
| `B` | Slow down / reverse |
| `H` | Stop the car |

### Blue Car Controls
| Key | Action |
|-----|--------|
| `X` | Speed up |
| `Y` | Slow down / reverse |
| `Z` | Stop the car |

### Windmill Controls
| Key | Action |
|-----|--------|
| `L` | Rotate **anticlockwise** |
| `R` | Rotate **clockwise** |
| `S` | **Stop** rotation |

---

## ✨ Features & Animation Details

- **Day/Night Cycle:** The sun automatically arcs across the sky. When it sets, the scene transitions to night — sky darkens, stars and moon appear, and all object colors shift to night variants.
- **Windmill Rotation:** Blades spin continuously using an idle callback and a global `spin` variable updated each frame.
- **Moving Cars:** The red car moves right-to-left; the blue car moves left-to-right. Both loop seamlessly off-screen.
- **Animated Clouds:** Five clouds drift in alternating directions and wrap around the viewport.
- **Rain Effect:** Randomly placed line segments simulate falling rain when toggled on.
- **Viewport:** 1200×600 window with a 1000×500 orthographic coordinate space.

---

## 🐛 Known Issues

- Rain rendering uses OpenGL calls outside the main `display()` function, which may cause flickering on some systems.
- Color values slightly above `1.0` (e.g. `glColor3f(0.533, 1.293, 0.0)`) are clamped by OpenGL — these are intentional stylistic choices in the original code.
- Night mode triggered by pressing `N` uses `glutIdleFunc(night)` which may conflict with windmill idle callbacks.

---

## 👤 Author

**Ahadul Islam Chowdhury** - 
Computer Graphics course project — **Windmill Countryside** scene.
