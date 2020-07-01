# Nervos CKB Development Update #37

Covering Jun 1 to Jun 28, 2020

By [Ian Yang](https://github.com/doitian).

## TL;DR

* Released ckb [v0.33.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.33.0).
* Continue working on chain sync performance.

## Changes in CKB

We have:

* Released CKB [v0.33.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.33.0).
* Improved chain sync performance. ([#2067](https://github.com/nervosnetwork/ckb/pull/2067), [#2081](https://github.com/nervosnetwork/ckb/pull/2081))
* Added a new sub-command `replay` to verify the local chain ([#2045](https://github.com/nervosnetwork/ckb/pull/2045))
* Fixed a vulnerability that ckb process crashes on invalid input. ([GHSA-pr39-8257-fxc2](https://github.com/nervosnetwork/ckb/security/advisories/GHSA-pr39-8257-fxc2))
* Added document to explain different protocol handles in tentacle. ([ProtocolHandle](https://github.com/nervosnetwork/tentacle/blob/7a278a243f47b062ed739d5e566d4ffbc4269bd9/src/service/config.rs#L203-L228))
* Supported updating log levels dynamically via RPC ([#2113](https://github.com/nervosnetwork/ckb/pull/2113))
* Added RPC `truncate` to ease testing and development ([#2064](https://github.com/nervosnetwork/ckb/pull/2064))
* Removed RPC `estimate_fee_rate` for performance issue ([#2126](https://github.com/nervosnetwork/ckb/pull/2126))

We are:

* Separating code and hot data in database for performance. ([#2118](https://github.com/nervosnetwork/ckb/pull/2118))
* Improving RPC errors. ([#2038](https://github.com/nervosnetwork/ckb/pull/2038))
* Introducing fail points for test. ([#2090](https://github.com/nervosnetwork/ckb/pull/2090))
