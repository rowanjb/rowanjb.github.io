---
title: "EGU25 poster and plume video"
excerpt: 'Showing what I mean by "shallow open-ocean convective plumes"'
collection: works
---

This video shows a shallow open-ocean convective plume modelled using MITgcm. 

<video width="519" height="360" controls>
  <source src="/files/plume2D_mrb_052_T.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

My current model setup is based on the `tutorial_deep_convection` test case with the following modifications:
 * Horizontal resolution: $20$ m
 * Vertical resolution: Variable from $1$ m to $38$ m
 * Domain: $150$ $\times$ $150$ $\times$ $50$ grid cells (i.e., $3$ km $\times$ $3$ km $\times$ $500$ m)
 * Initialisation: Temperature and salt profile from mooring time series (September 13, 2021) with WOA September climatology used to fill above and below the mooring measurements; initial velocities are $0$ m/s in all directions 
 * Timestep: $3$ s
 * Equation of state: TEOS-10
 * Coriolis: $f_0=-1.358 \times 10^{-4}$, $\beta=8.194 \times 10^{-12}$
 * Boundary conditions: `no_slip_bottom` and `no_slip_sides` are both `.FALSE.`, with tracer relaxation using sponges 10 cells thick at the sides and 15 cells thick at the bottom
 * Surface forcing: Salt flux of $0.03$ for $30$ hours (i.e., very high) and heat flux of -$5000$ W/m$^2$ for $70$ hours (i.e., extremely high, but also using...)
 * Surface temperature limitation (i.e., `allowFreezing=.TRUE.`): `Tfreezing=-2.05` (i.e., probably too low!)
 * Non-hydrostatic solver: `cg3dMaxIters=40` 
 * Advection scheme: `tempAdvScheme` and `saltAdvScheme` are both $33$ and diffusivities are all $0$
 * Viscosity: `viscAh` and `viscAz` are both $4 \times 10^{-2}$

There are still lots of improvements to be made, but this is my current best effort!

I made this video to accompany the following poster, which itself was made for the EGU General Assembly 2025.

![EGU25 poster](/images/RowanBrown_EGU25_poster_final.png)