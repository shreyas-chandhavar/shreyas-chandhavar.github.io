# References and data provenance

The project deliberately uses public, attributable technical sources rather than proprietary aircraft data.

## Primary AGARD 445.6 benchmark

1. **Yates, E. Carson Jr.** (1987). *AGARD Standard Aeroelastic Configurations for Dynamic Response: Candidate Configuration I — Wing 445.6*. NASA TM-100492. NASA Technical Reports Server (NTRS): https://ntrs.nasa.gov/citations/19880001820
   - Used for: structural grid geometry, weakened Model-3 modal frequencies, tabulated modal displacement/slope coefficients, damping guidance, mass-ratio/fluid-density information, and measured flutter points.
   - NTRS status: **Distribution Limits: Public**; **Copyright: Work of the US Gov. Public Use Permitted.**

2. **Stanford, B. K.; Jacobson, K. E.** (2023). *Transonic Flutter Dips of the AGARD 445.6 Wing*. NASA / AIAA SciTech. NTRS: https://ntrs.nasa.gov/citations/20220017734
   - Used as modern context for the benchmark, especially sensitivity to wind-tunnel-wall modelling and the difficult transonic region.

## Classical unsteady aerodynamics

3. **Theodorsen, T.** *General Theory of Aerodynamic Instability and the Mechanism of Flutter*. NACA Report 496. NTRS: https://ntrs.nasa.gov/citations/19930090935
   - Used for the typical-section frequency-domain unsteady aerodynamic comparison.
   - NTRS status: **Work of the US Gov. Public Use Permitted.**

4. **Jones, R. T.** *Operational Treatment of the Nonuniform-Lift Theory in Airplane Dynamics*. NACA TN 667. NTRS PDF: https://ntrs.nasa.gov/archive/nasa/casi.ntrs.nasa.gov/19930081472.pdf
   - Used as a public classical source for operational unsteady-lift modelling. The notebook uses the standard two-exponential Jones approximation to Wagner's response.

## Aerodynamic software

5. **DLR Institute of Aeroelasticity — PanelAero.** GitHub: https://github.com/DLR-AE/PanelAero
   - Used for VLM/DLM aerodynamic influence calculations.
   - License: BSD 3-Clause.
   - The PanelAero project asks scientific users to cite its associated technical report; consult the upstream repository for the current citation text.

## Software libraries

NumPy, SciPy, pandas, Matplotlib and scikit-learn are used as third-party Python dependencies. Their source code is not vendored in this repository; each remains under its own upstream license.

## Data-reuse practice in this repository

- No proprietary OEM aircraft geometry, loads, internal reports or CAD are used.
- No NASA report pages or figures are copied into the repository.
- Numerical benchmark values transcribed from NASA TM-100492 are explicitly attributed in the notebook cells that use them.
- The project’s figures are generated from the author’s own calculations.
- Siemens NX screenshots/geometry should be treated as project evidence; Siemens trademarks/software remain the property of Siemens.
