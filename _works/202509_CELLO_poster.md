---
title: "CELLO poster"
excerpt: 'Essentially a four-month update on EGU25'
collection: works
---

My newest plume video:

<video width="519" height="360" controls>
  <source src="/files/plume2D_mrb_052_T.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

This model setup is based on the `tutorial_deep_convection` test case with the following modifications:
 * Resolution: $2$ m $\times$ $2$ $m $\times$ $2$ m
 * Domain: $198$ $\times$ $198$ $\times$ $198$ grid cells
 * Initialisation: Temperature and salt profile from mooring time series (three-day mean around September 4, 2021) with a normalised WOA September climatology used to fill at each depth level (temperature is prevented from freezing and static instabilities are homogenised to ensure $N**2 > 0$). This results in a staircase and other sharp points in the potential density profile which are smoothed out using a short integration with very high diffusivities.
 * Initial velocities are $0$ m s$^{-1}$ in all directions 
 * Timestep: $2$ s
 * Equation of state: TEOS-10
 * Coriolis: $f_0=-1.358 \times 10^{-4}$, $\beta=8.194 \times 10^{-12}$
 * Boundary conditions: `no_slip_bottom` and `no_slip_sides` are both `.FALSE.`, with no tracer relaxation sponges
 * Surface forcing: Constant salt flux of $0.03$ g m$^{-2}$ s$^{-1}$ and heat flux of -$200$ W m$^{-2}$
 * Surface temperature limitation (i.e., `allowFreezing=.TRUE.`): `Tfreezing=-1.85` (i.e., a wee bit of supercooling)
 * Non-hydrostatic solver: `cg3dMaxIters=40` 
 * Advection scheme: `tempAdvScheme` and `saltAdvScheme` are both $33$ and diffusivities are all $0$
 * Viscosity: therein lies the question... 

There are still lots of improvements to be made, but this is my current best effort!

![CELLO poster](/images/RowanBrown_EGU25_poster_final.png)