# Computer Graphics Notes

A personal knowledge base for computer graphics and the engines it runs inside — theory notes, worked exercises, runnable implementations, and an orientation in the field as a research discipline. It spans mathematics through rendering, physics, architecture and systems programming.

It is an **Obsidian** vault that stays fully readable on **GitHub**. Every cross-reference is a relative markdown link, so the knowledge graph works in both.

This is the hub. The buildable projects live in their own repositories — see [Projects](#projects).

---

## Overview

The vault is organized **domain first**. Each top-level numbered folder is a domain, each domain holds subjects, and every subject carries its own `Concepts/`, `Exercises/` and `Assets/`.

Every domain has two files at its root: a `README.md` indexing what exists there now, and a `00_Roadmap.md` — a scoped study plan naming the subjects to cover and what to deliberately skip. Domains that have not been started yet have only the roadmap's worth of content.

Exercises are bound to the theory they practise: every question links to its solution, and every solution links back to the concept note it came from. Practice and theory stay connected rather than drifting apart.

New here? Start with [Your First Study Session](00_Documentation/tutorials/FirstStudySession.md).

---

## Domains

| Domain                                                                     | Covers                                                                      |
| :------------------------------------------------------------------------- | :-------------------------------------------------------------------------- |
| [01_Mathematics](01_Mathematics/README.md)                                 | Linear algebra, calculus, numerical methods, probability, signal processing |
| [02_Rendering](02_Rendering/README.md)                                     | MVP, rasterization, graphics APIs, shading, shadows                         |
| [03_Physics](03_Physics/README.md)                                         | Collision primitives, GJK/SAT, rigid body dynamics                          |
| [04_Engine_Architecture](04_Engine_Architecture/README.md)                 | Game loop, memory, ECS, resources, tooling patterns                         |
| [05_Data_Structures](05_Data_Structures/README.md)                         | Spatial structures, cache-aware containers                                  |
| [06_Algorithms](06_Algorithms/README.md)                                   | Computational geometry, pathfinding, procedural generation                  |
| [07_Concurrency_and_Parallelism](07_Concurrency_and_Parallelism/README.md) | Memory model, job systems, lock-free structures                             |
| [08_Systems_and_Performance](08_Systems_and_Performance/README.md)         | Cache hierarchy, data-oriented design, SIMD, profiling                      |
| [09_Tools_and_Pipeline](09_Tools_and_Pipeline/README.md)                   | Asset pipeline, serialization, build systems, editor tooling                |
| [10_Audio](10_Audio/README.md)                                             | Real-time audio, mixing, spatialization, DSP                                |
| [11_Networking](11_Networking/README.md)                                   | Transport, state sync, latency hiding, determinism                          |
| [12_Research](12_Research/README.md)                                       | Venues, authors, landmark papers, open questions, finding new work          |

Each domain link lands on that domain's **index** — what exists there now, and how much of it.
The index links on to `00_Roadmap.md`, the study plan for what does not exist yet.

Nothing here is ever finished — notes get revisited and deepened as the material gets used, and a domain reaching the end of its roadmap only means the first pass is done. Open threads are tracked in [TODO.md](TODO.md).

---

## Projects

The notes are the theory; these are the things built from it. Each is its own repository —
they are buildable projects with their own history, not folders in a vault.

| Project | What it is | State |
| :--- | :--- | :--- |
| [ray-tracer](https://github.com/alessandrogpz/ray-tracer) | CPU ray tracer in C++, built test-first from *The Ray Tracer Challenge*. Spheres, Phong shading, shadows, matrix transforms | Renders scenes; 8 images in its README |
| [learn-opengl](https://github.com/alessandrogpz/learn-opengl) | OpenGL 3.3 core-profile foundation — window, shaders, buffers | Early |
| [pppc-notes](https://github.com/alessandrogpz/pppc-notes) | Chapter-by-chapter work through Stroustrup's *Programming: Principles and Practice*, 3rd ed. | Through the core chapters |
| [dsa-notes](https://github.com/alessandrogpz/dsa-notes) | Data structures and algorithms practice | Ongoing |

The mathematics those projects run on is documented here: the ray tracer's matrix transforms
are derived in [04_Transforms](01_Mathematics/01_Linear_Algebra/README.md#04_transforms), and
its intersection tests in [05_Geometry](01_Mathematics/01_Linear_Algebra/README.md#05_geometry).

Links out use absolute URLs deliberately. A relative path between repositories resolves in
neither Obsidian nor GitHub, so a cross-repository reference has to be a full link.

---

## Documentation

Documentation lives in [00_Documentation](00_Documentation/README.md), indexed there in full. It follows the [Diátaxis](https://diataxis.fr/) framework.

* [Tutorials](00_Documentation/README.md#tutorials)
* [How-to Guides](00_Documentation/README.md#how-to-guides)
* [Reference](00_Documentation/README.md#reference)
* [Explanation](00_Documentation/README.md#explanation)

---

## Tooling

| | |
| :--- | :--- |
| [randomizer.py](randomizer.py) | Picks one random question to practise — [reference](00_Documentation/references/Randomizer.md) |
| [90_Code](90_Code/README.md) | C++23 CMake project with a GoogleTest suite — [build guide](00_Documentation/how-to/BuildAndTest.md) |
| [99_Templates](99_Templates/README.md) | Question and solution templates |
| [scripts](scripts/README.md) | Link and math checkers — run in CI on every push |

```bash
python3 randomizer.py                     # one question to practise
cmake -S 90_Code -B build -G Ninja        # configure the code project
```
