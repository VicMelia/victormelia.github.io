---
layout: ../../components/MarkdownPost.astro
title: "Real-Time GPU Foliage Instancing on Arbitrary Surfaces Using Quasi-Monte Carlo Sampling – 2025"
author: 
  name: "Victor Melia-Vilar, Miguel Chover"
  url: "/QMC.PNG"
image:
  url: "/QMC.PNG"
  alt: "GPU Foliage Instancing"
tags: ["GPU rendering","QMC sampling","real-time graphics","foliage instancing","compute shaders"]
pubDate: 'Jun 14, 2025'
source: "https://ssrn.com/abstract=5295246"
---

Real-time rendering of dense vegetation typically depends on detailed 3D plant models that combine trunks, branches, and leaves into a single mesh. While effective for predefined assets, this approach breaks down when vegetation must adapt to irregular or procedurally generated surfaces such as complex canopies, terrains, or green walls. The limitations of these traditional methods—rigid topology, memory cost, and poor adaptability—highlight the need for a more flexible solution.

This paper introduces a fully GPU-based technique for instancing individual leaves directly on arbitrary surfaces. Instead of relying on Poisson Disk Sampling, which requires spatial validation structures and iterative rejection steps, the method uses Quasi-Monte Carlo (QMC) sampling—specifically Halton sequences—to achieve uniform distribution without neighbor checks or CPU processing. All placement, sampling, and evaluation are executed in parallel via compute shaders, making the system deterministic, reproducible, and highly scalable.

On a mid-range RTX 3050 GPU, the technique can place more than 400,000 leaves in roughly two seconds, using just 133 MB of VRAM. The method supports both triangular meshes and heightmap-based terrains, enabling leaf instancing on a wide variety of geometries. By computing normals, applying controlled random perturbations, and batching instances for rendering, the technique integrates efficiently into real-time rendering pipelines.

This GPU-driven approach demonstrates strong advantages: improved scalability, predictable distributions, negligible CPU load, and robust performance even in dense scenes. The authors conclude that QMC-based foliage instancing can serve as a foundation for next-generation real-time vegetation systems, especially in interactive graphics and procedural content workflows.

