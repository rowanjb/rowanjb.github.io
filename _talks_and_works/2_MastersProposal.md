---
title: "Master's research proposal"
excerpt: "Proposal for my master's research, which I'm posting to serve as writing sample"
collection: talk_and_works
---

Introduction
=====

It is estimated that human activity has caused an increase of at least 1.0 °C in mean air temperature compared to pre-industrial levels, and that the current rate of emissions will lead to an additional increase of 3.7 °C by the end of the current century (Pörtner et al., 2019). The potential effects of this warming process on the hydrosphere are diverse, and include changes in ocean circulation, temperature, oxygen content, and acidity, which in turn pose risks such as increased flooding due to sea level rise, decreased biodiversity, and threats to food and water security.

Climate variability and ocean dynamics have long been linked by paleoceanographers, and past millennial-scale climate warming and cooling has been attributed to variability in the Atlantic Meridional Overturning Circulation (AMOC) (Lozier et al., 2019). For example, during the most recent ice age, pronounced evidence in the ice-core records revealed warming and cooling superimposed on the glacial timescale, and analyses of multiple proxies suggested a connection between these climate oscillations and the AMOC (Hirschi et al., 2020).

A fundamental role of the ocean is the uptake and redistribution of heat, anthropogenic carbon dioxide, and oxygen from the atmosphere. This is accomplished efficiently in areas of deep convection, such as the Labrador Sea (LS), where buoyancy loss in surface waters can result in sinking to depths greater than 2,000 m (Garcia-Quintana et al., 2019). As these surface waters sink, they transport dissolved oxygen and carbon dioxide from the atmosphere and inject them into the deep ocean. At the same time, this sinking helps to drive basin-scale overturning circulation by connecting the shallow and deep branches of the AMOC, although the exact relationship between LS deep convection and variability in the AMOC is still under debate (e.g., Feucher et al., 2019; Yashayaev & Loder, 2016; Menary et al., 2020; Lozier et al., 2019).

There is therefore an important relationship between deep convection in the LS and the wider Earth system via (1) its role in the large-scale circulation and (2) its role as a conduit for dissolved gases entering the deep Atlantic. In this proposal, an overview on LS deep convection and its representation in numerical models is given. The following three salient questions are then identified: how accurate is the representation of LS deep convection when including (1) the parameterization for restratification proposed by Fox-Kemper et al. (2008) (hereafter referred to as the Fox-Kemper scheme) and (2) tidal forcing? And (3) what are the pathways of deep water out of the LS when using these two schemes? I propose to investigate these questions, specifically using a numerical model with a resolution consistent with large-scale coupled climate models. My results might then be used to inform future large-scale modelling studies by identifying when the two aforementioned schemes should be employed.

Background
=====

Deep convection in the LS occurs when heat loss from the ocean to the atmosphere causes surface waters to become denser and sink. This facilitates the exchange of dissolved gases and heat between the atmosphere and the deep ocean. It also results in the production of Labrador Sea Water (LSW), which is distinctly characterized by low salinity and high concentrations of oxygen and anthropogenic carbon dioxide (Rhein et al., 2017). These characteristics allow it to be identified throughout deep North Atlantic, where it is exported as part of the AMOC lower limb.

There are three requirements for seasonal deep convection: strong atmospheric forcing where cold, dry winds from over land or ice induce significant heat flux at the sea surface; pre-existing weak stratification in the water column, which can be an aftereffect of deep convection from the previous year; and underlying waters that are consistently brought to the surface, which is favoured by cyclonic circulation and the resultant doming of isopycnals (Lab Sea Group, 1998). The LS satisfies all three of these requirements; for example, heat loss during the cold months can exceed 400 W m2 (Courtois et al., 2020). This results in reoccurring wintertime deep convection.

It is useful to consider deep convection in the following three stages: preconditioning (of the order 100 km), in which gyre-scale circulation and buoyancy forcing reduce stratification and predispose an area to overturn; active deep convection (on scales of order 1 km), in which deep mixing is contained within relatively narrow plumes; and post-convection lateral exchange (of order 5–100 km) between plumes and their surroundings, which works to restore stratification (Lab Sea Group, 1998). Figure 1 shows these stages illustratively.

