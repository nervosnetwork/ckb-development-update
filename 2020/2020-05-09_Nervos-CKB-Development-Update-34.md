# Nervos CKB Development Update \#34

Covering Apr 21 to May 4

------------------------------------------------------------------------

### Nervos CKB Development Update \#34

Covering Apr 21 to May 4

![](https://cdn-images-1.medium.com/max/800/1*PN9QMqTsAkc6ipN0mG3H7Q.png)

By [Cipher Wang](https://github.com/CipherWang), [Ian Yang](https://medium.com/u/72022cac4c7c)

### TL;DR

-   Released [ckb v0.32.0-rc1](https://github.com/nervosnetwork/ckb/releases) and Neuron [v0.30.0-rc1/rc2](https://github.com/nervosnetwork/neuron/releases).
-   Optimized chain sync speed by 50%.

### Changes in CKB

#### **Completed:**

-   Released [ckb v0.32.0-rc1](https://github.com/nervosnetwork/ckb/releases).
-   Optimized the block download tasks with a simple scheduler. ([ckb\#1999](https://github.com/nervosnetwork/ckb/pull/1999)). It has reduced the chain sync time by about 50%.
-   Fixed a memory leak bug in p2p. ([p2p\#218](https://github.com/nervosnetwork/p2p/pull/218))
-   Improved the molecule document. ([ckb\#2003](https://github.com/nervosnetwork/ckb/pull/2003), [molecule\#26](https://github.com/nervosnetwork/molecule/pull/26))
-   Fixed an undefined behavior in molecule. ([molecule\#GHSA-rffv-8x7x-p7pw](https://github.com/nervosnetwork/molecule/security/advisories/GHSA-rffv-8x7x-p7pw), [ckb\#GHSA-q669–2vfg-cxcg](https://github.com/nervosnetwork/ckb/security/advisories/GHSA-q669-2vfg-cxcg))

#### **In Progress:**

-   Improve RPC errors. ([ckb\#2038](https://github.com/nervosnetwork/ckb/pull/2038), [ckb\#2049](https://github.com/nervosnetwork/ckb/pull/2049))
-   RocksDB performance tuning
-   BIP 37 and 157 like light client service demo

### Changes in Applications

#### **Neuron:**

-   Release Neuron v0.30.0-rc1/rc2
-   Better Nervos DAO UI/UX
-   Improve syncing speed
-   Working on UDT support

#### **CKB Explorer:**

-   Add script explanation label
-   Working on new UX and new charts

------------------------------------------------------------------------

**Join our community:** [Discord](https://discord.gg/AqGTUE9) — [Github](https://github.com/nervosnetwork) — [Nervos Talk Forum](https://talk.nervos.org/) — [Twitter](https://twitter.com/nervosnetwork)

For discussions or questions join the conversation on [**Discord**](https://discord.gg/Cc8Tr6K) or check out one of our community Telegram channels: [**English**](https://t.me/NervosNetwork)**,** [**Korean**](http://t.me/NervosKorea)**,** [**Russian**](https://t.me/NervosRussia)**,** [**Japanese**](http://t.me/NervosNertwork_japan)**,** [**Spanish**](https://t.me/NervosNetworkES)**,** [**Vietnamese**](https://t.me/nervosvietnam) and [**Chinese**](https://t.me/NervosNetworkcn)

By [Ian Yang](https://medium.com/@doitian) on [May 9, 2020](https://medium.com/p/4bc796624ea4).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-34-4bc796624ea4)

Exported from [Medium](https://medium.com) on May 12, 2020.
