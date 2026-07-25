# NACA 2412 Airfoil CFD Simulation — ANSYS Fluent (Student Version)

Introduction

Airfoils are the fundamental building block of aircraft wings, and their aerodynamic behavior directly determines how much lift an aircraft can generate, how much drag it must overcome, and at what conditions it will stall. The NACA 2412 is a classic cambered airfoil section from the NACA 4-digit series (2% max camber at 40% chord, 12% max thickness), widely used as a benchmark case in aerodynamics because decades of wind-tunnel and flight-test data exist for it — making it ideal for validating a CFD setup against real experimental results.

This project uses ANSYS Fluent (Student Version) to numerically simulate flow over a NACA 2412 airfoil and extract its aerodynamic performance, following the workflow demonstrated by Cillian Thomas in his tutorial: 🎥 NACA 2412 Airfoil CFD Simulation — ANSYS Fluent

Problem Statement

Given the NACA 2412 airfoil geometry operating in a subsonic air stream at a Reynolds number of 3.1 million, the objective is to:

Generate accurate airfoil geometry and a suitable computational (C-type) fluid domain around it.
Build a mesh fine enough near the wall to resolve the boundary layer correctly.
Solve the flow field using an appropriate turbulence model.
Extract the lift coefficient (Cl) and drag coefficient (Cd) at a given angle of attack.
Validate these results against published NASA experimental data.
Study how Cl and Cd — and the flow itself — change as the angle of attack increases, up to and including stall.

In short: can a student-licensed CFD setup reproduce trustworthy, experimentally-validated lift and drag predictions for a well-known airfoil, across a range of operating conditions?

Key Aerodynamic Concepts
Lift and Drag
Lift (L) is the force generated perpendicular to the oncoming flow direction, arising mainly from the pressure difference between the airfoil's upper (suction) and lower (pressure) surfaces. It is what keeps an aircraft airborne.
Drag (D) is the force acting parallel to the flow direction, resisting motion. For an airfoil at moderate angles of attack, drag is a combination of skin-friction (viscous) drag and pressure (form) drag.
These forces are reported in non-dimensional form as the lift coefficient (Cl) and drag coefficient (Cd), which allow comparison across different speeds, sizes, and air densities. Tracking how Cl and Cd change with angle of attack reveals the airfoil's performance envelope and the angle at which stall occurs — the point where flow separates from the upper surface and lift suddenly drops.
Y+ Value
Y+ (y-plus) is a non-dimensional wall distance that describes how well the first mesh cell near a solid surface resolves the viscous boundary layer.
It matters because turbulence models like SST k-ω rely on the near-wall mesh being fine enough to capture steep velocity gradients close to the airfoil surface — this is where skin-friction drag and flow separation behavior are determined.
The target for this simulation is y⁺ < 1, meaning the first cell lies within the viscous sublayer. A poorly resolved y⁺ leads to inaccurate drag predictions and unreliable stall behavior, even if the overall mesh looks "fine enough" elsewhere.
Pressure Distribution
The pressure distribution over the airfoil surface (commonly viewed as a pressure coefficient, Cp, plot or as pressure contours) shows exactly how pressure varies from the leading edge to the trailing edge, and between the upper and lower surfaces.
It's important because lift is essentially the integrated effect of this pressure difference — visualizing it shows where on the airfoil lift is being generated, helps identify suction peaks near the leading edge, and reveals early signs of flow separation as angle of attack increases.
Comparing simulated pressure distribution shape against experimental trends is one of the clearest sanity checks that a CFD setup is physically reasonable, beyond just matching the final Cl/Cd numbers.

## Source / Credit

This project follows the tutorial by **Cillian Thomas**:
🎥 [NACA 2412 Airfoil CFD Simulation — ANSYS Fluent Tutorial](https://youtu.be/3i9Ryq-m1HA)

All credit for the original workflow, methodology, and teaching goes to the
creator. This repository is a personal reproduction/study project built while
following along, with my own geometry, mesh, and result files.


## Simulation Parameters (Baseline Case)

- **Airfoil:** NACA 2412
- **Domain type:** C-type fluid domain
- **Turbulence model:** SST k-ω
- **Reynolds number:** 3.1 × 10⁶
- **Boundary condition:** Velocity inlet (magnitude/components derived from Re and angle of attack)
- **Near-wall target:** y⁺ < 1


Personal academic/study project. Original tutorial content © Cillian Thomas.
