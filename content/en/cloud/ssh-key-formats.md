---
title: "What SSH key formats are supported?"
type: docs
tags:
- SSH
---

You can add SSH keys in the following formats using the
[dashboard]({{< relref "cloud-dashboard#add-generate-and-delete-ssh-keys" >}})
or the
[Cloud API]({{< relref "api-add-ssh-key#add-an-existing-ssh-key-to-your-account" >}}):

- OpenSSH (the format `ssh-keygen` uses by default when generating keys)
- RFC4716 (the format PuTTYgen uses when you save a public key)
- PKCS8
- PEM

{{% alert title="Note" color="info" %}}
- OpenSSH keys look like:

  ```
  ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIK5HIO+OQSyFjz0clkvg+48YAihYMo5J7AGKiq+9Alg8 cody@lambdal.com
  ```

- RFC4716 keys begin with:

  ```
  ---- BEGIN SSH2 PUBLIC KEY ----
  ```

- PKCS8 keys begin with:

  ```
  -----BEGIN PUBLIC KEY-----
  ```

- PEM keys begin with, for example:

  ```
  -----BEGIN RSA PUBLIC KEY-----
  ```
{{% /alert %}}
