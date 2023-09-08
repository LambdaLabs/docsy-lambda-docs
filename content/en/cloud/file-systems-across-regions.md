---
title: "Can I use a file system in different regions?"
type: docs
tags:
- storage
---

Persistent storage file systems can only be attached to instances in the same
region.

For example, a file system created in the us-west-1 (California, USA) region
can only be attached to instances in the us-west-1 region.

{{% alert title="Note" color="info" %}}
File systems can't be transferred from one region to another. However, you can
copy data between file systems using `rsync`.
{{% /alert %}}
