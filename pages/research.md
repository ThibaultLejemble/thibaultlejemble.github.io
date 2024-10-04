---
layout: page
title: Research
permalink: /research/
published: false
---

## 3D Point Cloud Processing

### Curvature estimation

<div style="text-align: justify">
Curvatures of curves and surfaces are local properties that are fundamental in geometry processing.
They correspond to local features that characterize small neighborhoods of points on a surface.
Their uses are numerous: keypoints extraction, sharp features detection, shape matching, smoothing, segmentation...
Differential properties of smooth surfaces are well understood in theory since Gauss work in 1827.
The challenge is now to estimate these quantities on point-sampled surfaces using accurate and precise estimators.
Algorithms must be efficiency in time and memory, and must be adapted to GPU implementations.
Theoretical proofs of convergence under asymptotic settings should certify that these estimators tends toward the correct differential invariant and that they remains robust in the presence of noise.
</div>

- [Stable and efficient differential estimators on oriented point clouds](/articles/lejemble2021stable.pdf), Lejemble at al., 2021 ([Github](https://github.com/STORM-IRIT/algebraic-shape-operator))
- [Ponca](https://github.com/poncateam/ponca), header only C++/CUDA library for point cloud analysis

### Segmentation and classification


### Geometric Deep Learning




## SAT Solvers on GPU


