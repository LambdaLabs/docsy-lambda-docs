---
title: "How do I fix slow performance with my Gen 4 M.2 NVMe drive?"
type: docs
tags:
- hardware
- storage
- troubleshooting
---

There's a known issue where Gen 4 M.2 NVMe drives experience slow performance
when installed into the **M.2_1** slot in ASUS Pro WS WRX80E-SAGE SE WIFI
motherboards, which are used in Lambda workstations.

If you run `sudo dmesg | grep -E 'Hardware Error|AER'`, you'll see error
messages that look like:

```
[  169.304022] {3}[Hardware Error]: It has been corrected by h/w and requires no further action
[  169.304023] {3}[Hardware Error]: event severity: corrected
[  169.304024] {3}[Hardware Error]:  Error 0, type: corrected
[  169.304025] {3}[Hardware Error]:   section_type: PCIe error
[  169.304026] {3}[Hardware Error]:   port_type: 0, PCIe end point
[  169.304026] {3}[Hardware Error]:   version: 0.2
[  169.304027] {3}[Hardware Error]:   command: 0x0406, status: 0x0010
[  169.304028] {3}[Hardware Error]:   device_id: 0000:2c:00.0
[  169.304029] {3}[Hardware Error]:   slot: 0
[  169.304029] {3}[Hardware Error]:   secondary_bus: 0x00
[  169.304030] {3}[Hardware Error]:   vendor_id: 0x1022, device_id: 0xb000
[  169.304030] {3}[Hardware Error]:   class_code: 010802
[  169.304031] {3}[Hardware Error]:   bridge: secondary_status: 0x0000, control: 0x0000
```

The error messages might also look like:

```
[    4.172130] acpi PNP0A08:03: PCIe AER handled by firmware
[   59.749158] nvme 0000:2c:00.0: AER: aer_status: 0x00002001, aer_mask: 0x00000000
[   59.749860] nvme 0000:2c:00.0: AER:	  [ 0] RxErr		      (First)
[   59.750522] nvme 0000:2c:00.0: AER:	  [13] NonFatalErr
[   59.751161] nvme 0000:2c:00.0: AER: aer_layer=Physical Layer, aer_agent=Receiver ID
```

If you're experiencing slow performance and seeing errors,
[contact Lambda Support](https://support.lambdalabs.com/hc/en-us/requests/new)
for a BIOS update that fixes the issue.
