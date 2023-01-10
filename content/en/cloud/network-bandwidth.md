---
title: "What network bandwidth does Lambda GPU Cloud provide?"
type: docs
tags:
- network
aliases:
- faq/network-bandwidth
---

## Texas, USA region (us-south-1)

The bandwidth between instances in our Texas, USA region (us-south-1) is          
approximately 200 Gbps.                                                       
                                                                              
Bandwidth to the Internet is approximately 20 Gbps.

## Arizona, USA region (us-west-2)

The bandwidth between instances in our Arizona, USA region (us-west-2) is
approximately 3.7 Gbps when using the instances' _private IP addresses_.

When using the instances' _public IP addresses_, the bandwidth is
approximately 3.5 Gbps.

Bandwidth to the Internet is approximately 10 Gbps.

## Virginia, USA region (us-east-1)

The bandwidth between instances in our Virginia, USA region (us-east-1) is
approximately 3.7 Gbps when using the instances' _private IP addresses_.

Bandwidth to the Internet is approximately 10 Gbps.

## Arizona, USA (us-west-2) ↔ Virginia, USA (us-east-1)

The bandwidth between instances in our Arizona, USA (us-west-2) and Virginia,
USA (us-east-1) regions is approximately 100 Mbps.

{{% alert title="Note" color="info" %}}
The bandwidth approximations for connections between instances were obtained
using [iPerf3](https://iperf.fr/).

The bandwidth approximations for connections to the Internet were obtained
using [Speedtest CLI](https://www.speedtest.net/apps/cli).
{{% /alert %}}

{{% alert title="Note" color="info" %}}
Real-world network bandwidth depends on a variety of factors, including the
total number of connections opened by your applications.
{{% /alert %}}

{{% alert title="Note" color="info" %}}
We're in the process of testing the network bandwidth in our other regions.
{{% /alert %}}
