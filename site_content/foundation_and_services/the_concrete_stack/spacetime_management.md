---
title: Spacetime management
parent: The CONCRETE stack
nav_order: 9
---
# Spacetime management
{: .fs-9 .no_toc }


Clocks are critical
{: .fs-6 .fw-300 }
----

Although not always obvious, clocks play many crucial roles within digital systems. For example, as pure periodically ticking devices, they are used to orchestrate the movement of data within chips, and as frequency references for sensors. As time-keeping devices, when these ticks are counted, they are used when time-stamping events, and in navigation systems such as GPS.

Within a distributed system, there are many functions that require these clocks to be synchronised eg when seeking to combine data from sensors connected to different nodes.  There are also various security-related concerns with clocks eg it might be important that accurate times of events are being recorded within a security system.  As clocks affect system behaviour, it is important, in some situations, to consider how (re)sychronisation events could effect users (eg it could cause a vehicle's navigation solution to jump, that in turn causes the vehicle to move). Users do not want unknown ghosts in the machine (LINK).

Clock accuracy, performance, and capability are closely related; there are many benefits to be gained by using more accurate clock references.  Of note though, clock references are now accurate enough that we need to consider relativistic spacetime effects.  That is, we have to take into account that clocks run faster or slower depending their positions and speeds.  Clocks and navigation systems are inextricably linked at these levels of accuracy.  

Countries typically maintain national time references, it is important for CONCRETE to establish technologies, approaches, and services to enable spacetime synchronisation.



