---
title: "Is it possible to use more than one SSH key?"
type: docs
tags:
- SSH
---

It's possible to allow more than one SSH key to access your instance. To do
so, you need to add public keys to `~/.ssh/authorized_keys`. You can do
this with the `echo` command.

{{% alert title="Tip" color="success" %}}
You can also [import SSH keys from GitHub]({{< relref "ssh-key-from-github" >}}).
{{% /alert %}}

{{% alert title="Note" color="info" %}}
This FAQ assumes that you've already generated another SSH key pair, that is,
a private key and a public key.

Public keys look like this:

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIK5HIO+OQSyFjz0clkvg+48YAihYMo5J7AGKiq+9Alg8 user@hostname
```
{{% /alert %}}

SSH into your instance as you normally do and run:

```bash
echo 'PUBLIC-KEY' >> ~/.ssh/authorized_keys
```

Replace `PUBLIC-KEY` with the public key you want to add to your instance.
**Make sure to keep the single quotes (`' '`).**

You should now be able to log into your instance using the SSH key you just added.
{{% alert title="Tip" color="success" %}}
You can make sure the public key has been added by running:

```
cat ~/.ssh/authorized_keys
```

The last line of output should be the public key you just added.
{{% /alert %}}
