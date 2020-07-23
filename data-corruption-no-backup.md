## Data corruption, no backup

### Problem

> [Andrew](https://twitter.com/cyber_hokie/status/1282362238423175170): I ran into one instance where my docker crashed and the image and data dir were corrupted somehow, and I had no backup of to restore. Ended up losing that validator. And as much as I like Docker/Bezel images vs local binaries, neither are particularly well known for error proof stability.

### Possible solution(s)

Duplicate folder on validator creation (with just the keys)?

If you generate your keys according to EIPs [2333](https://eips.ethereum.org/EIPS/eip-2333) and [2334](https://eips.ethereum.org/EIPS/eip-2334) -- a set of standards that describe how withdrawal and signing keys are related, and how they can be derived from a single mnemonic -- then all you need to do is keep your mnemonic in a safe place. Deposit Launchpad helps enforce this.

### References

[Original tweet](https://twitter.com/cyber_hokie/status/1282362622030028800)

