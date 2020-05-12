# Nervos CKB development update \#18

Aug 19 to Sep 1

------------------------------------------------------------------------

### Nervos CKB Development Update \#18

Aug 19 to Sep 1

by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92).

![](https://cdn-images-1.medium.com/max/1200/1*Auo7J1wsxCGfCwe4peElQw.png)

### TL;DR

-   We have published the serialization specification ([PR\#136](https://github.com/nervosnetwork/rfcs/pull/136)).
-   [v0.20.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.20.0-rc1) will release this Saturday, Sept 7

### Changes in RFCs

-   [PR\#136](https://github.com/nervosnetwork/rfcs/pull/136) describes the serialization format used in CKB.
-   [RFC\#0022](https://github.com/nervosnetwork/rfcs/pull/134) is an informational document about the CKB Transaction Structure.

### Changes in CKB

During the last two weeks, the team was busy fixing bugs found in v0.19.0. Version v0.20.0 is a minor release which only contains refactoring and bug fixes.

We have refactored the serialization schema to make it more space efficient, such as

-   [\#1505](https://github.com/nervosnetwork/ckb/pull/1505): Refactor serialization schema for performance ([@doitian](https://github.com/doitian))
-   [\#1469](https://github.com/nervosnetwork/ckb/pull/1469): Change `Header#dao` to Byte32 ([@quake](https://github.com/quake))
-   [\#1486](https://github.com/nervosnetwork/ckb/pull/1486): Use Byte32 to replace the majority of H256 ([@yangby-cryptape](https://github.com/yangby-cryptape))

[@Quake](https://github.com/quake) has fixed a bug ([\#1519](https://github.com/nervosnetwork/ckb/pull/1519)) and a performance issue ([\#1520](https://github.com/nervosnetwork/ckb/pull/1520)) in indexer RPC.

### Changes in CKB VM

-   [\#81](https://github.com/nervosnetwork/ckb-vm/pull/81): Upgrade goblin ([@driftluo](https://github.com/driftluo))
-   [\#82](https://github.com/nervosnetwork/ckb-vm/pull/82): Fix FlatMemory overflows

### Changes in P2P

-   [\#181](https://github.com/nervosnetwork/p2p/pull/181): Support new serialization([molecule](https://crates.io/crates/molecule)), and can switch by features
-   [\#182](https://github.com/nervosnetwork/p2p/pull/182): Default shutdown network service when protocol handler panicked
-   [\#183](https://github.com/nervosnetwork/p2p/pull/183): Fix a security issue in yamux

### Changes in CKB CLI

-   [\#49](https://github.com/nervosnetwork/ckb-cli/pull/49): Support dao transaction
-   [\#63](https://github.com/nervosnetwork/ckb-cli/pull/63): Add serialization utils sub-commands

### Changes in Toolchains

**SDKs**

-   Release v0.19.0
-   Start implementing client side serialization

**Neuron Wallet**

-   Fix keystore mac calculation bug
-   Update code sign certification
-   Improve error handling
-   Update SDK to v0.19.0

**CKB Explorer**

-   Tweak performance to load large data pages faster
-   Update SDK to v0.19.0
-   Apply address format change
-   Update block reward and hash rate display

**CKB Testnet Faucet**

-   Update SDK to v0.19.0
-   Refactor (remove unused APIs)

**Join our community:** [Forum](https://talk.nervos.org/) [Telegram](https://t.me/nervosnetwork) [Twitter](https://twitter.com/nervosnetwork) [Reddit](https://www.reddit.com/r/NervosNetwork) [Github](https://github.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [September 5, 2019](https://medium.com/p/cd4e474d133f).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-18-cd4e474d133f)

Exported from [Medium](https://medium.com) on May 12, 2020.
