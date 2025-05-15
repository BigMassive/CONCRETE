---
title: Maths Standards
parent: The CONCRETE stack
nav_order: 12
---
# Maths standards
{: .fs-9 .no_toc }


So things add up right
{: .fs-6 .fw-300 }
----

To start with a well-known example about why maths standards are important in CONCRETE, most computer systems can accurately complete integer arithmetic (1 + 1 = 2), but they struggle to consistently deal with numbers with decimal points (+1.5625).  Binary representations of numbers in computers can only have a finite number of 0s and 1s (a typical way of representing these kinds of numbers within a 32 bit computer is shown below).

![a binary representation of a floating point number](../../../../images/current/floating_point_in_binary.png)

Only having a finite number of 0s and 1s means that a computer cannot directly represent a 'real' number that has infinitely many decimal places.  A finite number of 0s and 1s can only represent a finite number of real numbers (green marks on a number line below)  

![not all the real numbers can be represented in a finite number of binary bits, there are always gaps](../../../../images/current/floating_point.png)

If a calculation should generate a number that is not representable (eg adding 2 numbers together where the answer does not coincide with a green mark above), a decision about how to be inaccurate is needed.  There are many 'standards', but is no standard 'right way' of dealing with these situations. This is important in general, but within a flexible, distributed, decentralised system, such as CONCRETE, we do not want the outcomes or answers to calculations to depend on where they are run. This would break our [understandability and predictability]({% link site_content/foundation_and_services/some_basic_needs.md%}#understandability-and-predictability) requirement. 

The need for maths standards goes beyond these high-level number-representation considerations, all the way to the roots of mathematics. This standardisation is part of what it means to be foundational.

