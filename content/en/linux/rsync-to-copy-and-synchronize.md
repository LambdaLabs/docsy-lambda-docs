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

Similarly, to use `rsync` to copy files between remote servers directly, you
need to be able to SSH into the remote servers.
{{% /alert %}}

## Copy files between your computer and a remote server

## From your computer to a remote server

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
