---
title: "Remotely accessing your Vector using SSH"
type: docs
tags:
- network
- SSH
- Ubuntu
---

You can install OpenSSH Server on your Vector to allow secure remote access
via SSH.

To install OpenSSH Server:

1. Press **Ctrl** + **Alt** + **T** on your keyboard to open a terminal.

1. In the terminal, type:

   ```bash
   sudo apt -yqq update && sudo apt -yqq install openssh-server
   ```

   Then, press **Enter** on your keyboard to run the command.

   The command will install and configure OpenSSH Server.

Once OpenSSH Server is installed on your Vector, you can SSH into your Vector
from other computers.

For example, to SSH into your Vector from another computer running Ubuntu:

1. Press **Ctrl** + **Alt** + **T** on the other computer's keyboard to open a
   terminal.

1. In the terminal, type in the following command:

   ```bash
   ssh USERNAME@HOST
   ```

   Replace **USERNAME** with your username on your Vector. Replace **HOST**
   with your [Vector's IP address]({{< relref "connecting-to-your-network" >}}).

   Then, press **Enter** on the keyboard to run the command.

1. The first time you SSH into your Vector, you'll see a warning similar to
   the following:

   ```
   The authenticity of host '192.168.122.181 (192.168.122.181)' can't be established.
   ED25519 key fingerprint is SHA256:atnhDBdkhdxpVgBhRXAnkrOBrQqshA65O/1toxafdTU.
   This key is not known by any other names
   Are you sure you want to continue connecting (yes/no/[fingerprint])?
   ```

   Type `yes`, then press **Enter**.

   You'll be prompted to enter your password. Type in your password, then
   press **Enter**.

   {{% alert title="Note" color="info" %}}
   You won't see masking characters such as `*` or `•` as you type in your
   password.
   {{% /alert %}}

   You're now remotely logged into your Vector.
