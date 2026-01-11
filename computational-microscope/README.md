# Computational Microscope — Physics-Based Forward Modeling and Inverse Reconstruction

Status: Ongoing research project

## Overview
This project studies a computational microscopy system in which spatial information is encoded through a physics-based optical forward model and recovered via inverse reconstruction.

The focus is not on downstream task performance or visual appeal, but on understanding how **forward-model assumptions, undersampling, and model mismatch** fundamentally limit reconstruction stability and resolution.

This work is motivated by the observation that many reconstruction failures arise from the measurement process itself rather than the choice of optimization or learning algorithm.

---

## Problem Formulation
The imaging process is formulated as an inverse problem:

\[
y = A(x) + n
\]

where:
- \(x\) is a high-resolution spatiotemporal scene,
- \(A\) is a physics-based forward operator modeling optical blur, spatial tiling, and sensor integration,
- \(y\) denotes compressed measurements,
- \(n\) represents measurement noise.

The problem is ill-posed due to severe undersampling, aggregation across overlapping optical channels, and sensitivity to forward-model mismatch.

---

## Forward Model
The forward model explicitly simulates the physical measurement process:

- Optical blur modeled via an incoherent optical transfer function (OTF) derived from pupil functions, numerical aperture, wavelength, and pixel size.
- Spatial encoding implemented through microlens-based tiling, followed by tile-wise summation on the sensor.
- Controlled spatial motion and shear applied to ground-truth scenes to probe sensitivity to temporal and geometric variations.

In addition to the high-resolution tiled measurement model, a low-resolution auxiliary imaging model is implemented to enforce cross-scale consistency during reconstruction.

---

## Inverse Reconstruction
Reconstruction is performed via gradient-based optimization under multiple constraints:

- Data fidelity to the tiled measurement model.
- Consistency with low-resolution measurements.
- Optional total variation (TV) regularization to control spatial smoothness and stabilize inversion.

The reconstruction process exposes explicit trade-offs between sharpness, stability, and robustness, rather than attempting to maximize perceptual quality.

---

## Key Technical Challenges
This project explicitly explores several core challenges in computational imaging:

- Severe undersampling caused by tile-wise summation and limited sensor measurements.
- Sensitivity of reconstruction quality to OTF mismatch and blur assumptions.
- Resolution–stability trade-offs as regularization strength varies.
- Interactions between low-resolution constraints and high-resolution reconstruction objectives.

Failure cases are analyzed to understand why reconstruction degrades, not only when it succeeds.

---

## What I Explored
- Quantitative loss decomposition to study convergence behavior under different constraint weightings.
- Comparison between naive interpolation-based reconstruction and physics-constrained inversion.
- Stability analysis under forward-model mismatch and noise perturbations.
- Visualization of reconstruction artifacts and failure modes to guide modeling decisions.

---

## What This Project Demonstrates
- Ability to reason from physical measurement to inverse problem formulation.
- Understanding of why reconstruction becomes unstable under realistic constraints.
- Comfort working at the interface of optics, modeling, and numerical optimization.
- Research-oriented thinking beyond end-to-end black-box reconstruction.

---

## Current Status and Next Steps
This project is ongoing. Current efforts focus on:
- Systematic analysis of reconstruction stability under controlled forward-model mismatch.
- Exploration of alternative regularization strategies for improved robustness.
- Studying identifiability limits imposed by spatial aggregation and undersampling.

---

## Notes on Code Availability
Implementation is not publicly available due to lab policy.
The forward model, optimization formulation, and reconstruction logic can be discussed in detail upon request.
