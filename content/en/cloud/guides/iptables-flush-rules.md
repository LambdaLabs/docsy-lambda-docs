---
title: "Use iptables to disable firewall"
type: docs
---

By default,
[Lambda GPU Cloud reserved instances](https://lambdalabs.com/service/gpu-cloud/reserved)
allow incoming connections only to TCP port 22, which is typically used for
`ssh` access.

To allow incoming connections to ports other than TCP port 22, the instance's
default firewall rules need to be modified.

`iptables` can be used to modify the firewall rules or disable the firewall
entirely.

{{% alert title="Warning" color="warning" %}}
The instructions below **completely disable the firewall on the instance and
don't follow best security practices**.

For security, firewalls should be configured to allow incoming connections
only to the ports needed for specific services. For example:

- TCP/80 and TCP/443 for `http` and `https`, respectively
- TCP/22 for `ssh`
- TCP/25 for `smtp`

The instructions below provide a quick, simple, but **insecure** way to ensure
network traffic between instances isn't being blocked by a firewall.

We highly recommend that you:

- Read the `iptables` [manual page](https://linux.die.net/man/8/iptables) to
  learn more advanced usage of `iptables`, including how to fine-tune firewall
  rules

- Configure your firewall rules to allow incoming connections only to the
  ports needed for the services that you're running
{{% /alert %}}

To entirely disable the firewall on the instance, run the following commands:

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
