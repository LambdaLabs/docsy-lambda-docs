---
title: "What should I do about timeout waiting for RPC from GSP errors?"
type: docs
---

If you're seeing in your instance's logs error messages about `Timeout waiting
for RPC from GSP!`, the system software installed on your instance needs to be
upgraded.

{{% alert title="Note" color="info" %}}
`nvidia-smi` might also produce output similar to the following:

```
+-------------------------------+----------------------+----------------------+
|   4  NVIDIA A100-SXM...  On   | 00000000:8C:00.0 Off |                    0 |
| N/A   34C    P0    60W / 400W |      0MiB / 81920MiB |      0%      Default |
|                               |                      |             Disabled |
+-------------------------------+----------------------+----------------------+
|   5  ERR!                On   | 00000000:91:00.0 Off |                 ERR! |
|ERR!  ERR! ERR!    ERR! / ERR! |      0MiB / 81920MiB |    ERR!      Default |
|                               |                      |                 ERR! |
+-------------------------------+----------------------+----------------------+
```
{{% /alert %}}

To upgrade the system software installed on your instance, run:

```bash
sudo apt update && sudo apt full-upgrade && sudo reboot
```

{{% alert title="Warning" color="warning" %}}
The above command will reboot your instance.
{{% /alert %}}
