---
title: "What network bandwidth does Lambda GPU Cloud provide?"
type: docs
tags:
- network
aliases:
- faq/network-bandwidth
---

{{% alert title="Note" color="info" %}}
Some sites limit transfer speeds. This is known as _bandwidth throttling_.

**Lambda GPU Cloud doesn't limit your transfer speeds but can't control other
sites' use of bandwidth throttling.**

Further, real-world network bandwidth depends on a variety of factors,
including the total number of connections opened by your applications and
overall network utilization.
{{% /alert %}}

## Utah, USA region (us-west-3)

The bandwidth between instances in our Utah, USA region (us-west-3) can be up
to 200 Gbps.

Bandwidth to the Internet can be up to 20 Gbps.

## Texas, USA region (us-south-1)

The bandwidth between instances in our Texas, USA region (us-south-1) can be
up to 200 Gbps.

Bandwidth to the Internet can be up to 20 Gbps.

## Arizona, USA region (us-west-2)

The bandwidth between instances in our Arizona, USA region (us-west-2) can be
up to 3.7 Gbps when using the instances' _private IP addresses_.

When using the instances' _public IP addresses_, the bandwidth can be up to
3.5 Gbps.

Bandwidth to the Internet can be up to 10 Gbps.

## Virginia, USA region (us-east-1)

The bandwidth between instances in our Virginia, USA region (us-east-1) can be
up to 7.2 Gbps when using the instances' _private IP addresses_.

Bandwidth to the Internet can be up to 10 Gbps.

## Arizona, USA (us-west-2) ↔ Virginia, USA (us-east-1)

The bandwidth between instances in our Arizona, USA (us-west-2) and Virginia,
USA (us-east-1) regions can be up to 100 Mbps.

{{% alert title="Note" color="info" %}}
The bandwidth tests for connections between instances were performed using
[iPerf3](https://iperf.fr/).

The bandwidth tests for connections to the Internet were performed using
[Speedtest CLI](https://www.speedtest.net/apps/cli).
{{% /alert %}}

{{% alert title="Note" color="info" %}}
We're in the process of testing the network bandwidth in our other regions.
{{% /alert %}}
