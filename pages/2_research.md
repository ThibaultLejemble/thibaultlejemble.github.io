---
layout: page
title: Research
permalink: /research/
---

## 3D Point Cloud Processing

<div style="text-align: justify">
A point cloud is a 3D data representation obtained through numerical acquisition. Depth sensors, such as LiDAR, or computer vision algorithms, like Multi-View Stereo, typically generate a discrete set of 3D coordinates that sample a real-world scene. Processing point clouds poses several challenges, including acquisition noise, missing data due to occlusions, large data volumes often reaching billions of points equivalent to hundreds of gigabytes, and the lack of a regular structure. Common processing techniques include denoising, registration, meshing, compression, segmentation, and classification. Many fields, such as robotics, aerospace, virtual/augmented reality, cultural heritage, Computer-Aided Design (CAD), and urban planning, now extensively use 3D scanning technologies and point clouds.
</div>

### Curvature estimation

<div style="text-align: justify">
Curvatures of curves and surfaces are local properties that are fundamental in geometry processing.
They correspond to local features that characterize small neighborhoods of points on a surface.
Their applications in computer vision are numerous, including keypoint extraction, sharp feature detection, shape matching, smoothing, and segmentation.
The differential properties of smooth surfaces have been well understood in theory since Gauss's work in 1827.
The current challenge is to estimate these quantities on point-sampled surfaces using accurate and precise estimators.
Algorithms must be efficient in terms of time and memory and adapted to GPU implementations.
Theoretical proofs of convergence under asymptotic settings should certify that these estimators tend toward the correct differential invariants and that they remain robust in the presence of noise.
</div>

- [Stable and efficient differential estimators on oriented point clouds](/articles/lejemble2021stable.pdf), Lejemble at al., 2021 ([Github](https://github.com/STORM-IRIT/algebraic-shape-operator))
- [Ponca](https://github.com/poncateam/ponca), header only C++/CUDA library for point cloud analysis

### Segmentation and classification

<div style="text-align: justify">
Segmentation aims to divide a 3D point cloud into distinct regions.
Geometric criteria are usually used to define these regions. Planes and feature curves are examples of geometric patterns that can be extracted using a segmentation algorithm.
Classification adds another level of abstraction, where semantics play an essential role. 
Specific objects, such as furniture in a building, pedestrians on the street, and electric poles in a landscape, can be detected in a 3D scan.
Classification is increasingly addressed by deep learning methods, as a large amount of scanned data is now available. 
However, labeling 3D points is costly, and real scanned data exhibit a wide variety of shapes that cannot be well captured by mid-size neural networks. 
Finally, there is a strong need for machine learning approaches that do not require hundreds of hours of training on expensive hardware.
</div>

- [PCEDNet: A lightweight neural network for fast and interactive edge detection in 3D point clouds](/articles/himeur2021pcednet.pdf), Himeur et al., 2021 ([Website](https://storm-irit.github.io/pcednet-supp))
- [Persistence Analysis of Multi-scale Planar Structure Graph in Point Clouds](/articles/lejemble2020persistence.pdf), Lejemble et al., 2020 ([Github](https://github.com/STORM-IRIT/Plane-Detection-Point-Cloud))
- [SHREC'19 track: Feature Curve Extraction on Triangle Meshes](), Thompson et al., 2019
- see also the [CGAL classification package](https://doc.cgal.org/latest/Classification/index.html)

## SAT Solvers on GPU

<div style="text-align: justify">
SAT problems are fundamental in computer science, and many solvers exist today.
However, due to the ever-growing size of SAT formulas, efficient solvers are still actively being researched in various directions: sequential algorithms, parallel algorithms on multi-core processors, and parallel algorithms in cloud computing environments.
Another type of hardware that has not yet been widely utilized in this domain is massively parallel architectures, such as GPUs.
The challenge is to design a new kind of solver that leverages the computational power of GPUs to accelerate SAT problem solving.
</div>

