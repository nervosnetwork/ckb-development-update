# Nervos CKB Development Update \#22

Covering Oct 21 to Nov 3

------------------------------------------------------------------------

### Nervos CKB Development Update \#22

Oct 21 — Nov 3

by [Ian Yang](https://medium.com/u/72022cac4c7c) and [James Chen](https://medium.com/u/24192bbe4c92)

![](https://cdn-images-1.medium.com/max/800/1*qmTuf6_bJYHqpwSzc5ERYw.png)

### TL;DR

-   CKB [v0.24.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.24.0) released on Nov 3rd.
-   There’s a new RFC ([PR\#142](https://github.com/nervosnetwork/rfcs/pull/142)) describing deposit and withdrawal transactions in the Nervos DAO.

### Changes in RFCs

-   [PR\#142](https://github.com/nervosnetwork/rfcs/pull/142) ([@janx](https://github.com/janx)): Explains deposit and withdrawal transaction in the Nervos DAO.
-   [PR\#140](https://github.com/nervosnetwork/rfcs/pull/140) ([@shaojunda](https://github.com/shaojunda)): This fixed the outdated information about how to generate an address from lock script.

### Changes in CKB

CKB [v0.24.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.24.0) released on Nov 3rd.

There are two major changes in v0.24.0:

[\#1739](https://github.com/nervosnetwork/ckb/pull/1739): Use molecule to serialize witnesses ([@jjyr](https://github.com/jjyr))

> All the system scripts store temporary data in witness as a structure serialized by molecule.

[\#1707](https://github.com/nervosnetwork/ckb/pull/1707): Resolved uncles hash calculation issue ([@quake](https://github.com/quake))

> It’s a bug. Now the uncles hash calculation logic is consistent with the proposals hash.

We have tweaked the consensus rules and system scripts:

[\#1726](https://github.com/nervosnetwork/ckb/pull/1726): Tweaked consensus params ([@zhangsoledad](https://github.com/zhangsoledad))

[\#1769](https://github.com/nervosnetwork/ckb/pull/1769): Adapt to 2-phase Nervos DAO implementation ([@xxuejie](https://github.com/xxuejie))

[\#1785](https://github.com/nervosnetwork/ckb/pull/1785): Upgrade system script for modified multi-sign lock script ([@xxuejie](https://github.com/xxuejie))

A new RPC is added:

[\#1659](https://github.com/nervosnetwork/ckb/pull/1659): Fee estimate RPC ([@jjyr](https://github.com/jjyr))

> This PR adds a new RPC [estimate\_fee\_rate](https://github.com/nervosnetwork/ckb/pull/1659/files#diff-622e6d119ac5d43f7eb41cb596159f9fR907). It takes the basic idea from bitcoin’s [estimate\_smart\_fee](https://bitcoincore.org/en/doc/0.16.0/rpc/util/estimatesmartfee/), however, we ignore the magic numbers and tricks from the original code.

### Changes in Toolchains

SDKs

-   Added new RPC estimate fee rate
-   Added min fee calculation
-   Applied witness serialization and sign changes
-   Released v0.24.0

Neuron Wallet

-   Improved UI for transaction fees, menus, etc.
-   Refactored app startup flow and data access
-   Improved sync speed
-   Updated SDK to v0.23.0, then v0.24.0

CKB Explorer

-   Improved sync performance and speed
-   Added feature for switching testnet and mainnet
-   Implemented automatic deployment and updated CI/CD
-   Implemented Nervos DAO related features

CKB Testnet Faucet

-   Updated SDK to v0.24.0

------------------------------------------------------------------------

**Stay up to date on Nervos:** [Github](https://github.com/nervosnetwork) [Forum](https://talk.nervos.org/) [Telegram](https://t.me/nervos_ckb_dev) [Reddit](https://www.reddit.com/r/NervosNetwork) [Twitter](https://twitter.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [November 6, 2019](https://medium.com/p/97bb2c943364).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-22-97bb2c943364)

Exported from [Medium](https://medium.com) on May 12, 2020.