Hence, deep convection in the LS is governed mainly by ocean-atmosphere heat flux due to its effects on buoyancy stratification. However, stratification can also be modulated by freshwater exchange because salty water is denser than freshwater. In other words, freshwater overlying saltier water will require additional heat loss to induce sinking.

Within the LS, both freshwater and heat can be imported from the cyclonic flowing boundary currents, thereby affecting the spatial distribution of deep convection. It is there- fore necessary to include a short discussion on these currents. They are illustrated below in Figure 2. The two relevant currents are the West Greenland Current (WGC) in the eastern LS and the Labrador Current (LC) in the west.

Both the WGC and the LC are characterized by cold and fresh water of Arctic origin separated by a thermohaline front from warmer and saltier water of Atlantic origin. Beneath the LC and along the deep continental slope is the deep Labrador Current (DLC). The DLC is part of the vigorous Deep Western Boundary Current (DWBC), which contains the bulk of the Sverdrup return flow of the subpolar gyre (Fratantoni & Pickart, 2007) as well as North Atlantic Deep Water, of which a large portion is LSW (Dengler et al., 2006).

Fluxes of heat and freshwater from boundary currents modulate LS deep convection via two types of eddies: Irminger Rings (IRs) and Boundary Current Eddies (BCEs) (Chanut et al., 2008). While IRs are generated by instabilities off Cape Desolation, BCEs are gen- erated throughout the full length of the boundary current system. Together, they work to counteract ocean-atmosphere buoyancy loss so that stratification is maintained, effectively inhibiting deep convection throughout much of the interior LS. This effect is minimal within the southwest LS, so seasonal deep convection is usually limited to this region.
A third important eddy type in the LS is generated by baroclinic instabilities following intra-plume deep convection, when isopycnals are sloped away from horizontal and towards vertical—in other words, when neighbouring waters at a given depth have different densities. This results in horizontal density gradients and so-called Convective Eddies (CEs) (Chanut et al., 2008). CEs and BCEs work in concert to play a critical role in the third stage of deep convection, lateral exchange, in which BCEs import heat from the boundary currents and CEs mix it with the convective plumes to induce restratification, eventually resulting in the production of LSW.

Numerical modelling of the Labrador Sea
=====

State-of-the-art models of the LS can have very high resolutions. For example, VIKING20X and its predecessor VIKING20 are 1/4° simulations with 1/20° nests of the North Atlantic. LAB60, which has an even higher resolution, represents the LS using a 1/60° nest within the larger 1/4° Arctic Northern Hemisphere Atlantic (ANHA4) simulation (Pennelly & Myers, 2020). Figure 3 shows the ANHA4 domain as well as the nested domains of LAB60 and SPG12, which is an intermediate 1/12° nest of the subpolar gyre. ANHA4 and its nests are built on the primitive equation Nucleus for European Modelling of the Ocean model (NEMO) coupled with the Louvain-la-Neuve Ice Model (LIM2).

General circulation models like NEMO carefully employ simplifications to limit computational expense. These include the Boussinesq hypothesis, the hydrostatic hypothesis (the consequences of which are explored below), incompressibility, the neglecting of certain terms in the momentum equation, and more (Madec et al., 2022). While these simplifications can reduce computational costs, they risk representing certain processes poorly, such as vertical mixing during deep convection, thereby making parameterizations necessary.

Mixing processes, such as those occurring in deep convection, can happen on small scales. High-resolution models like LAB60 are therefore useful because they are more skilled at cap- turing small-scale processes, and hence rely less strongly on simplifying assumptions (Pennelly & Myers, 2020; Hirschi et al., 2020). The problem with these models is the high computa- tional expense required to run them, and consequently many high-resolution numerical stud- ies only cover small geographic regions. For example, Figure 3 shows how much smaller the 1/60° LAB60 nest is than its parent 1/4° ANHA4 domain. Therefore, many recent large-scale coupled ocean-atmosphere models, such as those used in the 2019 Intergovernmental Panel on Climate Change (IPCC) special report The Ocean and Cryosphere in a Changing Climate (Pörtner et al., 2019), still utilize resolutions of 1/4° or coarser.

Deep convection in models
===

All NEMO-based configurations, including LAB60 and ANHA4, make the hydrostatic as- sumption (Madec et al., 2022). This reduces the vertical momentum equation to a balance of pressure and buoyancy, expressed mathematically as .

