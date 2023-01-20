---
title: "Why are high-speed interconnects needed for Echelon?"
type: docs
tags:
- hardware
- network
- storage
---

[Echelon GPU clusters](https://lambdalabs.com/gpu-cluster/echelon) need
[InfiniBand](https://www.nvidia.com/en-us/networking/products/infiniband/)
(or another high-speed network interconnect solution) to maximize bandwidth
and minimize latency within the cluster.

Additionally, high-speed network interconnects such as InfiniBand support RDMA
(Remote Direct Memory Access). RDMA technology significantly reduces latency
between nodes by enabling the nodes to directly access each other's memory,
bypassing the node operating systems and CPUs.
