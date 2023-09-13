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
