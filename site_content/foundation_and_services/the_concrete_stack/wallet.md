---
title: Wallet
parent: The CONCRETE stack
nav_order: 6
---

# Wallet 
{: .fs-9 .no_toc }


Somewhere secure to keep valuables
{: .fs-6 .fw-300 }
----

A wallet is a secure data storage mechanism that enables users to hold and control valuable data.

<span>Stable</span>{: .label .label-green } The need for individual users to securely store data within CONCRETE, as described here, is considered to be stable. However, the functional requirements of wallets within CONCRETE are yet to be determined.

A large proportion of the CONCRETE foundation is associated with security. Much of this boils down to applied cryptography; particularly, how people will use mathematical locks and keys to manage security-related risks. 

Within CONCRETE, most data can be expected to be cryptographically locked.  There is no point in holding data if it is not going to be used. Other than in some specialist situations [^fhe], various mechanisms (eg identity and authority) will determine whether access is to be granted.  Given the go-ahead, a key will be used to decrypt the data.  The vast majority of this will be happening 'under-the-hood'; users should not be coming into contact with the keys themselves. These keys need to be stored securely.  This is the primary role of a wallet.

Wallets need to be secure.  The trusted hardware and seL4 layers of the CONCRETE stack will enable formal methods approaches to be used in wallet development (to enable security-related wallet properties to be proven).  

Although the basic functions of a wallet are well understood, the wider functionality required within CONCRETE has yet to be fully determined. For example:

-  Key rotation functionality.  How and when is data re-encrypted by a new key?
-  Oversight and monitoring.  Can boss-characters monitor key holdings of users? 

[^fhe]:
    [Homomorhic encryption](https://en.wikipedia.org/wiki/Homomorphic_encryption) techniques do enable algorithms to be run directly on un-decrypted cyphertext.  While seemingly amazing, the efficiency of these algorithms can be of-the-order of 1,000,000x worse than their non-homomorphic equivalents - this can often represent a substantial performance penalty. 





