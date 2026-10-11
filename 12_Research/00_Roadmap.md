# Computer Graphics Learning Path

Oct 6, 2026 · @Alessandro

A step-by-step checklist from the math you need to reading 2026 SIGGRAPH papers in rendering, simulation, geometry or real-time graphics. Tick items off as you go; each stage ends with a small project and a check for whether you're ready to move on.

## At a glance

&#91;embedded content: learning path · 4 tracks sharing Stages 0, 1, 5 and 7\]

Everyone starts with Stages 0 and 1, then picks a track: rendering (the default, Stages 2–4 and 6), simulation, geometry or real-time. Each track has the same four steps in the same order. Deep learning (Stage 5) can start any time after the math and is needed before each track's bridge papers and recent work; all tracks end in the same reading habit (Stage 7).

## Stage 0 — Math foundations

Goal: be comfortable with the four kinds of math every graphics paper assumes. If you already know some of it, skim the exercises and move on; you can also run this stage alongside Stage 1.

**Linear algebra** (transforms, cameras, solving systems)

- [ ] Watch *Essence of Linear Algebra* by 3Blue1Brown ([link](https://www.3blue1brown.com/topics/linear-algebra)) for intuition
- [ ] Work through MIT 18.06 Linear Algebra (Gilbert Strang, free on [MIT OpenCourseWare](https://ocw.mit.edu/courses/18-06-linear-algebra-spring-2010/)): vectors, matrices, dot/cross products, eigenvectors, least squares

**Multivariable calculus** (integrals over surfaces and directions)

- [ ] Watch *Essence of Calculus* by 3Blue1Brown ([link](https://www.3blue1brown.com/topics/calculus))
- [ ] Work through MIT 18.02 Multivariable Calculus ([MIT OpenCourseWare](https://ocw.mit.edu/courses/18-02-multivariable-calculus-fall-2007/)): partial derivatives, gradients, double/triple integrals, change of variables, spherical coordinates

**Probability** (the basis of Monte Carlo rendering)

- [ ] Harvard Stat 110 with Joe Blitzstein (lectures and free book, [link](https://projects.iq.harvard.edu/stat110)): random variables, probability density functions, expectation, variance

**Numerical methods and optimization** (simulation, geometry, learning)

- [ ] Read chapters 1–4, 9 and 11 of Justin Solomon's *Numerical Algorithms* (free [PDF](https://people.csail.mit.edu/jsolomon/share/book/numerical_book.pdf)): floating point, linear solvers, least squares, gradient descent, conjugate gradients
- [ ] Later, as needed: chapters 14–16 (numerical integration, ODEs, PDEs) before simulation papers

**You're ready when** you can compute the gradient of a function of three variables, convert an integral to spherical coordinates, and explain what the expected value and variance of a random variable are.

## Stage 1 — Graphics fundamentals

Goal: know the whole pipeline at an introductory level: transforms, cameras, rasterization, ray tracing, shading, textures, meshes and basic animation.

- [ ] Follow one full course: CMU 15-462 *Computer Graphics* by Keenan Crane (lecture videos free on YouTube; course materials linked from [his site](https://www.cs.cmu.edu/~kmcrane/))
- [ ] Read alongside it: *Fundamentals of Computer Graphics* (Marschner & Shirley), the standard undergraduate textbook
- [ ] Optional free reference for any topic you get stuck on: [Scratchapixel](https://www.scratchapixel.com/)
- [ ] **Project:** build a ray tracer with [*Ray Tracing in One Weekend*](https://raytracing.github.io/) (book 1), then book 2 (*The Next Week*)
- [ ] **Project:** write a tiny software rasterizer (draw triangles with a z-buffer and simple Phong shading), so you understand what a GPU does

**You're ready when** you can explain the difference between rasterization and ray tracing, derive a camera's view and projection matrices, and your ray tracer renders spheres with reflections and soft shadows.

## Stage 2 — Rendering theory

Goal: learn the three things the key papers assume (radiometry, the BRDF and Monte Carlo integration) and use them in your own renderer.

- [ ] Read *Ray Tracing: The Rest of Your Life* ([raytracing.github.io](https://raytracing.github.io/), book 3): probability densities and importance sampling explained through code
- [ ] Read the Monte Carlo integration chapter of [*PBRT*, 4th edition](https://pbr-book.org/) (free online)
- [ ] Read the radiometry chapter of *PBRT*: solid angle, flux, irradiance, radiance
- [ ] Read the reflection models chapter of *PBRT*: BRDFs, Fresnel, microfacet models
- [ ] Read Veach's thesis, chapter 2 (Monte Carlo integration) and chapter 3 (radiometry and light transport), free on the [Stanford page](https://graphics.stanford.edu/papers/veach_thesis/)
- [ ] Read Naty Hoffman's "Background: Physics and Math of Shading" from the SIGGRAPH *Physically Based Shading* course notes ([Self Shadow publications](https://blog.selfshadow.com/publications/))
- [ ] **Project:** turn your ray tracer into a path tracer with area lights, a microfacet (GGX) material and importance sampling
- [ ] **Project:** render the same scene in [Mitsuba 3](https://www.mitsuba-renderer.org/) and compare images to check your renderer is correct

**You're ready when** you can explain why radiance stays constant along a ray, write the Monte Carlo estimator for an integral, and show why importance sampling reduces noise.

## Stage 3 — The three key papers

Goal: read the three papers that define physically based rendering. Together they give you the material model, the problem, and the method for solving it. All are free in the ACM Digital Library.

1. **Cook & Torrance, "A Reflectance Model for Computer Graphics" (ACM TOG, 1982)**
   - [ ] Prep: Hoffman's shading notes (Stage 2), Fresnel equations, the half vector
   - [ ] Read the paper
   - [ ] Follow-up: Walter et al., "Microfacet Models for Refraction through Rough Surfaces" (EGSR 2007), which introduced GGX
2. **Kajiya, "The Rendering Equation" (SIGGRAPH 1986)**
   - [ ] Prep: the light-transport chapter of *PBRT*, which states the same equation in modern notation
   - [ ] Read the paper; map each of its terms onto the *PBRT* version
3. **Veach & Guibas, "Optimally Combining Sampling Techniques for Monte Carlo Rendering" (SIGGRAPH 1995)**
   - [ ] Prep: importance sampling (Stage 2)
   - [ ] Read the paper, then chapter 9 of Veach's thesis, which expands it

- [ ] **Project:** add multiple importance sampling (light sampling + BRDF sampling, balance heuristic) to your path tracer and reproduce Veach's glossy-highlights test scene: four plates of different roughness lit by four lights of different sizes

**You're ready when** your MIS renders are less noisy than either strategy alone and you can explain in one sentence what each paper contributed.

## Stage 4 — Bridge papers (2001–2018)

Goal: fill the gap between the classics and today. Each paper below is a direct ancestor of a technique in Stage 6; the note says which.

- [ ] **Zwicker, Pfister, van Baar, Gross — "Surface Splatting" (SIGGRAPH 2001) / "EWA Volume Splatting" (IEEE Vis 2001).** Rendering with projected Gaussians; the math inside 3D Gaussian Splatting
- [ ] **Talbot, Cline, Egbert — "Importance Resampling for Global Illumination" (EGSR 2005).** Resampled importance sampling; the core of ReSTIR
- [ ] **Burley — "Physically-Based Shading at Disney" (SIGGRAPH 2012 course).** The principled BRDF used across film and game engines
- [ ] **Heitz — "Understanding the Masking-Shadowing Function in Microfacet-Based BRDFs" (JCGT 2014).** The clearest modern explanation of microfacet theory; free
- [ ] **Wilkie, Nawaz, Droske, Weidlich, Hanika — "Hero Wavelength Spectral Sampling" (EGSR 2014).** Efficient spectral rendering, used in Wētā's Manuka
- [ ] **Kalantari, Bako, Sen — "A Machine Learning Approach for Filtering Monte Carlo Noise" (SIGGRAPH 2015)** and **Bako et al. — "Kernel-Predicting Convolutional Networks" (SIGGRAPH 2017).** Learned denoising; needs Stage 5 basics
- [ ] **Müller, Gross, Novák — "Practical Path Guiding" (EGSR 2017).** Learning where light comes from during rendering; leads to neural radiance caching
- [ ] **Fascione, Hanika et al. — "Manuka: A Batch-Shading Architecture for Spectral Path Tracing in Movie Production" (ACM TOG 2018).** How a production renderer at Wētā puts all of this together
- [ ] **Li, Aittala, Durand, Lehtinen — "Differentiable Monte Carlo Ray Tracing through Edge Sampling" (SIGGRAPH Asia 2018).** Start of differentiable rendering

Read these with the three-pass method from Stage 7: you don't need every derivation, just what each paper changes and why.

**You're ready when** you can name, for each Stage 6 paper, which earlier idea it builds on.

## Stage 5 — Deep learning basics for graphics

Goal: understand the learning tools used in about half of recent papers. This stage is independent of Stages 2–4, so you can run it in parallel once Stage 0 is done.

- [ ] Andrej Karpathy, [*Neural Networks: Zero to Hero*](https://karpathy.ai/zero-to-hero.html), first four videos: backpropagation and autodiff built from scratch (micrograd), MLPs, training and debugging networks
- [ ] [*Dive into Deep Learning*](https://d2l.ai/) (free book with code), chapters on convolutional networks and optimization
- [ ] Lilian Weng, ["What are Diffusion Models?"](https://lilianweng.github.io/posts/2021-07-11-diffusion-models/), the standard overview of how image generators work
- [ ] Read Tancik et al., "Fourier Features Let Networks Learn High Frequency Functions in Low Dimensional Domains" (NeurIPS 2020): why NeRF needs positional encoding
- [ ] **Project:** in PyTorch, train a small MLP to reproduce a single image from pixel coordinates, first without and then with Fourier features. This is a neural field, the core idea behind NeRF
- [ ] **Project (optional):** follow a Mitsuba 3 inverse-rendering tutorial to recover a material from an image using gradients

**You're ready when** you can explain what backpropagation computes, why the image-fitting MLP is blurry without Fourier features, and what a diffusion model learns to do.

## Stage 6 — Recent landmarks

Goal: read the papers that define rendering today. There are two threads; do them in either order.

**Thread A — Real-time path tracing**

- [ ] Prep: "A Gentle Introduction to ReSTIR" (SIGGRAPH 2023 course notes, Wyman et al.)
- [ ] Bitterli et al., "Spatiotemporal Reservoir Resampling for Real-Time Ray Tracing with Dynamic Direct Lighting" (SIGGRAPH 2020), ReSTIR
- [ ] Ouyang et al., "ReSTIR GI: Path Resampling for Real-Time Path Tracing" (HPG 2021)
- [ ] Müller et al., "Real-time Neural Radiance Caching for Path Tracing" (SIGGRAPH 2021)
- [ ] Karis et al., "A Deep Dive into Nanite Virtualized Geometry" (SIGGRAPH 2021 Advances in Real-Time Rendering course)
- [ ] **Project:** add a simple ReSTIR direct-lighting pass with many lights to your renderer, or study an open-source implementation

**Thread B — Neural rendering**

- [ ] Mildenhall et al., "NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis" (ECCV 2020)
- [ ] Barron et al., "Mip-NeRF" (ICCV 2021): anti-aliasing for neural fields
- [ ] Müller, Evans, Schied, Keller, "Instant Neural Graphics Primitives with a Multiresolution Hash Encoding" (SIGGRAPH 2022)
- [ ] Kerbl, Kopanas, Leimkühler, Drettakis, "3D Gaussian Splatting for Real-Time Radiance Field Rendering" (SIGGRAPH 2023)
- [ ] Huang et al., "2D Gaussian Splatting" (SIGGRAPH 2024) and Moënne-Loccoz et al., "3D Gaussian Ray Tracing" (SIGGRAPH Asia 2024)
- [ ] **Project:** capture a scene with your phone and train a Gaussian splat with an open-source library (for example nerfstudio or gsplat); then read the rasterizer code and match it to the EWA math from Stage 4

**You're ready when** you can read the SIGGRAPH 2026 best paper "Inverse Rendering for Discrete X-Ray Computed Tomography" (Nuic, Zhang, Sager, Jakob) or the honorable mention "Spatio-Temporal Control Variates with ReSTIR for Real-Time Rendering" and understand what they change.

## Stage 7 — Staying current and reading papers well

Goal: turn reading papers into a habit you can keep up with.

**How to read a paper** (S. Keshav's three-pass method, from "How to Read a Paper", ACM SIGCOMM CCR 2007)

1. First pass, about 10 minutes: title, abstract, introduction, figures, conclusion. Decide whether to keep going.
2. Second pass, about an hour: read everything but skip proofs; note what is new compared with the papers it cites.
3. Third pass, several hours: re-derive the key equations or reimplement the core idea.

**Routine**

- [ ] Weekly: read [Graphics Programming weekly](https://www.jendrikillner.com/tags/weekly/) and pick one paper for a first pass
- [ ] Each July and December: skim the SIGGRAPH and SIGGRAPH Asia lists on [Ke-Sen Huang's page](https://www.realtimerendering.com/kesen/) and the award posts on the [ACM SIGGRAPH blog](https://blog.siggraph.org/)
- [ ] Each month: browse [arXiv cs.GR](https://arxiv.org/list/cs.GR/recent) for preprints in your area
- [ ] Each quarter: do a third pass on one paper, ideally reimplementing its core result in your renderer
- [ ] Keep a reading log (title, one-sentence contribution, which earlier paper it builds on); this becomes your related-work section later

For more sources, see section 4 of your Computer Graphics Research Guide.

## Other tracks

Simulation, geometry and real-time rendering each replace Stages 2, 3, 4 and 6 with their own versions; Stages 0, 1, 5 and 7 are shared by every track. The numbers keep the same meaning everywhere:

| Step | Role | Rendering | Simulation | Geometry | Real-time |
| --- | --- | --- | --- | --- | --- |
| 2 | Foundations: textbook, notes, first project | Stage 2 | S2 | G2 | R2 |
| 3 | Key papers: the three to read closely | Stage 3 | S3 | G3 | R3 |
| 4 | Bridge papers that connect the classics to today | Stage 4 | S4 | G4 | R4 |
| 5 | Deep learning (shared) | Stage 5 | Stage 5 | Stage 5 | Stage 5 |
| 6 | Recent work, ending at a SIGGRAPH 2026 paper | Stage 6 | S6 | G6 | R6 |

Pick one track to go deep in first; the others are much faster once you have finished one, because the math and reading habits carry over.

## Simulation track (fluids, cloth, VFX)

This is the track behind Wētā's water, fire and cloth work. It leans hardest on Solomon's numerical chapters from Stage 0.

### S2 — Simulation foundations

Goal: understand time integration, linear solvers and the grid/particle view of fluids.

- [ ] Read chapters 11 and 14–16 of Solomon's *Numerical Algorithms* (iterative solvers, numerical differentiation, ODEs, PDEs)
- [ ] Read Witkin & Baraff, *Physically Based Modeling* (SIGGRAPH 2001 course notes, freely available online): particles, rigid bodies, implicit integration, constraints
- [ ] Read Robert Bridson, *Fluid Simulation for Computer Graphics* (2nd ed.): advection, pressure projection, level sets, FLIP
- [ ] Read Kim & Eberle, [*Dynamic Deformables: Implementation and Production Practicalities*](https://www.tkim.graphics/DYNAMIC_DEFORMABLES/) (SIGGRAPH 2020/2022 course, Pixar; free notes and C++ code)
- [ ] **Project:** a mass-spring cloth, first with explicit Euler (watch it explode with stiff springs), then with implicit Euler and conjugate gradients
- [ ] **Project:** a 2D grid smoke solver: semi-Lagrangian advection plus pressure projection

**You're ready when** you can explain the CFL condition, why implicit integration is stable for stiff systems, and what pressure projection enforces.

### S3 — Three key simulation papers

1. **Baraff & Witkin, "Large Steps in Cloth Simulation" (SIGGRAPH 1998)**
   - [ ] Prep: the implicit-methods section of the Witkin & Baraff notes
   - [ ] Read the paper; it made implicit cloth practical and is still the template for production cloth solvers
2. **Stam, "Stable Fluids" (SIGGRAPH 1999)**
   - [ ] Prep: Bridson's chapters on advection and projection
   - [ ] Read the paper and compare it with your smoke solver
3. **Zhu & Bridson, "Animating Sand as a Fluid" (SIGGRAPH 2005)**
   - [ ] Prep: Bridson's particle chapter
   - [ ] Read the paper; its FLIP method is how most film water is simulated

- [ ] **Project:** a 2D FLIP liquid with a free surface, splashing in a box

**You're ready when** your liquid splashes without visible volume loss and you can explain why FLIP is less dissipative than a pure grid method.

### S4 — Bridge papers (2001–2018)

- [ ] **Fedkiw, Stam, Jensen — "Visual Simulation of Smoke" (SIGGRAPH 2001).** Vorticity confinement to keep smoke detailed
- [ ] **Foster & Fedkiw — "Practical Animation of Liquids" (SIGGRAPH 2001).** Particle level sets for liquid surfaces
- [ ] **Bridson, Fedkiw, Anderson — "Robust Treatment of Collisions, Contact and Friction for Cloth Animation" (SIGGRAPH 2002).** The collision handling most cloth solvers build on
- [ ] **Müller et al. — "Position Based Dynamics" (2006/2007).** Fast, stable constraint-based simulation for games
- [ ] **Bergou et al. — "Discrete Elastic Rods" (SIGGRAPH 2008).** The standard model for hair and threads
- [ ] **Museth — "VDB: High-Resolution Sparse Volumes with Dynamic Topology" (ACM TOG 2013).** The data structure behind OpenVDB, used across VFX
- [ ] **Stomakhin et al. — "A Material Point Method for Snow Simulation" (SIGGRAPH 2013).** MPM in production (*Frozen*); follow with the SIGGRAPH 2016 MPM course notes (Jiang et al.)
- [ ] **Bouaziz et al. — "Projective Dynamics" (SIGGRAPH 2014)** and **Macklin, Müller, Chentanez — "XPBD" (MIG 2016).** Fast implicit-style solvers
- [ ] **Smith, de Goes, Kim — "Stable Neo-Hookean Flesh Simulation" (ACM TOG 2018).** Robust soft bodies for characters (Pixar)

**You're ready when** you can say, for any production simulation paper, whether it is grid-based, particle-based or hybrid, and which integrator it uses.

### S6 — Recent simulation work

- [ ] Li et al., "Incremental Potential Contact" (SIGGRAPH 2020): guaranteed intersection-free contact
- [ ] Sanchez-Gonzalez et al., "Learning to Simulate Complex Physics with Graph Networks" (ICML 2020): learned simulators (needs Stage 5)
- [ ] Lesser et al., "Loki: A Unified Multiphysics Simulation Framework for Production" (SIGGRAPH 2022, Wētā FX)
- [ ] Wretborn, Stomakhin, Batty, "A Unified Multi-scale Method for Simulating Immersed Bubbles" (Eurographics 2025, Wētā FX)
- [ ] Wretborn et al., "A Practical Partitioner for Distributed Simulations on Sparse Dynamic Domains using Optimal Transport" (ACM TOG 2026, Wētā FX)
- [ ] Doug James & Ethan James, "Mixwell: Sharp 2D Fluid Brushes for Progressive Physics-Based Mixing" (SIGGRAPH 2026 best paper)
- [ ] **Project:** write a 2D MPM simulation with a GPU-friendly Python framework (for example Taichi or NVIDIA Warp), then add a second material and watch them interact

**You're ready when** you can read the SIGGRAPH 2026 honorable mention "Spatiotemporal FLIP for Fast Free-Surface and Two-Phase Simulation With Very Large Time Steps" (Braun, Winchenbach, Bender, Thuerey) and explain what it changes about FLIP.

## Geometry track (meshes, shape, PDEs on surfaces)

This track is about representing and processing shape: meshes, point clouds, implicit surfaces and the PDEs that live on them. It leans on linear algebra (eigenvectors, sparse solvers) more than any other track.

### G2 — Geometry foundations

Goal: understand meshes as discrete surfaces and the Laplacian as the tool behind most of geometry processing.

- [ ] Read chapters 4–7 and 10 of Solomon's *Numerical Algorithms* (least squares, sparse systems, eigenvectors, SVD, constrained optimization)
- [ ] Follow Keenan Crane's *Discrete Differential Geometry* course (CMU 15-458; notes and lecture videos free, via [his site](https://www.cs.cmu.edu/~kmcrane/)): exterior calculus, curvature, the cotangent Laplacian
- [ ] Read Botsch, Kobbelt, Pauly, Alliez, Lévy, *Polygon Mesh Processing*: data structures, smoothing, parameterization, remeshing, simplification
- [ ] Work through the [libigl tutorial](https://libigl.github.io/tutorial/) and set up [Polyscope](https://polyscope.run/) for visualizing meshes
- [ ] **Project:** load a mesh, compute vertex normals, Gaussian and mean curvature, and the cotangent Laplacian; run Laplacian smoothing and visualize each result

**You're ready when** you can explain the half-edge data structure, derive the cotangent formula, and say why the Laplacian's eigenvectors behave like a Fourier basis on a surface.

### G3 — Three key geometry papers

1. **Garland & Heckbert, "Surface Simplification Using Quadric Error Metrics" (SIGGRAPH 1997)**
   - [ ] Prep: Botsch et al.'s simplification chapter
   - [ ] Read the paper; it is still the standard simplification method, including inside level-of-detail systems such as Nanite
2. **Desbrun, Meyer, Schröder, Barr, "Implicit Fairing of Irregular Meshes using Diffusion and Curvature Flow" (SIGGRAPH 1999)**
   - [ ] Prep: Crane's notes on the Laplacian and curvature
   - [ ] Read the paper; it brought the cotangent Laplacian and implicit time-stepping into graphics
3. **Kazhdan, Bolitho, Hoppe, "Poisson Surface Reconstruction" (SGP 2006)**
   - [ ] Prep: Poisson equations in Solomon chapter 16
   - [ ] Read the paper; it turns scanned point clouds into watertight meshes

- [ ] **Project:** implement quadric-error simplification and implicit Laplacian smoothing; run Poisson reconstruction (via a library) on a scanned point cloud

**You're ready when** your simplifier reduces a mesh to 5% of its triangles while keeping its silhouette, and you can explain why implicit smoothing allows large time steps.

### G4 — Bridge papers (1996–2019)

- [ ] **Hoppe — "Progressive Meshes" (SIGGRAPH 1996).** Continuous level of detail
- [ ] **Lévy et al. — "Least Squares Conformal Maps for Automatic Texture Atlas Generation" (SIGGRAPH 2002).** UV unwrapping, still used in modeling tools
- [ ] **Sorkine & Alexa — "As-Rigid-As-Possible Surface Modeling" (SGP 2007).** Shape deformation by local rigidity
- [ ] **Ovsjanikov et al. — "Functional Maps" (SIGGRAPH 2012).** Shape correspondence using Laplacian eigenbases
- [ ] **Crane, Weischedel, Wardetzky — "Geodesics in Heat" (ACM TOG 2013).** Distances on surfaces from one heat-flow solve
- [ ] **Jacobson, Kavan, Sorkine-Hornung — "Robust Inside-Outside Segmentation using Generalized Winding Numbers" (SIGGRAPH 2013).** Inside/outside tests for messy, broken meshes
- [ ] **Solomon et al. — "Convolutional Wasserstein Distances" (SIGGRAPH 2015; 2026 Test-of-Time).** Optimal transport on images and meshes
- [ ] **Hu et al. — "Tetrahedral Meshing in the Wild" (SIGGRAPH 2018).** Robust volume meshing for simulation
- [ ] **Park et al. — "DeepSDF" (CVPR 2019).** Shapes as neural signed distance functions (needs Stage 5)

**You're ready when** you can say, for a new geometry paper, which representation it uses (mesh, point cloud, implicit, neural) and which operator or energy it optimizes.

### G6 — Recent geometry work

- [ ] Sawhney & Crane, "Monte Carlo Geometry Processing: A Grid-Free Approach to PDE-Based Methods on Volumetric Domains" (SIGGRAPH 2020): Walk on Spheres
- [ ] Sawhney, Miller, Gkioulekas, Crane, "Walk on Stars: A Grid-Free Monte Carlo Method for PDEs with Neumann Boundary Conditions" (SIGGRAPH 2023)
- [ ] Fuchs & Crane, "Robust Planar Maps for 3D Vectorization" (SIGGRAPH 2026 best paper)
- [ ] Genest & Coeurjolly, "Uncertainty-Aware Geometry Processing on Gaussian Process Implicit Surfaces" (SIGGRAPH 2026 honorable mention)
- [ ] Corman, Soliman, Magnet, Gillespie, "Implicit Minimal Surfaces for Bijective Correspondences" (SIGGRAPH 2026 honorable mention)
- [ ] "BSP-OT: Sparse transport plans between discrete measures in loglinear time" (SIGGRAPH Asia 2025 best paper)
- [ ] **Project:** implement Walk on Spheres to solve the Laplace equation inside a 2D shape, and compare it with a finite-element solution from libigl

**You're ready when** you can read the SIGGRAPH 2026 best paper "Walk on Decomposed Subdomains: A Hybrid Monte Carlo-Deterministic Solver for Elliptic PDEs" (Jambon, Nabizadeh, Konaković Luković) and explain what it combines.

## Real-time track (games, GPUs)

This track is about making images in a few milliseconds per frame. Much of its best material is in talks and course slides rather than papers, so the "papers" below include SIGGRAPH course talks.

### R2 — Real-time foundations

Goal: understand the GPU pipeline, a modern graphics API and physically based shading under a frame budget.

- [ ] Read Fabian Giesen's blog series "A trip through the Graphics Pipeline 2011": what the GPU actually does, stage by stage
- [ ] Work through [LearnOpenGL](https://learnopengl.com/) up to and including the PBR and image-based lighting chapters
- [ ] Read *Real-Time Rendering* (4th ed., Akenine-Möller et al.), especially the chapters on the pipeline, shading, shadows, global illumination and acceleration
- [ ] Learn one explicit API (Vulkan or Direct3D 12) with a tutorial such as *Vulkan Guide* (vkguide.dev)
- [ ] Learn to profile a frame with RenderDoc and your GPU vendor's profiler
- [ ] **Project:** a deferred renderer with GGX materials, image-based lighting and tone mapping, holding 60 fps on a test scene

**You're ready when** you can explain what a draw call costs, why deferred shading helps with many lights, and how a GPU runs shaders in groups (warps/waves).

### R3 — Three key real-time papers and talks

1. **Williams, "Casting Curved Shadows on Curved Surfaces" (SIGGRAPH 1978)**
   - [ ] Prep: the shadows chapter of *Real-Time Rendering*
   - [ ] Read the paper; it introduced shadow mapping, still the main real-time shadow technique
2. **Saito & Takahashi, "Comprehensible Rendering of 3-D Shapes" (SIGGRAPH 1990)**
   - [ ] Read the paper; its G-buffer is the idea behind deferred shading in nearly every engine
3. **Karis, "Real Shading in Unreal Engine 4" (SIGGRAPH 2013 Physically Based Shading course)**
   - [ ] Prep: Stage 3's Cook–Torrance paper and Hoffman's shading notes (Stage 2)
   - [ ] Read the notes; the split-sum approximation for image-based lighting became an industry standard

- [ ] **Project:** add cascaded shadow maps with filtering and split-sum image-based lighting to your renderer

**You're ready when** your renderer has stable, soft-edged shadows across a large scene and you can derive the split-sum approximation.

### R4 — Bridge papers and talks (2006–2020)

- [ ] **Donnelly & Lauritzen — "Variance Shadow Maps" (I3D 2006).** Filterable shadows
- [ ] **Mittring — "Finding Next Gen: CryEngine 2" (SIGGRAPH 2007 course).** Introduced screen-space ambient occlusion
- [ ] **Olsson, Billeter, Assarsson — "Clustered Deferred and Forward Shading" (HPG 2012).** Thousands of lights per frame
- [ ] **Lagarde & de Rousiers — "Moving Frostbite to Physically Based Rendering" (SIGGRAPH 2014 course).** A full engine's move to PBR, in detail
- [ ] **Karis — "High-Quality Temporal Supersampling" (SIGGRAPH 2014 Advances in Real-Time Rendering).** Temporal anti-aliasing, the base of modern upscalers
- [ ] **Hillaire — "Physically Based and Unified Volumetric Rendering in Frostbite" (SIGGRAPH 2015 Advances).** Real-time fog and volumes
- [ ] **Heitz et al. — "Real-Time Polygonal-Light Shading with Linearly Transformed Cosines" (SIGGRAPH 2016).** Area lights in real time
- [ ] **Schied et al. — "Spatiotemporal Variance-Guided Filtering" (HPG 2017).** Denoising for real-time ray tracing
- [ ] **Hillaire — "A Scalable and Production Ready Sky and Atmosphere Rendering Technique" (EGSR 2020).** Physically based skies used in Unreal Engine

**You're ready when** you can explain, for any engine feature in a GDC or Advances talk, which of these techniques it builds on and what it trades for speed.

### R6 — Recent real-time work

- [ ] Bitterli et al., "Spatiotemporal Reservoir Resampling" (SIGGRAPH 2020), ReSTIR
- [ ] Müller et al., "Real-time Neural Radiance Caching for Path Tracing" (SIGGRAPH 2021)
- [ ] Karis et al., "A Deep Dive into Nanite Virtualized Geometry" (SIGGRAPH 2021 Advances)
- [ ] Wright, Narkowicz, Kelly, "Lumen: Real-time Global Illumination in Unreal Engine 5" (SIGGRAPH 2022 Advances)
- [ ] Zeltner et al., "Real-Time Neural Appearance Models" (ACM TOG 2024, NVIDIA): neural materials (needs Stage 5)
- [ ] Browse the latest [Advances in Real-Time Rendering](https://advances.realtimerendering.com/) course and the I3D 2026 and HPG papers on [Ke-Sen Huang's page](https://www.realtimerendering.com/kesen/)
- [ ] **Project:** add hardware ray-traced shadows or ReSTIR direct lighting with a denoiser to your Vulkan/D3D12 renderer, or build a meshlet renderer with GPU culling

**You're ready when** you can read the SIGGRAPH 2026 honorable mention "Spatio-Temporal Control Variates with ReSTIR for Real-Time Rendering" (Shi, Wu, Wu, Xu) and explain what it adds to ReSTIR.

## Sources

Pages opened to confirm free access and contents:

- [Numerical Algorithms](https://people.csail.mit.edu/jsolomon/share/book/numerical_book.pdf), Justin Solomon (full book PDF)
- [Robust Monte Carlo Methods for Light Transport Simulation](https://graphics.stanford.edu/papers/veach_thesis/), Eric Veach's thesis (chapters 2, 3 and 9 used here)
- [Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html), Andrej Karpathy
- [SIGGRAPH 2026 Technical Papers Awards](https://blog.siggraph.org/2026/05/siggraph-2026-technical-papers-awards-best-papers-honorable-mentions-and-test-of-time.html) (2026 papers named in Stage 6 and the branches)
- [Ke-Sen Huang's paper lists](https://www.realtimerendering.com/kesen/)

* [Dynamic Deformables: Implementation and Production Practicalities](https://www.tkim.graphics/DYNAMIC_DEFORMABLES/), Kim & Eberle (simulation track)
* [Wētā FX Key Publications](https://www.wetafx.co.nz/research-and-tech/key-publications) (Wētā simulation papers in S6)
* [SIGGRAPH Asia 2025 award winners](https://asia.siggraph.org/2025/program/award-winners/) (BSP-OT in G6)

All ACM papers (SIGGRAPH, TOG, HPG, I3D) are free to read in the ACM Digital Library since January 2026. Paper years and venues are from standard references; confirm exact citations there before citing them in your assignment.
