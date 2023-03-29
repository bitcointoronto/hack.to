---
title: "History of Bitcoin Wallets"
date: 2023-03-29
author: "KryptoKidz"
tags:
    - historyofbitcoinwallets
---

In this blog post we will go through the history of bitcoin wallets, and how they have progressed.

## Early Days  

Before the introduction of BIPs (Bitcoin Improvement Proposals) and the development of HD wallets, bitcoin users primarily relied on simple software wallets that stored a single private key and associated bitcoin address. These wallets were often referred to as "single-address wallets”. 

Single-address wallets were easy to use but had several limitations. For example, users had to manually back up their private keys, and if they lost their private key, they would lose access to their bitcoin. Additionally, if users wanted to manage multiple bitcoin addresses, they had to create separate wallets for each address and manage them separately. 

Another type of wallet that was available before the introduction of BIPs was a paper wallet. A paper wallet is a physical piece of paper that contains a bitcoin address and its associated private key. Paper wallets were often used for long-term storage of bitcoin, as they provided a high level of security and were not susceptible to online attacks. However, paper wallets were not very user-friendly, and users had to manually generate and print out their paper wallets, which was a complex and time-consuming process. 

Overall, before the introduction of BIPs, bitcoin wallet options were limited and often required manual backup and management of private keys. The introduction of HD wallets and other wallet improvements through BIPs has made Bitcoin wallets more user-friendly and secure, and has enabled more efficient management of multiple Bitcoin addresses. 

## Progression of BIPs 

Bitcoin wallets have evolved over time, with new wallet types and features being introduced through Bitcoin Improvement Proposals (BIPs). 

1. BIP32, also known as the Hierarchical Deterministic (HD) Wallets BIP, was proposed in 2012 and introduced a new type of bitcoin wallet that made it easier to manage multiple Bitcoin addresses. With HD wallets, a single seed phrase can be used to generate an unlimited number of private and public keys, which makes it easier to manage funds across multiple addresses. 

2. BIP44, proposed in 2014, built upon the HD wallet concept and introduced a new type of wallet called a Multi-Account Hierarchy for Deterministic Wallets. BIP44 made it easier for users to manage multiple cryptocurrencies with a single seed phrase, as it introduced a standardized way to derive addresses for multiple cryptocurrencies from a single master key. These address types begin with **1**. 

3. BIP49, proposed in 2015, introduced a new type of wallet called a P2SH-P2WPKH (Pay-to-Witness-Public-Key-Hash-in-Pay-to-Script-Hash) wallet, which enabled the use of Segregated Witness (SegWit) addresses. SegWit is a protocol upgrade that was introduced in 2017 to improve the scalability and efficiency of the Bitcoin network. P2SH-P2WPKH wallets allowed users to take advantage of SegWit without having to upgrade to new address formats. This type of address with begins with a **3** is compatible with the above and below address types. 

4. BIP84, proposed in 2016, introduced a new type of wallet called a Native SegWit or Bech32 wallet. Native SegWit wallets use a new address format that is more efficient than P2SH-P2WPKH addresses, and they provide additional security benefits. Bech32 addresses are longer than traditional bitcoin addresses, but they are easier to read and are less prone to human error. These address types begin with **bc1**.  

## BIP39 - Wallet Seed Creation Standardization 

BIP39, also known as the Mnemonic Code for Generating Deterministic Keys BIP, was proposed in 2013 and introduced a standardized way to generate seed phrases for HD wallets. Prior to BIP39, different wallet software used different methods for generating seed phrases, which made it difficult to switch between different wallet software or recover funds if a wallet was lost or corrupted. 

BIP39 standardized the process of generating seed phrases, which enabled users to easily switch between different wallet software that supported BIP39. With BIP39, a user can create a seed phrase consisting of 12, 18, or 24 words, which can be used to generate a hierarchical tree of private keys and addresses. 

The use of a standardized seed phrase also made it easier to recover funds if a wallet was lost or corrupted. As long as a user has their seed phrase, they can restore their wallet and access their funds on any wallet software that supports BIP39. 

