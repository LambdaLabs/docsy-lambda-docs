---
title: "How do I learn my instance's private IP address and other info?"
type: docs
tags:
- network
---

You can learn your instance's private IP address with the `ip` command.

## Learn your instance's private IP address

<!-- The instructions, below, assume:
     - Instances are assigned only one private IP address.
     - Instance private IP addresses always begin with '10.'. -->

To learn your instance's private IP address, SSH into your instance and run:

```bash
ip -4 -br addr show |grep '10.'
```

The above command will output, for example:

```
enp5s0           UP             10.19.60.24/20
```

In the above example, the instance's private IP address is **10.19.60.24**.

{{% alert title="Tip" color="success" %}}
If you want your instance's private IP address and that address only, you can
run the following command instead:

```bash
ip -4 -br addr show |grep -Eo '10\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)'
```

The above command will output, for example:

```
10.19.60.24
```
{{% /alert %}}
