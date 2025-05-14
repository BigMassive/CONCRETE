---
title: The CONCRETE stack
parent: Foundation and Services
nav_order: 2
has_toc: false
---

# The CONCRETE stack
{: .fs-9 .no_toc }


A technical sketch
{: .fs-6 .fw-300 }
----

The [basic user needs]({% link site_content/foundation_and_services/some_basic_needs.md %}) drive us to taking a distributed and decentralised approach, where to be foundational is to describe what it means to be a single abstract node.[^caveat]

[^caveat]:
    <span>To-do</span>{: .label .label-blue} This is a slight lie. The technical stack depicted assumes that all nodes have processors with operating systems.  While this is likely to represent many devices it would be possible to define a node in other ways - more work required.  Similarly, a raw processor is unlikely to be useful without other peripherals.  Further work is required to understand how these fit in with the trusted hardware layer. Amongst many other things, this signals the need for an approach to hardware identity.

![In a distributed decentralised system everything is just an abstract node](../../../../images/current/abstract_node.png)

The diagram below is a technical sketch of the make-up of an abstract node and some key ancillary functions. This should not be taken literally. The components shown act as a shorthand description; we should really add '-like' at the end of most of them. This is just a starting point for refinement.  The need for many of these components can be deduced directly from the basic user needs; some appear here out-of-the blue and are introduced later. From a major technical sub-component perspective though, **this is it**.  This section provides introductions to these components individually and then provides more insight into bringing them together. The next socio-technical section does not add more components, it adds detail about how this would be configured and used.  

![stack of concrete components](../../../../images/current/CONCRETE_stack_2.png)

| Component                                                                                                                                                    | Description                                                                  |
|:-------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------|
| [Trusted Hardware]({% link site_content/foundation_and_services/the_concrete_stack/trusted_hardware.md %})                                                   | The physical hardware and associated risks.                                  |
| [&#174; seL4]({% link site_content/foundation_and_services/the_concrete_stack/seL4.md %})                                                                    | The world's most highly assured operating system kernel.                     |
| [Ouroboros]({% link site_content/foundation_and_services/the_concrete_stack/ouroboros.md %})                                                                 | Networking.                                                                  |
| [IPFS]({% link site_content/foundation_and_services/the_concrete_stack/ipfs.md %})                                                                           | Distributed, decentralised data storage.                                     |
| [IOTA]({% link site_content/foundation_and_services/the_concrete_stack/iota.md %})                                                                           | Distributed ledger and compute.                                              |
| [Wallet]({% link site_content/foundation_and_services/the_concrete_stack/wallet.md %})                                                                       | Somewhere to store cryptographic keys etc.                                   |
| [Matrix]({% link site_content/foundation_and_services/the_concrete_stack/matrix.md %})                                                                       | Distributed, decentralised communications media.                             |
| [Security and Risk]({% link site_content/foundation_and_services/the_concrete_stack/security_and_risk.md %})                                                 | Applications associated with security and risk.                              |
| [Spacetime Management]({% link site_content/foundation_and_services/the_concrete_stack/spacetime_management.md %})                                           | Infrastructure and processes associated with clock synchronisation           |
| [Dongles]({% link site_content/foundation_and_services/the_concrete_stack/dongles.md %})                                                                     | Non-nodal devices for users and security.                                    |
| [HMI Best Practice]({% link site_content/foundation_and_services/the_concrete_stack/hmi_best_practice.md %})                                                 | Human Machine Interface standards - crucial for efficiency and effectiveness |
| [Maths Standards]({% link site_content/foundation_and_services/the_concrete_stack/maths_standards.md %})                                                     | 1.0 + 1.0 should always equal 2.0 no matter where it is calculated          |
| [Single 4D Ontological Data Model Approach]({% link site_content/foundation_and_services/the_concrete_stack/single_4d_ontological_data_model_approach.md %}) | The ultimate in data interoperability and quality                            |






