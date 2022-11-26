---
title: "How do I get started using the dashboard?"
type: docs
tags:
- storage
- billing
---

The [dashboard](https://cloud.lambdalabs.com/instances) makes it easy to get
started using Lambda GPU Cloud.

From the dashboard, you can:

- [Create and manage instances]({{< relref "#create-and-manage-instances" >}})
- [Create and manage persistent storage file systems]({{< relref "#create-and-manage-persistent-storage-file-systems" >}})
- [Create and manage SSH keys](#)
- [View your resource usage](#)
- [Change your account settings](#)

## Create and manage instances

### Launch instances

To launch an instance:

1. Click **Instances** in the left sidebar of the dashboard.

   {{< imgproc dashboard-sidebar Resize "200x" >}}{{< /imgproc >}}

   Then, click **Launch instance** at the top-right of the dashboard.

   {{< imgproc launch-instance-button Resize "200x" >}}{{< /imgproc >}}

1. Click the instance type that you want to launch.

   {{< imgproc launch-instance-type Resize "400x" >}}{{< /imgproc >}}

1. Click the region in which you want to launch the instance.

   {{< imgproc select-region Resize "400x" >}}{{< /imgproc >}}

1. Click the
   [persistent storage file system]({{< relref "#create-and-manage-persistent-storage-file-systems" >}})
   that you want to attach to your instance.

   If you don't want to or can't attach a persistent storage file system to
   your instance, click **Don't attach a filesystem**.

   {{< imgproc select-filesystem Resize "400x" >}}{{< /imgproc >}}

1. Select the SSH key that you want to use for your instance. Then, click
   **Launch instance**.

   {{< imgproc select-ssh-key Resize "400x" >}}{{< /imgproc >}}

   {{% alert title="Tip" color="success" %}}
   You can
   [add additional SSH keys]({{< relref "../more-than-one-ssh-key" >}}) to
   your instance once your instance has launched.
   {{% /alert %}}

1. Review the license agreements and terms of service. If you agree to them,
   click **I agree to the above** to launch your instance.

   {{< imgproc licensing-agreements Resize "400x" >}}{{< /imgproc >}}

In the dashboard, you should now see your instance listed. Once your instance
has finished booting, you'll be provided with the details needed to begin
using your instance.

{{< imgproc instance-details Resize "800x" >}}{{< /imgproc >}}

## Create and manage persistent storage file systems

### Create a persistent storage file system

To create a persistent storage file system:

1. Click **Storage** in the left sidebar of the dashboard.

   {{< imgproc dashboard-sidebar Resize "200x" >}}{{< /imgproc >}}

   Then, click **Create filesystem** at the top-right of the dashboard.

   {{< imgproc create-filesystem-button Resize "200x" >}}{{< /imgproc >}}

1. Enter a name and select a region for your file system. Then click **Create
   filesystem**.

   {{< imgproc create-filesystem.png Resize "400x" >}}{{< /imgproc >}}

You should now see your persistent storage file system listed in the
dashboard.

   {{< imgproc persistent-storage-details Resize "800x" >}}{{< /imgproc >}}
