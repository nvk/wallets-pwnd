# Wallets Pwnd [Beta]


**A list of Bitcoin Hardware, Phone and Desktop wallet attacks**

**This list is not an endorsement of the security or the quality of any of the wallets.**

## Hardware

Fixed?|Severity|Vendor|Model|Wallet Version Affected|Product Docs|Vulnerability Report|Vendor Announcement|Fix
:---:|:---:|---|---|---|---|---|---|---
Y/N|1-10|Vendor Name|Model|Version|[↗︎]()/[Archive]()|[↗︎]()/[Archive]()|[↗︎]()/[Archive]()|[↗︎]()/[Archive]()


## Desktop
TODO

## Phone
TODO

## Web
TODO

---

### Severity Scale:

WIP

1. ie Leaks privacy
2. 
3. 
4. 
5. 
6. 
7. 
8. 
9. 
10. 

Notes:
- WIP

Icon|Legend
:---:|---
🛑|WIP

---

## Requirements for listing

- Working Proof of Concept
- Severity?
- HW|SW|HW+SW



## Explainer: Wallet Types (from walletsrecovery.org)

+ [**Paper wallets**](https://en.bitcoin.it/wiki/Paper_wallet) are not actually wallets, but rather private keys and addresses printed out on paper. While the keys and addresses can technically be generated non-deterministically or deterministically, the usability is basically the same or poorer than a non-deterministic software wallet. Paper wallets have a number of significant drawbacks, including encouraging address reuse, exposing keys to poorly secured networked devices (printer), and not handling change addresses. Paper wallets should not be confused with [recovery seeds](https://wiki.trezor.io/Recovery_seed).
+ **Non-deterministic wallets** randomly generate all private / public key pairs independent of each other. A [keypool buffer](https://en.bitcoin.it/wiki/Key_pool) was added to the Bitcoin-Qt / Bitcoin Core wallet in [October](https://bitcointalk.org/index.php?topic=1414.0) [2010](https://bitcointalk.org/index.php?topic=1528.0), which allowed the wallet to create a collection of unused addresses, rather than generating new addresses one by one upon use. While this feature allowed for less frequent backups than before, the non-determinism still carried the risk of key loss if the pool was exhausted and a new key was generated beyond what was saved in backup.
+ **Deterministic wallets** are essentially any wallet where "[you can backup once... because all future addresses are determined in advance](https://bitcointalk.org/index.php?topic=19137.msg239768#msg239768)," which was a massive improvement in recoverability. There are [two different forms](https://bitcoin.stackexchange.com/questions/18102/does-a-wallet-containing-multiple-addresses-have-a-single-private-key):
   + **Sequential deterministic wallets** take a single seed phrase / passphrase and repeatedly increment it in order to generate new keypairs. This meant that the system would only need to store addresses, and then re-generate the private keys when needed.
   + **Hierarchical deterministic wallets** take a single seed phrase and randomly generate a master private / public key pair, which is then used to derive child key pairs that generate addresses. This system allows for the generation of addresses to occur without the master private key, with only the public key.
+ **Multi-signature wallets** require multiple signatures or parties to sign a transaction in order to spend bitcoin. An M-of-N [BIP11](https://github.com/bitcoin/bips/blob/master/bip-0011.mediawiki) address must first be generated in order to receive bitcoin for spending in multi-signature transactions. While the 2-of-2 and 2-of-3 schemes are the most common, the [maximum number of public keys](https://bitcoin.stackexchange.com/questions/81223/why-is-20-the-maximum-public-keys-in-a-multisig-transaction) is higher, and this could increase much more in the future [with Schnorr signatures](https://twitter.com/J9Roem/status/991098233828139008) and [Taproot](https://bitcoinops.org/en/newsletters/2019/05/14/). 'Partially Signed Bitcoin Transactions' (PSBT) according to [BIP174](https://github.com/bitcoin/bips/blob/master/bip-0174.mediawiki) (proposed), where unsigned or partially signed transactions are passed around to multiple signers or signing devices, may also be an option.


---


Did we get it wrong? Just let us know, and this will be updated. :)

Want to contribute, make a [Pull Request](https://github.com/nvk/wallets-recovery/pulls).
