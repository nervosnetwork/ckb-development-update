# Nervos CKB Development Update \#27

Dec 30 to Jan 12

------------------------------------------------------------------------

### Nervos CKB Development Update \#27

Covering Dec 30 to Jan 12

by [LinFeng Qian](https://github.com/TheWaWaR), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38) and [Ian Yang](https://medium.com/u/72022cac4c7c)

![](https://cdn-images-1.medium.com/max/800/1*gqRohWfGiWcwfN40Kow6-w.png)

#### TL;DR

-   [ckb 0.27.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.27.0) released on Jan 10
-   The team is currently working on: [Animagus](https://github.com/xxuejie/animagus) — an AST contract framework, [Randao](https://github.com/keroro520/randao) — a random number generator and [Godwoken](https://github.com/jjyr/godwoken) — a layer 1.5 framework for Optimistic Rollup or Zk Rollup.

------------------------------------------------------------------------

#### Changes in RFCs

We have made several revisions to the existing RFCs ([\#167](https://github.com/nervosnetwork/rfcs/pull/167), [\#166](https://github.com/nervosnetwork/rfcs/pull/166), [\#156](https://github.com/nervosnetwork/rfcs/pull/156) and [\#164](https://github.com/nervosnetwork/rfcs/pull/164)). Thanks to [@paymog](https://github.com/paymog), [@louzhixian](https://github.com/louzhixian) and [@stwith](https://github.com/stwith) for the contribution.

#### Changes in CKB

[ckb 0.27.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.27.0) release

This version allows executing a script when the local chain has changed ([\#1891](https://github.com/nervosnetwork/ckb/pull/1891)).

[@quake](https://github.com/quake) has added TCP and WebSocket to RPC service ([\#1882](https://github.com/nervosnetwork/ckb/pull/1882)), which will allow us to add pub/sub RPCs in the next release.

In addition to the new release, the team is also working on:

-   [Animagus](https://github.com/xxuejie/animagus) — an AST contract framework.
-   [Randao](https://github.com/keroro520/randao) — a random number generator.
-   [Godwoken](https://github.com/jjyr/godwoken) — a layer 1.5 framework for Optimistic Rollup or Zk Rollup
-   Add a pruning mode to lower the disk requirement on the node.
-   Upgrade Rust toolchain and switch to new version of Tokio.

#### Changes in CKB Cli

-   q[\#227](https://github.com/nervosnetwork/ckb-cli/pull/227): Update ckb dependency to v0.27.0

#### Changes in CKB VM

-   [\#93](https://github.com/nervosnetwork/ckb-vm/pull/93) Add step mode for AsmMachine

------------------------------------------------------------------------

**Stay up to date on Nervos:** [Github](https://github.com/nervosnetwork) [Forum](https://talk.nervos.org/) [Telegram](https://t.me/nervos_ckb_dev) [Reddit](https://www.reddit.com/r/NervosNetwork) [Twitter](https://twitter.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [January 15, 2020](https://medium.com/p/d48918df00c5).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-27-d48918df00c5)

Exported from [Medium](https://medium.com) on May 12, 2020.
