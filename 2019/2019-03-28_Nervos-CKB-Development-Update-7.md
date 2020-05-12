# Nervos CKB Development Update \#7

Covering Mar 11 to Mar 24

------------------------------------------------------------------------

### Nervos CKB Development Update \#7

Covering Mar 11 to Mar 24

![](https://cdn-images-1.medium.com/max/1200/1*t1MMQcZ_RhFIpZ6yHlBkSg.png)

### TL;DR

-   CKB has switched to the new P2P library.
-   CKB VM has merged the baseline JIT in master.

### Changes in RFCs

[PR\#83](https://github.com/nervosnetwork/rfcs/pull/83) has been accepted as RFC0017. It suggests adding a new consensus rule to prevent a cell to be spent before a certain block timestamp or a block number.

[PR\#91](https://github.com/nervosnetwork/rfcs/pull/91) adds data structure document. It also captures the ongoing script refactoring changes in [ckb\#344](https://github.com/nervosnetwork/ckb/pull/344).

### Changes in CKB

CKB has frozen the code for v0.8.0.

The major change in the version is the P2P library switch ([\#295](https://github.com/nervosnetwork/ckb/pull/295)). The new P2P library brings back the network discovery feature ([\#340](https://github.com/nervosnetwork/ckb/pull/340)).

Developer [@jjyr](https://github.com/jjyr) did several refactoring related to the peers management:

-   [\#345](https://github.com/nervosnetwork/ckb/pull/345): Add `random_peers` function to PeerStore
-   [\#356](https://github.com/nervosnetwork/ckb/pull/356): Unify network peer scoring
-   [\#349](https://github.com/nervosnetwork/ckb/pull/349): Refactor peer store

These refactoring allow us to implement the future reputation rules for better security.

[@zhangsoledad](https://github.com/zhangsoledad) made the code safer and easy to debug to avoid the usage of `unwrap`.

-   [\#350](https://github.com/nervosnetwork/ckb/pull/350): Use TryFrom convert protocol. This prevents the node crashing on invalid network messages.
-   [\#346](https://github.com/nervosnetwork/ckb/pull/346): Replace unwrap with expect.

He also added several missing verifications while sorting out the [RFC0016](https://github.com/nervosnetwork/rfcs/pull/80).

-   [\#335](https://github.com/nervosnetwork/ckb/pull/335): Enforce `type` field of a cellbase output cell must be absent
-   [\#334](https://github.com/nervosnetwork/ckb/pull/334): Version verification
-   [\#341](https://github.com/nervosnetwork/ckb/pull/341): Verify tx cycles in relay protocol

[@quake](https://github.com/quake) refactored some code with CellProvider ([\#343](https://github.com/nervosnetwork/ckb/pull/343)). This refactoring is intended to remove closure in ChainService and duplicate code in ChainState.

[@u2](https://github.com/u2) finished another task of [cellbase outputs maturity checking](https://github.com/nervosnetwork/ckb/issues/54), [\#336](https://github.com/nervosnetwork/ckb/pull/336), which indexes whether a transaction is a cellbase in the chain.

There are two features which are going to be included in v0.8.0, but are not merged yet.

-   [\#344](https://github.com/nervosnetwork/ckb/pull/344) revises script structure to make the model simple and elegant.
-   [\#355](https://github.com/nervosnetwork/ckb/pull/355) integrates sentry to capture errors.

### Changes in CKB VM

-   The baseline JIT is merged into master! Now it’s organized as an optional feature, we will continue be testing and working on the baseline JIT to make sure it is both fast and secure
-   Refactoring work are going on in the CKB VM repo to make it better: [PR\#31](https://github.com/nervosnetwork/ckb-vm/pull/31), [PR\#32](https://github.com/nervosnetwork/ckb-vm/pull/32), [PR\#33](https://github.com/nervosnetwork/ckb-vm/pull/33), [PR\#34](https://github.com/nervosnetwork/ckb-vm/pull/33)
-   We are also working on upgrading CKB to use the latest CKB VM in time for the testnet

### Changes in P2P

-   Update discovery protocol [PR\#66](https://github.com/nervosnetwork/p2p/pull/66), [PR\#71](https://github.com/nervosnetwork/p2p/pull/71), [PR\#74](https://github.com/nervosnetwork/p2p/pull/74)
-   Add an error type (MuxerError) [PR\#70](https://github.com/nervosnetwork/p2p/pull/70)
-   Add keypair API to ServiceContext [PR\#75](https://github.com/nervosnetwork/p2p/pull/75)
-   Abstract transport layer(prepare for support websocket) [PR\#76](https://github.com/nervosnetwork/p2p/pull/76)
-   Fix dial failed bug [PR\#79](https://github.com/nervosnetwork/p2p/pull/79)

### Changes in Toolchains

CKB Explorer

-   Prototype design and project plan.
-   Start initial project.

CKB Testnet Faucet

-   Integrate Swift SDK with SPM (Swift Package Manager)
-   Implement lock tool
-   Refactor backend/frontend

Ruby Demo

-   Improve tests
-   Update blake2b scripts and docs
-   Extract SDK and refactor

Ruby SDK

-   Extract SDK from Ruby Demo

Swift SDK

-   Remove Ruby unlock script
-   Improve tests
-   Add SPM support

Java SDK

-   Remove Ruby unlock script
-   Improve RPC interfaces and tests

JavaScript SDK

-   Remove Ruby unlock script
-   Add blake2b-wasm type definitions

Misc

-   Update scripts (system & ruby) with blake2b, fixes bugs

By [Ian Yang](https://medium.com/@doitian) on [March 28, 2019](https://medium.com/p/688735bbf265).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-7-688735bbf265)

Exported from [Medium](https://medium.com) on May 12, 2020.
