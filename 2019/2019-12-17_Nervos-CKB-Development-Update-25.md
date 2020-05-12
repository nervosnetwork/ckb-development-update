# CKB Biweekly Report 2019-12-17

Covering Dec 2 to 15

## TL;DR

* CKB [v0.26.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.26.0) has released. The RPC `get_cells_by_lock_hash` and `get_live_cells_by_lock_hash` added two new fields in the response.
* Neuron v0.26.0 has released. It has bundled with the embedded CKB node
* There are three ongoing proposals [nervosnetwork/ckb#1866](https://github.com/nervosnetwork/ckb/issues/1866), [nervosnetwork/ckb#1867](https://github.com/nervosnetwork/ckb/issues/1867) and [nervosnetwork/rfcs#158](https://github.com/nervosnetwork/rfcs/pull/158).



## Changes in CKB

CKB [v0.26.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.26.0) has released.

We have added two new fields about the cells in RPC `get_cells_by_lock_hash` ([#1838](https://github.com/nervosnetwork/ckb/pull/1838)) and `get_live_cells_by_lock_hash` ([#1864](https://github.com/nervosnetwork/ckb/pull/1864)).

[@xxuejie](https://github.com/xxuejie) has upgraded ckb-vm to improve the performance by tweaking the slot calculation algorithm. ([#1854](https://github.com/nervosnetwork/ckb/pull/1854))

We also have three ongoing proposals, please join the discussions:


* Add an optional `outputs_validator` parameter to `send_transaction` rpc · Issue [#1866](https://github.com/nervosnetwork/ckb/issues/1866) · nervosnetwork/ckb
* JSON-RPC subscriptions · Issue [#1867](https://github.com/nervosnetwork/ckb/issues/1867) · nervosnetwork/ckb
* Propose POA testnet by jjyr · Pull Request [#158](https://github.com/nervosnetwork/rfcs/pull/158) · nervosnetwork/rfcs



## Changes in CKB Cli

* [#209](https://github.com/nervosnetwork/ckb-cli/pull/209): Human readable rpc result fields (capacity, timestamp, epoch, since)
* [#210](https://github.com/nervosnetwork/ckb-cli/pull/210): Update ckb dependency to v0.26.0-rc2



## Changes in Toolchains

* Update CKB Explorer UI 
* Release Neuron v0.26.0, bundle with embedded CKB node
* Release alpha version golang sdk: [ckb-sdk-go](https://github.com/ququzone/ckb-sdk-go)


