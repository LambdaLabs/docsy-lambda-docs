---
title: "What network bandwidth does Lambda GPU Cloud provide?"
type: docs
tags:
- network
aliases:
- faq/network-bandwidth
---

All of our [on-demand instances](https://lambdalabs.com/service/gpu-cloud)
share a single symmetric 10 Gbps connection to the Internet. We plan on
upgrading this connection to 20 Gbps in the coming months.

Internally, many of our servers have a 200 Gbps connection to our data
center's network. Some of our servers have a 20 Gbps connection, shared by up
to 8 instances.

{{% alert title="Note" color="info" %}}
Real-world network bandwidth depends on a variety of factors, including the
total number of connections opened by your applications.
{{% /alert %}}
