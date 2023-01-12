---
title: "How do I learn my instance's private IP address and other info?"
type: docs
tags:
- network
---

You can
[learn your instance's private IP address]({{< relref "#learn-your-instances-private-ip-address" >}})
with the `ip` command.

You can
[learn what ports are open on your instance]({{< relref "#learn-what-ports-on-your-instance-are-publicly-accessible" >}})
with the `nmap` command.

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
If you want your instance's private IP address and only that address,
run the following command instead:

```bash
ip -4 -br addr show | grep -Eo '10\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)'
```

The above command will output, for example:

```
10.19.60.24
```
{{% /alert %}}

## Learn what ports on your instance are publicly accessible

You can use `nmap` to learn what ports on your instance are publicly
accessible, that is, reachable over the Internet.

{{% alert title="Note" color="info" %}}
The instructions, below, assume you're running Ubuntu on your computer.
{{% /alert %}}

First, install `nmap` by running:

```bash
sudo apt install -y nmap
```

Next, run:

```bash
nmap -Pn INSTANCE-IP-ADDRESS
```

Replace **INSTANCE-IP-ADDRESS** with your instance's IP address, which you can
get from the [Cloud dashboard](https://cloud.lambdalabs.com/instances).

The command will output, for example:

```
Starting Nmap 7.80 ( https://nmap.org ) at 2023-01-11 13:22 PST
Nmap scan report for 129.159.46.35
Host is up (0.041s latency).
Not shown: 999 filtered ports
PORT   STATE SERVICE
22/tcp open  ssh

Nmap done: 1 IP address (1 host up) scanned in 6.42 seconds
```

In the above example, TCP port 22 (SSH) is publicly accessible.

{{% alert title="Note" color="info" %}}
`nmap -Pn INSTANCE-IP-ADDRESS` only scans the 1,000 most common TCP ports.
{{% /alert %}}
