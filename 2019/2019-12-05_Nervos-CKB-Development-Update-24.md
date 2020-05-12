# Nervos CKB Development Update \#24

Covering Nov 18 to Dec 1

------------------------------------------------------------------------

### Nervos CKB Development Update \#24

by [LinFeng Qian](https://github.com/TheWaWaR), [Cipher Wang](https://github.com/CipherWang), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38) and [Ian Yang](https://medium.com/u/72022cac4c7c)

Nov 18 - Dec 1

![](https://cdn-images-1.medium.com/max/800/1*SstRgmFTU6zsyOpzOPynSA.png)

### TL;DR

-   Aggron Testnet has been re-set.
-   The team is focusing on the performance, interface, tests and documentation.

### Changes in CKB

Aggron Testnet was halted because of a hash rate surge. We have [re-set the chain](https://gist.github.com/doitian/573513c345165c0fe4f3504ebc1c8f9f). In the future, we’ll re-set the testnet as needed, and whenever there are no blocks mined within an hour of the re-set.

The team’s focus in this stage is to improve performance and interface, test and document. We are working on these areas:

-   Add options to prune history data. It will reduce both memory and disk storage requirement to run a full node.
-   Improve the chain synchronization performance.
-   Refactor the RPC interfaces. Add more RPC, based on the feature requests.
-   Propose and implement a more decentralized boot nodes configuration solution.
-   Improve documentation.

### Changes in CKB VM

-   [\#90](https://github.com/nervosnetwork/ckb-vm/pull/90): Tweak slot calculation algorithm

### Changes in CKB Cli

-   [\#186](https://github.com/nervosnetwork/ckb-cli/pull/186): CKB address full support
-   Add various utiltities, including molecule encoder/decoder and eaglesong hasher.

### Changes in P2P

-   [\#200](https://github.com/nervosnetwork/p2p/pull/200): Add transport connection limit on listener

### Changes in Toolchain

Explorer:

-   private address locked CKB loopup feature
-   circulating\_supply API for coinmarketcap
-   several UX improvements

### Neuron Wallet

-   Fixed balance bugs
-   Fixed DAO compensation rate calculation bug
-   Neuron bundle CKB node— develop and test

### SDK

-   Java SDK added Nervos DAO APIs
-   DevOps
-   Optimized service deploy process
-   Defend DDOS attack

------------------------------------------------------------------------

Join our Dev community [Telegram](http://t.me/nervos_ckb_dev) channel for more updates

By [Ian Yang](https://medium.com/@doitian) on [December 5, 2019](https://medium.com/p/44b3c9b814bf).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-24-44b3c9b814bf)

Exported from [Medium](https://medium.com) on May 12, 2020.
