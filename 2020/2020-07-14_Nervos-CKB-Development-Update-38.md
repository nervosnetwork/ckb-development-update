# Nervos CKB Development Update #38

Covering Jun 29 to Jul 12, 2020

By [Ian Yang](https://github.com/doitian).

## TL;DR

* The latest release is v0.33.1, which fixed a security advisory [GHSA-r9rv-9mh8-pxf4](https://github.com/nervosnetwork/ckb/security/advisories/GHSA-r9rv-9mh8-pxf4).
* We are working to limit the ckb memory usage.
* Tentacle now has a Go version.

## Status Update

The latest release is [v0.33.1](https://github.com/nervosnetwork/ckb/releases/tag/v0.33.1).

We have released v0.33.1 because of the issue [GHSA-r9rv-9mh8-pxf4](https://github.com/nervosnetwork/ckb/security/advisories/GHSA-r9rv-9mh8-pxf4). We observed a surge of uncle rate on Jul 1st. It by turn increased the block interval. Because from the consensus algorithm's perspective, large block interval should lower the uncle rate. However, it did not work. The root cause was that a miner did not synchronize the local time, which is about 15 seconds ahead, and there's a bug in the code which will ban peers which relays the block more than 15 seconds in the future. Thus that miner was banned by most peers and could not catch up the network best tip and continuously produced uncle blocks.

We received some complaints that the ckb node consumes too much memory. [Xuejie](https://github.com/xxuejie) met the similar issue when he tried to [port ckb into ARM](https://github.com/xxuejie/ckb-on-aarch64) and ran ckb on his Raspberry Pi which only has 1G memory. So [Boyu](https://github.com/yangby-cryptape) has started series work to confine the memory usage of CKB. He has already done some jobs on it, such as [not caching all headers in memory during header sync](https://github.com/nervosnetwork/ckb/pull/2147).

[Chao](https://github.com/driftluo) had submitted an PR before to schedule block download tasks between peers according to the history latency statistics. We are running more simulation tests to find better parameters.

Chao also finished the first version of [Tentacle Go](https://github.com/driftluo/tentacle-go). Implementing the framework in another language taught Chao a lot and he started to reflecting and refactoring the Rust version.

There are more and more requirements to use ckb as an library. So [Quake](https://github.com/quake) [had](https://github.com/nervosnetwork/ckb/pull/2096) [made](https://github.com/nervosnetwork/ckb/pull/2100] [various](https://github.com/nervosnetwork/ckb/pull/2013] [refactoring](https://github.com/nervosnetwork/ckb/pull/2107) to make ckb more friendly to be used as a library.

We know that our RPC error messages are terrible. [Ian](https://github.com/doitian) recently [submitted](https://github.com/nervosnetwork/ckb/pull/2038) [three](https://github.com/nervosnetwork/ckb/pull/2049) [PRs](https://github.com/nervosnetwork/ckb/pull/2164) to improve the RPC error messages.
