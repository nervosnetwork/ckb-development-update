# Nervos CKB Development Update \#29

Covering Feb 3 to Feb 16

------------------------------------------------------------------------

### Nervos CKB Development Update \#29

Feb 3 — Feb 16

By [Cipher Wang](https://github.com/CipherWang), [Ian Yang](https://medium.com/u/72022cac4c7c)

![](https://cdn-images-1.medium.com/max/800/1*TuRIpEp1hPHumL0azJ2h4g.png)

#### TL;DR

-   Released CKB v0.28.0 and Neuron v0.28.0.
-   Molecule plugin system and [driftluo/moleculec-go](https://github.com/driftluo/moleculec-go).
-   Neuron now supports full payload format addresses.
-   Neuron now supports public key export & import, which is important to read-only wallet and Neuron debugging.

#### Changes in CKB

We released CKB [v0.28.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.28.0). The breaking change [\#1879](https://github.com/nervosnetwork/ckb/pull/1879) added `outputs_validator` to `send_transaction` RPC ([@quake](https://github.com/quake)).

Linfeng published an article to explain how to [construct complex transaction using ckb-cli](https://github.com/nervosnetwork/ckb-cli/wiki/Handle-Complex-Transaction).

Molecule now supports plugin, see [driftluo/moleculec-go](https://github.com/driftluo/moleculec-go) as an example. And yes, you can use molecule in Go now.

The team is actively probing the area *Light Client* and *Lighting Network*.

#### Changes in Toolchain

Neuron has released v0.28.0, and it’s bundled with CKB node v0.28.0.

-   Now support full payload format addresses
-   Support public key export & import, which is important to read-only wallet and Neuron debugging

CKB Explorer changes

-   Add wallet page portal on title bar
-   Add transaction index jump and highlight functionality

Keyper project has been started. Keyper is an experimental project which is going to provide an ownership layer for CKB.

Publish molecule-javascript, a plugin for the molecule serialization system to generate JavaScript code.

------------------------------------------------------------------------

**Join our community:** [Github](https://github.com/nervosnetwork) [Forum](https://talk.nervos.org/) [Reddit](https://www.reddit.com/r/NervosNetwork) [Twitter](https://twitter.com/nervosnetwork)

For discussions or questions join the conversation on [**Discord**](https://discord.gg/Cc8Tr6K) **or** check out one of our community Telegram channels: [**English**](https://t.me/NervosNetwork)**,** [**Korean**](http://t.me/NervosKorea)**,** [**Russian**](https://t.me/NervosRussia)**,** [**Japanese**](http://t.me/NervosNertwork_japan)**,** [**Spanish**](https://t.me/NervosNetworkES)**,** [**Vietnamese**](https://t.me/nervosvietnam) and [**Chinese**](https://t.me/NervosNetworkcn)

By [Ian Yang](https://medium.com/@doitian) on [March 1, 2020](https://medium.com/p/6172a71b985f).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-29-6172a71b985f)

Exported from [Medium](https://medium.com) on May 12, 2020.
