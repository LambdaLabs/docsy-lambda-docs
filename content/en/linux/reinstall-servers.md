---
title: "How do I reinstall Ubuntu and Lambda Stack on my server?"
type: docs
tags:
- Lambda Stack
- recovery
- Ubuntu
---

To reinstall Ubuntu and Lambda Stack on your Lambda server,
[download the Ubuntu 22.04 Server install image](https://releases.ubuntu.com/22.04/),
then follow
[Ubuntu's Server installation instructions](https://ubuntu.com/server/docs/installation).

Install the latest Lambda Stack by logging into Ubuntu and running
`wget -nv -O- https://lambdalabs.com/install-lambda-stack.sh | sh -`.

{{% alert title="Note" color="info" %}}
[Recovery images]({{< relref "recovery-images" >}}) aren't available for
servers.
{{% /alert %}}
