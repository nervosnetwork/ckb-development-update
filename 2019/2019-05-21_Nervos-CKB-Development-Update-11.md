# Nervos CKB Development Update \#11

Covering May 6 to May 19

------------------------------------------------------------------------

### Nervos CKB Development Update \#11

Covering May 6 to May 19

![](https://cdn-images-1.medium.com/max/800/1*IfjVjRsDItHFBLQYzETTfg.jpeg)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92).

### TL;DR

-   [Nervos testnet Rylai is live](https://medium.com/nervosnetwork/https-medium-com-nervosnetwork-nervos-testnet-is-live-501b6907a383)!

### Changes in CKB

We have released v0.11.0 and [v0.12.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.12.0) last two weeks, where v0.12.0 is the release for testnet launch.

Features highlights in v0.12.0:

This is the last sprint before testnet launch. We did many performance test, and have resolved several performance issues and fixed many bugs.

The release contains two important features:

-   [\#718](https://github.com/nervosnetwork/ckb/pull/718): Initial NervosDAO implementation ([@xxuejie](https://github.com/xxuejie)). This is a corner stone of our economic model. In order to implement DAO, we added the ability to read a block header in VM ([\#620](https://github.com/nervosnetwork/ckb/pull/620)) without breaking the transaction execution result certainty.
-   [\#579](https://github.com/nervosnetwork/ckb/pull/579): Epoch revision ([@zhangsoledad](https://github.com/zhangsoledad)). This is a part of the NC-MAX Consensus. An epoch issues fixed amount of CKB but the blocks number in an epoch varies.

### Changes in VM

By default, CKB is running on our latest assembly based CKB VM interpreter now! Compared to the old Rust based implementation, this brings 2–3x speedup on real workload.

For maximum security, we added [W^X](https://en.wikipedia.org/wiki/W%5EX) memory protection in CKB VM now. The loaded script code will be marked as executable, while all the other memory pages will be marked as writable. The running script cannot write to executable memory and vice versa. We believe this will significantly enhance the security of CKB VM.

-   [\#49](https://github.com/nervosnetwork/ckb-vm/pull/49): fix misaligned jump bug
-   [\#50](https://github.com/nervosnetwork/ckb-vm/pull/50): mulw bug in assembly based VM
-   [\#51](https://github.com/nervosnetwork/ckb-vm/pull/51): Beautify CKB VM API
-   [\#52](https://github.com/nervosnetwork/ckb-vm/pull/52): shrink VM’s memory from 16MB to 4MB
-   [\#53](https://github.com/nervosnetwork/ckb-vm/pull/53): W^X initial implementation
-   [\#56](https://github.com/nervosnetwork/ckb-vm/pull/56): Numerous performance tweaks based on current design assumption
-   [\#57](https://github.com/nervosnetwork/ckb-vm/pull/57): refactor: calculate address first before cond operation

### Changes in P2P

Refactor library to limit send/receive buffer size, otherwise it will easily cause OOM when broadcast large amount of messages to peers. Carefully use `tokio::timer::{Interval, Delay}`, it may cause network service can not shutdown.

-   [\#129](https://github.com/nervosnetwork/p2p/pull/129): Implement task priority in the framework
-   [\#131](https://github.com/nervosnetwork/p2p/pull/131): Limit send buffer size
-   [\#135](https://github.com/nervosnetwork/p2p/pull/135): Improve task schedule strategy
-   [\#141](https://github.com/nervosnetwork/p2p/pull/141): Move notify to protocol stream
-   [\#144](https://github.com/nervosnetwork/p2p/pull/144) : Gracefully shutdown network service
-   [\#150](https://github.com/nervosnetwork/p2p/pull/150): Fix future task loop forever bug

### Changes in Toolchains

SDKs

-   Released v0.11.0 and v0.12.0 adapting many CKB changes to be ready for testnet.
-   Updated to fully work on testnet.

CKB testnet faucet

-   Implemented GitHub authorization capacity transferring.

CKB Explorer

-   Polished UI design, finished core features
-   Launched with CKB testnet Rylai

CKB Neuron Wallet

-   Registered BIP44 cointype 309
-   Updated SDK, Electron and other dependencies to new versions
-   Implemented mnemonic seed import and wallet storage

> **Get started on the Rylai testnet** [**here**](https://docs.nervos.org/)**.**

Please connect with us on [**Github**](https://github.com/nervosnetwork/ckb)**,** [**CKB Dev telegram**](https://t.me/nervos_ckb_dev) or the [**Nervos Forum**](https://talk.nervos.org/)if you run into any issues or can help improve documentation.

By [Ian Yang](https://medium.com/@doitian) on [May 21, 2019](https://medium.com/p/59a4037b6cd3).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-11-59a4037b6cd3)

Exported from [Medium](https://medium.com) on May 12, 2020.
