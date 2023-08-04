---
title: "How do I import an SSH key from a GitHub account?"
type: docs
tags:
- SSH
- Ubuntu
---

To import an SSH key from a GitHub account and add it to your instance:

1. Using your existing SSH key, SSH into your instance.

1. Import the SSH key from the GitHub account by running:

   ```bash
   ssh-import-id gh:USERNAME
   ```

   Replace **USERNAME** with the GitHub account's username.

If the SSH key is successfully imported, `ssh-import-id` will output a message
similar to:

```
2023-08-04 15:03:52,622 INFO Authorized key ['256', 'SHA256:C6pl0q4evVYZWcyByVF69D6fdbdKa7F8ei8V2F/bTW0', 'cbrownstein-lambda@github/67649580', '(ED25519)']
2023-08-04 15:03:52,623 INFO [1] SSH keys [Authorized]
```

If the SSH key _isn't_ successfully imported, `ssh-import-id` will output a
message similar to:

```
2023-08-04 15:06:36,425 ERROR Username "fake-cbrownstein-lambda" not found at GitHub API. status_code=404 user=fake-cbrownstein-lambda
```
