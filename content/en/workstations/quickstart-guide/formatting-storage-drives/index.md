---
title: "Formatting your storage drives"
type: docs
tags:
- hardware
- storage
weight: 60
---

If you purchased storage drives with your Vector, that is, drives in addition
to your boot drive, you need to format them before you can use them.

To format your storage drives:

1. Press the
   <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-windows" viewBox="0 0 16 16">
     <path d="M6.555 1.375 0 2.237v5.45h6.555V1.375zM0 13.795l6.555.933V8.313H0v5.482zm7.278-5.4.026 6.378L16 16V8.395H7.278zM16 0 7.33 1.244v6.414H16V0z"/>
   </svg> key on your keyboard to open the **Activities** overview. Then, type `disks`.

   {{% alert title="Tip" color="success" %}}
   The
   <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-windows" viewBox="0 0 16 16">
     <path d="M6.555 1.375 0 2.237v5.45h6.555V1.375zM0 13.795l6.555.933V8.313H0v5.482zm7.278-5.4.026 6.378L16 16V8.395H7.278zM16 0 7.33 1.244v6.414H16V0z"/>
   </svg> key on your keyboard is located between the **Ctrl** and **Alt** keys.

   <img src="/lib/images/super-key.svg" width="203" height="108" alt="">
   {{% /alert %}}

1. Click **Disks** to open GNOME Disks.

1. In the left sidebar, click your storage drive.

   Information about the drive, including a graph showing how the drive is
   currently partitioned and formatted, will show in the right pane.

   Since the drive hasn't yet been partitioned and formatted, only a single
   unformatted partition will show as **Unknown**.

   {{< imgproc unformatted-partition Resize "700x">}}{{< /imgproc >}}

1. In the graph, click the unformatted partition, then click
   <img src="/lib/images/settings-symbolic.svg" alt="">. Choose **Format
   Partition**.

1. In the **Format Volume** dialog that opens:

   - In the **Volume Name** field, enter a name to identify your storage
     drive.

   - Leave **Erase** toggled off.

   - For **Type**, choose **Internal disk for use with Linux systems only
     (Ext4)**.

     (Optional) Select **Password protect volume (LUKS)** to encrypt your
     storage drive with a password.

   {{< imgproc format-volume Resize "600x">}}{{< /imgproc >}}

1. Click **Next** in the dialog title bar. You'll be warned that all data on
   the drive will be erased.

   {{< imgproc warning-all-data-will-be-lost Resize "600x">}}{{< /imgproc >}}

   Click **Format** in the title bar. When prompted, enter your user password,
   then click **Authenticate**.

   {{< imgproc authentication-required Resize "400x">}}{{< /imgproc >}}

Your storage drive is now formatted and ready for use.

{{< imgproc formatted-partition Resize "700x">}}{{< /imgproc >}}
