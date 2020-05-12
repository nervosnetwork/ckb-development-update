# Nervos CKB Development Update \#2

Covering Jan 1, 2018–Jan 13, 2019

------------------------------------------------------------------------

### Nervos CKB Development Update \#2

Covering Dec22, 2018–Jan 13, 2019

![](https://cdn-images-1.medium.com/max/1200/1*RpRxL2imLZPxd3Cw5svHiA.png)

Happy New Year! Here is the first report in 2019. Thanks to [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [James Chen](https://medium.com/u/24192bbe4c92), [Jiang Jinyang](https://medium.com/u/d953e604b9ae), they have also contributed to this writing.

**TL;DR**

-   Proposed [RFC0013](http://RFC0013) block template protocol and [RFC0014](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0014-vm-cycle-limits/0014-vm-cycle-limits.md) cycle limit.
-   Implemented [RFC0011](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0011-transaction-filter-protocol/0011-transaction-filter-protocol.md) transaction filter protocol and [RFC0014](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0014-vm-cycle-limits/0014-vm-cycle-limits.md) cycle limit.
-   Added new consensus rule to verify block timestamp.
-   Working on VM JIT.

### Changes in RFCs

#### New RFC

-   [RFC0013](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0013-get-block-template/0013-get-block-template.md): block template RFC describes the decentralized CKB mining protocol.
-   [RFC0014](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0014-vm-cycle-limits/0014-vm-cycle-limits.md): cycle limit RFC describes cycle limits used to regulate VM scripts. CKB VM is a flexible VM that is free to implement many control flow constructs, such as loops or branches. As a result, we will need to enforce certain rules in CKB VM to prevent malicious scripts, such as a script with infinite loops.

#### Updates

-   [RFC0003](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0003-ckb-vm/0003-ckb-vm.md): update CKB VM examples based on latest development ([\#63](https://github.com/nervosnetwork/rfcs/issues/63))
-   [RFC0006](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0006-merkle-tree/0006-merkle-tree.md): use more reasonable proof structure ([\#62](https://github.com/nervosnetwork/rfcs/issues/62))

### Changes in CKB

CKB has released [v0.4.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.4.0).

This version includes the implementations of several RFCs, including the two new ones.

-   [RFC0011](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0011-transaction-filter-protocol/0011-transaction-filter-protocol.md), transaction filter protocol, allows peers to reduce the amount of transaction data they send.
-   [RFC0014](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0014-vm-cycle-limits/0014-vm-cycle-limits.md): cycle limit RFC.

The implementation of RFC0013 block template has started and is scheduled to release in the next version.

CKB has adopted a new consensus rule to verify block timestamp based on the past blocks median time ([c63d64b](https://github.com/nervosnetwork/ckb/commit/c63d64b)). It will also print a warning message when the node finds out its local time has a big difference with its peers.

We have removed the broken KAD discovery protocol ([f2d86ba](https://github.com/nervosnetwork/ckb/commit/f2d86ba)). Thus the node only connects to the peers listed in the configuration file. The new P2P framework will include the discovery protocol as mentioned in [RFC0012](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0012-node-discovery/0012-node-discovery.md).

The peer store uses SQLite now to ease implementing rules defined in [RFC0007](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0007-scoring-system-and-network-security/0007-scoring-system-and-network-security.md).

There is also a bundle of incompatible refactorings:

-   CellStatus uses dead and live now. `CellOutput#contract` is renamed to `CellOutput#_type.`
-   JSONRPC encodes binary fields in hex.
-   P2P encodes `H256` and `ProposalShortId` using the FlatBuffers struct instead of bytes array before.

See the change log in the release about all the breaking changes.

### Changes in VM

-   Add support for RFC0014, the cycle limit RFC.
-   Use `checked_add` when calculating cycles to avoid integer overflows.
-   CKB VM JIT research and initial implementation ([ckb-vm\#20](https://github.com/nervosnetwork/ckb-vm/issues/20)).

CKB VM JIT will be a 2-level JIT:

-   A baseline JIT which handles most common code segments, which works quite like QEMU’s [TCG](https://wiki.qemu.org/Documentation/TCG) or [rv8](https://rv8.io/). At this level, JIT compilation time will be as important as execution speed of generated code, so we would only employ certain easier optimizations here.
-   A more sophisticated SSA-based JIT for handling very hot code segments. At this layer, the execution speed of generated code will take much higher priority than JIT compilation time, so more effective but time-consuming optimizations would occur here. We might also introduce existing compiling frameworks to solve this.

### Changes in P2P

-   Refactor network service API ([PR\#9](https://github.com/nervosnetwork/p2p/pull/9))

Thanks for checking, we plan to have this development update on a bi-weekly basis. See you next time!

By [Ian Yang](https://medium.com/@doitian) on [January 16, 2019](https://medium.com/p/7085337352b4).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-2-7085337352b4)

Exported from [Medium](https://medium.com) on May 12, 2020.