In the case of deep convection, motion occurs over scales that are not consistent with this assumption and which are not resolved by the model, so mixing must therefore be parameterized. In LAB60 and ANHA4, instabilities are handled using the ‘Enhanced vertical diffusion’ parameterization from NEMO, in which vertical eddy mixing coefficients are greatly increased wherever stratification is unstable. This results in horizontal pressure gradients (i.e., sloping isopycnals) that can in turn result in instabilities like CEs and other mixed layer eddies. These help to restratify the upper ocean following wintertime buoyancy loss (Fox-Kemper et al., 2008; Lab Sea Group, 1998).

Fox-Kemper et al. (2008) and companion papers present the theory and numerical implementation of a streamfunction-based parameterization for restratification due to small-scale ageostrophic baroclinic instabilities (the Fox-Kemper scheme). In essence, it works by tilting isopycnals from the vertical to the horizontal. Without it, this aspect of restratification is often ignored, resulting in artificially weak surface stratification.

Within their own coarse-resolution simulations, the authors found that their parameteri- zation provided novel climate sensitivity. However, while it is implemented within NEMO, its effects on LS deep convection have not yet been directly investigated. I propose to perform this study as part of my master’s research.

Tides in models
===

Tides are caused by the centrifugal and gravitation forces of the Earth, Moon, Sun, and other planets (Sutherland, 2010). They are a vital driver of meridional overturning circulation via their role in deep mixing, supplying an estimated 3.7 TW of mechanical energy for dissipation in the oceans. There is therefore an intricate link between the energetics of meridional overturning circulation and small-scale mixing from tides (Munk & Wunsch, 1998).

Tides are initially barotropic until they break over rough topography and generate baroclinic internal waves, a process known as baroclinic conversion. This dissipates a fraction of the tidal energy by conversion into successively smaller scales (Sutherland, 2010). Tidally generated baroclinic internal waves are particularly important because they are associated with enhanced diapycnal mixing. This, in turn, can alter the local vertical structure (Epstein, 2018), potentially affecting the strength of deep convection and the vertical transport of heat, salt, and dissolved gases.

In numerical models, diapycnal mixing is often parameterized using prescriptions of vertical diffusivity. Past modelling studies have shown that heat transport and the uptake and storage of tracers is sensitive to this parameterization (Epstein, 2018). Recently, it has become more practical to include tidal forcing within the model, eliminating the need for reliance on such parameterizations but creating the need for validation of the tidal forcing schemes.

In the LS, the possible effects of tides on deep convection are numerous and complex. For example, in the Arctic, tidal parameterizations were found to decrease stratification, leading to decreased ice concentration, decreased albedo, and increased freshwater export (Epstein, 2018). This could in turn increase LS stratification and inhibit convection. Conversely, tides could enhance local mixing, thereby having the opposite effect. Hence, the effects of tidal forcing on LS deep convection warrant further study, which I propose to include within my master’s research.

Labrador Sea Water export pathways
===

LSW is characterized by low salinity, low potential vorticity, and high concentrations of dis- solved tracers (Rhein et al., 2017). It can also be characterized by its density, which typically ranges from 27.68 kg m-3 to 27.80–27.82 kg m-3 (Garcia-Quintana et al., 2019; Courtois et al., 2020). A significant volume of LSW is exported from the LS via the DLC, which forms part of the DWBC. The DWBC extends throughout the North Atlantic, providing a conduit for LSW southward into the tropics. Some LSW also exits eastward into the Irminger Basin, with the potential to re-enter the LS via the WGC (Kieke et al., 2009).

Total transport in the DWBC is around 30 Sv, depending on latitude, recirculation gyres, etc. (Dengler et al., 2006; Fischer et al., 2010). A majority of this transport is LSW, supplemented by other recently ventilated waters. Flowing southward, these waters are continuously shed into the interior North Atlantic, with significant detrainment around the Tail of the Grand Banks (Gary et al., 2012; Rhein et al., 2015). Therefore, both the DWBC and interior pathways are important for the southward flux of LSW. Interior pathways are also important because they bring ventilated water, carrying oxygen and carbon, into the deep interior where they would be otherwise scarce.

