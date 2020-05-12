# Nervos CKB Development Update \#20

Sep 16— Oct 8

------------------------------------------------------------------------

### Nervos CKB Development Update \#20

Sep 16— Oct 8

by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38) and [Qian Linfeng](https://github.com/thewawar)

![](https://cdn-images-1.medium.com/max/1200/1*HYkQKXb-HbcmWBUpYuaKqA@2x.jpeg)

### TL;DR

-   CKB v0.22.0 has released. In this release, we made several changes to the header structure and consensus rules.
-   CKB VM now has a [standalone debugger](https://github.com/nervosnetwork/ckb-standalone-debugger).

### Changes in CKB

We released [v0.22.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.22.0) on Oct 5.

[\#1585](https://github.com/nervosnetwork/ckb/pull/1585): Include fractions in epoch number representations ([@xxuejie](https://github.com/xxuejie))

> We use a rational number format to represent epoch number.  
> The lower 54 bits of the epoch number field are split into 3  
> parts (listed in the order from higher bits to lower bits): 1. The highest 16 bits represent the epoch length; 2. The next 16 bits represent the current block index in the epoch; 3. The lowest 24 bits represent the current epoch number.

[\#1643](https://github.com/nervosnetwork/ckb/pull/1643): Compress header ([@zhangsoledad](https://github.com/zhangsoledad))

> We removed `uncles_count,` merged `transactions_root` and `witnesses_root`, and replaced `difficulty`with `compact_target`.

[\#1632](https://github.com/nervosnetwork/ckb/pull/1632): Change script args and witness to single bytes ([@quake](https://github.com/quake))

> We changed script args and witness from `Vec<Bytes>` to `Bytes`. The `main` method no longer receives  
> script args as argv. The new system call `load_script` should be used to get the script args.

[\#1646](https://github.com/nervosnetwork/ckb/pull/1646): Use epoch as the basic maturity unit ([@yangby-cryptape](https://github.com/yangby-cryptape))

> Cellbase outputs can be used after 4 epochs.

[\#1609](https://github.com/nervosnetwork/ckb/pull/1609): Use DAO type script hash in DAO transaction ([@TheWaWaR](https://github.com/TheWaWaR))

> DAO deposite must use type as the `hash_type` to reference the DAO system script.

[\#1617](https://github.com/nervosnetwork/ckb/pull/1617): Setup issuance schedule ([@doitian](https://github.com/doitian))

> Primary reward starts at 4.2B a year. Secondary reward is 1.344B a year.

[\#1666](https://github.com/nervosnetwork/ckb/pull/1666): Expand nonce to 128-bit ([@zhangsoledad](https://github.com/zhangsoledad))

> We expanded nonce to 128-bit and changed `pow_message` from `nonce || pow_hash` to `pow_hash || nonce`.

### Changes in CKB VM

-   [\#85](https://github.com/nervosnetwork/ckb-vm/pull/85) criterion updates
-   [\#87](https://github.com/nervosnetwork/ckb-vm/pull/87) Return loaded program consumed bytes

We split the script part in CKB into a separate project: <https://github.com/nervosnetwork/ckb-standalone-debugger>. This enables off-chain script debugging, what’s more, it’s now possible to compile the debugger into a proper WASM program. This enables the potential to build a Remix-style debugger for CKB.

### Changes in P2P

-   [\#187](https://github.com/nervosnetwork/p2p/pull/187): Upgrade molecule version

### Changes in CKB CLI

-   [\#91](https://github.com/nervosnetwork/ckb-cli/pull/91): Add extended-address sub-command
-   [\#92](https://github.com/nervosnetwork/ckb-cli/pull/92): Require transaction fee when send transaction

------------------------------------------------------------------------

**Join our community:** [Forum](https://talk.nervos.org/) [Telegram](https://t.me/nervosnetwork) [Twitter](https://twitter.com/nervosnetwork) [Reddit](https://www.reddit.com/r/NervosNetwork) [Github](https://github.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [October 12, 2019](https://medium.com/p/bc2b9ae691e1).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-20-bc2b9ae691e1)

Exported from [Medium](https://medium.com) on May 12, 2020.
