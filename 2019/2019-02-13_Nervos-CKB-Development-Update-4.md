# Nervos CKB Development Update \#4

Covering Jan 28 to Feb 10

------------------------------------------------------------------------

### Nervos CKB Development Update \#4

Covering Jan 28 to Feb 10

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c) and [James Chen](https://medium.com/u/24192bbe4c92).

![](https://cdn-images-1.medium.com/max/1200/1*WestFe06HtNsRbQ8ZsEyRw.png)

### TL;DR

-   A new RPC [Occupied capacity increment rate](https://github.com/nervosnetwork/rfcs/pull/71/files?short_path=439ac1c#diff-439ac1c77d7b29d6a9df26812c42c84f) has been posted.
-   CKB v0.6.0 is ready for release. It has implemented RFC0013 `get_block_template`and replaced `local_node_id`with a new RPC `local_node_info`.

### Changes in RFCs

### New RFC

-   [Occupied capacity increment rate](https://github.com/nervosnetwork/rfcs/pull/71/files?short_path=439ac1c#diff-439ac1c77d7b29d6a9df26812c42c84f) is an RFC to limit the occupied capacity in each block. It indirectly controls the network’s total occupied capacity and the increment rate of occupied capacity.

### Updates

-   **RFC0003:**Remove atomic operation support in CKB VM ([\#68](https://github.com/nervosnetwork/rfcs/issues/68)) ([af51e3a](https://github.com/nervosnetwork/rfcs/commit/af51e3a))

### Changes in CKB

CKB v0.6.0 is [ready for release](https://github.com/nervosnetwork/ckb/pull/266).

This version has implemented [RFC0013](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0013-get-block-template/0013-get-block-template.md) `get_block_template`, which is an essential part of the decentralized CKB mining protocol.

A new RPC `local_node_info`([64e41f6](https://github.com/nervosnetwork/ckb/commit/64e41f6)) obsoletes the old `local_node_id`. The new one returns better node addresses.

This version contains several important refactorings:

-   Only fully verify blocks in the main chain ([\#158](https://github.com/nervosnetwork/ckb/issues/158)) ([07d6a69](https://github.com/nervosnetwork/ckb/commit/07d6a69)), which can speed up verification by adding caches upon the main chain tip.
-   Make rocksdb configurable via config file ([f46b4fa](https://github.com/nervosnetwork/ckb/commit/f46b4fa))
-   Service stop handler ([e0143eb](https://github.com/nervosnetwork/ckb/commit/e0143eb)) ensures the node shutdowns gracefully.
-   Use new merkle proof structure ([\#232](https://github.com/nervosnetwork/ckb/issues/232)) ([da97390](https://github.com/nervosnetwork/ckb/commit/da97390))
-   Extract merkle tree as crate ([\#223](https://github.com/nervosnetwork/ckb/issues/223)) ([a159cdf](https://github.com/nervosnetwork/ckb/commit/a159cdf)).

### Changes in Toolchains

JavaScript SDK

-   Implement asw and udt account
-   Update naming convention

Java SDK

-   Implement asw account

Ruby SDK

-   Fix/rename some methods

By [Ian Yang](https://medium.com/@doitian) on [February 13, 2019](https://medium.com/p/8ff00627f886).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-4-8ff00627f886)

Exported from [Medium](https://medium.com) on May 12, 2020.