However, it is difficult to quantify the transport of LSW by interior pathways. An unquantified amount is thought to flow out of the subpolar gyre along the Mid-Atlantic Ridge. Other pathways flow through the Irminger Sea and into the eastern subpolar gyre (Kieke et al., 2009). There is also disagreement about how strongly LSW is entrained within the DWBC; for example, Gary et al. (2012) argue that only a small proportion of LSW particles are transported continuously within the DWBC, and that the majority are ejected before rejoining north of 26°N. Conversely, Rhein et al. (2015) argue that a larger proportion of particles are consistently entrained in the current, and that the release of ventilated particles is monotonic.

Identifying the pathways of LSW within the North Atlantic and quantifying their trans- port is an active area of research. Within numerical models, the representation of LSW pathways is dependent on disparate factors, such as bottom topography, frontal represen- tation, and LSW production. It also requires a large domain, eliminating the possibility of employing high-resolution models like LAB60. I hypothesize that the schemes discussed in Sections 3.1 and 3.2 will change the representation of deep convection, which could in turn lead to a more accurate understanding of LSW pathways. I therefore propose to include the study of LSW pathways within my master’s research.

Proposal
=====

Deep convection occurs in the LS, where it results in the production of LSW. Variability in LS deep convection has been linked to variability in the strength of the AMOC (e.g. Feucher et al., 2019), although recent research has called into question the precept that LS density anomalies drive AMOC variability (Menary et al., 2020; Lozier et al., 2019). Whether this is true or not, LS deep convection is also important as a way for young LSW, which is rich in oxygen and carbon dioxide, to enter the deep North Atlantic (Rhein et al., 2017; Garcia- Quintana et al., 2019). However, a complete and quantitative understanding of its spread within the North Atlantic is an open question.

I propose to study deep convection in the LS using the ANHA4 model. It has a 1/4° resolution, which is consistent with many large-scale coupled models that are used to study climate change. Specifically, I propose to investigate the effects of (1) the Fox-Kemper scheme for restratification and (2) tidal forcing. I hypothesize that these will improve the representation of LS deep convection when compared to the high-resolution LAB60 model and observations. I also propose to study the pathways of LSW within the North Atlantic, and I hypothesize that the improved representation of LS deep convection will allow the identification of more accurate LSW pathways.

To this end, the representation of LS deep convection and LSW pathways will be compared between model runs with schemes (1) and (2), only scheme (2), and with neither. Where possible, the results will also be compared with those from LAB60 and observational data, although this is dependent on data availability and computational resources. Ultimately, whether the representation of LS deep convection is improved, I believe that my research could inform future modelling efforts by showing the importance of employing the two aforementioned schemes. My research might also add to the body of literature on LSW pathways, in which there is currently no consensus.

Budget
=====

M.Sc. funding: $2,000 per month for 24 months
Conference travel (potentially ‘The Ocean Sciences Meeting’, 2024): $3,000
Publication fees (two publications): $4,000
Computational costs (share of Compute Canada high performance computing allocation): $7,000

Timeline
=====
March - April 2023: Complete coursework
May - June 2023: Complete initial analysis of existing ANHA4 model runs (e.g., calculate fluxes, freshwater content, convective resistance, mixed layer depth, internal pathways etc.) July - December 2023: Repeat analyses on LAB60; compare representation of mixing in coarse and high-resolution models; compare with observational dataset(s)
January - June 2024: Synthesize results and write thesis

References
=====

Chanut, J., Barnier, B., Large, W., Debreu, L., Penduff, T., Molines, J. M., & Mathiot, P. (2008). Mesoscale eddies in the labrador sea and their contribution to convection and restratification. Journal of Physical Oceanography, 38(8), 1617–1643.

Courtois, P., Garcia-Quintana, Y., Hu, X., & Myers, P. G. (2020). Kinematic subduction rate of labrador sea water from an eddy-permitting numerical model. Journal of Geophysical Research: Oceans, 125(7), e2019JC015475.

Dengler, M., Fischer, J., Schott, F. A., & Zantopp, R. (2006). Deep labrador current and its variability in 1996–2005. Geophysical Research Letters, 33(21).
Epstein, J.-L. (2018). The impact of internal tide mixing parameterizations in an eddy- permitting model of the arctic ocean (Doctoral dissertation, University of British Columbia). doi: http://dx.doi.org/10.14288/1.0365809

