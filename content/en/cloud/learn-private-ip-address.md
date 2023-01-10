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
ip -4 -br addr show | grep '10.'
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
ip -4 -br addr show | grep -Eo '10\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)'
```

The above command will output, for example:

```
10.19.60.24
```
{{% /alert %}}

## Learn what ports are publicly accessible

You can use `nmap` to learn what ports on your instance are publicly
accessible, that is, reachable over the Internet.

First, SSH into your instance. Then, install `nmap` by running:

```bash
sudo apt install -y nmap
```

Next, run:

```bash
nmap "$(curl -s https://ipinfo.io/ip)"
```

The command will output, for example:

```
Starting Nmap 7.80 ( https://nmap.org ) at 2023-01-05 16:07 UTC
Nmap scan report for 129.159.46.35
Host is up (0.00011s latency).
Not shown: 998 closed ports
PORT    STATE SERVICE
22/tcp  open  ssh
111/tcp open  rpcbind

Nmap done: 1 IP address (1 host up) scanned in 0.33 seconds
```

In the above example, the instance's IP address is **129.159.46.35**, and TCP
ports 22 and 111 are publicly accessible.

{{% alert title="Note" color="info" %}}
`nmap "$(curl -s https://ipinfo.io/ip)"` only scans the 1,000 most common TCP
ports.
{{% /alert %}}
