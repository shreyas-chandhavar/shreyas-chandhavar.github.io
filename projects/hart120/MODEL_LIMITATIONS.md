# HART-120 Model Limitations and Claim Boundary

HART-120 is a reduced-order conceptual engineering study. Its value is in the design reasoning, coupling of disciplines and verification workflow, not in claiming certification-level aircraft performance.

## What the model can support

The project supports comparative, project-level conclusions such as:
- how increasing aspect ratio changes induced drag in the adopted aerodynamic model;
- how simplified beam/wingbox stiffness and mass change with span;
- how passive aeroelastic washout can redistribute spanwise loading;
- how active load redistribution can reduce selected root-load metrics;
- how actuator dynamics and preview timing affect conceptual gust-load-alleviation performance;
- how fail-safe requirements can add structural mass;
- how technology-system mass can erode aircraft-level aerodynamic benefit;
- how uncertainty can invalidate a nominal controller;
- how ML surrogates can accelerate screening when final candidates are rechecked with the physics model.

## What the model does not establish

The project does **not** establish:
- aircraft certification compliance;
- real OEM loads or structural margins;
- flutter or divergence clearance;
- detailed composite laminate allowables;
- local crippling, fastener, joint or load-introduction failure;
- 3D viscous/transonic aerodynamic behaviour;
- control-surface hinge moments;
- actuator power or thermal qualification;
- flight-control-law certification;
- complete handling qualities;
- complete mission fuel burn;
- operational or economic business-case viability.

## Key simplifying assumptions

- fictional HART-120 geometry;
- elliptical reference span loading;
- reduced-order finite-wing induced drag;
- Euler-Bernoulli / first-mode structural representation;
- equivalent material properties;
- simplified two-cap wingbox representation;
- simplified web shear sizing;
- project-defined stiffness/deflection limits;
- conceptual compression-panel buckling treatment;
- reduced-order static aeroelastic torsion;
- simplified actuator dynamics and preview/feedforward control;
- Monte Carlo uncertainty ranges selected for project-level robustness studies;
- Breguet-type cruise fuel approximation.

## Interpretation rule

All reported percentages are valid **within the model assumptions and selected design space**. They should be presented as conceptual comparative results, not predictions for a real aircraft programme.
