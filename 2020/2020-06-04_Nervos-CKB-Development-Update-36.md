# Nervos CKB Development Update #36

Covering May 18 to 31, 2020

By [Cipher Wang](https://github.com/CipherWang), [Xuejie Xiao](https://github.com/xxuejie), [Ian Yang](https://github.com/doitian).

## TL;DR

* We have released ckb [v0.32.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.32.0) and Neuron [v0.31.0-rc1](https://github.com/nervosnetwork/neuron/releases/tag/v0.31.0-rc1).
* [lumos](https://github.com/nervosnetwork/lumos) now has a [sample project](https://github.com/xxuejie/felix) for you to check out.
* We have started to work on yet another [new project](https://github.com/mohanson/wasc).

## Changes in CKB

We have released [v0.32.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.32.0), which continues improving the chain sync.

We are working on

* Improving RPC error messages and documentations.
* Implementing Chain Freezer to separate code and hot data in the database.
* Improving chain sync.
* Adding more tests.
* Collecting more data via benchmarks.


## Changes in DT

* [lumos](https://github.com/nervosnetwork/lumos) is starting to get into shape! We are still enhancing the documents on lumos, but we do already have a [sample project](https://github.com/xxuejie/felix) for you to check out.
* [capsule](https://github.com/nervosnetwork/capsule) is also getting many new features, such as debugger integration, latest Rust version upgrades, usability enhancements, etc.
* We have started to work on yet another [new project](https://github.com/mohanson/wasc), it aims to build a full AOT compiler from WASM to RISC-V, with this new project, CKB will have the potential for full WASM integration. Note that we are not talking about half-baked integrations that might be quirky in some way, we are talking about a complete WASI-compatible integration in Nervos CKB, so we can enjoy the greatest WASM ecosystem.

## Changes in MAKE

We have released Neuron [v0.31.0-rc1](https://github.com/nervosnetwork/neuron/releases/tag/v0.31.0-rc1), with the following updates

- New logo and setting window style
- Add transaction history export & language switch functionalities
- Export more bundled CKB logs for debug info
- New logic for fee settings

CKB-Explorer [v0.9.6](https://github.com/nervosnetwork/ckb-explorer/releases/tag/v0.9.6)

- Add lots of charts for economic data and mining data
- Add sUDT pages
- Update home page style
