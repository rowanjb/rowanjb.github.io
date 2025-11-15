---
title: "AWI Science Week poster"
excerpt: 'Essentially a two-month update on CELLO!'
collection: works
---

My newest plume video:

<video width="519" height="360" controls>
  <source src="/files/plume2D_mrb_094_T_fullWidth.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

The goal is to recreate a plume that occurred over the 36 hours between noon on September 13 (2021) and midnight on September 15--16.

Our model setup uses a heavily-modified MITgcm `tutorial_deep_convection` test case.  Some key changes:
 * Resolution: $4$ m $\times$ $4$ m $\times$ variable in the vertical ($1$ m at the surface to $11$ m at depth)
 * Domain: $594$ $\times$ $33$ $\times$ $99$ grid cells (9 cores)
 * Initialisation: Temperature and salt profile from mooring time series (24 h mean starting from noon on September 12, 2021)
 * Initial velocities: $0$ m s$^{-1}$ in all directions 
 * Timestep: $4$ s
 * Equation of state: TEOS-10
 * Coriolis: $f_0=-1.358 \times 10^{-4}$, $\beta=8.194 \times 10^{-12}$
 * Boundary conditions: `no_slip_bottom=.FALSE.` and `no_slip_sides=.FALSE.`, with no tracer relaxation sponges
 * Surface forcing: Buoyancy forcing is applied for 24 hours through a 100 m-wide pseudo sea ice lead; the heat flux is constant at -$200$ W m$^{-2}$ and the salt flux follows Stefan's law
 * Surface temperature limitation (i.e., `allowFreezing=.TRUE.`): `Tfreezing=-1.9` (i.e., a bit of supercooling)
 * Non-hydrostatic solver: `cg3dMaxIters=40` 
 * Advection scheme: `tempAdvScheme=33` and `saltAdvScheme=33` (and no prescribed diffusivities)
 * Viscosity: Three dimensional Smagorinsky scheme with the default coefficient

![Science Week poster](/images/Brown_ScienceWeek_poster.png)
