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

- [Launch and manage instances]({{< relref "#create-and-manage-instances" >}})
- [Create and manage persistent storage file systems]({{< relref "#create-and-manage-persistent-storage-file-systems" >}})
- [Add, generate, and manage SSH keys]({{< relref "#add-generate-and-manage-ssh-keys" >}})
- [View your resource usage](#)
- [Change your account settings](#)

## Launch and manage instances

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

{{< imgproc instance-details Resize "1000x" >}}{{< /imgproc >}}

{{% alert title="Tip" color="success" %}}
You can also
[launch instances using the Cloud API]({{< relref "../launch-instance-api" >}}).
{{% /alert %}}

### Manage instances

Restart instances by clicking the checkboxes next to the instances you want to
restart. Then, click **Restart** at the top-right of the dashboard.

Terminate instances by clicking the checkboxes next to the instances you want
to terminate. Then, click **Terminate** at the top-right of the dashboard.

{{< imgproc restart-terminate Resize "200x" >}}{{< /imgproc >}}

{{% alert title="Tip" color="success" %}}
You can also
[terminate instances using the Cloud API]({{< relref "../terminate-instance-api" >}}).
{{% /alert %}}

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

## Add, generate, and manage SSH keys

### Add or generate an SSH key

To add an SSH key that you already have:

1. Click **SSH keys** in the left sidebar of the dashboard.

   {{< imgproc dashboard-sidebar Resize "200x" >}}{{< /imgproc >}}

   Then, click **Add SSH key** at the top-right of the dashboard.

1. In the text input box, paste your public SSH key. Enter a name for your
   key, then click **Add SSH key**.

To generate a new SSH key:

1. Instead of pasting your public SSH key as instructed, above, click
   **Generate a new SSH key**. Type in a name for your key, then click
   **Create**.

   {{< imgproc generate-new-ssh-key Resize "400x" >}}{{< /imgproc >}}

   The private key for your new SSH key will automatically download.

{{% alert title="Tip" color="success" %}}
You can also
[use the Cloud API to add and generate SSH keys]({{< relref "../api-add-ssh-key" >}}).
{{% /alert %}}
