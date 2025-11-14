---
title: "AWI Science Week poster"
excerpt: 'Essentially a two-month update on CELLO!'
collection: works
---

My newest plume video:

<video width="519" height="360" controls>
  <source src="/files/plume2D_mrb_094_T_fullWidth.h264" type="video/h264">
  Your browser does not support the video tag.
</video>

This model setup uses a heavily-modified MITgcm `tutorial_deep_convection` test case. Some highlights:
 * Resolution: $4$ m $\times$ $4$ m $\times$ variable in the vertical ($1$ m at the surface to $11$ m at depth)
 * Domain: $594$ $\times$ $33$ $\times$ $99$ grid cells (9 cores)
 * Initialisation: Temperature and salt profile from mooring time series (24 h mean starting from noon on September 12, 2021)
 * Initial velocities are $0$ m s$^{-1}$ in all directions 
 * Timestep: $4$ s
 * Equation of state: TEOS-10
 * Coriolis: $f_0=-1.358 \times 10^{-4}$, $\beta=8.194 \times 10^{-12}$
 * Boundary conditions: `no_slip_bottom` and `no_slip_sides` are both `.FALSE.`, with no tracer relaxation sponges
 * Surface forcing: Constant heat flux of -$200$ W m$^{-2}$ and a salt flux following Stefan's law for the first 24 h, then forcings ceased for the last 12 h
 * Surface temperature limitation (i.e., `allowFreezing=.TRUE.`): `Tfreezing=-1.9` (i.e., a wee bit of supercooling)
 * Non-hydrostatic solver: `cg3dMaxIters=40` 
 * Advection scheme: `tempAdvScheme` and `saltAdvScheme` are both $33$ (and diffusivities are all $0$)
 * Viscosity: Three dimensional Smagorinsky scheme with default coefficient

![Science Week poster](/images/Brown_ScienceWeek_poster.png)