# Nervos CKB Development Update \#16

Covering Jul 22 to Aug 4

------------------------------------------------------------------------

### Nervos CKB Development Update \#16

Covering Jul 22 to Aug 4

This post is co-authored by [Ian Yang](/u/72022cac4c7c?source=post_page---------------------------), [Xuejie Xiao](/u/6f2cfa203c38?source=post_page---------------------------), [Qian Linfeng](https://github.com/thewawar?source=post_page---------------------------) and [James Chen](/u/24192bbe4c92?source=post_page---------------------------).

![](https://cdn-images-1.medium.com/max/1200/1*0awMZjtMlKkVM5UYIA8ABA.jpeg)

### TL;DR

-   Transaction structure change [preview](https://github.com/nervosnetwork/ckb/pull/1354#issuecomment-519797310).
-   Consensus changes: [\#1252](https://github.com/nervosnetwork/ckb/pull/1252) Uncle descendant limit and [\#1343](https://github.com/nervosnetwork/ckb/pull/1343) Tweak cellbase maturity.

### Changes in CKB

We have published [v0.19.0-pre1](https://github.com/nervosnetwork/ckb/releases/tag/v0.19.0-pre1), which includes all work completed in the last two weeks.

**Updates and features in this version:**

[\#1297](https://github.com/nervosnetwork/ckb/pull/1297): Add RPC `get_block_finalized_reward_info` ([@u2](https://github.com/u2))

> This RPC split the block reward into different components, which can help to understand the economic model.

[\#1252](https://github.com/nervosnetwork/ckb/pull/1252): Uncle descendant limit ([@zhangsoledad](https://github.com/zhangsoledad))

> It changed the uncle verification rule to fix a potential security issue that blocks from another chain can be packaged as uncles.

[\#1323](https://github.com/nervosnetwork/ckb/pull/1323): Send bulk of tx hashes ([@u2](https://github.com/u2))

> This is an important performance improvement. It avoids transactions broadcast flooding.

[\#1319](https://github.com/nervosnetwork/ckb/pull/1319): Leverage rocksdb transaction ([@zhanghesoledad](https://github.com/zhangsoledad))

> An important refactoring that utilizes the rocksdb transaction to simplify the codebase.

[\#1279](https://github.com/nervosnetwork/ckb/pull/1279): Extract data field from CellOutput to Transaction ([@jjyr](https://github.com/jjyr))

> This PR removes data from the transaction cell output, and adds new field output data into the transaction.

[\#1343](https://github.com/nervosnetwork/ckb/pull/1343): Tweak cellbase maturity ([@zhangsoledad](https://github.com/zhangsoledad))

> The cellbase maturity duration is changed to 7200 blocks.

The version 0.19.0 has many changes to the cell model. [This comment](https://github.com/nervosnetwork/ckb/pull/1354#issuecomment-519797310) describes how the transaction will look like in the new version.

### Changes in CKB VM

-   [\#80](https://github.com/nervosnetwork/ckb-vm/pull/80): fix: ELF parsing panics in AOT mode

### Changes in CKB CLI

-   [\#24](https://github.com/nervosnetwork/ckb-cli/pull/24): Mock transaction support

### Changes in Toolchains

**SDK**

-   Released v0.17.0
-   Updated address format
-   Added new chain and net RPC methods

**Explorer**

-   Implemented new UI
-   Refactored Toast component and global state management
-   Added secondary epoch reward
-   Applied new address format
-   Updated data sync method

**Neuron Wallet**

-   Improved Windows Assisted Installer
-   Fixed a bug that makes the app unable to quit properly
-   Added experimental updater
-   Improved sync performance
-   Polished UI screens
-   Fixed several bugs

### Stay updated on Nervos

[Forum](https://talk.nervos.org/), [Twitter](https://twitter.com/NervosNetwork), [Telegram](https://t.me/NervosNetwork), [Reddit](https://www.reddit.com/r/NervosNetwork/), [Youtube](https://www.youtube.com/nervosnetwork), [Facebook](https://www.facebook.com/theNervosNetwork/)

By [Ian Yang](https://medium.com/@doitian) on [August 9, 2019](https://medium.com/p/8eabe4567311).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-16-8eabe4567311)

Exported from [Medium](https://medium.com) on May 12, 2020.
