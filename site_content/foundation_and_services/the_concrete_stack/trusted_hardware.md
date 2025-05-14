---
title: Trusted Hardware
parent: The CONCRETE stack
nav_order: 1
---

# Trusted Hardware
{: .fs-9 .no_toc }


Risk management associated with chips
{: .fs-6 .fw-300 }
----

Hardware can never be fully trusted - this isn't a binary trusted / un-trusted thing - this is about risk (again).

Add a section about FPGAs / FPGA-like things.

Is it what I think it is?

Has it been tampered with?

Even if it is what I think it is, does it do what I expect it does?

Linking with seL4, does the hardware work in a deterministic way?

Design and supply chain - not just about having a sovereign chip manufacturing facility.  

The properties and organisational principles of such facilities become important.  

Not necessarily about having the most densely packed chips.  

Nor is it about having the most sophisticated techniques working in-silica - sometimes this might act against the underlying need for strong determinism.

There are probably things here where we do want to do stuff in silica, that we don't already.  Eg networking, resource management / MoveVM, supervision etc. 

And remember that huge foundaries also make great targets.

Not just about chips - although they play a major role - also about all the other hardware.

There are opportunities to better design chips with 'trust' in mind eg making them harder to de-cap without people noticing.  Eg continuous polling to check that something is still turned on.

Potential for running on-chip software to help to monitor factors that change our perception of risk associated with some hardware.

Also related to physical security measures - we'll want to use CONCRETE nodes to help to monitor CONCRETE nodes to help to ensure that they are not being modified in some way.

Hand-me-down hardware - because this is about the management of risk, if a processor's provenance becomes too 'unknown'/risky for one use, doesn't mean that it has to be scrapped, it could still be used for other things.



