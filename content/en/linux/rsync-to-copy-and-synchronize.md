---
title: "How do I use rsync to copy and synchronize files?"
type: docs
tags:
- SSH
- storage
---

`rsync` is a tool that you can use to
[copy files between your computer and a remote server]({{< relref "#copy-files-between-your-computer-and-a-remote-server" >}}).

`rsync` can also be used to
[copy files directly between remote servers]({{< relref "#copy-files-directly-between-remote-servers" >}}),
bypassing your computer entirely.

{{% alert title="Tip" color="success" %}}
`rsync` is useful for copying files between
[Cloud persistent storage file systems in different regions]({{< relref "../cloud/file-system-without-instance" >}}).
{{% /alert %}}

{{% alert title="Note" color="info" %}}
`rsync` copies files using SSH. For this reason, to copy files between your
computer and a remote server, you need to be able to SSH into the remote
servers.

To use `rsync` to copy files between remote servers directly, you need to be
able to SSH into the remote servers using public key authentication with an
SSH agent.
{{% /alert %}}

## Copy files between your computer and a remote server

To copy files from your computer to a remote server using `rsync`, run:

```bash
rsync -av --info=progress2 FILES USERNAME@SERVER-IP:REMOTE-PATH
```

Replace **FILES** with the files you want to copy to the remote server.
Alternatively, you can specify a directory.

Replace **USERNAME** with your username on the remote server.

Replace **SERVER-IP** with the IP address of the remote server.

Replace **REMOTE-PATH** with the directory into which you want to copy files.

In the below example, `rsync` was used to copy the local directory
`rsync_example_dir`, containing a single empty file named `EXAMPLE_FILE`, into
the home directory of the user `ubuntu` on a remote server with the IP address
`146.235.208.193`.

```
$ rsync -a --progress rsync_example_dir ubuntu@146.235.208.193:~
sending incremental file list
rsync_example_dir/
rsync_example_dir/EXAMPLE_FILE
              0 100%    0.00kB/s    0:00:00 (xfr#1, to-chk=0/2)
```

## Copy files directly between remote servers

{{% alert title="Note" color="info" %}}
To copy files directly between remote servers using `rsync`, you must use
public key (rather than password) authentication for SSH with an SSH agent.

You can add your private key to the SSH agent by running:

```bash
ssh-add SSH-PRIVATE-KEY
```

Replace **SSH-PRIVATE-KEY** with the path to your SSH private key, for
example, `~/.ssh/id_ed25519`.

You can confirm your key was added to the SSH agent by running:

```bash
ssh-add -L
```

Your public key will be listed in the output.
{{% /alert %}}

To copy files directly between remote servers using `rsync`, first SSH into
the server you want to copy files _from_ by running:

```bash
ssh -A USERNAME-1@SERVER-IP-1
```

Replace **SERVER-IP-1** with the IP address of the server you want to copy
files from, referred to below as _Server 1_.

Replace **USERNAME-1** with your username on _Server 1_.

{{% alert title="Tip" color="success" %}}
It's recommended to run the `rsync` command, below, in a `tmux` or `screen`
session. This way, you can log out of _Server 1_ and the `rsync` command will
continue to run.
{{% /alert %}}

Then, on _Server 1_, run:

```bash
rsync -av --info=progress2 FILES USERNAME-2@SERVER-IP-2:REMOTE-PATH
```

Replace **SERVER-IP-2** with the IP address of the server you want to copy
files _to_, referred to below as _Server 2_.

Replace **FILES** with the files (or directory) you want to copy to _Server 2_.

Replace **USERNAME-2** with your username on _Server 2_.

Replace **SERVER-IP-2** with the IP address of _Server 2_.

Replace **REMOTE-PATH** with the directory into which you want to copy files.
