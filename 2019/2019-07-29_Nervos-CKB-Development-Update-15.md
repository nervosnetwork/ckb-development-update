# Nervos CKB Development Update \#15

Covering Jul 8 to Jul 21

------------------------------------------------------------------------

### Nervos CKB Development Update \#15

Covering Jul 8 to Jul 21

![](https://cdn-images-1.medium.com/max/1200/1*mpEhRLd5AHNeOT-xP2jimA.png)

This post is co-authored by [Ian Yang](/u/72022cac4c7c?source=post_page---------------------------), [Xuejie Xiao](/u/6f2cfa203c38?source=post_page---------------------------), [Qian Linfeng](https://github.com/thewawar?source=post_page---------------------------) and [James Chen](/u/24192bbe4c92?source=post_page---------------------------).

### TL;DR

-   RFC for the PoW function Eaglesong is published.
-   Max block interval is adjusted to 30s

### Changes in RFCs

-   [\#129](https://github.com/nervosnetwork/rfcs/pull/129): The RFC for Eaglesong (the proof-of-work function) is published by [@aszepieniec](https://github.com/aszepieniec).

### Changes in CKB

We have freezed [v0.17.0](https://github.com/nervosnetwork/ckb/pull/1255) for release. Following are the highlights of the features developed in the last two weeks.

[\#1165](https://github.com/nervosnetwork/ckb/pull/1165): Reference script code via dep cell’s type hash ([@xxuejie](https://github.com/xxuejie))

> This allows us to build a new paradigm that allows upgrading of scripts without affecting lock/type hash.

[\#1230](https://github.com/nervosnetwork/ckb/pull/1230): Use tokio\_threadpool::blocking to handle heavy future task ([@TheWaWaR](https://github.com/TheWaWaR))

> According performance test use `tokio_threadpool::blocking` to handle heavy future task can improve TPS.

[\#1232](https://github.com/nervosnetwork/ckb/pull/1232): IBD with whitelist ([@driftluo](https://github.com/driftluo))

> 1\. Enable IBD with whitelist peers  
> 2. Rename reserved to whitelist

[\#1220](https://github.com/nervosnetwork/ckb/pull/1220): Network flood control ([@TheWaWaR](https://github.com/TheWaWaR))

> Do not send blocks to peer when session send buffer is full.

[\#1246](https://github.com/nervosnetwork/ckb/pull/1246): Send a message to remote peer when disconnect ([@TheWaWaR](https://github.com/TheWaWaR))

[\#1274](https://github.com/nervosnetwork/ckb/pull/1274): Adjust max block interval to 30s ([@doitian](https://github.com/doitian))

See the release [v0.17.0-rc1](https://github.com/nervosnetwork/ckb/releases/tag/v0.17.0-rc1) for the full change logs.

### Changes in CKB VM

-   [\#78](https://github.com/nervosnetwork/ckb-vm/pull/78): fix: Various places where panic might happen in case of malicious data
-   [\#79](https://github.com/nervosnetwork/ckb-vm/pull/79): chore: update rust to 1.36.0

### Changes in CKB CLI

[\#23](https://github.com/nervosnetwork/ckb-cli/pull/23): Release for ckb v0.17.0

-   Support Get key info by address or lock-arg
-   Support index code hash and type hash
-   Show lock hash in account info
-   Allow send transaction with data from file
-   Add get\_header/get\_header\_by\_number sub-commands
-   Customize script verifier debugger
-   Check alerts when start ckb-cli and use rpc command in interactive mode

### Changes in P2P

-   [\#173](https://github.com/nervosnetwork/p2p/pull/173): Record pending data size in `SessionContext`

### Changes in Toolchains

SDKs

-   Released SDK v0.16.0
-   Added hash type support

CKB Test Faucet

-   Updated SDK to v0.15.0
-   Fixed a bug that address with whitespace couldn’t be used

CKB Explorer

-   Added more data for net/chain, epoch and block
-   Added statics info charts
-   Fixed fee calculation bug
-   Improved cache
-   Improved responsive design for mobile

Neuron Wallet

-   Polished more UI screens
-   Dropped Node 11 support and upgraded Electron to 5.0.7
-   Added support for macOS binary notarizing
-   Improved transaction sync/queue logic
-   Added miner info

Please connect with us on [**Github**](https://github.com/nervosnetwork/ckb?source=post_page---------------------------)**,** [**CKB Dev telegram**](https://t.me/nervos_ckb_dev?source=post_page---------------------------) or the [**Nervos Forum**](https://talk.nervos.org/?source=post_page---------------------------) if you have any questions, run into any issues or can help improve the documentation.

Keeping up with Nervos:  
[Forum](https://talk.nervos.org/?source=post_page---------------------------)  
[Twitter](https://twitter.com/nervosnetwork?source=post_page---------------------------)  
[Github](https://github.com/NervosNetwork?source=post_page---------------------------)  
[Reddit](http://reddit.com/r/nervosnetwork?source=post_page---------------------------)  
[Youtube](https://www.youtube.com/channel/UCONuJGdMzUY0Y6jrPBOzH7A?source=post_page---------------------------)

By [Ian Yang](https://medium.com/@doitian) on [July 29, 2019](https://medium.com/p/28bf2eb66a38).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-15-28bf2eb66a38)

Exported from [Medium](https://medium.com) on May 12, 2020.
