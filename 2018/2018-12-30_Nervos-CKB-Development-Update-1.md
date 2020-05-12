# Nervos CKB Development Update \#1

covering 11/26–12/21 2018

------------------------------------------------------------------------

### Nervos CKB Development Update \#1

covering Nov.26–Dec.21 2018

![](https://cdn-images-1.medium.com/max/1200/1*Jox4nnTe7Pn8kQVZXUKmQw.png)

Hello from the CKB team, since the open-source of [Nervos CKB](https://github.com/nervosnetwork/ckb), we have released [v0.2.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.2.0) this month. I put together a development update covering Nov.26 to Dec.21, and we will be sharing the CKB development update on a bi-weekly basis starting next month.

Thanks for the input from [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [dingwei.zhang](https://medium.com/u/c29952f3ded), [Jan Xie](https://medium.com/u/ad74c0ef8418), [James Chen](https://medium.com/u/24192bbe4c92), [Jiang Jinyang](https://medium.com/u/d953e604b9ae), [Qian Linfeng](https://github.com/thewawar) and [Luo Chao](https://github.com/driftluo).

### TL;DR

-   Upgraded Rust to 1.31.0 and migrated to numext.
-   Miner is now a separate process.
-   Started the brand-new P2P framework.
-   Enhanced peers management with inbound connections eviction, group and a new peer store.
-   Revised and refactored the syscalls for future scripts development.
-   More demos: partial signature, non-interactive transfer, fixed cap UDT.
-   Initiated Swift and Java SDK.

### Changes in RFCs

The RFC (Request for Comments) process is intended to provide an open and community driven path for new protocols, improvements and best practices. One month later after open source, we have 11 RFCs in draft or proposal status. We haven’t finalized them yet, discussions and comments are welcome.

-   [RFC0002](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0002-ckb/0002-ckb.md) provides an overview of the Nervos Common Knowledge Base (CKB), the core component of the Nervos Network, a decentralized application platform with a layered architecture. The CKB is the layer 1 of Nervos, and serves as a general purpose common knowledge base that provides data, asset, and identity services.
-   [RFC0003](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0003-ckb-vm/0003-ckb-vm.md) introduces the VM for scripting on CKB the layer 1 chain. VM layer in CKB is used to perform a series of validation rules to determine if transaction is valid given transaction’s inputs and outputs. CKB uses [RISC-V](https://riscv.org/) ISA to implement VM layer. CKB relies on dynamic linking and syscalls to provide additional capabilities required by the blockchain, such as reading external cells or other crypto computations. Any compilers with RV64I support, such as [riscv-gcc](https://github.com/riscv/riscv-gcc), [riscv-llvm](https://github.com/lowRISC/riscv-llvm) or [Rust](https://github.com/rust-embedded/wg/issues/218) can be used to generate CKB compatible scripts.
-   [RFC0004](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0004-ckb-block-sync/0004-ckb-block-sync.md) is the protocol how CKB nodes synchronize blocks via the P2P network. Block synchronization **must** be performed in stages with Bitcoin Headers First style. Block is downloaded in parts in each stage and is validated using the obtained parts.
-   [RFC0006](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0006-merkle-tree/0006-merkle-tree.md) proposes Complete Binary Merkle Tree(CBMT) to generate *Merkle Root* and *Merkle Proof* for a static list of items in CKB. Currently, CBMT is used to calculate *Transactions Root*. Basically, CBMT is a ***complete binary tree***, in which every level, except possibly the last, is completely filled, and all nodes are as far left as possible. And it is also a ***full binary tree\*, in which every node other than the leaves has two children. Compare with other Merkle trees, the hash computation of CBMT is minimal, as well as the proof size.***
-   [RFC0007](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0007-scoring-system-and-network-security/0007-scoring-system-and-network-security.md) describes the scoring system of CKB P2P Networking layer and several networking security strategies based on it.
-   [RFC0009](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0009-vm-syscalls/0009-vm-syscalls.md) describes syscalls specification, and all the RISC-V VM syscalls implemented in CKB so far.
-   [RFC0010](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0010-cellbase-maturity-period/0010-cellbase-maturity-period.md) defines the consensus rule “cellbase maturity period”. For each input, if the referenced output transaction is cellbase, it must have at least `CELLBASE_MATURITY` confirmations; else reject this transaction.
-   [RFC0011](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0011-transaction-filter-protocol/0011-transaction-filter-protocol.md), transaction filter protocol, allows peers to reduce the amount of transaction data they send. Peer which wants to retrieve transactions of interest, has the option of setting filters on each connection. A filter is defined as a [Bloom filter](http://en.wikipedia.org/wiki/Bloom_filter) on data derived from transactions.
-   [RFC0012](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0012-node-discovery/0012-node-discovery.md) proposes a P2P node discovery protocol. CKB Node Discovery Protocol mainly refers to [Satoshi Client Node Discovery](https://en.bitcoin.it/wiki/Satoshi_Client_Node_Discovery), with some modifications to meet our requirements.

#### Changes in CKB

CKB has [released](https://github.com/nervosnetwork/ckb/releases) v0.2.0 this month and we will release v0.3.0 next month.

🎉 Rust 2018 🎉. We have upgraded all the major repositories to Rust 1.31.0 and 2018 edition. After the Rust upgrade, we can switch to [**numext**](https://github.com/yangby-cryptape/rust-numext)**,** which is a [high-performance](https://gist.github.com/zhangsoledad/969dfaff85fa6efd77388c840701ea12) big number library relying on some new features in 1.31.0.

CKB is [dockerized](https://hub.docker.com/r/nervos/ckb). It has never been easier to run a CKB node: `docker run -ti nervos/ckb:latest run`

The node started via `ckb run` no longer produces new blocks. This feature is now in a new process which is launched by `ckb miner` ([\#52](https://github.com/nervosnetwork/ckb/pull/52)). The new process gets block template from a node and submits new block with resolved PoW puzzle via node's RPC. The RPC interface for miners is temporary, and we are working on an RFC proposal for this. After this change, we also modularized RPCs ([\#118](https://github.com/nervosnetwork/ckb/pull/118)). Now each RPC module can be disabled via config file.

Another feature we are actively developing is peers management. This month, we have implemented network group and inbound peer eviction which described in [RFC0007](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0007-scoring-system-and-network-security/0007-scoring-system-and-network-security.md). We also delivered a new version of `peerstore` which allow us to support security strategies defined in RFC0007 in the future.

Annoyed by the problems of existing P2P libraries, we started to work on a brand new [P2P protocol](https://github.com/nervosnetwork/p2p) from the ground up. It is still in [an early stage](https://github.com/nervosnetwork/p2p/commit/95582ec7d27e887f6d47c31a44a397329f53e55c#commitcomment-31794039) and is a minimal implementation for a multiplexed p2p network based on `yamux` that supports mounting custom protocols. We already implemented 3 core components yamux/secio/service. yamux and secio are mainly refer to their corresponding golang implementations, API are clear and easy to use. Those 3 core components are all use channel based lock-free design with good code readability and maintainability. We are adding up more custom protocols layers, and is going to integrate the discovery protocol soon as described in [RFC0012](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0012-node-discovery/0012-node-discovery.md).

We have refactored the rust utility library to mock time for debug and test ([\#111](https://github.com/nervosnetwork/ckb/pull/111)). It is now available as [a separate crate](https://github.com/nervosnetwork/faketime).

There are some other features we are still working on, such as implementation of [RFC0006](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0006-merkle-tree/0006-merkle-tree.md) and [RFC0011](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0011-transaction-filter-protocol/0011-transaction-filter-protocol.md), and the RFC about serialization format [CFB](https://github.com/nervosnetwork/rfcs/pull/47). We are going to release them in next month.

#### Changes in VM

All the CKB related syscalls used in the VM have been revisited and refactored to be more future proof.

CKB VM used in CKB has upgraded to the latest revision with the following notable changes:

-   With experience learned from real contracts, the maximum memory in CKB VM has been reduced from 128MB to 16MB
-   CKB VM has adopted Rust 2018 style

#### Changes in SDK

-   Implement [all bitcoin payment schemes](https://github.com/nervosnetwork/ckb-demo-ruby-sdk/tree/master/contracts/bitcoin) in CKB Ruby SDK.
-   Add [a new account UDT wallet mode](https://github.com/nervosnetwork/ckb-demo-ruby-sdk/pull/10) that supports one-step token transfer
-   Add new [UDT type with fixed upper cap](https://github.com/nervosnetwork/ckb-demo-ruby-sdk/tree/master/contracts/fixed_amount_udt)
-   Refactor Ruby SDK to eliminate dependency on modifying genesis block
-   Start [Swift](https://github.com/nervosnetwork/ckb-sdk-swift) and [Java](https://github.com/nervosnetwork/ckb-sdk-java) SDK. Basic RPC feature implemented.

Thanks for checking this, and we’d love to hear from you, email us at **ckb-dev@nervos.org** if you have any questions! Wish you a happy new year and may your journey be wonderful.

By [Ian Yang](https://medium.com/@doitian) on [December 30, 2018](https://medium.com/p/d23ca1a8c380).

[Canonical link](https://medium.com/@doitian/covering-11-26-12-21-2018-d23ca1a8c380)

Exported from [Medium](https://medium.com) on May 12, 2020.
