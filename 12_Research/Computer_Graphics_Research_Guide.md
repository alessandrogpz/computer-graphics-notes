# Computer Graphics Research Guide

Oct 6, 2026 · @Alessandro

Computer graphics research is concentrated in one flagship venue (ACM SIGGRAPH / SIGGRAPH Asia, published in ACM Transactions on Graphics) and a handful of specialist conferences, with a strong industry track (film VFX and game studios) alongside academia. This guide answers the three questions in order: venues and authors, important papers, then candidate research questions to pick from. The last section lists sources that work like the Wētā FX publication page and Jendrik Illner's weekly roundup, so you can keep up after the assignment.

## 1a. Most relevant publication venues

ACM SIGGRAPH is the top venue: SIGGRAPH 2026 (Los Angeles, 19–23 July) drew more than 1,120 technical paper submissions, the most in its 53 years ([SIGGRAPH blog](https://blog.siggraph.org/2026/05/siggraph-2026-technical-papers-awards-best-papers-honorable-mentions-and-test-of-time.html)). It accepted 132 journal and 195 conference papers, with an 11.2% journal-track acceptance rate ([Ke-Sen Huang](https://www.realtimerendering.com/kesen/)). Journal-track papers from SIGGRAPH and SIGGRAPH Asia appear in ACM Transactions on Graphics (TOG), so "published in TOG" is the field's main quality signal.

| Venue | Focus | Tier | Published in | Next / recent edition |
| --- | --- | --- | --- | --- |
| [ACM SIGGRAPH](https://s2026.siggraph.org/) | Everything: rendering, geometry, animation, simulation, imaging, generative AI | Flagship | ACM TOG (journal track) + Conference Proceedings | SIGGRAPH 2027, Anaheim, 8–12 Aug 2027 |
| [SIGGRAPH Asia](https://asia.siggraph.org/2026/) | Same scope as SIGGRAPH | Flagship | ACM TOG + Conference Proceedings | Kuala Lumpur, 1–4 Dec 2026 |
| ACM Transactions on Graphics (TOG) | All of graphics; also accepts direct journal submissions | Top journal | ACM | Continuous |
| Eurographics (EG) | All of graphics, Europe's main conference | Top tier | Computer Graphics Forum (CGF) | Annual, spring |
| Computer Graphics Forum (CGF) | Journal for EG, EGSR, SGP, SCA, Pacific Graphics, HPG | Top journal | Wiley / Eurographics | Continuous |
| EGSR (Eurographics Symposium on Rendering) | Light transport, materials, real-time and offline rendering | Top specialist | CGF + proceedings | Annual, summer |
| HPG (High-Performance Graphics) | GPUs, ray tracing hardware/algorithms, real-time performance | Top specialist | CGF / PACMCGIT | Annual, co-located with SIGGRAPH or EGSR |
| I3D (ACM Symposium on Interactive 3D Graphics and Games) | Real-time rendering, games | Specialist | PACMCGIT | Annual, spring |
| SGP (Symposium on Geometry Processing) | Meshes, shape analysis, geometric optimization | Top specialist | CGF | Annual, summer |
| SCA (Symposium on Computer Animation) | Physics simulation, character animation | Top specialist | CGF / PACMCGIT | Annual |
| Pacific Graphics | General graphics, Asia-Pacific | Strong | CGF | Annual, autumn |
| IEEE TVCG + IEEE VIS | Visualization, VR/AR | Top in its area | IEEE | VIS annual, autumn |
| CVPR / ICCV / ECCV, NeurIPS | Neural rendering, 3D reconstruction, generative 3D (now heavily overlapping with graphics) | Top (vision/ML) | IEEE/CVF, NeurIPS | Annual |
| [JCGT](https://jcgt.org/) (Journal of Computer Graphics Techniques) | Practical, implementable techniques, open access | Practitioner journal | Open access | Continuous |
| DigiPro (Digital Production Symposium) | Film/VFX production technology | Industry | ACM | Annual, before SIGGRAPH |

Industry venues matter as much as papers for production graphics. The key ones are SIGGRAPH Courses (notably "Advances in Real-Time Rendering in Games" and "Physically Based Shading in Theory and Practice"), SIGGRAPH Talks and Production Sessions, GDC (Game Developers Conference) and Digital Dragons. Wētā FX, Pixar, Disney Research, ILM and the game studios publish much of their work there rather than in TOG.

## 1b. Most relevant authors and research groups

The most influential people are best found per subfield, since graphics is split into rendering, geometry, animation/simulation and neural/3D-vision communities that rarely overlap. The names below recur across SIGGRAPH best papers, Test-of-Time awards and standard textbooks; affiliations are from memory and people move, so confirm on Google Scholar or [DBLP](https://dblp.org/) before citing.

| Subfield | Key authors (affiliation) | Known for |
| --- | --- | --- |
| Physically based rendering | Wenzel Jakob (EPFL), Matt Pharr (NVIDIA), Ravi Ramamoorthi (UC San Diego), Kavita Bala (Cornell), Wojciech Jarosz (Dartmouth), Henrik Wann Jensen | Mitsuba renderer and *PBRT* book; light transport theory; photon mapping; volumetric rendering |
| Differentiable and inverse rendering | Tzu-Mao Li (UC San Diego), Shuang Zhao, Wenzel Jakob, Kun Xu (Tsinghua) | Differentiable path tracing; Monte Carlo PDE solvers; 2026 best paper on inverse rendering for CT |
| Real-time rendering (industry) | Brian Karis (Epic, Nanite), Tomas Akenine-Möller and Chris Wyman (NVIDIA), Naty Hoffman, Sebastien Hillaire, Eric Heitz | Virtualized geometry; ReSTIR-era real-time path tracing; physically based shading in games; *Real-Time Rendering* book |
| Neural rendering and graphics | Thomas Müller and Jan Novák (NVIDIA), Jon Barron and Ben Mildenhall (NeRF), George Drettakis and Bernhard Kerbl (Inria), Gordon Wetzstein (Stanford), Christian Theobalt (MPI Informatics) | Instant-NGP; NeRF; 3D Gaussian Splatting; neural fields and displays |
| Geometry processing | Keenan Crane (CMU), Alec Jacobson (Toronto), Olga Sorkine-Hornung (ETH Zürich), Daniele Panozzo (NYU), Justin Solomon (MIT), Mirela Ben-Chen (Technion) | Discrete differential geometry; libigl; robust meshing; optimal transport; Walk on Spheres |
| Physics simulation | Doug James (Stanford), Robert Bridson (UBC), Ron Fedkiw (Stanford), Chenfanfu Jiang (UCLA), Matthias Müller and Miles Macklin (NVIDIA), Jan Bender (RWTH Aachen), Nils Thuerey (TU Munich), Christopher Batty (Waterloo) | Fluids (FLIP), MPM (snow in *Frozen*), position-based dynamics, sound synthesis, differentiable simulation |
| Character animation | Taku Komura (HKU), Daniel Holden (Epic), Xue Bin (Jason) Peng (SFU / NVIDIA), Michiel van de Panne (UBC) | Learned motion synthesis (2026 Test-of-Time); phase-functioned networks; physics-based character control (DeepMimic, AMP) |
| Imaging and appearance capture | Noah Snavely (Cornell / Google), Abhijeet Ghosh (Imperial), Paul Debevec, Pradeep Sen (UCSB) | Photo tourism; light-stage capture; image-based lighting; learned denoising |

**Industry labs to follow.** NVIDIA Research, Adobe Research, Disney Research Studios (Zürich), Pixar Research, Wētā FX, Meta Reality Labs Research, Google Research/DeepMind, Epic Games, EA SEED, Ubisoft La Forge, Activision Research. At Wētā FX the recurring names are Johannes Hanika, Luca Fascione, Andrea Weidlich and Jiří Vorba (Manuka spectral path tracer, path guiding) and Alexey Stomakhin and Joel Wretborn (Loki multiphysics, water and bubbles).

**Groups to know.** Use [CSRankings](https://csrankings.org/) with only "Computer graphics" ticked to see which universities publish most at SIGGRAPH/SIGGRAPH Asia; recurring leaders include Stanford, CMU, MIT, Toronto, ETH Zürich, EPFL, Tsinghua, Inria, MPI Informatics, TU Munich and UC San Diego.

## 2. Most important papers

The papers below are the ones most often cited as turning points: the foundations every graphics course teaches, then the recent work that reshaped the field. A useful objective check is SIGGRAPH's Test-of-Time award (running since 2023 for papers 10+ years old) and the ACM book *Seminal Graphics Papers: Pushing the Boundaries, Volume 2* (2023), which collects the field's landmark papers for SIGGRAPH's 50th anniversary. Years and venues are from standard references; verify the exact citation on the ACM Digital Library.

### Foundations (in reading order)

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

### Recent landmarks (newest first)

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

### The newest award winners (what is "hot" now)

- **SIGGRAPH 2026 best papers** ([source](https://blog.siggraph.org/2026/05/siggraph-2026-technical-papers-awards-best-papers-honorable-mentions-and-test-of-time.html)): GimmBO (interactive merging of image-generation models; Liu, Ling, Jacobson), Mixwell (sharp 2D fluid brushes; Doug and Ethan James), Walk on Decomposed Subdomains (hybrid Monte Carlo PDE solver; Jambon, Nabizadeh, Konaković Luković), Robust Planar Maps for 3D Vectorization (Fuchs, Crane), Inverse Rendering for Discrete X-Ray CT (Nuic, Zhang, Sager, Jakob).
- **SIGGRAPH 2026 Test-of-Time**: besides the Holden and Kalantari papers above, Convolutional Wasserstein Distances (Solomon et al., 2015) and Intrinsic Images in the Wild (Bell, Bala, Snavely, 2014).
- **SIGGRAPH Asia 2025 best papers** ([source](https://asia.siggraph.org/2025/program/award-winners/)): Fovea Stacking; BSP-OT (sparse optimal transport in log-linear time); Automatic Sampling for Discontinuities in Differentiable Shaders; Control Operators for Interactive Character Animation; Curve-Based Slicer for Multi-Axis DLP 3D Printing.

## 3. Research questions of interest

This question asks for *your* interest, so pick two or three from the list below and justify them in your own words. Each is open right now, judging by what SIGGRAPH 2026 rewarded and where industry (Wētā, NVIDIA, Epic) is publishing; the right-hand column gives the papers to start from.

| Area | Research question | Why it is open now | Start from |
| --- | --- | --- | --- |
| Neural rendering | Can Gaussian splats or neural fields become a full production primitive, with relighting, editing, animation and correct ray-traced effects? | 3D Gaussian Splatting is fast but stores baked lighting and has no clean surface; film and games need editable, relightable assets | Kerbl et al. 2023; Huang et al. 2024 (2DGS); Moënne-Loccoz et al. 2024 |
| Real-time rendering | How far can learned components (denoisers, neural radiance caches, neural materials, upscalers) replace hand-built parts of the real-time pipeline while staying stable and controllable? | NVIDIA presented DLSS 5 neural rendering at SIGGRAPH 2026; temporal stability and artist control remain unsolved | Bitterli et al. 2020 (ReSTIR); Müller et al. 2021 (neural radiance caching); 2026 honorable mention on ReSTIR control variates |
| Physically based rendering | How can spectral, polarized and wave-optical effects (thin films, iridescence, fibers) be rendered at production cost? | Wētā and others render spectrally, but wave effects and multi-scale fibers are still expensive | Wilkie et al. 2014; Fascione et al. 2018 (Manuka); Wētā's yarn appearance models (2023–24) |
| Inverse / differentiable rendering | How do we get robust, low-variance gradients through visibility and volumes to recover shape, material and lighting from photos? | Two 2026 award papers (inverse CT, joint extinction gradients) show the topic is spreading to science and capture | Li et al. 2018; Nuic et al. 2026; Yan et al. 2024 (variance-aware inverse rendering, Wētā) |
| Simulation | Can coupled multiphysics (water, foam, cloth, hair, fire) be simulated at film scale and still be art-directable? | Production needs both physical plausibility and director control; scaling across machines is an active problem | Zhu & Bridson 2005; Stomakhin et al. 2013; Lesser et al. 2022 (Loki); Wētā 2026 TOG distributed partitioner |
| Geometry processing | Can Monte Carlo ("walk on spheres") solvers replace meshing for simulation and geometry tasks on messy real-world geometry? | Walk on Decomposed Subdomains won best paper in 2026; variance and boundary handling remain open | Sawhney & Crane 2020; Jambon et al. 2026 |
| Character animation | How can learned motion models stay physically plausible, controllable by animators and generalize to new characters? | Generative motion is improving fast but animators need precise, editable control | Holden et al. 2016/2017; Peng et al. 2018; SIGGRAPH Asia 2025 "Control Operators" |
| Generative 3D content | How can generative models produce assets with clean topology, UVs, rigs and physically based materials that slot into existing pipelines? | Text/image-to-3D outputs look good but are rarely production-ready; SIGGRAPH 2026 Real-Time Live! winner was interactive 3D asset creation | DreamFusion (Poole et al., ICLR 2023); GimmBO (Liu et al. 2026) |

**Example answer you can adapt.** "I am most interested in making neural scene representations production-ready. Gaussian splatting gives real-time photorealism from captured data, but its baked lighting and lack of surfaces block relighting and simulation. I want to study how splats can be combined with physically based materials and ray tracing, building on Kerbl et al. (2023) and the 2024 follow-ups."

## 4. Where to keep finding papers

Since 1 January 2026 the entire ACM Digital Library, including every SIGGRAPH and TOG paper, is free to read ([ACM](https://www.acm.org/publications/openaccess)), so the bottleneck is now finding papers, not accessing them. The sources below work like the two you found: curated lists from the community and publication pages from studios.

| Source | What it is | Use it for |
| --- | --- | --- |
| [Ke-Sen Huang's paper lists](https://www.realtimerendering.com/kesen/) | Per-conference lists with author PDFs, project pages and videos; covers SIGGRAPH 2026, SIGGRAPH Asia 2026, EG 2026, I3D 2026, EGSR, HPG, SCA | The single best way to scan a whole conference |
| [Stephen Hill's SIGGRAPH links (Self Shadow)](https://blog.selfshadow.com/) | Yearly roundup of SIGGRAPH courses, talks and slides, plus the Physically Based Shading course notes | Industry course material that never reaches TOG |
| [Advances in Real-Time Rendering](https://advances.realtimerendering.com/) | Slides of the annual SIGGRAPH course where game studios present engine tech (Nanite, Lumen, etc.) | Real-time state of the art |
| [Real-Time Rendering resources](https://www.realtimerendering.com/) | Site and blog of the *Real-Time Rendering* book; curated links and free books | Background and pointers |
| [Physics-Based Animation](http://www.physicsbasedanimation.com/) | Christopher Batty's blog listing new simulation papers | Simulation and animation research |
| [Graphics Programming weekly](https://www.jendrikillner.com/tags/weekly/) | Jendrik Illner's weekly digest (one of your two sources) | Weekly awareness |
| [arXiv cs.GR](https://arxiv.org/list/cs.GR/recent) | Daily preprints in graphics | Seeing papers months before publication |
| [JCGT](https://jcgt.org/) | Free journal of practical, reproducible techniques | Implementable methods with code |
| [Eurographics Digital Library](https://diglib.eg.org/) | EG, EGSR, SGP, SCA, CGF papers | European venues |
| [GDC Vault](https://gdcvault.com/) | Game Developers Conference talks (many free) | How studios ship techniques |
| Studio research pages: [Pixar](https://graphics.pixar.com/library/), [Disney Research Studios](https://studios.disneyresearch.com/), [NVIDIA Real-Time Rendering Research](https://research.nvidia.com/labs/rtr/), [EA SEED](https://www.ea.com/seed), [Activision Research](https://research.activision.com/) | Publication lists like the Wētā page | Industry-driven research |
| [Semantic Scholar](https://www.semanticscholar.org/) / [Connected Papers](https://www.connectedpapers.com/) | Citation graphs | Finding the papers around one you like, and how influential a paper is |
| [CSRankings](https://csrankings.org/) (graphics only) | Ranking of institutions by top-venue papers | Finding active groups and supervisors |
| Free books: [PBRT 4th ed.](https://pbr-book.org/), *Ray Tracing Gems* I and II | Reference texts, free online | Background for any rendering topic |

**A simple routine.** Each July and December, skim the SIGGRAPH and SIGGRAPH Asia lists on Ke-Sen Huang's page; each week, read Graphics Programming weekly; follow the award posts on the [ACM SIGGRAPH blog](https://blog.siggraph.org/) for the best-paper and Test-of-Time picks.

### Sources used

- [SIGGRAPH 2026 Technical Papers Awards](https://blog.siggraph.org/2026/05/siggraph-2026-technical-papers-awards-best-papers-honorable-mentions-and-test-of-time.html) (ACM SIGGRAPH Blog, 19 May 2026)
- [SIGGRAPH 2026 award winners](https://blog.siggraph.org/2026/09/excellence-on-display-recognizing-the-siggraph-2026-award-winners.html/) (ACM SIGGRAPH Blog, 29 Sep 2026)
- [SIGGRAPH Asia 2026 About](https://asia.siggraph.org/2026/about-the-event/about-siggraph-asia/)
- [SIGGRAPH Asia 2025 award winners](https://asia.siggraph.org/2025/program/award-winners/)
- [Ke-Sen Huang's Home Page](https://www.realtimerendering.com/kesen/) (acceptance statistics)
- [Wētā FX Key Publications](https://www.wetafx.co.nz/research-and-tech/key-publications)
- [ACM open access announcement](https://www.acm.org/publications/openaccess)
