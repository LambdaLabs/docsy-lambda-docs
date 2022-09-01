---
title: "Where can I find my server's IPMI (BMC) password?"
type: docs
---

## Supermicro

On Supermicro chassis, the IPMI password appears on one or more of the
following:

- a sticker near the BMC (Baseboard Management Controller)

- a sticker near the motherboard serial number label

- the service tag

See Supermicro's
[BMC Unique Password Guide [PDF]](https://www.supermicro.com/support/BMC_Unique_Password_Guide.pdf)
for more information.

## GIGABYTE

On GIGABYTE chassis, the IPMI password appears on one or more of the following:

- a sticker affixed to the motherboard

- the chassis itself

See GIGABYTE's
[BMC Unique Pre-Programmed Password Reference Guide [PDF]](https://www.gigabyte.com/Fileupload/Global/Multimedia/101/file/573/1015.pdf)
for more information.

{{% alert title="Tip" color="success" %}}
You can choose your own IPMI password from within Ubuntu:

1. Run `sudo apt-get install ipmitool` to install `ipmitool`, which is a
   program for managing IPMI functions.

1. Run `ipmitool user list 1`. Confirm that `ID 2` is `admin` or `ADMIN`.

1. Run `ipmitool user set password 2` to set a new IPMI password.
{{% /alert %}}
