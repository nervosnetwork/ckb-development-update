# Nervos CKB Development Update \#31

Covering Mar 9 to Mar 22

------------------------------------------------------------------------

### Nervos CKB Development Update \#31

Mar 9 — Mar 22

By [Cipher Wang](https://github.com/CipherWang), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Ian Yang](https://medium.com/u/72022cac4c7c).

![](https://cdn-images-1.medium.com/max/800/1*Hlefd2AuQjrwtpG1S4ogEg.png)

### TL;DR

-   Released [v0.31.0-pre1](https://github.com/nervosnetwork/ckb/releases/tag/v0.31.0-pre1) with block sync improvements.
-   Released [Neuron v0.29.0-rc3](https://github.com/nervosnetwork/neuron/releases) to fix several bugs and tweak performance.
-   [Reset Aggron testnet](https://github.com/nervosnetwork/ckb/wiki/Chains).
-   Created a new ‘developer tool’ team to focus on building tools to help developers on-board and build on CKB

### CKB Updates

#### Completed

-   A lot of work completed to improve the chain sync performance. See changes log of [v0.30.1-pre1](https://github.com/nervosnetwork/ckb/releases/tag/v0.31.0-pre1).
-   Improved RPC error message when a method is disabled ([\#1948](https://github.com/nervosnetwork/ckb/pull/1948) by [@driftluo](https://github.com/driftluo)).
-   Built [ckb-net-monitor](https://github.com/quake/ckb-net-monitor) to collect CKB network metrics.
-   Added tracers to analyze memory usage ([\#1940](https://github.com/nervosnetwork/ckb/pull/1940), [\#1946](https://github.com/nervosnetwork/ckb/pull/1946) and [\#1927](https://github.com/nervosnetwork/ckb/pull/1927)) by [yangby-cryptape](https://github.com/yangby-cryptape)).
-   Fixed a VM performance regression ([\#1955](https://github.com/nervosnetwork/ckb/pull/1955) by [xxuejie](https://github.com/xxuejie)).

#### In Progress

Working on blocks filtering service PoC like BIP [37](https://github.com/bitcoin/bips/blob/master/bip-0037.mediawiki) and [157](https://github.com/bitcoin/bips/blob/master/bip-0157.mediawiki).

### Dev Tool Updates

#### Completed

-   Created [CKB JavaScript Toolkit](https://github.com/xxuejie/ckb-js-toolkit) and [Molecule JavaScript Plugin](https://github.com/xxuejie/moleculec-es).
-   Created a new [CKB Ruby SDK](https://github.com/quake/ckb-ruby-sdk)
-   Created a new developer tool team that is specialized in developing tools that can help developers build better CKB software! While this small team is still in planning phase, we already have many interesting plans ahead, please stay tuned.

### Application Updates

#### Completed

-   [Reset testnet Aggron](https://github.com/nervosnetwork/ckb/wiki/Chains) with the spec defined in CKB node v0.30.1
-   Released [Neuron v0.29.0-rc3](https://github.com/nervosnetwork/neuron/releases) to fix several bugs and tweak performance

#### In Progress

-   Working on new NervosDAO UX of Neuron
-   Working on [sUDT](https://talk.nervos.org/t/rfc-simple-udt-draft-spec/4333)support for both Neuron and CKB Explorer

------------------------------------------------------------------------

**Join our community:** [Github](https://github.com/nervosnetwork) [Forum](https://talk.nervos.org/) [Reddit](https://www.reddit.com/r/NervosNetwork) [Twitter](https://twitter.com/nervosnetwork)

For discussions or questions join the conversation on [**Discord**](https://discord.gg/Cc8Tr6K) **or** check out one of our community Telegram channels: [**English**](https://t.me/NervosNetwork)**,** [**Korean**](http://t.me/NervosKorea)**,** [**Russian**](https://t.me/NervosRussia)**,** [**Japanese**](http://t.me/NervosNertwork_japan)**,** [**Spanish**](https://t.me/NervosNetworkES)**,** [**Vietnamese**](https://t.me/nervosvietnam) and [**Chinese**](https://t.me/NervosNetworkcn)

By [Ian Yang](https://medium.com/@doitian) on [March 25, 2020](https://medium.com/p/7b253fdb464).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-31-7b253fdb464)

Exported from [Medium](https://medium.com) on May 12, 2020.
