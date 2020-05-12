# Nervos CKB Development Update \#5

Covering Feb 11 to Feb 24

------------------------------------------------------------------------

### Nervos CKB Development Update \#5

Covering Feb 11 to Feb 24

![](https://cdn-images-1.medium.com/max/1200/1*xiOpqH1mr2l8nShkASCSMA.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92).

### TL;DR

-   CKB VM Baseline JIT is [ready for review](https://github.com/nervosnetwork/ckb-vm/pull/29).
-   Proposal [Occupied capacity increment rate](https://github.com/nervosnetwork/rfcs/pull/71/files?short_path=439ac1c#diff-439ac1c77d7b29d6a9df26812c42c84f)has been rejected.

### Changes in RFCs

-   Proposal [Occupied capacity increment rate](https://github.com/nervosnetwork/rfcs/pull/71/files?short_path=439ac1c#diff-439ac1c77d7b29d6a9df26812c42c84f)has been rejected. We prefer to limit the capacity increment via block size and cycles limit indirectly.

### Changes in CKB

CKB v0.6.0 has just released. We found some bugs in this version and have rewrote JSONRPC HTTP server ([6cca12d](https://github.com/nervosnetwork/ckb/commit/6cca12d)) because of locking issues.

This version also contains a performance refactoring that transaction verification result is cached ([1aa6788](https://github.com/nervosnetwork/ckb/commit/1aa6788)).

The team had been implementing get block template ([\#165](https://github.com/nervosnetwork/ckb/issues/165)) and CFB encoding ([\#144](https://github.com/nervosnetwork/ckb/issues/144)), and will send pull requests in the following weeks.

### Changes in CKB VM

🎉 Baseline JIT is [ready for review](https://github.com/nervosnetwork/ckb-vm/pull/29).

CKB VM’s Baseline JIT is an initial simple JIT implementation that serves 2 purposes:

1.  Provides a basic feature complete JIT implementation
2.  Serves as a underlying skeleton for enabling all the more sophisticated JIT optimizations

### Changes in P2P

-   Bug fixes
-   Change `dial`API [\#42](https://github.com/nervosnetwork/p2p/pull/42)
-   Change `send_message`API [\#46](https://github.com/nervosnetwork/p2p/pull/46)
-   Support DNS reslover [\#43](https://github.com/nervosnetwork/p2p/pull/43)

### Changes in Toolchains

-   Do research on HD Wallet, UTXO collection, etc.
-   Release JavaScript SDK initial alpha (v0.0.1-alpha.1), Java SDK v0.6.0 and Ruby Demo (SDK) v0.6.0.

#### Java SDK v0.6.0 changes

-   rename `localNodeInfo`RPC method
-   support asw account and transfer

#### Ruby Demo (SDK) v0.6.0 changes

-   add support for Ruby 2.3

By [Ian Yang](https://medium.com/@doitian) on [February 26, 2019](https://medium.com/p/622d5afefe93).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-5-622d5afefe93)

Exported from [Medium](https://medium.com) on May 12, 2020.
