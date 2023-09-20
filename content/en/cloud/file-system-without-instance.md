---
title: "Can I access my persistent storage without an instance?"
type: docs
tags:
- storage
---

You can't access your persistent storage file systems without attaching them
to an instance _at the time the instance is launched_.

For this reason, _it's recommended that you keep a local copy of the files you
have saved in your persistent storage file systems_.

{{% alert title="Note" color="info" %}}
You're
[billed for persistent storage usage]({{< relref "persistent-storage-billing" >}})
whether or not your file systems are attached to an instance.
{{% /alert %}}
