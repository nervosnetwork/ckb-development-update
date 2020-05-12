# Nervos CKB Development Update \#3

Covering Jan 14 to 27, 2019

------------------------------------------------------------------------

### Nervos CKB Development Update \#3

Covering Jan 14 to 27, 2019

![](https://cdn-images-1.medium.com/max/1200/1*f-jEp9E_w92dBUugOM76Ww.png)

This post is co-authored by [Ian Yang](https://medium.com/u/72022cac4c7c), [Xuejie Xiao](https://medium.com/u/6f2cfa203c38) and [TheWaWaR](https://github.com/TheWaWaR).

### **TL;DR**

-   There is a major update to CKB whitepaper.
-   On-going VM JIT development.

### **Changes in RFCs**

#### **Updates**

-   [RFC0002](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0002-ckb/0002-ckb.md): This is a major update to CKB whitepaper, one year after its publication. Jan added the latest results come from discussions and developments and removed obsolete contents. ([\#64](https://github.com/nervosnetwork/rfcs/pull/64))
-   [RFC0003](https://github.com/nervosnetwork/rfcs/blob/master/rfcs/0003-ckb-vm/0003-ckb-vm.md): Previously, we keep atomic support in CKB VM hoping for maximum compatibility, but since now rv64imc without atomic support is starting to get popular, we don’t need to keep atomic instruction support in our design. ([\#68](https://github.com/nervosnetwork/rfcs/issues/68))

### **Changes in CKB**

The code for [v0.5.0 has been frozen](https://github.com/nervosnetwork/ckb/pull/215). This version has upgraded Rust to 1.31.1 to use the stabilized integer bytes APIs.  
  
We added transaction trace api ([\#181](https://github.com/nervosnetwork/ckb/issues/181)) ([e759128](https://github.com/nervosnetwork/ckb/commit/e759128)), which can help to figure out the reason when a transaction is not packaged into blocks.

The team is discussing and working out several important features of Cell scripts to support layer-2, which will be published as RFCs soon.

### Changes in VM

-   On-going VM JIT development
-   VM refactoring aiding JIT architecture([\#21](https://github.com/nervosnetwork/ckb-vm/pull/21), [\#22](https://github.com/nervosnetwork/ckb-vm/pull/22), [\#25](https://github.com/nervosnetwork/ckb-vm/pull/25))
-   Other VM refactoring([\#23](https://github.com/nervosnetwork/ckb-vm/pull/23), [\#24](https://github.com/nervosnetwork/ckb-vm/pull/24))

### **Changes in P2P**

-   Fix a bug in tokio-yamux.
-   Add some integrate tests.
-   Add some benckmarks.

By [Ian Yang](https://medium.com/@doitian) on [January 29, 2019](https://medium.com/p/abff07494132).

[Canonical link](https://medium.com/@doitian/nervos-ckb-development-update-3-abff07494132)

Exported from [Medium](https://medium.com) on May 12, 2020.
