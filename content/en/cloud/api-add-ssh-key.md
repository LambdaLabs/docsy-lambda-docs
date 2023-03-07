---
title: "Can I use the Cloud API to add an SSH key to my account?"
type: docs
tags:
- API
- SSH
---

You can use the [Cloud API](https://cloud.lambdalabs.com/api/v1/docs) to
[add an existing SSH key to your account]({{< relref "#add-an-existing-ssh-key-to-your-account" >}})
or
[generate a new SSH key pair]({{< relref "#generate-a-new-ssh-key-pair" >}}).

{{% alert title="Note" color="info" %}}
Following these instructions won't add the SSH key to existing instances.

To add SSH keys to existing instances, read our FAQ on
[using more than one SSH key]({{< relref "more-than-one-ssh-key" >}})
{{% /alert %}}

# Add an existing SSH key to your account

To add an existing SSH key to your account:

1. [Generate an API key](https://cloud.lambdalabs.com/api-keys) if you don't
   have one already.

2. Create a file named `ssh-key.json` that contains the
   [necessary payload](https://cloud.lambdalabs.com/api/v1/docs#operation/launchInstance).
   For example:

   ```json
   {
     "name": "my-new-key",
     "public_key": "ssh-ed25519 KEY COMMENT"
   }
   ```

3. Run the following command:

   ```bash
   curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/ssh-keys -d @ssh-key.json -H "Content-Type: application/json" | jq .
   ```

Replace **API-KEY** with your actual API key. **Don't remove the trailing
colon (:).**

# Generate a new SSH key pair

To generate a new SSH key pair:

1. [Generate an API key](https://cloud.lambdalabs.com/api-keys) if you don't
   have one already.

2. Run the following command:

   ```bash
   curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/ssh-keys -d '{ "name": "my-generated-key" }' -H "Content-Type: application/json" | jq -r '.data.private_key' > my-generated-private-key.pem
   ```

   Replace **API-KEY** with your actual API key. **Don't remove the trailing
   colon (:).**

3. The private key for your SSH key pair will be saved as
   `my-generated-private-key.pem`.

   Run `chmod 400 my-generated-private-key.pem` to set the correct file
   permissions for your private key.

# List the SSH keys saved in your account

To list the SSH keys saved in your account,
[generate an API key](https://cloud.lambdalabs.com/api-keys) if you don't
already have one. Then, run the following command:

```bash
curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/ssh-keys | jq .
```

Replace **API-KEY** with your actual API key. **Don't remove the trailing
colon (:).**

# Delete an SSH key from your account

To delete an SSH key from your account,
[generate an API key](https://cloud.lambdalabs.com/api-keys) if you don't
already have one. Then, run the following command:

```bash
curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/ssh-keys/SSH-KEY-ID | jq .
```

Replace **API-KEY** with your actual API key. **Don't remove the trailing
colon (:).**

Replace **SSH-KEY-ID** with the ID of the instance you want details about.

{{% alert title="Note" color="info" %}}
[Use the API to obtain the IDs of the SSH keys saved in your account]({{< relref "#list-the-ssh-keys-saved-in-your-account" >}}).
{{% /alert %}}
