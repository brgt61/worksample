# Wearable fNIRS for ADHD — Modeling-Guided Design and Safety Analysis

This project evaluates the feasibility and design constraints of a wearable fNIRS system for objective monitoring of prefrontal cortex (PFC) activity in ADHD.
The focus is **measurement physics + safety bounds + design trade-offs**, rather than downstream classification performance.

## Goals
- Estimate cortical sensitivity under realistic head geometry and tissue layers
- Quantify thermal safety limits for sustained optical illumination
- Translate modeling constraints into wearable mechanical design decisions

## Modeling (COMSOL)

### Optical propagation (fluence)
- Modeled photon propagation in a multilayer head volume using diffusion-based formulation (Helmholtz-type PDE setup in COMSOL).
- Applied an air–tissue boundary condition (Robin boundary form) and evaluated fluence distribution versus optode placement and separation.
- Used modeling to justify the final optode geometry and to understand depth sensitivity limitations.

### Thermal safety (Pennes bioheat + CEM43)
- Modeled tissue heating from incident optical power using the **Pennes bioheat equation** with convective boundary conditions on the scalp surface.
- Computed **thermal dose (CEM43)** to account for cumulative heating effects over time.
- Performed a **mesh independence study** (e.g., scalp CEM43 vs mesh resolution) to ensure numerical stability of safety conclusions.

## Key Design Choices (Driven by Modeling)
- **Dual-wavelength illumination (760/850 nm)** for hemodynamic contrast.
- **Source–detector separation ~131 mm** to reach target cortical sensitivity in simulation.
- Modeled power-dependent heating to ensure scalp/skull/brain CEM43 stays within recognized safety thresholds over the evaluation window.

## Mechanical Design (Wearability)
- Designed a forehead-fitting cap architecture with optode modules and strap/clasp components (SolidWorks).
- Material choices reflect comfort and robustness requirements for a wearable form factor.

## Main Findings / Limitations
- Thermal analysis indicates a feasible operating regime where tissues remain below CEM43-based thresholds.
- Achieving cortical sensitivity required an unusually large **~131 mm** separation, implying:
  - stronger attenuation / SNR challenges,
  - higher sensitivity to placement error,
  - risk of false negatives if optodes are not positioned precisely.

## Notes
- This repo presents the modeling- and design-driven reasoning; no human subject data are included.
- Detailed report is available upon request.
