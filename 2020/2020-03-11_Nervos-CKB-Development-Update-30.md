# Nervos CKB Development Update \#30

Covering Feb 24 to Mar 8

------------------------------------------------------------------------

### Nervos CKB Development Update \#30

Feb 24 — Mar 8

By [Cipher Wang](https://github.com/CipherWang), [Ian Yang](https://medium.com/u/72022cac4c7c)

![](https://cdn-images-1.medium.com/max/800/1*uhK2YbTBGxv6LeN4J2vvJQ.png)

### TL;DR

-   Released [CKB v0.29.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.29.0) and Neuron [v0.29.0-rc2](https://github.com/nervosnetwork/neuron/releases).
-   Published a h[ow-to on scripting with Duktape](https://xuejie.space/2020_02_21_introduction_to_ckb_script_programming_advanced_duktape_examples/).

### Changes in CKB

#### **We have**

-   Released [CKB v0.29.0](https://github.com/nervosnetwork/ckb/releases/tag/v0.29.0). This version changed the default value of a new field added in v0.28.0 to make the RPC backward compatible with the older version.
-   Published a h[ow-to on scripting with Duktape](https://xuejie.space/2020_02_21_introduction_to_ckb_script_programming_advanced_duktape_examples/).
-   Added proptest for Molecule [C, Rust](https://github.com/nervosnetwork/molecule/pull/24) and [Go](https://github.com/driftluo/moleculec-go).

#### **We are**

-   Trying to improve block synchronization speed and avoid stuck.
-   Collecting network metrics to guide future improvements.
-   Surveying Light Client protocols.

### Changes in Toolchain

#### **Neuron** [**v0.29.0-rc2**](https://github.com/nervosnetwork/neuron/releases) **released.**

-   Bundled CKB node v0.29.0
-   New feature: sign/verify message
-   New feature: customized assets, allows user to claim their tokens with time lock
-   New feature: transaction with locktime
-   Performance tweak: we have found and fixed a serious performance issue with this version.

### **CKB Explorer**

-   New version of [testnet faucet](https://faucet.nervos.org/) is online.
-   Several UI adjustments related to transaction presentation.

------------------------------------------------------------------------

**Join our community:** [Github](https://github.com/nervosnetwork) [Forum](https://talk.nervos.org/) [Reddit](https://www.reddit.com/r/NervosNetwork) [Twitter](https://twitter.com/nervosnetwork)

For discussions or questions join the conversation on [**Discord**](https://discord.gg/Cc8Tr6K) **or** check out one of our community Telegram channels: [**English**](https://t.me/NervosNetwork)**,** [**Korean**](http://t.me/NervosKorea)**,** [**Russian**](https://t.me/NervosRussia)**,** [**Japanese**](http://t.me/NervosNertwork_japan)**,** [**Spanish**](https://t.me/NervosNetworkES)**,** [**Vietnamese**](https://t.me/nervosvietnam) and [**Chinese**](https://t.me/NervosNetworkcn)

By [Ian Yang](https://medium.com/@doitian) on [March 11, 2020](https://medium.com/p/e05a4ddb6ab1).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-30-e05a4ddb6ab1)

Exported from [Medium](https://medium.com) on May 12, 2020.
