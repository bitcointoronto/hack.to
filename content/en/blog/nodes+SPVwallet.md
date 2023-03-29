---
title: "Archival vs Full Nodes vs SPV wallet"
date: 2023-03-29
author: "KryptoKidz"
tags:
    - nodes+SPVwallet
---

## Archival vs Pruned Nodes vs SPV wallet 

In this blog post we will differentiate between archival and pruned nodes, as well as how an SPV wallet compares to them.

## Archival vs Pruned Nodes 

Archival and pruned nodes are two types of full nodes in the Bitcoin network. A full node is a type of software that fully validates and stores a complete copy of the bitcoin blockchain, which contains all the transaction records since its inception. The main difference between archival and pruned nodes is the amount of historical data they store. 

An archival node stores a complete copy of the entire bitcoin blockchain, including every transaction that has ever occurred on the network, which makes it possible to validate any transaction or block from the beginning of the Bitcoin network. Archival nodes are useful for researchers, developers, and other users who require access to historical data for analysis or testing purposes. 

On the other hand, a pruned node only stores a subset of the complete blockchain, which allows it to validate new transactions and blocks while discarding older data that is no longer necessary. Pruned nodes store only the most recent blocks and transactions, which allows them to operate with less storage space and memory requirements than archival nodes. Pruned nodes are useful for users who want to run a full node but have limited resources or storage space. 

The advantages of an archival full node over a pruned node are mainly related to its ability to access and validate historical data. 

1. Complete Transaction History: An archival full node stores a complete copy of the bitcoin blockchain, which includes every transaction that has ever occurred on the network. This means that users can access and validate any transaction or block from the beginning of the Bitcoin network, which is not possible with a pruned node. 
2. Better Privacy: Archival nodes offer better privacy because they store all transactions, including those that have been deleted from the UTXO (Unspent Transaction Output) set. This means that it is possible to trace the history of all transactions on the network, which can be useful for restoring and old wallet with many transactions into new wallet software, the ability to use your own personal block explorer, and even forensic analysis and investigative purposes. 
3. Research and Development: Archival nodes are essential for researchers, developers, and other users who require access to historical data for analysis or testing purposes. With an archival node, users can run simulations, test new features or algorithms, or conduct other experiments using accurate historical data. 
4. Improved Security: By storing a complete copy of the blockchain, archival nodes offer better security against potential attacks or blockchain forks. In case of a fork or network split, archival nodes can quickly validate the correct chain and prevent users from losing funds or making invalid transactions.

However, the main disadvantage of an archival node is its storage and resource requirements. Archival nodes require significantly more storage space and memory than pruned nodes, which can be a limiting factor for users with limited resources or bandwidth. Additionally, archival nodes require more processing power and longer synchronization time, which can make them less suitable for users who require fast and lightweight node operation. 

## SPV Wallet 

An SPV (Simplified Payment Verification) wallet is a lightweight bitcoin wallet that does not store a complete copy of the bitcoin blockchain but instead relies on a trusted full node to verify the validity of transactions. SPV wallets only store a subset of the blockchain's data, including block headers and transaction IDs, which allows them to operate with much less storage space and processing power than full nodes. However, they rely on a trusted full node to provide them with accurate information about the state of the Bitcoin network. SPV wallets are useful for users who require fast and convenient access to their bitcoin funds and don't need to validate transactions themselves. 
