# Nervos CKB Development Update \#21

Covering Oct 9 to Oct 20

------------------------------------------------------------------------

### Nervos CKB Development Update \#21

Oct 9 — Oct 20

by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38), [James Chen](https://medium.com/u/24192bbe4c92) and [Qian Linfeng](https://github.com/thewawar).

![](https://cdn-images-1.medium.com/max/1200/1*B6xLYGfv4OGXAbuG3PhyIA.png)

### TL;DR

-   CKB v0.23.0 has released. This is a bug fixing release which is compatible with v0.22.0.
-   P2P has replaced the encryption algorithm ([\#191](https://github.com/nervosnetwork/p2p/pull/191)).

### Changes in CKB

We released [v0.23.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.23.0) on Oct 19. This release fixed several bugs. It only introduces one new feature:

[\#1645](https://github.com/nervosnetwork/ckb/pull/1645): Min transaction fee filter ([@jjyr](https://github.com/jjyr))

> The node configures a minimal fee rate. It will reject submitting transaction via RPC and relaying via P2P when the fee is below the threshold.

### Changes in CKB VM

-   [\#88](https://github.com/nervosnetwork/ckb-vm/pull/88): Expose running methods in SupportMachine trait
-   [\#89](https://github.com/nervosnetwork/ckb-vm/pull/89): Implement StdError for Error @brson

### Changes in P2P

-   [\#191](https://github.com/nervosnetwork/p2p/pull/191): Replace encryption algorithm
-   [\#194](https://github.com/nervosnetwork/p2p/pull/194): Report error when handler panic
-   [\#195](https://github.com/nervosnetwork/p2p/pull/195): Fix potential overflow
-   [\#196](https://github.com/nervosnetwork/p2p/pull/196): Fix handshake attack
-   [\#197](https://github.com/nervosnetwork/p2p/pull/197): Fix windows support

### Changes in CKB CLI

-   [\#119](https://github.com/nervosnetwork/ckb-cli/pull/119): Detect network type by blockchain info
-   [\#130](https://github.com/nervosnetwork/ckb-cli/pull/130): Add compact-target/difficulty conversion subcommands
-   [\#132](https://github.com/nervosnetwork/ckb-cli/pull/132): Zeroize when private key dropped

### Changes in Toolchains

**SDKs**

-   Added tx fee calculation
-   Released v0.23.0

**Neuron Wallet**

-   Fixed balanced calculation bug
-   Fixed sync error when switching networks
-   Refactored controller layer and app start up flow
-   Developed Neuron Key Manager
-   Fixed an issue with app icon not displaying on Linux

**CKB Explorer**

-   Implemented Nervos DAO deposit/withdraw
-   Designed and implemented Nervos DAO API and contract data view
-   Added uncle rate chart
-   Supports different styles for mainnet/testnet

CKB Testnet Faucet

-   Updated SDK to v0.23.1 and fixed tx sending issue caused by min fee requirement

------------------------------------------------------------------------

**Stay up to date on Nervos:** [Github](https://github.com/nervosnetwork) [Forum](https://talk.nervos.org/) [Telegram](https://t.me/nervos_ckb_dev) [Reddit](https://www.reddit.com/r/NervosNetwork) [Twitter](https://twitter.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [October 29, 2019](https://medium.com/p/e33bbe34f3ba).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-21-e33bbe34f3ba)

Exported from [Medium](https://medium.com) on May 12, 2020.
