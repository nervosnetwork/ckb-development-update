# Nervos CKB Development Update \#13

Covering Jun 3 to Jun 23

------------------------------------------------------------------------

### Nervos CKB Development Update \#13

Covering Jun 3 to Jun 23

![](https://cdn-images-1.medium.com/max/1200/1*U9dBSVbE-LL-DzVc6iIP2Q.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92). Because of development schedule change, we have deferred the report one week. Thus it reviews our work in the previous three weeks.

### TL;DR

-   New RFC: [RFC\#0020](https://github.com/nervosnetwork/rfcs/pull/124), the consensus protocol.

CKB Highlights:

-   [\#922](https://github.com/nervosnetwork/ckb/pull/922): Feat: proposer reward.
-   [nervosnetwork/ckb-system-scripts\#15](https://github.com/nervosnetwork/ckb-system-scripts/pull/15): The default secp256k1 uses recoverable signature.

CKB VM Highlights:

-   New AOT execution mode!
-   Full RISC-V test suite integration.

### Changes in RFC

[@nirenzang](https://github.com/nirenzang) has published the Consensus Protocol as [RFC\#0020](https://github.com/nervosnetwork/rfcs/pull/124).

> Bitcoin’s Nakamoto Consensus (NC) is well-received due to its simplicity and low communication overhead. However, NC suffers from two kinds of drawback: first, its transaction processing throughput is far from satisfactory; second, it is vulnerable to a selfish mining attack, where attackers can gain more block rewards by deviating from the protocol’s prescribed behavior.

> The CKB consensus protocol is a variant of NC that raises its performance limit and selfish mining resistance while keeping its merits. By identifying and eliminating the bottleneck in NC’s block propagation latency, our protocol supports very short block interval without sacrificing security. The shortened block interval not only raises the throughput, but also lowers the transaction confirmation latency. By incorporating all valid blocks in the difficulty adjustment, selfish mining is no longer profitable in our protocol.

### Changes in CKB

CKB [v0.14.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.14.0) has released, and [v0.15.0](https://github.com/nervosnetwork/ckb/pull/1091) is ready.

Feature highlights in v0.15.0

-   [\#922](https://github.com/nervosnetwork/ckb/pull/922): Feat: proposer reward ([@zhangsoledad](https://github.com/zhangsoledad))

Earliest transaction proposer get 40% of the transaction fee as a reward.

Block reward is deferred until the proposal window is closed.

-   [\#1054](https://github.com/nervosnetwork/ckb/pull/1054): Replace system cell ([@driftluo](https://github.com/driftluo), [@jjyr](https://github.com/jjyr))

We upgraded the default secp256k1 to use recoverable signature. See details in [nervosnetwork/ckb-system-scripts\#15](https://github.com/nervosnetwork/ckb-system-scripts/pull/15)

-   [\#910](https://github.com/nervosnetwork/ckb/pull/910): Implement the alert system in CKB for urgent situation ([@jjyr](https://github.com/jjyr))
-   [\#1000](https://github.com/nervosnetwork/ckb/pull/1000): Allow miner add an arbitrary message into the cellbase ([@driftluo](https://github.com/driftluo))
-   [\#905](https://github.com/nervosnetwork/ckb/pull/905): Add indexer related rpc ([@quake](https://github.com/quake))

See the release page for the full change list.

### Changes in VM

This is a heavy week in CKB VM. First, we have Brian Anderson reviewing and helping enhancing CKB VM! Brian is kind enough to help us with 2 fixes:

-   [\#67](https://github.com/nervosnetwork/ckb-vm/pull/67) Replace custom power\_of\_2 function with std
-   [\#68](https://github.com/nervosnetwork/ckb-vm/pull/68) Replace uses of rounddown / roundup with round\_page\_down / round\_page\_up

There’re also 2 big announcements in CKB VM:

-   First, we have implemented the new AOT execution mode! This significantly bump the runtime performance of CKB VM on top of our already fast assembly interpreter. Our benchmark shows that a secp256k1 operation can finish in the new AOT mode in under 1 ms, while the current assembly interpreter needs 5 ms at best. This brings us to the same order of magnitude of native code.
-   We have integrated full RISC-V test suite into CKB VM, now each change we made is validated against the comprehensive test suites thanks to the awesome RISC-V community. We are very serious on ensuring the correctness of CKB VM.

The exact changes for this PR include:

-   [\#64](https://github.com/nervosnetwork/ckb-vm/pull/64) refactor: windows support adjustments
-   [\#69](https://github.com/nervosnetwork/ckb-vm/pull/69) feat: add flag denoting if PC should be updated when loading ELF
-   [\#70](https://github.com/nervosnetwork/ckb-vm/pull/70) Add coverage CI job containing full CKB VM test suite
-   [\#71](https://github.com/nervosnetwork/ckb-vm/pull/71) Eliminate as much usize as making sense from CKB VM
-   [\#72](https://github.com/nervosnetwork/ckb-vm/pull/72) feat: Add new AOT mode to replace experimental JIT mode
-   [\#74](https://github.com/nervosnetwork/ckb-vm/pull/74) feat: Do not trigger coverage jobs in PRs
-   [\#75](https://github.com/nervosnetwork/ckb-vm/pull/75) test: avoid make-cov run test two times [@u2](https://github.com/u2)
-   [\#76](https://github.com/nervosnetwork/ckb-vm/pull/76) feat: Set codecov coverage target

### Changes in P2P

-   [\#162](https://github.com/nervosnetwork/p2p/pull/162): Refactor identify protocol
-   [\#163](https://github.com/nervosnetwork/p2p/pull/163): Fix bug on protocol open command send by control
-   [\#164](https://github.com/nervosnetwork/p2p/pull/164): Add open protocols interface (`DialProtocol` will deprecated on 0.3)
-   [\#168](https://github.com/nervosnetwork/p2p/pull/168): Allow dns resolver on current thread runtime

### Changes in Toolchains

SDKs

-   Released SDK `v0.14.0`
-   Added support for indexer RPC module
-   Implemented Secp256k1 recoverable sign

CKB testnet faucet

-   Removed lock-generation-tool
-   Updated to use SDK `v0.14.0`

CKB Explorer

-   Separated to two projects: front-end and server (back-end)
-   Applied many bug fixes and UI tweaks
-   Applied performance tweaks for both front end and back end
-   Enhanced block data syncing

Neuron Wallet

-   Implemented BIP39
-   Set up CI with Azure Pipelines
-   Moved transaction and chain data syncing module off main process to renderer (background) process
-   Added BIP32 public key derivation
-   Refactored keys module
-   Implemented basic layout as per design mockups
-   Implemented multiple inputs signing

Please connect with us on [**Github**](https://github.com/nervosnetwork/ckb)**,** [**CKB Dev telegram**](https://t.me/nervos_ckb_dev) or the [**Nervos Forum**](https://talk.nervos.org/)if you have any questions, run into any issues or can help improve the documentation.

Keeping up with Nervos:  
[Forum](https://talk.nervos.org)  
[Twitter](https://twitter.com/nervosnetwork)  
[Github](https://github.com/NervosNetwork)  
[Reddit](http://reddit.com/r/nervosnetwork)  
[Youtube](https://www.youtube.com/channel/UCONuJGdMzUY0Y6jrPBOzH7A)

By [Ian Yang](https://medium.com/@doitian) on [June 26, 2019](https://medium.com/p/a35985c9ea6d).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-13-a35985c9ea6d)

Exported from [Medium](https://medium.com) on May 12, 2020.
