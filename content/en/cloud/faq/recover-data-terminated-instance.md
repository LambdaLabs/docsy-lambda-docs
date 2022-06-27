---
title: "Can my data be recovered once I've terminated my instance?"
weight: 20
type: docs
---

{{% alert title="Warning" color="warning" %}}
We cannot recover your data once you've terminated your instance! Before
terminating an instance, make sure to back up all data that you want to keep.
{{% /alert %}}

If you want to save data even after you terminate your instance, create a
[persistent filesystem](https://lambdalabs.com/blog/persistent-storage-beta/).

When you create a persistent filesystem, a directory with the name of your
persistent filesystem is created in your home directory. For example, if the
name of your persistent filesystem is **PERSISTENT-FILESYSTEM**, the directory
is created at `/home/ubuntu/PERSISTENT-FILESYSTEM`. **Data not stored in this
directory is erased once you terminate your instance and cannot be
recovered.**
