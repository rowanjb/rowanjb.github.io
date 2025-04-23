---
title: "Plume video"
excerpt: 'What do I mean by "shallow open-ocean convective plumes?'
collection: works
---

This video shows a shallow open-ocean convective plume modelled using MITgcm. 

<video width="519" height="360" controls>
  <source src="/files/plume2D_mrb_052_T.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Model setup (based on the `tutorial_deep_convection` test case with the following modifications):
 * Domain: $150$ $x$ $150$ $x$ $50$
 * Horizontal resolution: $20$ $m$
 * Vertical resolution: Variable from $1$ $m$ to $38$ $m$
 * Initialisation: Temperature and salt profile from mooring timeseries (September 13, 2021) with WOA September climatology filling above and below the mooring measurements; initial velocities are $0$ $m/s$ in all directions 
 * Timestep: $3$ $s$
 * Equation of state: TEOS-10
 * Coriolis: $f_0=-1.358E-4$, $\beta=8.194E-12$
 * Boundary conditions: `no_slip=.FALSE.` with tracer relaxation
 * Surface forcing: Salt flux of $0.03$ for $40$ hours (i.e., very high) and heat flux of $-5000$ $W/m^2$ for $70$ hours (i.e., extremely high, but also with...)
 * Surface temperature limit (i.e., `allowFreezing=.TRUE.`): `Tfreezing=-2.05` (i.e., probably too low!)
 * Non-hydrostatic solver: `cg3dMaxIters=40` 
 * Advection scheme: `tempAdvScheme` and `saltAdvScheme` are both $33$ and diffusivities are all $0$
 * Viscosity: `viscAh` and `viscAz` are both $4.E-2$

There are still lots of improvements to be made, but this is my current set up in late April 2025.
 