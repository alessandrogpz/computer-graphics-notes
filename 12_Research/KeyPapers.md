# Key Papers

The papers below are the ones most often cited as turning points: the foundations every graphics course teaches, then the recent work that reshaped the field. A useful objective check is SIGGRAPH's Test-of-Time award (running since 2023 for papers 10+ years old) and the ACM book *Seminal Graphics Papers: Pushing the Boundaries, Volume 2* (2023), which collects the field's landmark papers for SIGGRAPH's 50th anniversary. Years and venues are from standard references; verify the exact citation on the ACM Digital Library.

## Foundations (in reading order)

| Year | Paper | Authors | Area | Why it matters |
| --- | --- | --- | --- | --- |
| 1975 | Illumination for Computer Generated Pictures (CACM) | Bui Tuong Phong | Shading | The Phong reflection model; basis of real-time shading for decades |
| 1978 | Recursively Generated B-Spline Surfaces on Arbitrary Topological Meshes | Edwin Catmull, Jim Clark | Geometry | Catmull–Clark subdivision, still the film modeling standard |
| 1980 | An Improved Illumination Model for Shaded Display (CACM) | Turner Whitted | Rendering | Recursive ray tracing |
| 1982 | A Reflectance Model for Computer Graphics (TOG) | Robert Cook, Kenneth Torrance | Materials | Microfacet BRDF, ancestor of all physically based shading |
| 1984 | Compositing Digital Images (SIGGRAPH) | Thomas Porter, Tom Duff | Imaging | Alpha compositing; every VFX pipeline uses it |
| 1984 | Distributed Ray Tracing (SIGGRAPH) | Robert Cook, Thomas Porter, Loren Carpenter | Rendering | Monte Carlo sampling for blur, depth of field, soft shadows |
| 1985 | An Image Synthesizer (SIGGRAPH) | Ken Perlin | Procedural | Perlin noise; procedural textures |
| 1986 | The Rendering Equation (SIGGRAPH) | James Kajiya | Rendering | The integral equation all physically based rendering solves; path tracing |
| 1987 | Marching Cubes (SIGGRAPH) | William Lorensen, Harvey Cline | Geometry | Surface extraction from volumes and implicit fields |
| 1987 | Flocks, Herds and Schools (SIGGRAPH) | Craig Reynolds | Animation | Boids; crowds and emergent behavior |
| 1995–97 | Optimally Combining Sampling Techniques (SIGGRAPH 95), Metropolis Light Transport (SIGGRAPH 97), PhD thesis | Eric Veach, Leonidas Guibas | Rendering | Multiple importance sampling and bidirectional methods; core of every production path tracer |
| 1996 | Light Field Rendering / The Lumigraph (SIGGRAPH) | Marc Levoy, Pat Hanrahan / Gortler et al. | Image-based | Ancestors of NeRF and Gaussian splatting |
| 1996 | Global Illumination Using Photon Maps (EGWR) | Henrik Wann Jensen | Rendering | Photon mapping; caustics |
| 1997 | Surface Simplification Using Quadric Error Metrics (SIGGRAPH) | Michael Garland, Paul Heckbert | Geometry | The standard mesh simplification method (also used by LOD systems) |
| 1998 | Rendering Synthetic Objects into Real Scenes (SIGGRAPH) | Paul Debevec | Imaging/VFX | HDR image-based lighting; how CG is lit to match plates |
| 1999 | Stable Fluids (SIGGRAPH) | Jos Stam | Simulation | Unconditionally stable fluid solver; start of graphics fluids |
| 2003 | Poisson Image Editing (SIGGRAPH) | Patrick Pérez, Michel Gangnet, Andrew Blake | Imaging | Gradient-domain editing |
| 2005 | Animating Sand as a Fluid (SIGGRAPH) | Yongning Zhu, Robert Bridson | Simulation | FLIP method used in Houdini and most film water |
| 2006 | Poisson Surface Reconstruction (SGP) | Michael Kazhdan, Matthew Bolitho, Hugues Hoppe | Geometry | Meshes from scanned point clouds |
| 2007 | Microfacet Models for Refraction through Rough Surfaces (EGSR) | Bruce Walter et al. | Materials | GGX distribution, today's default in games and film |
| 2007 | Position Based Dynamics (JVCIR) | Matthias Müller et al. | Simulation | Fast, stable real-time cloth and soft bodies |
| 2012 | Physically-Based Shading at Disney (SIGGRAPH course) | Brent Burley | Materials | The "Disney principled BRDF", adopted across film and game engines |
| 2013 | A Material Point Method for Snow Simulation (SIGGRAPH) | Alexey Stomakhin et al. | Simulation | MPM in production (*Frozen*); Stomakhin now co-authors most Wētā FX simulation papers |

## Recent landmarks (newest first)

