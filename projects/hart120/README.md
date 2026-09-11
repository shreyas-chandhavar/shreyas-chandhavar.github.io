# HART-120 — Flexible High-Aspect-Ratio Wing & Robust Gust-Load Alleviation

**Independent reduced-order conceptual aircraft study by Shreyas G. Chandhavar**

HART-120 is an original fictional 120-passenger-class transport concept created to investigate a real aerospace engineering problem:

> How far can a higher-aspect-ratio wing improve aerodynamic efficiency before structural mass, flexibility and gust/maneuver loads erase the benefit — and can passive aeroelastic tailoring plus active load alleviation recover useful design space?

This is not a generic ML exercise. The workflow starts from first-principles engineering models, uses ML only as a fast surrogate/screening layer, and returns shortlisted designs to the physics model for verification.

## Final frozen result

| Metric | Baseline / Requirement | Final result |
|---|---:|---:|
| Aspect ratio | 13.5 | **15.5** |
| Wing span | 39.13 m | **41.93 m** |
| Aircraft mass | 55,000 kg | **56,416.5 kg** |
| Structural + control package | 6,242.85 kg budget | **6,218.69 kg** |
| Structural budget margin | > 0 kg | **24.16 kg** |
| Induced-drag reduction | 0% | **8.36%** |
| Total cruise-drag reduction | 0% | **2.28%** |
| L/D | 18.91 | **19.85 (+4.97%)** |
| 3000-km cruise fuel | 6,234.17 kg | **6,109.06 kg** |
| Cruise fuel saving | — | **125.10 kg (2.01%)** |
| Final preview time | — | **0.070 s** |
| Sensor / processing delay | — | **0.040 s** |
| Effective timing lead | — | **0.030 s** |
| Mean envelope GLA | >=10% project objective | **15.79%** |
| 5th-percentile envelope GLA | >=10% | **13.81%** |
| P95 controlled root moment | <=3.729 MN·m | **3.687 MN·m** |
| Absolute load pass rate | >=95% | **98%** |
| Envelope >=10% GLA pass rate | >=95% | **100%** |
| Actuator pass rate | >=95% | **100%** |
| Joint robustness | >=95% | **98%** |
| Maximum actuator deflection | <=15 deg | **13.89 deg** |

**Project-level conclusion:** the final AR 15.5 configuration satisfies all defined conceptual design gates in the reduced-order model.

## Engineering workflow

1. **Baseline wing and loads** — fictional aircraft requirements, trapezoidal wing geometry, elliptical reference lift, shear and root bending moment.
2. **Flexible-wing calibration** — Euler-Bernoulli beam model with a project-level 5% half-span tip-deflection target.
3. **Simplified wingbox sizing** — equivalent spar caps and shear webs sized for stiffness, bending stress and shear.
4. **Structural redistribution** — equal-mass placement and fixed-mass redistribution to identify where stiffness is most effective.
5. **Maneuver + gust cases** — 2.5-g maneuver and vertical-gust loading.
6. **Active load alleviation** — zero-net-lift redistribution with control-authority limits.
7. **Actuator dynamics** — lag, delay, rate and deflection constraints.
8. **Dynamic gust response** — first bending mode and gust-gradient sensitivity.
9. **Static aeroelasticity** — torsional washout and passive load redistribution.
10. **Buckling screening** — compression-panel b/t and support-spacing checks.
11. **Aspect-ratio trade** — AR 13.5–18 with aerodynamic benefit versus structural penalty.
12. **Fail-safe sizing** — degraded/failed load-alleviation cases expose web shear as a limiting condition.
13. **System-mass accounting** — sensing, computing, actuation, electronics, wiring and integration mass.
14. **Mission closure** — added aircraft mass fed back into cruise CL, drag, L/D and fuel.
15. **Physics-generated ML** — surrogate models for multidisciplinary and dynamic GLA screening.
16. **Full-physics re-verification** — ML-selected candidates returned to the transient physics model.
17. **Monte Carlo robustness** — uncertainty in gust, structure, sensor/processing timing and actuation.
18. **Final controller redesign** — preview/delay architecture tuned to close the project robustness gates.

## Key engineering findings

### Higher AR is not automatically better
The aerodynamic benefit is real, but simplified wingbox mass rises quickly as span increases. AR 18 is aerodynamically attractive but structurally expensive in the adopted design model.

### Load alleviation creates useful design space
Under the project’s +30% structural-mass budget, the highest conventional configuration is AR 15.0. Passive + active load alleviation moves that boundary to **AR 15.5**.

### Fail-safe structure matters
The nominal load-alleviated design was not acceptable under complete active-control loss because web shear became governing. Fail-safe web resizing added 59.66 kg but preserved the AR 15.5 mass-budget closure.

### System mass can erase the benefit
After fail-safe sizing, only 99.16 kg remained for the full load-alleviation system. A conceptual 75 kg package was therefore included before aircraft-level conclusions were made.

### The benefit survives weight coupling
After the added structural/control mass is included, the final configuration retains **8.36% induced-drag reduction**, **2.28% total cruise-drag reduction**, **4.97% higher L/D** and **2.01% lower estimated cruise fuel** at 3000 km.

### Nominal controller performance was not enough
The first selected controller failed the project robustness objective under uncertainty. The final controller uses **0.070 s preview**, **0.040 s processing delay** and **0.030 s effective timing lead**, reaching **98% joint robustness** in the final 300-case study.

## Machine-learning role

ML is not the source of truth. It is used to screen large design spaces generated from the physics models.

Selected surrogate performance:
- fail-safe wingbox mass: R² ≈ 0.997
- cruise fuel: R² ≈ 0.998
- fuel-saving percentage: R² ≈ 0.988
- controlled dynamic root moment: R² ≈ 0.960
- dynamic root-moment reduction: R² ≈ 0.935

Some top ML-screened controller candidates failed full-physics verification, which is why the project retains a strict **ML-screen → physics-verify** workflow.

## Claim boundary

HART-120 is a **conceptual reduced-order study**, not aircraft certification analysis. It does not replace 3D transonic CFD, nonlinear aeroelasticity, detailed composite wingbox FEA, flutter/divergence clearance, certification-standard gust and maneuver envelopes, flight-control-law certification, hardware-in-the-loop testing or full mission economics.

See [`MODEL_LIMITATIONS.md`](MODEL_LIMITATIONS.md).

## Originality / IP

HART-120 is an original fictional aircraft concept. No proprietary OEM geometry, internal company loads, control laws or confidential datasets are used.

## Author

**Shreyas G. Chandhavar**  
Mechanical Engineer · Aero-Structural Analysis · Engineering Computation  
MSc Sustainable Energy Engineering, Lund University
