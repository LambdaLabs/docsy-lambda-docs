---
title: "Use iptables to disable firewall"
type: docs
---

To allow
[Lambda GPU Cloud reserved instances](https://lambdalabs.com/service/gpu-cloud/reserved)
to communicate with each other, the firewall on each instance should be
disabled.

{{% alert title="Tip" color="success" %}}
Technically, it's not necessary to entirely disable the firewall on each
instance. But, it's the easiest way to ensure network traffic between
instances isn't being blocked by a firewall.

You can learn more advanced usage of `iptables`, including how to fine-tune
firewall rules, by reading the `iptables`
[manual page](https://linux.die.net/man/8/iptables).
{{% /alert %}}

Run the following commands on each of your instances to disable the firewall:

```bash
sudo iptables -P INPUT ACCEPT   # accept all incoming traffic by default
sudo iptables -P OUTPUT ACCEPT  # accept all outgoing traffic by default
sudo iptables -P FORWARD ACCEPT # accept all forwarded traffic by default
sudo iptables -F                # delete all rules in the filter table
sudo iptables -t nat -F         # delete all rules in the nat table
sudo iptables -t mangle -F      # delete all rules in the mangle table
sudo iptables -X                # delete all non-built-in chains
```

To keep the firewall disabled after rebooting, run:
```bash
sudo iptables-save | sudo tee /etc/iptables/rules.v4 > /dev/null
```

{{% alert title="Note" color="info" %}}
The firewall that restricts traffic from the Internet to your Lambda GPU Cloud
reserved instances is managed by Lambda.

[Contact the Lambda Support team](mailto:cloud@lambdalabs.com?subject=%5BRESERVED%5D%20Modify%20VCN%20firewall)
if you need this firewall's rules to be modified.
{{% /alert %}}
