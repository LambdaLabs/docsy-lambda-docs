---
title: "What should I do about timeout waiting for RPC from GSP errors?"
type: docs
---

If you're seeing in your instance's logs error messages about `Timeout waiting
for RPC from GSP!`, the system software installed on your instance needs to be
upgraded.

To upgrade the system software installed on your instance, run:

```bash
sudo apt update && sudo apt full-upgrade && sudo reboot
```

{{% alert title="Warning" color="warning" %}}
The above command will reboot your instance.
{{% /alert %}}
