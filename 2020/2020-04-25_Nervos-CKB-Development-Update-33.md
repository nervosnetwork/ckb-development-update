# Nervos CKB Development Update \#33

Covering Apr 6 to Apr 19

------------------------------------------------------------------------

### Nervos CKB Development Update \#33

#### Apr 6 - Apr 19

![](https://cdn-images-1.medium.com/max/800/1*HLi1hr32GTA580BiFVk4vQ.jpeg)

By [Cipher Wang](https://github.com/CipherWang), [Ian Yang](https://medium.com/u/72022cac4c7c).

#### TL;DR

-   We have published [ckb-indexer](https://github.com/quake/ckb-indexer).
-   The new block download scheduler is [ready for review](https://github.com/nervosnetwork/ckb/pull/1999).
-   Neuron [v0.29.0](https://github.com/nervosnetwork/neuron/releases/tag/v0.29.0) has been released, with new features signing/verifying message, customized assets operation, and sending CKBytes with lock period.

#### Changes in CKB

Completed:

-   We have automated the benchmark test suite. See the result in [nervosnetwork/ckb\#2019](https://github.com/nervosnetwork/ckb/pull/2019).
-   [ckb-indexer](https://github.com/quake/ckb-indexer) is an external cells indexer which synchronizes data with the CKB node via CKB. The light client services will be built based on this.
-   The new block download scheduler is [ready for review](https://github.com/nervosnetwork/ckb/pull/1999). It has improved the chain synchronization speed by about 100%.

#### Changes in Applications

Neuron:

-   [v0.29.0](https://github.com/nervosnetwork/neuron/releases/tag/v0.29.0) has been released.
-   With new features including sign/verify message, customized assets operation, and send CKBytes with lock period.
-   We are working on new UX for Nervos DAO page.

CKB Explorer:

-   Rearrange the layout of charts page.
-   Add a balance distribution chart.
-   Add sUDT support for testnet explorer.

------------------------------------------------------------------------

**Join our community:** [Discord](https://discord.gg/AqGTUE9) - [Github](https://github.com/nervosnetwork) - [Nervos Talk Forum](https://talk.nervos.org/) - [Twitter](https://twitter.com/nervosnetwork)

For discussions or questions join the conversation on [**Discord**](https://discord.gg/Cc8Tr6K) or check out one of our community Telegram channels: [**English**](https://t.me/NervosNetwork)**,** [**Korean**](http://t.me/NervosKorea)**,** [**Russian**](https://t.me/NervosRussia)**,** [**Japanese**](http://t.me/NervosNertwork_japan)**,** [**Spanish**](https://t.me/NervosNetworkES)**,** [**Vietnamese**](https://t.me/nervosvietnam) and [**Chinese**](https://t.me/NervosNetworkcn)

By [Ian Yang](https://medium.com/@doitian) on [April 25, 2020](https://medium.com/p/60863398563e).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-33-60863398563e)

Exported from [Medium](https://medium.com) on May 12, 2020.
