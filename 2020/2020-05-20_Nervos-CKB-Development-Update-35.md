# Nervos CKB Development Update #35

Covering May 4 to May 17, 2020

By [Cipher Wang](https://github.com/CipherWang), [Xuejie Xiao](https://github.com/xxuejie), [Ian Yang](https://github.com/doitian).

## TL;DR

* CKB v0.32.0 will release on May 22 and Testnet Aggron will be reset on the same day.
* We are building two dApp development frameworks, [capsule](https://github.com/nervosnetwork/capsule) and [lumos](https://github.com/nervosnetwork/lumos).
* [CKB Explorer](https://explorer.nervos.org/) has a new look.
* Neuron v0.30.0 has been released.


## Changes in CKB

We have delayed the release of v0.32.0 to this Friday (May 22) because of bugs:

* Fix collaboration issues between two protocol by driftluo ([nervosnetwork/ckb#2075](https://github.com/nervosnetwork/ckb/pull/2075))
* Fix orphan block pool deadlock by quake ([nervosnetwork/ckb#2074](https://github.com/nervosnetwork/ckb/pull/2074))

We will also reset the testnet Aggron on 22nd, see [details](https://github.com/nervosnetwork/ckb/wiki/Chains) in wiki.

* Make minor change to pow algorithm for testnet by yangby-cryptape ([nervosnetwork/ckb#2028](https://github.com/nervosnetwork/ckb/pull/2028))

We are also working on

* Improving RPC error messages and documentations.
* Implementing Chain Freezer to separate code and hot data in the database.
* Improving chain sync.

See more details in this [public sprint board](https://github.com/nervosnetwork/ckb/projects/6).

## Changes in Dev Tools

We are busy building 2 useful development frameworks here:

* [capsule](https://github.com/nervosnetwork/capsule): a Rust based smart contract development framework.
* [lumos](https://github.com/nervosnetwork/lumos): a JavaScript/TypeScript based dapp development framework.

If you know the generator/validator separation of CKB, you would realize that capsule is for validator, while lumos is for generator. When working together, we expect them to provide top level development experience on Nervos CKB.

Both frameworks are making good progress, and are expected to be released soon. 

## Changes in Applications

We have updated the UX of [CKB Explorer](https://explorer.nervos.org/)

- Build a new mainpage theme with a large HUD.
- Introduce several new data charts.

Neuron v0.30.0 has been released

- Bundled with CKB node v0.31.1.
- Update UX components, including Settings, DAO page, and Experimental divider.
- Add operating system info in the Debug info.

We have release [ckb-rich-node](https://github.com/ququzone/ckb-rich-node) for dApp backend data source.

We are working on

- CKB network node count analysis.
- New project Keypering (a [Keyper](https://github.com/ququzone/keyper) agency) to handle the dApp interaction with CKB.
- sUDT support development and test on Neuron.
- sUDT and ACP code audit for mainnet deployment.
- Neuron backend refactoring.
