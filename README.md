# 3D Drone Propeller Design Suite

A full parametric design and optimisation pipeline for drone propellers, combining classical aerodynamic theory with modern machine learning surrogates and CFD case generation.

## Overview

This project implements an end-to-end propeller design workflow across 14 modules, progressing from first-principles aerodynamics to deep-learning-accelerated multi-objective optimisation:

| Module | Description |
|---|---|
| 1 | Interactive 3D propeller designer — parametric NACA 4-series blade geometry with per-blade chord/twist/thickness control, watertight STL export |
| 2 | Blade Element Momentum (BEM) theory with Buhl (2005) high-induction correction |
| 3 | Vortex Lattice Method (VLM) for rotating blades |
| 4 | Physics-Informed Neural Network (PINN) aerodynamic surrogate |
| 5 | Variational Autoencoder (VAE) for blade shape latent space |
| 6 | Bayesian optimisation in the learned latent space |
| 7 | Actuator disk & momentum theory |
| 8 | Differentiable propeller optimisation (gradient-based design) |
| 9 | Unsteady blade-vortex interaction (BVI) modelling |
| 10 | Multi-objective Pareto optimisation (thrust vs. efficiency vs. noise) |
| 11 | Fourier Neural Operator (FNO) for pressure field prediction |
| 12 | Reinforcement learning for blade shape search |
| 13 | Full OpenFOAM compressible CFD case generator (rotating-mesh AMI, LES-ready) |
| 14 | Interactive simulation dashboard |

## Highlights

- Combines **classical aerodynamic theory** (BEM, VLM, actuator disk) with **modern deep learning** (PINNs, VAEs, FNOs, RL) in a single coherent pipeline
- Generates **production-ready OpenFOAM cases** for high-fidelity CFD validation
- Learned **latent design space** (via VAE) enables efficient Bayesian optimisation over blade geometry
- Fully **differentiable optimisation** path for gradient-based design refinement
- Interactive **3D visualisation** (Plotly) and **STL export** for rapid prototyping

## Tech Stack

`Python` · `PyTorch` · `NumPy` · `SciPy` · `Plotly` · `ipywidgets` · `Matplotlib` · `OpenFOAM`

## Setup

```bash
pip install -r requirements.txt
jupyter notebook propeller_design_suite.ipynb
```

## Running

The notebook is organised into independent, sequentially-numbered modules. Each module can be run on its own after the Setup and Imports cells. Module 13 generates a complete OpenFOAM case directory (`./openfoam_case/`) which can be run with a standard OpenFOAM installation (`blockMesh`, `snappyHexMesh`, `rhoCentralFoam` or equivalent solver).

## Notes

This is a personal research/learning project exploring the intersection of classical aerodynamics and modern ML-based design optimisation. It is not a validated production tool — outputs should be cross-checked against experimental data or high-fidelity CFD before use in any real design decision.

## Author

Chiruvanuru Kumar Tapaswin — [LinkedIn](https://www.linkedin.com/in/chiruvanuru-kumar-tapaswin)
