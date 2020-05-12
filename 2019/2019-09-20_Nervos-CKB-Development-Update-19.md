# Nervos CKB Development Update \#19

Covering Sep 2 to Sep 15

------------------------------------------------------------------------

### Nervos CKB Development Update \#19

Sep 2 — Sep 15

by [Ian Yang](https://medium.com/@doitian), [Xuejie Xiao](https://medium.com/@defmacro), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/@ashchan)

![](https://cdn-images-1.medium.com/max/1200/1*o3DbGi-TVWOGKYgPSMyK_w@2x.jpeg)

### TL;DR

-   We have published a new Positioning Paper, [RFC0001](https://github.com/nervosnetwork/rfcs/pull/138)
-   CKB RPC uses hexadecimal number format uniformly ([\#1584](https://github.com/nervosnetwork/ckb/pull/1584))
-   Cellbase output data must be empty. ([\#1551](https://github.com/nervosnetwork/ckb/pull/1551))

### Changes in RFCs

[RFC0001](https://github.com/nervosnetwork/rfcs/pull/138) The Nervos Network Positioning Paper.

> We start this document with a detailed examination of the problems that public permissionless blockchains face today and the existing solutions attempting to solve them. \[…\] We then provide a high-level walkthrough of all parts of the Nervos Network, with a focus on how they work together to support the overall vision of the network.

### Changes in CKB

[v0.21.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.21.0-rc1) is ready to release

#### CONSENSUS

We have made several changes to consensus rules in v0.21.0.

[\#1571](https://github.com/nervosnetwork/ckb/pull/1571): `is_better_chain` uses first-received policy for security reason ([@u2](https://github.com/u2))

[\#1559](https://github.com/nervosnetwork/ckb/pull/1559): Block serialized size should not include uncles proposals serialized size ([@yangby-cryptape](https://github.com/yangby-cryptape)). This fixed the bug introduced when migrating to the new serialization format.

[\#1551](https://github.com/nervosnetwork/ckb/pull/1551): Cellbase output data must be empty. ([@driftluo](https://github.com/driftluo))

> Because the ckb reward is delayed, the ownership of the cellbase of the current block is not the miner who digs out the block, so cellbase’s output data must be disabled.

#### RPC

[\#1527](https://github.com/nervosnetwork/ckb/pull/1527): RPC `get_live_cell` added `with_data` argument and changed the response structure. ([@TheWaWaR](https://github.com/TheWaWaR))

[\#1584](https://github.com/nervosnetwork/ckb/pull/1584): Use hexadecimal number format uniformly ([@keroro520](https://github.com/keroro520))

#### OTHER

[\#1568](https://github.com/nervosnetwork/ckb/pull/1568): Indexer configuration ([@quake](https://github.com/quake)). The configuration allows us to allocate more system resources to speed up indexing.

[\#1586](https://github.com/nervosnetwork/ckb/pull/1586): Script package build adjustment ([@xxuejie](https://github.com/xxuejie)) and [\#1558](https://github.com/nervosnetwork/ckb/pull/1558): Expose method to invoke a single script on a transaction ([@xxuejie](https://github.com/xxuejie))

These changes can be helpful in CKB script debugger’s development.

### Changes in CKB VM

-   [\#83](https://github.com/nervosnetwork/ckb-vm/pull/83): EBREAK support for integrating debuggers
-   [\#84](https://github.com/nervosnetwork/ckb-vm/pull/84): Leverage YASM for building assembly interpreter on windows

One noticeable change — beginning with this version, the assembly based interpreter in CKB VM could also run on a 64-bit Windows machine, so CKB now uses the same performant VM across Linux, macOS and Windows platforms.

### Changes in P2P

-   [\#1528](https://github.com/nervosnetwork/ckb/pull/1528): CKB uses molc to serialize P2P handshake messages. ([@driftluo](https://github.com/driftluo))
-   [\#184](https://github.com/nervosnetwork/p2p/pull/184), [\#186](https://github.com/nervosnetwork/p2p/pull/186): Fix some bugs

### Changes in CKB CLI

-   [\#64](https://github.com/nervosnetwork/ckb-cli/pull/64): Add more rpc methods
-   [\#65](https://github.com/nervosnetwork/ckb-cli/pull/65): Fix index use wrong hash
-   [\#88](https://github.com/nervosnetwork/ckb-cli/pull/88): Split mock transaction structure to separate crate
-   [\#89](https://github.com/nervosnetwork/ckb-cli/pull/89): Disable color on windows when not supported
-   [\#90](https://github.com/nervosnetwork/ckb-cli/pull/90): Better error message when index db not synced

### Changes in Toolchains

-   SDKs Implement client side serialization (tx/script) and tx signing
-   Change RPC number type to encode/decode as hex string
-   Release v0.20.0

Neuron Wallet

-   Adapt SDK v0.20.0, serializing script and tx locally
-   Improve UI screens
-   Deindex addresses when wallet gets deleted
-   Release v0.20.0-beta.0

CKB Explorer

-   Adapt SDK v0.20.0
-   Change the way Hash Rate and Difficulty are displayed
-   Paginate address view
-   Add links between cells

CKB Testnet Faucet

-   Adapt SDK v0.19.0 and v0.20.0, serializing script and tx locally
-   Update deployment flow to make it faster

**Join our community:** [Forum](https://talk.nervos.org/) [Telegram](https://t.me/nervosnetwork) [Twitter](https://twitter.com/nervosnetwork) [Reddit](https://www.reddit.com/r/NervosNetwork) [Github](https://github.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [September 20, 2019](https://medium.com/p/4c08c740e66b).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-19-4c08c740e66b)

Exported from [Medium](https://medium.com) on May 12, 2020.
