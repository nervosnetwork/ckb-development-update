# Nervos CKB Development Update \#9

Covering Apr 8 to Apr 21

------------------------------------------------------------------------

### Nervos CKB Development Update \#9

Covering Apr 8 to Apr 21

![](https://cdn-images-1.medium.com/max/1200/1*MOTwzIR9rTu_xKLDnOP3Ug.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92).

You may encounter 500 errors when opening some links below. It is a bug of GitHub. We are sorry for the inconvenience, you can take following workarounds: log into your account, open it in a mobile phone, append `/file` at the end of the URL.

### TL;DR

-   RFC0019 has two pending changes: segwit ([PR\#98](https://github.com/nervosnetwork/rfcs/pull/98)), removal of version from script ([PR\#91](https://github.com/nervosnetwork/rfcs/pull/91)) and capacity unit ([PR\#103](https://github.com/nervosnetwork/rfcs/pull/103)).
-   CKB has implemented tx valid since ([\#372](https://github.com/nervosnetwork/ckb/pull/372)) and cellbase maturity verification ([\#473](https://github.com/nervosnetwork/ckb/pull/473)).
-   CKB has improved the P2P network stability.

### Changes in RFCs

New

-   [PR\#103](https://github.com/nervosnetwork/rfcs/pull/103) introduces the change to cell capacity unit.
-   [PR\#102](https://github.com/nervosnetwork/rfcs/pull/102) proposes W^X Memory and exec syscall for CKB VM.

Changes

-   We have revised the core data structure for two new features. RFC0019 will capture theses changes, where [PR\#98](https://github.com/nervosnetwork/rfcs/pull/98) is for segwit, and [PR\#91](https://github.com/nervosnetwork/rfcs/pull/91) has removed version from script.
-   [PR\#97](https://github.com/nervosnetwork/rfcs/pull/97) was merged, which finalized the design of `valid_since.`

### Changes in CKB

CKB [v0.9.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.9.0) has released, and [v0.10.0](https://github.com/nervosnetwork/ckb/pull/525) is ready.

Features highlights in v0.10.0:

-   [\#473](https://github.com/nervosnetwork/ckb/pull/473): cellbase maturity verification ([@u2](https://github.com/u2))
-   [\#372](https://github.com/nervosnetwork/ckb/pull/372): tx valid since ([@jjyr](https://github.com/jjyr))
-   [\#434](https://github.com/nervosnetwork/ckb/pull/434): Change all u64 fields in RPC to String ([@xxuejie](https://github.com/xxuejie))
-   [\#422](https://github.com/nervosnetwork/ckb/pull/422): Remove version from Script ([@xxuejie](https://github.com/xxuejie))

This release contains many bug fixings to improve the P2P network stability:

-   [\#448](https://github.com/nervosnetwork/ckb/pull/448): relay known filter ([@zhangsoledad](https://github.com/zhangsoledad))
-   [\#477](https://github.com/nervosnetwork/ckb/pull/477): fix mining dependent txs in one block ([@jjyr](https://github.com/jjyr))
-   [\#471](https://github.com/nervosnetwork/ckb/pull/471): CuckooEngine verify invalid length proof should not panic ([@quake](https://github.com/quake))
-   [\#469](https://github.com/nervosnetwork/ckb/pull/469): fix PeerStore unique constraint failures ([@jjyr](https://github.com/jjyr))
-   [\#455](https://github.com/nervosnetwork/ckb/pull/455): fix Sqlite can not start ([@TheWaWaR](https://github.com/TheWaWaR))
-   [\#414](https://github.com/nervosnetwork/ckb/pull/414): clear tx verfy cache when chain reorg ([@zhangsoledad](https://github.com/zhangsoledad))
-   [\#392](https://github.com/nervosnetwork/ckb/pull/392): avoid recursive lock ([@zhangsoledad](https://github.com/zhangsoledad))

### Changes in CKB VM

-   [\#47](https://github.com/nervosnetwork/ckb-vm/pull/47): Use real trace existence test instead of testing address is non-zero, thanks Zhiwei for reporting this bug!
-   [\#45](https://github.com/nervosnetwork/ckb-vm/pull/45)(still in review): Add new assembly based interpreter which leverages pure assembly for hot interpreter loop. Benchmarks show this is 3x the speed of our current optimized interpreter in Rust, this is even faster than our baseline JIT!

### Changes in P2P

-   [\#98](https://github.com/nervosnetwork/p2p/pull/98): Optional reopen handler when panic
-   [\#99](https://github.com/nervosnetwork/p2p/pull/99): Fix memory leak bug
-   [\#102](https://github.com/nervosnetwork/p2p/pull/102): Refactor discovery protocol
-   [\#105](https://github.com/nervosnetwork/p2p/pull/105): Support gracefully shutdown service
-   [\#106](https://github.com/nervosnetwork/p2p/pull/106): Fix set notify bug
-   [\#107](https://github.com/nervosnetwork/p2p/pull/107): Change ProtocolId/SessionId type
-   [\#108](https://github.com/nervosnetwork/p2p/pull/108): Change context API
-   [\#115](https://github.com/nervosnetwork/p2p/pull/115): Use deadline to output handle block error

### Changes in Toolchains

SDKs

-   Updated CKB core type structures
-   Implemented Bech32 hash and proposed address format (RFC PR [\#100](https://github.com/nervosnetwork/rfcs/pull/100))

ggCKB testnet faucet

-   Adapted CKB and Swift SDK `v0.9.0`
-   Implemented private key generating, tx sending, etc. and related APIs

CKB Explorer

-   Implemented Web API, added more tests
-   Refactored front-end components

By [Ian Yang](https://medium.com/@doitian) on [April 24, 2019](https://medium.com/p/5e069eeddbc2).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-9-5e069eeddbc2)

Exported from [Medium](https://medium.com) on May 12, 2020.
