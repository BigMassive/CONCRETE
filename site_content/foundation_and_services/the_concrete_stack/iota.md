---
title: IOTA
parent: The CONCRETE stack
nav_order: 5
---

# IOTA 
{: .fs-9 .no_toc }


A distributed decentralised ledger
{: .fs-6 .fw-300 }
----
[![iota icon](../../../../images/current/iota_icon.png)](https://www.iota.org/)


IOTA generates a single shared digital ledger (or database) across all nodes.  

<span>Stable</span>{: .label .label-green } Basic IOTA functionality within CONCRETE, as described here, is considered to be stable. Despite this, further work is known to be required to cohere this as part of a wider, performant, CONCRETE whole (LINK).

## Table of contents
{: .no_toc }

1. TOC
{:toc}

## IOTA overview

[IOTA](https://www.iota.org/) is a common piece of software that is run on all (or many[^bft]) nodes.  This software tracks and updates a single shared [^replicated] ledger, or database. A legitimate update, or transaction, requested by a user at node A (below) will eventually be recognised and replicated across the entire network. One of the key features of this (and other distributed ledgers such as Bitcoin, and Ethereum) is that consensus is maintained as a single source of 'truth' despite the potential for failures and hostile actors.

[^bft]:
    Increasing the number of (trustworthy) nodes running this software in a network improves performance and overall security (see wikipedia: [Byzantine fault tolerance](https://en.wikipedia.org/wiki/Byzantine_fault#), for an introduction to some of the security aspects of this).  

[^replicated]:
    Each full IOTA software node holds its own copy of the entire ledger.  There will always be some slight disparities between these nodes (if nothing else, this is a function of physics and the time it takes for information to pass around a network).  However, the algorithms used generate a form of guarantee of eventual consistency.  

![network of nodes each running an instance of iota](../../../../images/current/lettered_nodes_with_iota.png)

IOTA software, like other distributed ledgers technologies such as Bitcoin, use cryptographic (mathematical) techniques[^crypto-strength] to:

- Ensure that certain actions can only be conducted by authorised users.
- 'Mint' unforgeable tokens with similar characteristics to physical money eg they can only be owned by one person at a time.
- Enable 'smart' contracts to automate actions that cannot be tampered with, or be ignored by the parties involved.
- Store data that can only be modified by specific users.

[^crypto-strength]:
    The strength of these cryptographic techniques is important.  As is the quality of the software that is used to instantiate them. The mathematical techniques here are well-researched, and are already future-proofed against the potential for quantum computer attacks (should these ever materialise in practice). The inclusion of seL4 and trusted hardware in the CONCRETE stack will enable developers to formally, mathematically, prove properties about CONCRETE-IOTA-style functionality, rather than leaving any of this to engineering good practice.

Although IOTA and other distributed ledger technologies use cryptographic techniques to enable these capabilities, the data of the ledger itself is considered open (it can be secured by separate keys).  

CONCRETE has many potential uses for IOTA-based functionality.

## IOTA and identity

User digital identities will be defined in CONCRETE by a private cryptographic key (a large, secret, number) used by and within IOTA.  Although these keys will be used extensively, users will not be handling them on a day-to-day basis (these will primarily be used 'under-the-hood').  Beyond their primary identity, users will regularly be using cryptographic pseudonyms. These are useful, for example, for security, to ensure that Alice-1 and Alice-2 (2 pseudonyms for the same person) can be given different permissions by different 'boss' characters without the potential for Alice to aggregate and mis-use combined privileges. 

Various identity-related services can be expected in a CONCRETE-world.  The security of a CONCRETE network will be closely aligned with the security associated with these secret keys. Although this is a well-understood field, there are various layered security approaches to key and identity management to develop.

## IOTA for performant crypto-style tokens in hostile environments

Modern IOTA has adopted the [Move](https://sui.io/move) 2024 programming model[^move_details].  The Move language provides strong support for (posh term) the 'unspent transaction output' (UTxO) model approach for ledgers.  This means that the language enables programmers to easily create different flavoured cryptographic tokens that closely resemble day-to-day physical items such as unforgeable numbered bank notes, vouchers with expiry times, and tickets - these can be 'Moved' between owners. The alternative approach, which is still possible, is the 'account model' whereby the ledger acts more like a collection of bank account balances.  One of the benefits of this approach (to keep the physical cash analogy going) is that users can hand over ownership of a token without the need to talk to the bank (the IOTA ledger).  This means that many IOTA-related transactions can be conducted quickly in parallel, rather than having to wait for consensus about new balances to be recognised across the entire global ledger. 

[^move_details]:
    Move 2024 is a distributed-ledger-agnostic programming language for smart contracts.  For those interested, [The Move Book](https://move-book.com/index.html) provides an unusually good introduction to the language (albeit using a different ledger - SUI).  Move is a first-class programming citizen in IOTA; associated [documentation](https://docs.iota.org/developer/iota-101/move-overview/) is OK.     

This ability to generate unforgeable token-like entities is useful within CONCRETE to underpin any [financial approach to resource management]({% link site_content/foundation_and_services/configuration_and_use/managing_resources.md %}) and, for security, to make [capability tokens]({% link site_content/foundation_and_services/configuration_and_use/security_risk_and_trust/access_control.md %}) to control who can do what in the system.

The IOTA ledger mechanism is also important. Unlike blockchain ledgers, where the nodes generate a single chain of blocks representing transactions, IOTA achieves this consensus using a (messy) 'tangle' of transactions (visualised below).  The tangle approach eventually generates the same kind of universal consensus as a blockchain, but it also allows nodes to continue to cooperate when chunks of the network become detached (by any kind of network failure or sharding).  IOTA transactions are more robust and resilient in hostile environments. (To use the network diagram above, if nodes A,B,C become detached from the rest and then rejoin, the IOTA tangle will automatically, eventually, reconcile this - where blockchains would fail).

![iota tangle visualised](../../../../images/current/the_IOTA_tangle.png)

## IOTA for naming

The universally agreed ledger also plays an important CONCRETE role in naming, information security, and discoverability.  

IPFS provides a mechanism for storing data in a distributed network.  However, blocks of IPFS data have non-human-memorable alphanumeric names that are calculated directly from the data itself.  If the data represents a document, for example, each time the document changes an entirely new name will be generated.  IOTA can be used to generate openly accessible token-like objects that can be owned by individual users.  Having tokens that hold both an open non-changing name ('my car LIDAR data') and an associated modifiable (by the owner) IPFS fingerprint/CID, enables user to give data and information sources universally recognisable static names. These can also be used, in conjunction with cryptographic keys to enable access control measures.

More specifically for HQDM, one of IOTA's primitive mechanisms involves the generation of universally unique identifiers.  Ontologists (and associated software tools) need these kinds of unique identifiers / names.  The IOTA mechanisms enable them to be created and 'owned' such that their unique names will be consistent, and not be accidentally re-used, across an entire CONCRETE network. This consistent naming helps to enable ontological composability.

## IOTA and trustworthy automations

IOTA also provides a 'smart' contracting mechanism.  The are just algorithms run within a CONCRETE IOTA environment.  Although lots of software will exist largely independently of the underlying CONCRETE foundations, there will be times when universal automations will be useful. These algorithms can respond to external triggers (non-foundational software known as 'oracles') and can also be used to initiate non-foundational events. This kind of functionality can be useful for example when enabling security measures (eg having oracles that provide probabilities that a user is in a particular location).









