---
title: "Can I set a limit (quota) on my file system usage?"
type: docs
tags:
- storage
---

Currently, you can't set a limit (quota) on your persistent storage file
system usage.

You can see the usage of a persistent storage file system from within an
instance by running `df -h -BG`. This command will produce output similar to:

```
Filesystem           1G-blocks  Used   Available Use% Mounted on
udev                       99G    0G         99G   0% /dev
tmpfs                      20G    1G         20G   1% /run
/dev/vda1                1357G   23G       1335G   2% /
tmpfs                      99G    0G         99G   0% /dev/shm
tmpfs                       1G    0G          1G   0% /run/lock
tmpfs                      99G    0G         99G   0% /sys/fs/cgroup
persistent-storage 8589934592G    0G 8589934592G   0% /home/ubuntu/persistent-storage
/dev/vda15                  1G    1G          1G   6% /boot/efi
/dev/loop0                  1G    1G          0G 100% /snap/core20/1822
/dev/loop1                  1G    1G          0G 100% /snap/lxd/24061
/dev/loop2                  1G    1G          0G 100% /snap/snapd/18357
tmpfs                      20G    0G         20G   0% /run/user/1000
```

In the example output, above:

- The name of the file system is `persistent-storage`.
- The size of the file system is `8589934592G` (8 exabytes).
- The available capacity of the file system is `8589934592G`.
- The used percentage of the file system is `0%`.
- The file system is mounted on `/home/ubuntu/persistent-storage`.
