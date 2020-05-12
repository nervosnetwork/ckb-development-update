# Nervos CKB Development Update \#14

Covering Jun 24 to Jul 7

------------------------------------------------------------------------

### Nervos CKB Development Update \#14

Covering Jun 24 to Jul 7

![](https://cdn-images-1.medium.com/max/1200/1*r7uztzvzUWxXWkN_9qVo_Q.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [Qian Linfeng](https://github.com/thewawar) and [James Chen](https://medium.com/u/24192bbe4c92).

### TL;DR

-   Fixed severe bugs in v0.15.0
-   NervosDAO is implemented via CKB VM now
-   Neuron, the wallet, has released first several alpha versions

### Changes in CKB

We discovered some severe bugs in v0.15.0. We fixed the bugs and made several enhancements to allow the network to recover more quickly.

-   [\#1195](https://github.com/nervosnetwork/ckb/pull/1195): Bundle of several fixes ([@zhangsoledad](https://github.com/zhangsoledad)): 1. fix fetch invalid block; 2. fix response invalid block; 3. fix repeat process block overwrite block ext.
-   [\#1167](https://github.com/nervosnetwork/ckb/pull/1167): Proposal reward calculate consistency ([@zhangsoledad](https://github.com/zhangsoledad))
-   [\#1143](https://github.com/nervosnetwork/ckb/pull/1143): `get_ancestor` is inconsistent ([@zhangsoledad](https://github.com/zhangsoledad))

See the full change log in [v0.15.5](https://github.com/nervosnetwork/ckb/releases/tag/v0.15.5) and [v0.15.6](https://github.com/nervosnetwork/ckb/releases/tag/v0.15.6).

We have released the first preview of 0.17.0, which includes new features developed in the last two weeks.

The highlights in [v0.17.0-pre1](https://github.com/nervosnetwork/ckb/releases/tag/v0.17.0-pre1):

-   [\#1094](https://github.com/nervosnetwork/ckb/pull/1094): Secondary miner issurance, split DAO as a separate contract ([@xxuejie](https://github.com/xxuejie))
-   [\#1137](https://github.com/nervosnetwork/ckb/pull/1137): Remove output for bootstrap lock in genesis block ([@doitian](https://github.com/doitian))
-   [\#1119](https://github.com/nervosnetwork/ckb/pull/1119): Remove rules of special reserve blocks ([@doitian](https://github.com/doitian)). For block 1~11, the reward target is genesis block.

### Changes in CKB CLI

-   Use rocksdb as index database backend
-   Add web3 v3 keystore support
-   `wallet transfer` sub command now required password
-   Remove `wallet get-balance` sub command (use `wallet get-capacity` instead)
-   Remove `wallet generate-key` sub command (use `account new` instead)

### Changes in P2P

-   [\#170](https://github.com/nervosnetwork/p2p/pull/170): Use blocking thread to avoid the problem that the reactor is not timely

### Changes in Toolchains

SDKs

-   Released SDK `v0.15.0`

CKB Test Faucet

-   Updated to use SDK v0.14.0
-   Polished UI
-   Fixed some bugs

CKB Explorer

-   Updated front end design, implemented some mobile responsive views
-   Fixed and improved uncle block status syncing
-   Added cache layer for more objects
-   Fixed reward calculation bug

Neuron Wallet

-   Setup automatic packaging and uploading
-   Improved address scanning and syncing
-   Implemented sending transactions specifying fee
-   Added office-ui-fabric-react, revamping some UI views with it
-   Released first several alpha versions

Please connect with us on [**Github**](https://github.com/nervosnetwork/ckb)**,** [**CKB Dev telegram**](https://t.me/nervos_ckb_dev) or the [**Nervos Forum**](https://talk.nervos.org/)if you have any questions, run into any issues or can help improve the documentation.

Keeping up with Nervos:  
[Forum](https://talk.nervos.org)  
[Twitter](https://twitter.com/nervosnetwork)  
[Github](https://github.com/NervosNetwork)  
[Reddit](http://reddit.com/r/nervosnetwork)  
[Youtube](https://www.youtube.com/channel/UCONuJGdMzUY0Y6jrPBOzH7A)

By [Ian Yang](https://medium.com/@doitian) on [July 10, 2019](https://medium.com/p/dbf006f77126).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-14-dbf006f77126)

Exported from [Medium](https://medium.com) on May 12, 2020.
