---
title: "Slippers Engine"

featured: true

categories:
- Software Engineering

tags:
- C++
- OpenAL
- Engine Architecture
- Perforce

weight: 2

summary: "A custom C++ game engine built to explore rendering, engine architecture, audio programming, and reusable game systems."

showDate: false
showReadingTime: false
showWordCount: false
showAuthor: false
---

# Slippers Engine

> 🔵 **Status:** Completed

**Lead Engine Programmer • C++ • DirectX 11 • OpenAL**

---

# Overview

Introduce the engine.

- Why did you build it?
- What was your goal?
- What problems were you trying to solve?
- What technologies does it use?

---

# Technical Highlights

Implemented the foundational systems that support gameplay and rendering throughout the engine.

▶ [Engine Architecture](#engine-architecture)

▶ [Rendering Pipeline](#rendering-pipeline)

▶ [Resource Management](#resource-management)

▶ [Audio System](#audio-system)

▶ [Animation System](#animation-system)

▶ [Scene Management](#scene-management)

▶ [Lessons Learned](#lessons-learned)

---

<a id="engine-architecture"></a><h1 class="section-title">Engine Architecture</h1>

### Highlights

- Modular manager-based architecture.
- Separation between gameplay and rendering.
- Reusable engine components.
- Scalable system organization.

Describe the overall architecture.

Explain how the engine is organized.

Include an architecture diagram.

---

<a id="rendering-pipeline"></a><h1 class="section-title">Rendering Pipeline</h1>

### Highlights

- DirectX 11 renderer.
- Vertex & pixel shaders.
- Constant buffers.
- Lighting pipeline.
- Texture management.

Describe the rendering pipeline.

Explain how models move from CPU to GPU.

Discuss shader architecture.

Include screenshots or pipeline diagrams.

---

<a id="resource-management"></a><h1 class="section-title">Resource Management</h1>

### Highlights

- Shared asset loading.
- Resource caching.
- Manager-based ownership.
- Duplicate prevention.

Describe how models, textures, and shaders are loaded.

Explain how resources are reused instead of duplicated.

Include a manager diagram.

---

<a id="audio-system"></a><h1 class="section-title">Audio System</h1>

### Highlights

- OpenAL integration.
- Source pooling.
- 3D positional audio.
- Reverb zones.
- Listener management.

Describe your audio framework.

Explain source recycling.

Discuss positional audio.

Show audio diagrams or screenshots.

---

<a id="animation-system"></a><h1 class="section-title">Animation System</h1>

### Highlights

- Skeletal animation.
- Animation blending.
- State management.
- Time-based playback.

Explain how animation data is updated.

Describe animation states.

Include GIFs if available.

---

<a id="scene-management"></a><h1 class="section-title">Scene Management</h1>

### Highlights

- Scene graph.
- Object lifecycle.
- Update loop.
- Render ordering.

Describe how objects are created, updated, and destroyed.

Explain the game loop.

Include a diagram.

---

# Images

Throughout the page include:

- Architecture diagrams
- Rendering pipeline diagrams
- Screenshots
- Wireframe mode
- Lighting examples
- Shadow examples
- Audio visualization
- Code snippets where appropriate

---

<a id="lessons-learned"></a><h1 class="section-title">Lessons Learned</h1>

Discuss what developing a custom engine taught you.

Possible topics:

- Writing reusable systems.
- Designing for extensibility.
- Debugging low-level graphics issues.
- Performance optimization.
- Working with DirectX.
- Learning modern C++.
- Engine architecture decisions.
- What you would redesign today.

---

# Looking Ahead

Although Slippers Engine successfully achieved its educational goals, there are several areas I would explore in future iterations.

Future improvements include:

- Entity Component System (ECS)
- Deferred Rendering
- Physically Based Rendering (PBR)
- Multi-threaded Rendering
- GPU Instancing
- Asset Hot Reloading
- Editor Tools
- Vulkan or DirectX 12 support