---
title: "How are on-demand instances invoiced?"
type: docs
tags:
- billing
---

[On-demand instances](https://lambdalabs.com/service/gpu-cloud) are billed in
one-minute increments from the moment you spin up (start) the instance up to
the moment you terminate (stop) the instance.

{{% alert title="Warning" color="warning" %}}
Be sure to terminate any instances that you're not using!

**You will be billed for all minutes that an instance is running, even if the
instance isn't actively being used.**
{{% /alert %}}

The GPU Cloud dashboard allows you to
[view your resource usage](https://cloud.lambdalabs.com/usage).

Invoices are sent weekly for the previous week's usage.

{{% alert title="Note" color="info" %}}
On-demand instances require us to maintain excess capacity at all times so we
can meet the changing workloads of our customers. For this reason, on-demand
instances are priced higher than reserved instances.

Conversely, we offer
[reserved GPU Cloud instances](https://lambdalabs.com/service/gpu-cloud/reserved)
at a significant savings over on-demand instances, since they allow us to more
accurately determine our capacity needs ahead of time.
{{% /alert %}}
