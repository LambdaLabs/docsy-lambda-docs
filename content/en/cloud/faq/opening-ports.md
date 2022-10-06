---
title: "Is it possible to open ports other than for SSH?"
type: docs
---

Yes, it's possible to open ports other than for SSH.

Contact the
[Lambda Support team](mailto:cloud@lambdalabs.com?subject=Open%20ports) with
the following information:

1. The public IP address of your instance, that is, the IP address that you
   use to SSH into your instance.

2. The port number or range of ports you want opened. You can additionally
   specify the protocol, either TCP or UDP, or both. If you don't specify a
   protocol, the port(s) will be opened to both incoming TCP and UDP traffic.

3. The source IP address(es) you want to allow connections from. If you don't
   specify at least one source IP address, the ports will be opened to
   incoming traffic from any source.

The Lambda Support team can also configure your instance to reply to ICMP
messages used by diagnostic tools such as `ping` and `traceroute`.

{{% alert title="Note" color="info" %}}
If you're on a reserved instance, you'll have to
[modify your instance's firewall rules]({{< relref "../guides/iptables-flush-rules" >}})
in addition to contacting the Lambda Support team.
{{% /alert %}}
