# Nervos CKB Development Update \#28

Covering Jan 13 to Feb 2

------------------------------------------------------------------------

### Nervos CKB Development Update \#28

Jan 13 to Feb 2

by [Cipher Wang](https://github.com/CipherWang), [Ian Yang](https://medium.com/u/72022cac4c7c)

![](https://cdn-images-1.medium.com/max/800/1*Sg59GKr7-ilhNq8zXbZyNA.jpeg)

### TL;DR

-   CKB [v0.28.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.28.0) has released. There’s a breaking change to `send_transaction` RPC ([\#1879](https://github.com/nervosnetwork/ckb/pull/1879)).
-   We have [deployed Duktape (a Javascript VM) and mruby to testnet](https://github.com/nervosnetwork/ckb/wiki/Special-Live-Cells),
-   There is a new post about [CKB Type ID and upgradable contracts](https://xuejie.space/2020_02_03_introduction_to_ckb_script_programming_type_id/).

### Changes in CKB

-   [v0.28.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.28.0) has released
-   [@quake](https://github.com/quake) added the pub/sub RPC ([\#1900](https://github.com/nervosnetwork/ckb/pull/1900))
-   Also added: `outputs_validator` to `send_transaction` RPC ([\#1879](https://github.com/nervosnetwork/ckb/pull/1879)). This is a breaking change —the node will reject transactions which are not using the default secp256k1 as the output lock scripts.

[@driftluo](https://github.com/driftluo) moved the CKB specific p2p protocols from the p2p code repository to CKB. This will simplify the protocol upgrades in the future. ([\#1896](https://github.com/nervosnetwork/ckb/pull/1896)).

[@xxuejie](https://github.com/xxuejie) added a checker to reject new scripts with known bugs ([\#1915](https://github.com/nervosnetwork/ckb/pull/1915)).

[@TheWaWaR](https://github.com/TheWaWaR) added a new command in ckb-cli to sign any binary and verify the signature ([ckb-cli\#232](https://github.com/nervosnetwork/ckb-cli/pull/232)).

We have [deployed Duktape (a Javascript VM) and mruby to testnet](https://github.com/nervosnetwork/ckb/wiki/Special-Live-Cells). It allows writing contract using Javascript or Ruby.

There is a new post about [CKB Type ID and upgradable contracts](https://xuejie.space/2020_02_03_introduction_to_ckb_script_programming_type_id/). (Have fun, we’ll publish serial docs about contract development soon!)

### Changes in Toolchain

CKB Explorer changes.

-   Added some new charts and made some changes to existing charts.
-   Hid unessential information on transaction page and address page.
-   Added more explanation to NervosDAO transactions.

Neuron Wallet changes.

-   Release v0.27.0, bundled with CKB node v0.27.0

------------------------------------------------------------------------

**Join our community:** [Github](https://github.com/nervosnetwork) [Forum](https://talk.nervos.org/) [Telegram](https://t.me/nervos_ckb_dev) [Reddit](https://www.reddit.com/r/NervosNetwork) [Twitter](https://twitter.com/nervosnetwork)

By [Ian Yang](https://medium.com/@doitian) on [February 5, 2020](https://medium.com/p/5c85be7a599e).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-28-5c85be7a599e)

Exported from [Medium](https://medium.com) on May 12, 2020.
