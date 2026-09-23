# Biofluid Mechanics

Research-grade interactive models for blood rheology, arterial hydrostatics, capillary rise, and atherosclerotic-stenosis hemodynamics.

## Open the visualization

**[Launch the Biofluid Mechanics dashboard](https://jonnyterrero.github.io/BME-Visualizations/biofluid-mechanics/dashboard.html)**

**[Launch the Arterial Stenosis Hemodynamics tool](https://jonnyterrero.github.io/BME-Visualizations/biofluid-mechanics/atherosclerosis-cfd.html)**

Or open [`dashboard.html`](dashboard.html) locally in a browser.

## What is in this folder

| File | What it is |
| --- | --- |
| [`dashboard.html`](dashboard.html) | Three-tab computational dashboard with live Chart.js plots and sliders |
| [`atherosclerosis-cfd.html`](atherosclerosis-cfd.html) | Interactive reduced-order CFD of blood flow through a stenotic artery (straight **or** carotid-style bifurcation): velocity heat map, streamlines, pressure, and wall shear stress |

## Topics in the dashboard

1. **Rheology** — Newtonian plasma \(\tau = \mu\dot{\gamma}\) vs shear-thinning whole blood \(\tau = K\dot{\gamma}^n\), including the Fåhræus–Lindqvist effect in microvessels.
2. **Hydrostatics** — standing arterial pressure \(P_{total} = P_{heart} + \rho g h\). Drag density and gravity to see MAP at the feet change.
3. **Capillary action** — Jurin's law \(h = 2\sigma\cos\theta / (\rho g R)\). Radius, surface tension, and contact angle drive the animated meniscus (alveolar / organ-on-chip scale).

## Arterial stenosis hemodynamics (`atherosclerosis-cfd.html`)

A quasi-1-D reduction of the incompressible Navier–Stokes equations models blood flow through an atherosclerotic plaque, in either a **straight artery** or a **carotid-style bifurcation** (flow divides between two daughter branches by resistance, with a flow divider and sinus/bulb). Adjustable in real time: geometry mode, stenosis severity (% area reduction), plaque asymmetry (concentric → eccentric, or bilateral → unilateral in bifurcation mode), inlet velocity, dynamic viscosity, artery diameter, plaque length, blood density, and steady vs. pulsatile flow.

- **Continuity** \(U(x) = U_0 (D/H(x))^2\) drives the stenotic jet.
- **Reynolds number** \(Re = \rho V D / \mu\) updates live and flags laminar / transitional / turbulent regimes.
- **Poiseuille wall shear** \(\tau_w = 8\mu U / H\) and viscous loss \(dp/dx = 32\mu U/H^2\); **Bernoulli + Borda–Carnot** estimate the pressure drop.
- **Bifurcation mode** adds daughter-branch flow division by viscous conductance, an apex flow divider (high shear), and a carotid sinus with low / reversed outer-wall shear — the preferential site of plaque.
- Velocity heat map, particle streamlines, velocity vectors, a pressure band, and wall-shear coloring, plus axial plots of velocity, pressure, and wall shear stress. The tool labels which quantities are directly calculated, estimated, or qualitative, and is a teaching model — not a validated clinical CFD simulation.

## How to use

Switch tabs in the header. Hydrostatics and capillary panels update as soon as you move a slider. No install required.
