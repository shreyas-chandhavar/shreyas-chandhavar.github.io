# Model limitations and claim boundary

FLEX-445 is a reduced-order engineering study built to demonstrate a defensible aeroelastic design workflow on a public benchmark. The following limitations are part of the result, not footnotes to be hidden.

## Benchmark model

- The structural model retains four published AGARD 445.6 modes rather than a full high-fidelity finite-element model.
- The aerodynamic model uses linear potential-flow DLM/VLM methods. It does not resolve viscosity, shocks or nonlinear transonic flow.
- The Mach 0.960 representative point remains the largest benchmark discrepancy: approximately +12.5% flutter-velocity error. This limits the strength of claims near the transonic regime.
- Structural-to-aerodynamic coupling and wall-image modelling were audited and improved, but still remain reduced-order representations.

## Passive design

- The passive reinforcement model applies effective modal mass/stiffness changes rather than a detailed laminate/solid structural redesign.
- The relation between local GJ gain and added mass is a **notional design-study proxy** used for architecture comparison.
- No fatigue, buckling, local stress concentration, joint, adhesive, fastener, damage-tolerance or manufacturing analysis is included.

## Active control

- Control laws are reduced-order torsional feedback models, not certified flight-control laws.
- Bandwidth and delay are modelled; actuator saturation, thermal limits, power supply, sensor noise, redundancy, fault detection, certification and hardware-in-the-loop validation are outside scope.
- “Controller-off” means a steady re-computation of the passive flutter boundary with active gain removed. It is not a transient failure simulation.

## ML / surrogate optimization

- ML is trained only on physics-generated cases inside bounded DOE ranges.
- The surrogate is not used as final truth. Shortlisted designs are returned to the original p-k model.
- Five ML-selected designs were re-verified; three passed the final project requirements. This should be retained in any public presentation because it demonstrates why re-verification matters.

## Siemens NX concept

- The NX model is a concept-level geometric mapping of the benchmark wing, a nominal mid-span reinforcement region and an actuator packaging envelope.
- It does **not** independently demonstrate +24.362% GJ, validate the 2.436% mass proxy, or prove a manufacturable actuator installation.
- The NX nominal reinforcement region was created around 35–55% semispan during the deterministic phase. The final ML-selected candidate later shifted the optimized region to about 36.5–56.5% semispan.

## Appropriate public claim

A defensible summary is:

> FLEX-445 demonstrates a physics-guided passive–active flutter-mitigation workflow on the public AGARD 445.6 benchmark. A validated reduced-order model, controller robustness checks, physics-generated ML surrogates and physics re-verification identified a minimum-active-authority hybrid candidate with a predicted +6.13% flutter-velocity improvement and +4.25% controller-off margin within the model assumptions.

Do not describe the project as a certified aircraft flutter-suppression system, a production-ready actuator design, or an OEM-equivalent analysis.
