# NACA 2412 Airfoil CFD Simulation — ANSYS Fluent (Student Version)

A structured project repository for simulating and analyzing the aerodynamic
performance of a **NACA 2412 airfoil** using **ANSYS Fluent (Student Version)**.
This repo tracks the geometry, mesh, simulation setup, and results for the
workflow, plus notes on validating against experimental NASA data.

## Source / Credit

This project follows the tutorial by **Cillian Thomas**:
🎥 [NACA 2412 Airfoil CFD Simulation — ANSYS Fluent Tutorial](https://youtu.be/3i9Ryq-m1HA)

All credit for the original workflow, methodology, and teaching goes to the
creator. This repository is a personal reproduction/study project built while
following along, with my own geometry, mesh, and result files.

## Project Overview

| Stage | Description | Reference Timestamp |
|---|---|---|
| Geometry Creation | Airfoil profile generated via Airfoil Plotter; C-type fluid domain built in Design Modeler | 0:53 – 15:02 |
| Meshing | Structured mesh with edge sizing and bias controls | 16:48 – 22:03 |
| Y+ Validation | Checking near-wall resolution, target y⁺ < 1 | 22:03 – 27:13, 52:03 |
| Simulation Setup | SST k-ω turbulence model, velocity inlet BC at Re = 3.1 million | 28:23 – 33:24 |
| Solving & Analysis | Convergence monitoring, Cl/Cd calculation, pressure contours, velocity vectors | 33:24 – 44:20 |
| Data Comparison | CFD results validated against NASA experimental data | 34:58 – 39:45 |
| Angle of Attack Study | Adjusting velocity components/force vectors across AoA, observing stall onset | 44:20 – 52:03 |

## Repository Structure

```
naca2412-cfd-fluent/
├── README.md              # This file
├── docs/
│   ├── WORKFLOW.md         # Detailed step-by-step notes for each stage
│   └── validation.md       # NASA experimental data comparison notes
├── geometry/               # Airfoil coordinates, Design Modeler files
├── mesh/                   # Mesh files, sizing/bias settings, quality reports
├── setup/                  # Fluent case setup notes (BCs, models, solver settings)
└── results/                # Cl/Cd results, contour plots, convergence plots
```

## Simulation Parameters (Baseline Case)

- **Airfoil:** NACA 2412
- **Domain type:** C-type fluid domain
- **Turbulence model:** SST k-ω
- **Reynolds number:** 3.1 × 10⁶
- **Boundary condition:** Velocity inlet (magnitude/components derived from Re and angle of attack)
- **Near-wall target:** y⁺ < 1

## Status

- [ ] Geometry generated and imported
- [ ] Mesh built and y⁺ validated
- [ ] Baseline case (0° AoA) solved and converged
- [ ] Results compared against NASA experimental data
- [ ] Angle of attack sweep completed
- [ ] Stall behavior documented

## Notes on File Management

Following the tutorial's best-practice guidance, ANSYS project files (`.wbpj`,
solver `.cas`/`.dat` files, and temp/backup folders) are **not** committed to
this repository — see `.gitignore`. Only lightweight, version-controllable
artifacts (scripts, coordinates, settings notes, exported plots/images, and
result summaries) are tracked here to avoid repo bloat and data loss from
large binary files.

## License

Personal academic/study project. Original tutorial content © Cillian Thomas.
