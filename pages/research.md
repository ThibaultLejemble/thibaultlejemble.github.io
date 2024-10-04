---
layout: page
title: Research
permalink: /research/
---

## 3D Point Cloud Processing

### Curvature estimation

<div style="text-align: justify">
Curvatures of curves and surfaces are local properties that are fundamental in geometry processing.
They correspond to local features that characterize small neighborhoods of points on a surface.
Their uses in computer vision are numerous: keypoints extraction, sharp features detection, shape matching, smoothing, segmentation...
Differential properties of smooth surfaces are well understood in theory since Gauss work in 1827.
The challenge is now to estimate these quantities on point-sampled surfaces using accurate and precise estimators.
Algorithms must be efficiency in time and memory, and must be adapted to GPU implementations.
Theoretical proofs of convergence under asymptotic settings should certify that these estimators tends toward the correct differential invariant and that they remain robust in the presence of noise.
</div>

- [Stable and efficient differential estimators on oriented point clouds](/articles/lejemble2021stable.pdf), Lejemble at al., 2021 ([Github](https://github.com/STORM-IRIT/algebraic-shape-operator))
- [Ponca](https://github.com/poncateam/ponca), header only C++/CUDA library for point cloud analysis

### Segmentation and classification

<div style="text-align: justify">
Segmentation aims at dividing a 3D point cloud in different distinctive regions.
Geometric criterion are usually used to define those regions. 
Planes and feature curves are two examples of geometric patterns that can be extracted thanks to a segmentation algorithm.
Classification adds another level of abstraction where semantic plays an essential role.
Specific objects such as furnitures in a building, pedestrian on the street, and electric poles in a landscape can be detected in a 3D scan.
Classification is more and more tackled by deep learning methods since a large quantity of scanned data is now available. 
However, labeling 3D points is costly, and real scanned data show a wide variety of shape which cannot be well captured by mid-size neural networks.
Finally, there is a strong need of machine learning approaches that do not require hundred of hours of training on costly hardware. 
</div>

- [PCEDNet: A lightweight neural network for fast and interactive edge detection in 3D point clouds](/articles/himeur2021pcednet.pdf), Himeur et al., 2021 ([Website](https://storm-irit.github.io/pcednet-supp))
- [Persistence Analysis of Multi-scale Planar Structure Graph in Point Clouds](/articles/lejemble2020persistence.pdf), Lejemble et al., 2020 ([Github](https://github.com/STORM-IRIT/Plane-Detection-Point-Cloud))
- [SHREC'19 track: Feature Curve Extraction on Triangle Meshes](), Thompson et al., 2019
- see also the [CGAL classification package](https://doc.cgal.org/latest/Classification/index.html)

## SAT Solvers on GPU

<div style="text-align: justify">
SAT problems are fundamental in computer science and many solvers exist now.
However, due to the ever growing size of SAT formulas, efficient solvers are still actively researched in different directions: sequential algorithms, parallel algorithms on multi-core processors, and parallel algorithms in a cloud of computers.
Another type of hardware seems to not be really used in this domain yet: massively parallel architectures such as GPUs.
The challenge is to design a new kind of solver that laverage the computational power of GPUs to accelerate SAT problem solving. 
</div>