Overall, BIP39 helped improve wallet compatibility by providing a standardized way to generate seed phrases for HD wallets. This standardized approach enabled users to easily switch between different wallet software that supports BIP39 and recover funds if a wallet was lost or corrupted. With the ability to add a passphrase along with your seed phrase which allowed for added security, wallets which support BIP39 are the most recommended amongst Bitcoiners.

## Descriptor Wallet Backup Standardization

BIP32 introduced the concept of Hierarchical Deterministic (HD) wallets, which allowed for the creation of multiple addresses from a single master seed. However, HD wallets still required users to backup and manage a large number of individual private keys, which was not very user-friendly.

To address this issue, BIP39 introduced the use of mnemonic seed phrases, which made it easier to backup and restore HD wallets. Mnemonic seed phrases are a series of 12-24 words that can be used to generate an entire HD wallet, including all of its addresses and private keys.

However, mnemonic seed phrases were still not very user-friendly for non-technical users, as they required manual entry and management of long strings of words. To address this issue, BIP32 was extended with BIP44, which introduced the concept of a "derivation path" that allowed for the creation of wallet descriptors.

Output script descriptors (AKA wallet descriptors) are strings that contain all the information necessary to allow a wallet or other program to track payments made to or spent from a particular script or set of related scripts (i.e. an address or a set of related addresses such as in an HD wallet). Wallets supporting output descriptors aim to make the way addresses are generated within bitcoin wallets more straightforward for users by specifying what scripts or addresses are needed when interacting with particular public keys, letting engineers know in plain English what they need.

**Derivation Path example** 

```m/49'/0'/0'/0/0``` ```m/purpose'/coin_type'/account'/change/index```

**Wallet Descriptor example** 

```pkh([d34db33f/44'/0'/0']xpub6ERApfZwUNrhLCkDtcHTcxd75RbzS1ed54G1LkBUHQVHQKqhMkhgbmJbZRkrgZw4koxb5JaHWkY4ALHY2grBGRjaDMzQLcgJvLJuZZvRcEL/1/*)``` 
describes a set of P2PKH outputs, but additionally specifies that the specified xpub is a child of a master with fingerprint ```d34db33f```, and derived using path ```44'/0'/0'```

Many single-key constructions are used in practice, generally including P2PK, P2PKH, P2WPKH, and P2SH-P2WPKH.

To describe these, we model these as functions. The functions ```pk``` (P2PK), ```pkh``` (P2PKH) and ```wpkh``` (P2WPKH) take as input a ```KEY``` expression, and return the corresponding scriptPubKey. The functions ```sh``` (P2SH) and ```wsh``` (P2WSH) take as input a ```SCRIPT``` expression, and return the script describing P2SH and P2WSH outputs with the input as embedded script. The names of the functions do not contain "p2" for brevity.

BIP32 wallet descriptors are a human-readable language that describes the structure of an HD wallet, including its seed phrase and derivation path. This allowed wallet software to automatically generate and manage multiple addresses and private keys, making it easier for users to backup and restore their wallets.

In the end, it was BIP44 that added the descriptor wallet backup compatibility, allowing for the creation of wallet descriptors that could be used to easily backup and restore HD wallets.

## XPUBs vs ZPUBs vs YPUBs

XPUB is short for extended public key which allows full read-only view to all transactions, addresses, and balances in a specific wallet. ZPUBs are an ```xpub``` for BIP49 address types. YPUBs are an ```xpub``` for BIP84 address types. That being said, when using descriptor wallet backups it will always be ```xpub```, and never ```zpub```, or ```ypub```.

## Watch-only

A watch-only bitcoin wallet is a type of wallet that does not store or use private keys. It allows users to view transactions and balances on an online computer without risking their bitcoins, as well as keep an eye on their cold storage or paper wallet without touching your private key, by importing your XPUB.

-------

In conclusion, the evolution of bitcoin wallets through BIPs has enabled users to manage their funds more efficiently and securely, and has provided support for new protocol upgrades like SegWit. The use of BIPs allows for a standardized approach to wallet development, which benefits users and developers alike.