# Nervos CKB Development Update \#17

Covering Aug 5 to Aug 18

------------------------------------------------------------------------

### Nervos CKB development update \#17

Aug 5 to Aug 18

by [Ian Yang](/u/72022cac4c7c?source=post_page---------------------------), [Qian Linfeng](https://github.com/thewawar?source=post_page---------------------------) and [James Chen](/u/24192bbe4c92?source=post_page---------------------------).

![](https://cdn-images-1.medium.com/max/1200/1*wZaEZLSY2y1kgtGAtAjxqg.png)

### TL;DR

-   New serialization [\#1249](https://github.com/nervosnetwork/ckb/pull/1249).
-   New transaction structure described in the [post](https://talk.nervos.org/t/ckb-transaction-structure-part-i/3432).

### CKB Updates

The team has been busy preparing the next release v0.19.0. We have made quite a few changes since the last update.

[\#1249](https://github.com/nervosnetwork/ckb/pull/1249) : Apply new serialization to all crates ( [@yangby-cryptape](https://github.com/yangby-cryptape) )

> We have designed a new serialization format. This will be used in p2p messages, database storage and hash digest. After the change, it is possible to compute transaction hash and block hash in other programming languages. We’ll publish the serialization wire format specification soon.

[\#1307](https://github.com/nervosnetwork/ckb/pull/1307) : Difficulty adjustment RFC version ( [@zhangsoledad](https://github.com/zhangsoledad) )

> Update the difficulty adjustment algorithm according to the [consensus paper](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0020-ckb-consensus-protocol/0020-ckb-consensus-protocol.md#dynamic-difficulty-adjustment-mechanism).

[\#1336](https://github.com/nervosnetwork/ckb/pull/1336) : Refactoring block body store ( [@quake](https://github.com/quake) )

> After benchmark, we discover that the CKB node fetches a single transaction from the database more frequently than getting all the transactions in a block. Originally the transactions in a block are stored together. This PR stores transaction in its own slot.

PR [\#1341](https://github.com/nervosnetwork/ckb/pull/1341)

> *Implements the type ID checker in rust (* [*@xxuejie*](https://github.com/xxuejie) *).*

PR [\#1387](https://github.com/nervosnetwork/ckb/pull/1387)

> Adds the feature dep group ( [@TheWaWaR](https://github.com/TheWaWaR) ).

PR [\#1356](https://github.com/nervosnetwork/ckb/pull/1356)

> Refactors the deps and splits it into `cell_deps` and `header_deps`.

This [post](https://talk.nervos.org/t/ckb-transaction-structure-part-i/3432) describes what the transaction structure will look like in the new version. The second part is scheduled to introduce several extensions, such as code locating type script hash, type id, and dev group.

We also have a new contributor on board— [@zjhmale](https://github.com/zjhmale), who has added [\#1385](https://github.com/nervosnetwork/ckb/pull/1385) and [\#1382](https://github.com/nervosnetwork/ckb/pull/1382). Welcome 🎉.

### Changes in P2P

-   [\#177](https://github.com/nervosnetwork/p2p/pull/177): Fixed listen error address mistake

### Changes in CKB CLI

-   [\#48](https://github.com/nervosnetwork/ckb-cli/pull/48): Fixed jsonrpc-client thread leak

### Changes in Toolchains

**SDKs:**

-   Released v0.18.0
-   Fixed NervosDao issues (Ruby)
-   Updated transaction structures per CKB changes

**Neuron Wallet**

-   Implemented Keystore import
-   Implemented sync with Indexer RPC module
-   Implemented tx cycles calculation
-   Added more e2e tests
-   Tweaked performance for Address and History lists

**Explorer**

-   Added occupied capacity calculation
-   Updated tx fee calculation to include support DAO reward
-   Adapted English localization
-   Fixed data sync issue
-   Updated chart to exclude dates for the first 5 epochs

### Join our community

[Forum](https://talk.nervos.org) [Telegram](https://t.me/nervosnetwork) [Twitter](https://twitter.com/nervosnetwork) [Reddit](https://www.reddit.com/r/NervosNetwork) [Github](https://github.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [August 21, 2019](https://medium.com/p/1598832abfa5).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-17-1598832abfa5)

Exported from [Medium](https://medium.com) on May 12, 2020.
