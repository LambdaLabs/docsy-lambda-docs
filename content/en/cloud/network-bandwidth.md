---
title: "What network bandwidth does Lambda GPU Cloud provide?"
type: docs
tags:
- network
aliases:
- faq/network-bandwidth
---

## Texas, USA region (us-south-1)

All of the [on-demand instances](https://lambdalabs.com/service/gpu-cloud) in
our Texas, USA region (us-south-1) share two symmetric 10 Gbps connections to
the Internet, providing both redundancy and throughput of up to 20 Gbps.

Internally, many of our servers have a 200 Gbps connection to our data
center's network. Some of our servers have a 20 Gbps connection, shared by up
to 8 instances.

{{% alert title="Note" color="info" %}}
Real-world network bandwidth depends on a variety of factors, including the
total number of connections opened by your applications.
{{% /alert %}}
