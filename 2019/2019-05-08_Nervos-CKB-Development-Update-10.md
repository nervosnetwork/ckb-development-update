# Nervos CKB Development Update \#10

Covering Apr 22 to May 5

------------------------------------------------------------------------

### Nervos CKB Development Update \#10

Covering Apr 22 to May 5

![](https://cdn-images-1.medium.com/max/1200/1*Ks_AtsbLnLYPCzFThMXGZQ.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c) and [James Chen](https://medium.com/u/24192bbe4c92).

### TL;DR

-   Capacity uses unit shannon which is `10e-8` CKBytes
-   CKB will check database is compatible on startup.

### Changes in RFCs

-   A new syscall *Load Transaction Hash* is added ([PR\#110](https://github.com/nervosnetwork/rfcs/pull/110)).

### Changes in CKB

CKB [v0.10.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.10.0) has released, and [v0.11.0](https://github.com/nervosnetwork/ckb/pull/639) is ready.

Features highlights in v0.11.0:

The most important change in 0.11.0 is [\#528](https://github.com/nervosnetwork/ckb/pull/528): capacity uses unit shannon which is `10e-8` CKBytes ([@yangby-cryptape](https://github.com/yangby-cryptape)).

We did many performance tests, [@jjyr](https://github.com/jjyr) has added a sub command to ease running performance benchmarks [\#554](https://github.com/nervosnetwork/ckb/pull/554). According to the benchmark result, we have applied following performance tuning:

-   [\#587](https://github.com/nervosnetwork/ckb/pull/587): lazy load cell output ([@jjyr](https://github.com/jjyr))
-   [\#586](https://github.com/nervosnetwork/ckb/pull/586): Relay transaction by hash ([@TheWaWaR](https://github.com/TheWaWaR))
-   [\#624](https://github.com/nervosnetwork/ckb/pull/624): only verify unknown tx in block proposal ([@jjyr](https://github.com/jjyr))
-   [\#601](https://github.com/nervosnetwork/ckb/pull/601): Stop ask for transactions when initial block download ([@TheWaWaR](https://github.com/TheWaWaR))
-   [\#588](https://github.com/nervosnetwork/ckb/pull/588): Initial block download message storm ([@driftluo](https://github.com/driftluo))

The CKB is in rapid development, a common gotchas is running a new version with an old incompatible database, thus we added several guards to discovery such issue earlier:

-   [\#570](https://github.com/nervosnetwork/ckb/pull/570): check if the data in database is compatible with the program ([@yangby-cryptape](https://github.com/yangby-cryptape))
-   [\#569](https://github.com/nervosnetwork/ckb/pull/569): check if genesis hash in config file was same as 0th block hash in db ([@yangby-cryptape](https://github.com/yangby-cryptape))

### Changes in Toolchains

SDKs

-   Rename some core types
-   Update RPC types/methods and tests

CKB testnet faucet

-   Improve tests and depoyments (Docker + Nginx)

CKB Explorer

-   Refactor views
-   Build on-chain test data
-   Update with CKB’s recent changes, deploy to test server

CKB Neuron Wallet

-   Initial development: UI layer, chain sync, key management, etc.

By [Ian Yang](https://medium.com/@doitian) on [May 8, 2019](https://medium.com/p/42be0716ac9a).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-10-42be0716ac9a)

Exported from [Medium](https://medium.com) on May 12, 2020.
