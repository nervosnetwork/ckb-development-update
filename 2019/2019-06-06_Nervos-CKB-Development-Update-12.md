# Nervos CKB Development Update \#12

Covering May 20 to Jun 2

------------------------------------------------------------------------

### Nervos CKB Development Update \#12

Covering May 20 to Jun 2

![](https://cdn-images-1.medium.com/max/1200/1*D1zKXiQU5YvBeG6Sy_H0mQ.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92).

### TL;DR

-   CKB revamps the verification model.
-   P2P supports UPnP now.

### Changes in CKB

CKB [v0.13.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.13.0) has released, and [v0.14.0](https://github.com/nervosnetwork/ckb/pull/941) is ready.

The most important change in v0.14.0 is [\#913](https://github.com/nervosnetwork/ckb/pull/913), the new verification model ([@xxuejie](https://github.com/xxuejie)).

> Based on feedbacks gathered earlier, we are revising our verification  
> model with the following changes:

> When validating a transaction, CKB will grab all lock scripts from  
> all inputs, and group them based on lock script hash. The script in  
> each group will only be run once. The lock script itself will have  
> to do the validation task for all inputs in the same group

> CKB will also grab all type scripts from inputs and outputs(notice  
> different from previous version, the type scripts in inputs are  
> included here as well), and group them based on type script hash as  
> well. Each type script in each group will also be run once. The type  
> script itself needs to handle the validation task within the group

> Syscalls are also revised to allow fetching all the  
> inputs/outputs/witnesses within a single group.

> Input args is removed since the functionality can be replicated elsewhere

Other features highlights in v0.13.0 and v0.14.0:

-   [\#874](https://github.com/nervosnetwork/ckb/pull/874): Revise uncle rule ([@zhangsoledad](https://github.com/zhangsoledad)). It gets rid uncle age limit and tries to include disconnected block as uncle.
-   [\#845](https://github.com/nervosnetwork/ckb/pull/845): Limit TXO set memory usage ([@yangby-cryptape](https://github.com/yangby-cryptape)).
-   [\#841](https://github.com/nervosnetwork/ckb/pull/841): Apply transaction pool limit ([@zhangsoledad](https://github.com/zhangsoledad)). The limit controls the pool memory usage.
-   [\#890](https://github.com/nervosnetwork/ckb/pull/890): Revise remainder reward rule ([@zhangsoledad](https://github.com/zhangsoledad)). Instead the first block in an epoch get all the remainder, the remainder is divided evenly by first r blocks.
-   [\#859](https://github.com/nervosnetwork/ckb/pull/859): Use snappy to compress large messages ([@driftluo](https://github.com/driftluo)). It saves bandwidth with CPU overhead.

### Changes in VM

-   [\#59](https://github.com/nervosnetwork/ckb-vm/pull/59) fix a bad way to using machine ([@mohanson](https://github.com/mohanson))
-   [\#60](https://github.com/nervosnetwork/ckb-vm/pull/60) fix the broken bench tests ([@mohanson](https://github.com/mohanson))
-   [\#61](https://github.com/nervosnetwork/ckb-vm/pull/61) add an example named is13 ([@mohanson](https://github.com/mohanson))
-   [\#62](https://github.com/nervosnetwork/ckb-vm/pull/62) fix VM panics when ELF uses invalid file offset
-   [\#63](https://github.com/nervosnetwork/ckb-vm/pull/63) fix out of bound read check in assembly VM

### Changes in P2P

-   [\#156](https://github.com/nervosnetwork/p2p/pull/156): Replace discovery protocol tokio interval (may cause stop gracefully shutdown)
-   [\#158](https://github.com/nervosnetwork/p2p/pull/158): Add `before_receive/before_send` callback
-   [\#161](https://github.com/nervosnetwork/p2p/pull/161): Add UPnP support

### Changes in Toolchains

SDKs

-   Released v0.13.0 mainly adapting RPC changes
-   Added JRuby support to Ruby SDK
-   Added macOS support to Swift SDK

CKB testnet faucet

-   Switched to remote DB
-   Polished UI, fixed bugs

CKB Explorer

-   Fixed bugs and deployed hot-fixes
-   Added new features: lock hash search, CKB hashrate, block intervals, etc.
-   Adapted parts of UI for mobile devices

CKB Neuron Wallet

-   Added Node 12 support
-   Implemented BIP32
-   Improved background sync process
-   Refactored UI components

By [Ian Yang](https://medium.com/@doitian) on [June 6, 2019](https://medium.com/p/14052d113104).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-12-14052d113104)

Exported from [Medium](https://medium.com) on May 12, 2020.
