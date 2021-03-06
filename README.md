<h1 align="center">
  <br>
  <a href="https://github.com/jpbruyere/vkvg/blob/master/vkvg.svg">
	<img src="https://github.com/jpbruyere/vkvg/blob/master/vkvg.svg?sanitize=true" alt="vkvg" width="140">
  </a>
  <br>
	<br>
  Vulkan Vector Graphics
  <br>
<p align="center">
  <a href="https://www.paypal.me/GrandTetraSoftware">
	<img src="https://img.shields.io/badge/Donate-PayPal-green.svg">
  </a>
</p>
</h1>

### What is vkvg?

**vkvg** is a multiplatform **c** library for drawing 2D vector graphics with [Vulkan](https://www.khronos.org/vulkan/).

[Cairo](https://www.cairographics.org/) was missing a Vulkan backend, so I decided to start one myself trying to keep my api as close to Cairo as possible. 

### Current status:

**vkvg** is in early development stage, **0.1** beta release is on the road.

- Fill (with stencil even-odd technic) and Stroke functional.
- Basic painting operation.
- Font system with caching operational.
- Linear Gradients.
- Line caps and joins.
- Context should be thread safe, extensive tests required.
- Image loading and writing with [stb lib](https://github.com/nothings/stb)
- Test includes svg rendering with [nanoSVG](https://github.com/memononen/nanosvg)

<p align="center">
  <a href="https://github.com/jpbruyere/vkvg/blob/master/screenshot1.png">
    <img src="https://github.com/jpbruyere/vkvg/blob/master/screenshot1.png" width="500">
  </a>
</p>

### Requirements:

- [Vulkan](https://www.khronos.org/vulkan/)
- [FontConfig](https://www.freedesktop.org/wiki/Software/fontconfig/)
- [Freetype](https://www.freetype.org/)
- PkgConfig (currently used only to find harbfbuzz)
- [Harfbuzz](https://www.freedesktop.org/wiki/Software/HarfBuzz/)
- GLSLC: spirv compiler, included in [LunarG SDK](https://www.lunarg.com/vulkan-sdk/) (building only)
- [xxd](https://linux.die.net/man/1/xxd): generate headers with precompiled shaders (building only)
- [GLFW](http://www.glfw.org/) (only for running demo app)
- CMake

if glslc or xxd are not present, a precompiled version of the shaders is stored in the git tree.

### Building

```bash
git clone https://github.com/jpbruyere/vkvg.git     # Download source code from github
cd vkvg                                             # Enter the source directory
git submodule update --init --recursive             # Dowload vkhelpers sources
mkdir build					    # Create build directory
cd build
cmake ..					    # Run CMake, optionaly setup glslc path
make						    # Run Make
```

### Roadmap

- Radial gradients.
- Dashed lines.
- Operators.
- Improve stroke algorithms.
- Offscreen pattern building.
- Optimize vulkan memory allocations by sub-allocating from a single shared memory chunk per type.
- Optimize command submissions.
- Test SDF font rendering.
- Avoid line joins inside curves and arc.
- Structured unit testing.
- Perf and memory checks.
- Code clean and comment.
- Documentations.


