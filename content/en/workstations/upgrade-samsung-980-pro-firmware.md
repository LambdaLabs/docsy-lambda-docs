---
title: "How do I upgrade my Samsung 980 PRO SSD's firmware?"
type: docs
tags:
- hardware
- storage
- troubleshooting
- upgrade
---

Follow these instructions to upgrade your Samsung 980 PRO NVMe SSD's firmware.

{{% alert title="Warning" color="warning" %}}
[Samsung 980 PRO NVMe SSDs with the older 3B2QGXA7 firmware are known to fail](https://www.pugetsystems.com/support/guides/critical-samsung-ssd-firmware-update/).

To know if your SSD is using the 3B2QGXA7 firmware, install the
`smartmontools` package by running `sudo apt -y install smartmontools`. Then,
run `sudo smartctl -a /dev/nvme0`.

If your SSD is using the 3B2QGXA7 firmware, it's recommended that you upgrade
the firmware as soon as possible.
{{% /alert %}}

First, download the latest firmware ISO from Samsung's website by
running:

```bash
wget https://semiconductor.samsung.com/resources/software-resources/Samsung_SSD_980_PRO_5B2QGXA7.iso
```

Next, run `sudo -s` to open a shell with root (administrator) privileges.

Finally, run:

```bash
mkdir /mnt/iso && mount -o loop Samsung_SSD_980_PRO_5B2QGXA7.iso /mnt/iso && \
mkdir fwupdate && cd fwupdate && \
gzip -dc /mnt/iso/initrd | cpio -idv --no-absolute-filenames && \
cd root/fumagician && ./fumagician
```

The above command mounts the firmware upgrade ISO, extracts the firmware
upgrade, and launches the upgrade.

After the firmware upgrade completes, restart your computer.

Run `sudo smartctl -a /dev/nvme0` to confirm your SSD is using the new
firmware.
