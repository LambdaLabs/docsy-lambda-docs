---
title: "How do I fix slow performance with my Gen 4 M.2 NVMe drive?"
type: docs
tags:
- hardware
- storage
- troubleshooting
---

If you're experiencing slow performance or errors with your Gen 4 M.2 NVMe
drive, you might need to reinstall the drive into a new slot on your
workstation's motherboard.

There's a known issue where Gen 4 M.2 NVMe drives experience slow performance
and errors when installed into the **M.2_1** slot in ASUS Pro WS WRX80E-SAGE
SE WIFI motherboards, which are used in Lambda workstations. The manufacturer
of the motherboard, ASUS, has been notified of the issue.

Until ASUS releases a BIOS update that fixes the issue, you can work around
the issue:

- If you have only 1x M.2 NVMe drive in your workstation, move the drive from
  slot **M.2_1** to slot **M.2_2**.

- If you have 1x M.2 NVMe drive and 1x U.2 NVMe drive in your workstation,
  move the M.2 NVMe drive from slot **M.2_1** to slot **M.2_2**. Move the U.2
  NVMe drive from slot **U.2_1** to slot **U.2_2**.

{{< imgproc ASUS-WRX80E-motherboard-M.2-U.2-moves Resize "800x" >}}{{< /imgproc >}}

{{% alert title="Note" color="info" %}}
Unfortunately, there currently is no known workaround for workstations that
have 1x M.2 NVMe drive and 2x U.2 NVMe drives.
{{% /alert %}}