| Year | Paper | Authors | Area | Why it matters |
| --- | --- | --- | --- | --- |
| 2024 | 2D Gaussian Splatting (SIGGRAPH) / 3D Gaussian Ray Tracing (SIGGRAPH Asia) | Binbin Huang et al. / Nicolas Moënne-Loccoz et al. | Neural rendering | Make splats usable for accurate geometry and ray-traced effects |
| 2023 | 3D Gaussian Splatting for Real-Time Radiance Field Rendering (SIGGRAPH, best paper) | Bernhard Kerbl, Georgios Kopanas, Thomas Leimkühler, George Drettakis | Neural rendering | Real-time photoreal novel-view synthesis; the dominant 3D capture representation today |
| 2022 | Instant Neural Graphics Primitives with a Multiresolution Hash Encoding (SIGGRAPH, best paper) | Thomas Müller, Alex Evans, Christoph Schied, Alexander Keller | Neural rendering | Cut NeRF training from hours to seconds; hash grids used everywhere |
| 2022 | Loki: A Unified Multiphysics Simulation Framework for Production (SIGGRAPH) | Steve Lesser, Alexey Stomakhin et al. (Wētā FX) | Simulation | Coupled water, cloth, hair and fire for *Avatar: The Way of Water* |
| 2021 | A Deep Dive into Nanite Virtualized Geometry (SIGGRAPH course) | Brian Karis et al. (Epic) | Real-time | Film-resolution geometry in real time (Unreal Engine 5) |
| 2020 | NeRF: Representing Scenes as Neural Radiance Fields (ECCV) | Ben Mildenhall, Pratul Srinivasan, Matthew Tancik, Jonathan Barron, Ravi Ramamoorthi, Ren Ng | Neural rendering | Started the neural scene representation wave |
| 2020 | Spatiotemporal Reservoir Resampling (ReSTIR) (SIGGRAPH) | Benedikt Bitterli, Chris Wyman et al. | Real-time | Millions of dynamic lights in real time; basis of path tracing in games |
| 2020 | Incremental Potential Contact (SIGGRAPH) | Minchen Li, Danny Kaufman, Chenfanfu Jiang et al. | Simulation | Guaranteed intersection-free contact for deformables |
| 2020 | Monte Carlo Geometry Processing (SIGGRAPH) | Rohan Sawhney, Keenan Crane | Geometry | Walk on Spheres: solve PDEs without meshing; spawned 2026 best paper work |
| 2018 | Differentiable Monte Carlo Ray Tracing through Edge Sampling (SIGGRAPH Asia) | Tzu-Mao Li, Miika Aittala, Frédo Durand, Jaakko Lehtinen | Inverse rendering | Correct gradients through visibility; start of differentiable rendering |
| 2018 | Manuka: A Batch-Shading Architecture for Spectral Path Tracing in Movie Production (TOG) | Luca Fascione, Johannes Hanika et al. (Wētā) | Production rendering | Spectral path tracing at film scale |
| 2018 | DeepMimic (SIGGRAPH) | Xue Bin Peng, Pieter Abbeel, Sergey Levine, Michiel van de Panne | Animation | Reinforcement learning for physics-based characters |
| 2017 | Phase-Functioned Neural Networks for Character Control (SIGGRAPH) | Daniel Holden, Taku Komura, Jun Saito | Animation | Learned locomotion used in games |
| 2017 | Recurrent Denoising Autoencoder (SIGGRAPH) / Kernel-Predicting Convolutional Networks (SIGGRAPH) | Chakravarty Chaitanya et al. (NVIDIA) / Steve Bako et al. (Pixar, Disney) | Rendering | Neural denoising, now standard in production and real-time path tracing |
| 2016 | A Deep Learning Framework for Character Motion Synthesis and Editing (2026 Test-of-Time) | Daniel Holden, Jun Saito, Taku Komura | Animation | First deep motion manifold |
| 2015 | A Machine Learning Approach for Filtering Monte Carlo Noise (2026 Test-of-Time) | Nima Khademi Kalantari, Steve Bako, Pradeep Sen | Rendering | First learned denoiser |
| 2015 | SMPL: A Skinned Multi-Person Linear Model (SIGGRAPH Asia; 2025 Test-of-Time) | Matthew Loper, Michael Black et al. | Humans | Standard parametric body model |
| 2014 | Hero Wavelength Spectral Sampling (EGSR) | Alexander Wilkie, Johannes Hanika, Andrea Weidlich et al. | Rendering | Efficient spectral rendering, used in Manuka |

## The newest award winners (what is "hot" now)

- **SIGGRAPH 2026 best papers** ([source](https://blog.siggraph.org/2026/05/siggraph-2026-technical-papers-awards-best-papers-honorable-mentions-and-test-of-time.html)): GimmBO (interactive merging of image-generation models; Liu, Ling, Jacobson), Mixwell (sharp 2D fluid brushes; Doug and Ethan James), Walk on Decomposed Subdomains (hybrid Monte Carlo PDE solver; Jambon, Nabizadeh, Konaković Luković), Robust Planar Maps for 3D Vectorization (Fuchs, Crane), Inverse Rendering for Discrete X-Ray CT (Nuic, Zhang, Sager, Jakob).
- **SIGGRAPH 2026 Test-of-Time**: besides the Holden and Kalantari papers above, Convolutional Wasserstein Distances (Solomon et al., 2015) and Intrinsic Images in the Wild (Bell, Bala, Snavely, 2014).
- **SIGGRAPH Asia 2025 best papers** ([source](https://asia.siggraph.org/2025/program/award-winners/)): Fovea Stacking; BSP-OT (sparse optimal transport in log-linear time); Automatic Sampling for Discontinuities in Differentiable Shaders; Control Operators for Interactive Character Animation; Curve-Based Slicer for Multi-Axis DLP 3D Printing.
