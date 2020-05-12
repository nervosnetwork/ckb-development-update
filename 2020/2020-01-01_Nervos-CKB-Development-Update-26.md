# Nervos CKB Development Update \#26

Covering Dec 16 to 29

------------------------------------------------------------------------

### Nervos CKB Development Update \#26

Dec 16 — Dec 29

by [LinFeng Qian](https://github.com/TheWaWaR), [Cipher Wang](https://github.com/CipherWang) and [Ian Yang](https://medium.com/u/72022cac4c7c)

![](https://cdn-images-1.medium.com/max/800/1*a2ngsAH_w_5hsxmD12Ookg.png)

### TL;DR

-   CKB [v0.26.1](https://github.com/nervosnetwork/ckb/releases/tag/v0.26.1) has released.
-   Added a basic [tutorial](https://github.com/nervosnetwork/ckb-cli/wiki/Tutorials) for using ckb-cli.
-   Released Neuron v0.26.0 bundle with embedded CKB node
-   Released alpha version Golang SDK: [ckb-sdk-go](https://github.com/ququzone/ckb-sdk-go)

### Changes in RFCs

In the last two weeks, we have:

Merged a new informational RFC

-   [\#134](https://github.com/nervosnetwork/rfcs/pull/134): CKB Transaction Structure ([@doitian](https://github.com/doitian))

Updated VM memory model related RFCs

-   [\#102](https://github.com/nervosnetwork/rfcs/pull/102): Add W^X Memory and exec syscall for CKB VM ([@xxuejie](https://github.com/xxuejie))

Made small revisions to Nervos DAO

-   [\#161](https://github.com/nervosnetwork/rfcs/pull/161): 0023 fix I\_i and S\_i description in Nervos DAO ([@janx](https://github.com/janx))
-   [\#162](https://github.com/nervosnetwork/rfcs/pull/162): Update Nervos DAO spec with real examples from mainnet ([@xxuejie](https://github.com/xxuejie))

### Changes in CKB

CKB [v0.26.1](https://github.com/nervosnetwork/ckb/releases/tag/v0.26.1) has released.

A new RPC was added to get the balance of an indexed lock hash.

-   [\#1888](https://github.com/nervosnetwork/ckb/pull/1888): Add `get_capacity_by_lock_hash` RPC ([@quake](https://github.com/quake))

[@driftluo](https://github.com/driftluo) and [@jjyr](https://github.com/jjyr) have made many improvements in P2P module.

### Changes in CKB Cli

Added a basic [tutorial](https://github.com/nervosnetwork/ckb-cli/wiki/Tutorials) for using ckb-cli (especially transfer from time locked address)

-   [\#203](https://github.com/nervosnetwork/ckb-cli/pull/203): Add common transaction (sighash/multisig) sub-commands
-   [\#204](https://github.com/nervosnetwork/ckb-cli/pull/204): Add a global flag `--wait-for-sync`
-   [\#205](https://github.com/nervosnetwork/ckb-cli/pull/205): Wallet can transfer from time locked address
-   [\#206](https://github.com/nervosnetwork/ckb-cli/pull/206): Allow import keystore exported from Neuron
-   [\#207](https://github.com/nervosnetwork/ckb-cli/pull/207): Speed up sync index database (about `14` times faster)
-   [\#211](https://github.com/nervosnetwork/ckb-cli/pull/211): Implement a basic testing framework

### Changes in Toolchains

-   Updated CKB Explorer UI
-   Released Neuron v0.26.0, bundle with embedded CKB node
-   Released alpha version Golang SDK: [ckb-sdk-go](https://github.com/ququzone/ckb-sdk-go)

------------------------------------------------------------------------

**Stay up to date on Nervos:** [Github](https://github.com/nervosnetwork) [Forum](https://talk.nervos.org/) [Telegram](https://t.me/nervos_ckb_dev) [Reddit](https://www.reddit.com/r/NervosNetwork) [Twitter](https://twitter.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [January 1, 2020](https://medium.com/p/c4adcf386945).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-26-c4adcf386945)

Exported from [Medium](https://medium.com) on May 12, 2020.
