# Nervos CKB Development Update \#23

Nov 4 — Nov 17

------------------------------------------------------------------------

### Nervos CKB Development Update \#23

Nov 4 — Nov 17

by [James Chen](https://medium.com/u/24192bbe4c92), [Qian Linfeng](https://github.com/thewawar) and [Ian Yang](https://medium.com/u/72022cac4c7c)

![](https://cdn-images-1.medium.com/max/800/1*oC6-4T7ZIYCfvJQNmt1epg.png)

### TL;DR

-   [CKB Mainnet is Live](https://medium.com/nervosnetwork/nervos-ckb-mainnet-is-live-a028d9675dfb)

### Changes in CKB

CKB [v0.25.0-p1](https://github.com/nervosnetwork/ckb/releases/tag/v0.25.0-p1) released on Nov 15th; this is the version that is compatible with the mainnet. After mainnet launch, we fixed several bugs and released [v0.25.2](https://github.com/nervosnetwork/ckb/releases/tag/v0.25.2).

This newest version only contains refactoring and bug fixes.

### Changes in CKB Cli

-   [\#162](https://github.com/nervosnetwork/ckb-cli/pull/162): Removed `wallet get-lock-by-address` sub-command
-   [\#170](https://github.com/nervosnetwork/ckb-cli/pull/170): Removed DAO related sub-commandspp
-   [\#171](https://github.com/nervosnetwork/ckb-cli/pull/171): Fixed select immature live cell bug..i
-   [\#172](https://github.com/nervosnetwork/ckb-cli/pull/172): Static link openssl in macOS package
-   [\#176](https://github.com/nervosnetwork/ckb-cli/pull/176): Unify capacity display to CKB

### Changes in Toolchains

SDKs

-   Implemented Nervos DAO
-   Added support for long format (full payload) address
-   Improved transaction building with group input and witness signing
-   Added support for collecting cells using Indexer module
-   Released v0.25.0 for Mainnet Lina

Neuron Wallet

-   Implemented Nervos DAO feature
-   Improved testnet/mainnet switch
-   Released v0.25.0 for Mainnet Lina
-   Released v0.25.1, adding Clear Cache feature, fixing balance and sync bugs

CKB Testnet ;

-   Updated to v0.25.0 for testnet Aggron

CKB Explorer

-   Launched mainnet Lina Explorer
-   Launched testnet Aggron Explorer
-   Added support for multisig addresses
-   Released Nervos DAO

Join our Dev community [Telegram](http://t.me/nervos_ckb_dev) channel for more updates.

By [Ian Yang](https://medium.com/@doitian) on [November 23, 2019](https://medium.com/p/6b1ee3f0f8b5).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-23-6b1ee3f0f8b5)

Exported from [Medium](https://medium.com) on May 12, 2020.
