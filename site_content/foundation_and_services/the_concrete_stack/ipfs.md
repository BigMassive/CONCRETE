---
title: IPFS
parent: The CONCRETE stack
nav_order: 4
---
# Inter-Planetary File System 
{: .fs-9 .no_toc }


Content (not location) addressed distributed data storage
{: .fs-6 .fw-300 }
----
[![ipfs logo](../../../../images/current/ipfs.png)](https://ipfs.tech/)

IPFS is about data storage in distributed, decentralised networks.  

<span>Stable</span>{: .label .label-green } Basic IPFS functionality within CONCRETE, as described here, is considered to be stable. Despite this, further work is known to be required to cohere this as part of a wider, performant, CONCRETE whole (LINK).

## Table of contents
{: .no_toc }

1. TOC
{:toc}

## IPFS overview

The [Inter-Planetary File System (IPFS)](https://ipfs.tech/) provides a distributed and decentralised approach to data storage[^bittorrent].  We need a way to store and retrieve data in a decentralised network.  In centralised systems, the name of a data source commonly reflects its location eg file names, or web-address. This approach is not appropriate for distributed and decentralised systems. In an IPFS network, data is immutable (it cannot change); it can be stored and replicated, as often as desired, on any node.  The name of the data represents its content.  Users can request that content from anywhere.  As long as one connected node has it, it can be recovered.

[^bittorrent]:
    As a mental short-cut for some people 'of a certain age', IPFS has many similarties with Bittorrent file sharing from the pre-Spotify and Netflix era.  A data source is named, and can be requested, and served, from anywhere across a distributed network. 

![data being split up into different channels](../../../../images/current/data_output_division.png)

A block of stored data might represent a document (information), but it might also represent sensed values.  In a CONCRETE world, it is envisaged that sensor-style data would be disaggregated into separate data streams (depicted above), and within those streams the data would be 'chunked' into IPFS's Inter-Planetary Linked Data (IPLD) data objects. (This need is associated both with [security]({% link site_content/foundation_and_services/configuration_and_use/security_risk_and_trust/data_security.md %}) ; and efficient [resource management]({% link site_content/foundation_and_services/configuration_and_use/managing_resources.md %})).

![same block of data stored at two different nodes in a network](../../../../images/current/lettered_nodes_with_data_and_car.png)

To use the example scenario depicted above, the car node (A) has produced and locally stored some LIDAR sensor data labelled '1'(this may exist alongside potentially millions of other blocks of data).  This block of data has been replicated at another node (F). There are many reasons why this might be desirable.  For example:

- **Replication for long-term use**.  People might have a good use for the data, but the car only has so much storage capacity.  The car data will be over-written shortly.
- **Replication for risk management**.  The data has value, but the car might crash destroying the data.  The data is replicated elsewhere (potentially many times).
- **Replication for local efficiency**.  A person or process associated with node F might seek to co-locate a large amount of data at that node in order to efficiently run a particular algorithm.
- **Replication for network efficiency**.  Many people might benefit from this data, but the network overhead associated with retrieving it from the car node might be high (or it might lose connectivity altogether).  Although a (slight) time delay might be introduced, the node at F might have much more efficient network connectivity than the car itself.  

The immutability (unchangeability) property of this data is particularly important from a multi-user (socio-) perspective.  This enables any and all users to independently and locally make these kinds of risk/reward/efficiency decisions without stepping on each others toes.  A user can choose to replicate this data for their own benefit without it negatively affecting others.  For example, a user might be concerned that if the node E is lost, then nodes H, I, and J might lose access to this data source.  They could re-replicate the data at I, improving resilience, redundancy, and network performance not just for themselves but for other users too.  The ability for users to make these local risk/reward decisions is incredibly important from [dynamic risk management]({% link site_content/foundation_and_services/some_basic_needs.md%}#enabling-dynamic-risk-management-in-a-dynamic-world) perspective.  The overall risk/reward position is an emergent property of all the local decisions.  It is not something that is (or should be) centrally controlled.[^teamwork]

[^teamwork]:
    Although full central control of data-related risk would be inefficient and undesirable, this does not mean that users are forced to micro-manage all data. Users might choose to defer to broader centralised strategies; some users might be given data-enabling roles.  The important principle here is just that users can choose to closely manage data as and when they want to; any more centralised approaches are only there to support users when they wish.

## IPFS Content IDentifiers (CIDs)

In IPFS the short names for blocks of data (green fingerprints below - aka Content IDentifiers CIDs in IPFS) are calculated from, and uniquely identify, the associated data (blue). These fingerprints will often be much smaller than the data they refer to.  A user can request a block of data by providing the fingerprint, retreive it, and subsequently re-calculate the fingerprint/CID from the data received to confirm that they have exactly what was requested.

![basic ipfs fingerprint contains a hash of the data and some extra data about the fingerprinting method](../../../../images/current/fingerprint_details.png)

The IPFS/IPLD functionality enables larger blocks of data (below) to be referred to compactly by generating a new data object that contains links (fingerprints) to many others.

![a satellite image split up into tiles.  Each tile has its own fingerprint.  The whole image is a fingerprint representing a list of fingerprints](../../../../images/current/sat_dag_basic.png)

## IOTA names to create the impression of mutability

There are times when people want to have a permanent name to refer to something that may alter over time eg 'the latest version of this document'. Although IPFS itself enables this functionality, the expectation within CONCRETE is to use IOTA (LINK) to achieve this.

----




