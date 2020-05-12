# Nervos CKB Development Update \#6

Covering Feb 25 to Mar 10

------------------------------------------------------------------------

### Nervos CKB Development Update \#6

Covering Feb 25 to Mar 10

![](https://cdn-images-1.medium.com/max/1200/1*1ONrYRqUVIyWK_-hRoo_pg.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92).

### TL;DR

-   We have published [**“Crypto-Economics for the Nervos Common Knowledge Base”.**](https://github.com/nervosnetwork/rfcs/pull/78)
-   CKB switched config file format to TOML.
-   CKB will use blake2b as the hash algorithm uniformly.
-   P2P and CFB is ready to integrate.

### Changes in RFCs

There are three RFCs under review.

[PR\#78](https://github.com/nervosnetwork/rfcs/pull/78/files) describes the economic model, “Crypto-Economics for the Nervos Common Knowledge Base”. Feedback or general comments are welcome.

[PR\#80](https://github.com/nervosnetwork/rfcs/pull/80) is an overview document about various consensus verification rules.

[PR\#83](https://github.com/nervosnetwork/rfcs/pull/83) suggests adding a new consensus rule to prevent a cell to be spent before a certain block timestamp or a block number.

### Changes in CKB

CKB has frozen the code for [v0.7.0](https://github.com/nervosnetwork/ckb/pull/316).

This version switched the config file format to TOML, because of better documentation support.

It has fixed several bugs:

-   remove use of upgradable reads ([\#310](https://github.com/nervosnetwork/ckb/issues/310)) ([f9e7f97](https://github.com/nervosnetwork/ckb/commit/f9e7f97)), which can lead to dead lock.
-   `block_assembler`selects invalid uncle during epoch switch ([05d29fc](https://github.com/nervosnetwork/ckb/commit/05d29fc))
-   avoid generating uncles in solo mining ([abe7a8b](https://github.com/nervosnetwork/ckb/commit/abe7a8b))

We have decided to [adopt blake2b to replace sha3](https://github.com/nervosnetwork/ckb/pull/294), it is very likely to be included in v0.7.0.

The two sub-projects have made significant progress.

-   CKB will switch to P2P soon. The changes have been submitted to [PR\#295](https://github.com/nervosnetwork/ckb/pull/295).
-   [CFB Encoding builder](https://github.com/nervosnetwork/cfb/pull/3) is ready and is going to be integrated in the following weeks.

### Changes in P2P

-   Report open protocol failed PR[\#54](https://github.com/nervosnetwork/p2p/pull/54/files)
-   Support capture all events in ServiceEvent PR[\#58](https://github.com/nervosnetwork/p2p/pull/58/files)
-   Dial now need give protocol ids as arguments PR[\#62](https://github.com/nervosnetwork/p2p/pull/58/files)
-   Change protocol metadata from trait to struct PR[\#64](https://github.com/nervosnetwork/p2p/pull/64)
-   Remote Codec as a generic argument of Service PR[\#63](https://github.com/nervosnetwork/p2p/pull/63/files)
-   Add poll API to protocol handler PR[\#65](https://github.com/nervosnetwork/p2p/pull/65/files)

### Changes in Toolchains

Swift SDK

-   Replace secp256k1 Swift library wrapping C library directly.
-   Implement trace and network RPC methods.
-   Replace SHA3 with Blake2b.

Ruby (Demo) SDK

-   Implement trace and network RPC methods.
-   Replace SHA3 with Blake2b. (WIP)

JavaScript SDK

-   Implement trace and network RPC methods.
-   Replace SHA3 with Blake2b.
-   Release v0.0.1-alpha.3.

Java SDK

-   Implement trace RPC methods.
-   Replace SHA3 with Blake2b.

Misc

-   CKB Testnet Faucet: Bootstrap project.
-   CKB Explorer: Bootstrap project.

By [Ian Yang](https://medium.com/@doitian) on [March 12, 2019](https://medium.com/p/9ccd3b88d938).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-6-9ccd3b88d938)

Exported from [Medium](https://medium.com) on May 12, 2020.
