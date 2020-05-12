# Nervos CKB Development Update \#8

Covering Mar 25 to Apr 7

------------------------------------------------------------------------

### Nervos CKB Development Update \#8

Covering Mar 25 to Apr 7

![](https://cdn-images-1.medium.com/max/1200/1*QEB-OU0QUJtM5piG_DqY0Q.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92).

### TL;DR

-   [RFC0017](https://github.com/nervosnetwork/rfcs/pull/97) has a new design.
-   CKB has released segwit, and revised the script structure.

### Changes in RFCs

[PR\#97](https://github.com/nervosnetwork/rfcs/pull/97) revised RFC0017, which moves the `valid_since` field to transaction input and reserved the highest 8 bits as flags.

[PR\#91](https://github.com/nervosnetwork/rfcs/pull/91), which describes the core data structure, has been accepted as RFC0019. It will be merged once the CKB implementation has caught up all the changes.

### Changes in CKB

CKB has released [v0.8.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.8.0) and frozen [v0.9.0](https://github.com/nervosnetwork/ckb/pull/413).

In v0.9.0, we have delivered several features which had changed the code data structure.

-   [\#368](https://github.com/nervosnetwork/ckb/pull/368): segregated witness (by zhangsoledad). This feature has resolved the transaction id malleability problem.
-   [\#409](https://github.com/nervosnetwork/ckb/pull/409): remove uncle cellbase (by zhangsoledad). It is designed to reward uncle miner, but is no longer used.
-   [\#344](https://github.com/nervosnetwork/ckb/pull/344): Revise script structure (by xxuejie). This is a big change to the cell model. We have redesigned the scripts layout, and how to locate the scripts. The RFC0019 already covered all the changes.

We also reworked how to package config files. After discussion, we decided to bundle the default config files into the binary. [\#369](https://github.com/nervosnetwork/ckb/pull/369) is the first step to embed chain specs, and [\#425](https://github.com/nervosnetwork/ckb/pull/425) continues to bundle the app config files as well.

This release also has fixed bunch of bugs:

-   [\#410](https://github.com/nervosnetwork/ckb/pull/410): network panic errors
-   [\#386](https://github.com/nervosnetwork/ckb/pull/386): flatbuffers vtable `num_fields` overflow
-   [\#385](https://github.com/nervosnetwork/ckb/pull/385): Upgrade p2p fix repeat connection bug
-   [\#382](https://github.com/nervosnetwork/ckb/pull/382): reset peer store connection status when setup

### Changes in CKB VM

A lot of work has been done this week to optimize the performance of CKB VM’s interpreter mode.

-   Use traces to optimize interpreter performance [PR\#37](https://github.com/nervosnetwork/ckb-vm/pull/37)
-   Fix trace bug in memory writes [PR\#39](https://github.com/nervosnetwork/ckb-vm/pull/39)
-   Add interpreter benchmarks [PR\#40](https://github.com/nervosnetwork/ckb-vm/pull/40)
-   Instruction structure refactoring [PR\#41](https://github.com/nervosnetwork/ckb-vm/pull/41)

There’re 2 sides of the performance optimization:

1.  First, we manage to make CKB VM 2x faster;
2.  Second, we manage to shrink the memory required to run CKB VM, and we also change the data structure so that memory consumption has a fixed upper bound, which also enhances security.

### Changes in P2P

-   Change ServiceProtocol/SessionProtocol API (mainly context API) [PR\#82](https://github.com/nervosnetwork/p2p/pull/82)
-   Add flatbuffer verifier [PR\#84](https://github.com/nervosnetwork/p2p/pull/84)
-   Handle timer task in ServiceControl [PR\#85](https://github.com/nervosnetwork/p2p/pull/85)
-   Change send message API [PR\#87](https://github.com/nervosnetwork/p2p/pull/87)
-   Fix 2 session close bugs [PR\#88](https://github.com/nervosnetwork/p2p/pull/88), [PR\#92](https://github.com/nervosnetwork/p2p/pull/92)
-   Use unbounded channel for ServiceTask [PR\#94](https://github.com/nervosnetwork/p2p/pull/94)
-   Add more Error types [PR\#96](https://github.com/nervosnetwork/p2p/pull/96)
-   Allow user define version select function [PR\#97](https://github.com/nervosnetwork/p2p/pull/97)

### Changes in Toolchains

CKB Explorer

-   Complete API doc for frontend/backend
-   UI & feature development
-   Implement node data syncing logic

CKB Testnet Faucet

-   Integrate with Swift SDK v0.7.0, update to Swift 5
-   Fix logic of lock tool
-   Polish UI

Ruby Demo & SDKs

-   Update Script struct
-   Fix tests

By [Ian Yang](https://medium.com/@doitian) on [April 9, 2019](https://medium.com/p/49079b331f93).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-8-49079b331f93)

Exported from [Medium](https://medium.com) on May 12, 2020.