Feucher, C., Garcia-Quintana, Y., Yashayaev, I., Hu, X., & Myers, P. G. (2019). Labrador sea water formation rate and its impact on the local meridional overturning circulation. Journal of Geophysical Research: Oceans, 124(8), 5654–5670.

Fischer, J., Visbeck, M., Zantopp, R., & Nunes, N. (2010). Interannual to decadal variability of outflow from the labrador sea. Geophysical Research Letters, 37(24).

Fox-Kemper, B., Ferrari, R., & Hallberg, R. (2008). Parameterization of mixed layer eddies. part i: Theory and diagnosis. Journal of Physical Oceanography, 38(6), 1145–1165.

Fratantoni, P. S., & Pickart, R. S. (2007). The western north atlantic shelfbreak current system in summer. Journal of Physical Oceanography, 37(10), 2509–2533.
Garcia-Quintana, Y., Courtois, P., Hu, X., Pennelly, C., Kieke, D., & Myers, P. G. (2019). Sensitivity of labrador sea water formation to changes in model resolution, atmospheric forcing, and freshwater input. Journal of Geophysical Research: Oceans, 124(3), 2126– 2152.

Gary, S. F., Lozier, M. S., Biastoch, A., & Böning, C. W. (2012). Reconciling tracer and float observations of the export pathways of labrador sea water. Geophysical Research Letters, 39(24).

Hirschi, J. J.-M., Barnier, B., Böning, C., Biastoch, A., Blaker, A. T., Coward, A., . . . others (2020). The atlantic meridional overturning circulation in high-resolution models.

Journal of Geophysical Research: Oceans, 125(4), e2019JC015522.

Kieke, D., Klein, B., Stramma, L., Rhein, M., & Koltermann, K. P. (2009). Variability and propagation of labrador sea water in the southern subpolar north atlantic. Deep Sea

Research Part I: Oceanographic Research Papers, 56(10), 1656–1674.

Lab Sea Group. (1998). The labrador sea deep convection experiment. Bulletin of the American Meteorological Society, 79(10), 2033–2058.

Lozier, M. S., Li, F., Bacon, S., Bahr, F., Bower, A. S., Cunningham, S., . . . others (2019). A sea change in our view of overturning in the subpolar north atlantic. Science, 363 (6426), 516–521.

Madec, G., Bell, M., & Bourdallé-Badie, R. (2022). Nemo ocean engine version 4.2.0 [Computer software manual]. 11 Bd d’Alembert, 78280 Guyancourt, France.

Menary, M. B., Jackson, L. C., & Lozier, M. S. (2020). Reconciling the relationship between the amoc and labrador sea in osnap observations and climate models. Geophysical Research Letters, 47(18), e2020GL089793.

Munk, W., & Wunsch, C. (1998). Abyssal recipes ii: Energetics of tidal and wind mixing.

Deep Sea Research Part I: Oceanographic Research Papers, 45(12), 1977–2010. Pennelly, C., & Myers, P. G. (2020). Introducing lab60: A 1/ 60° nemo 3.6 numerical
simulation of the labrador sea. Geoscientific Model Development, 13(10), 4959–4975. Pörtner, H.-O., Roberts, D. C., Masson-Delmotte, V., Zhai, P., Tignor, M., Poloczanska, E., & Weyer, N. (2019). The ocean and cryosphere in a changing climate. IPCC Special
Report on the Ocean and Cryosphere in a Changing Climate.

Rhein, M., Kieke, D., & Steinfeldt, R. (2015). Advection of north atlantic deep water from the labrador sea to the southern hemisphere. Journal of Geophysical Research: Oceans, 120(4), 2471–2487.

Rhein, M., Steinfeldt, R., Kieke, D., Stendardo, I., & Yashayaev, I. (2017). Ventilation variability of labrador sea water and its impact on oxygen and anthropogenic carbon: a review. Philosophical Transactions of the Royal Society A: Mathematical, Physical and Engineering Sciences, 375(2102), 20160321.
Sutherland, B. R. (2010). Internal gravity waves. Cambridge University Press. doi: 10.1017/CBO9780511780318

Yashayaev, I., & Loder, J. W. (2016). Recurrent replenishment of labrador sea water and associated decadal-scale variability. Journal of Geophysical Research: Oceans, 121 (11), 8095–8114.