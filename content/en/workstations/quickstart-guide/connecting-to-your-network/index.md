---
title: "Connecting to your network"
type: docs
tags:
- hardware
- network
---

You can connect to your network using either Ethernet or Wi-Fi (if you
purchased your Vector with a Wi-Fi adapter).

{{% alert title="Tip" color="success" %}}
It's recommended to connect to your network using Ethernet rather than Wi-Fi.
Ethernet is more reliable and provides better performance than Wi-Fi.
{{% /alert %}}

## Connecting using Ethernet

<!-- TODO: Link to unboxing and set-up. -->
<!-- TODO: Use correct image. -->
If you connect to your network using Ethernet, your network settings will
likely automatically be configured using DHCP.

You should see <img src="nm-device-wired-symbolic.svg" alt=""> at the
top-right of your screen, which indicates you're connected to your network.

## Connecting using Wi-Fi

If you purchased your Vector with a Wi-Fi adapter, you can use the **Wi-Fi**
panel in **GNOME Settings** to connect to your Wi-Fi network.

To open the **Wi-Fi** panel in **GNOME Settings**:

<!-- TODO: Replace svg element, below, with something less ugly. -->
1. Press the
   <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-windows" viewBox="0 0 16 16">
     <path d="M6.555 1.375 0 2.237v5.45h6.555V1.375zM0 13.795l6.555.933V8.313H0v5.482zm7.278-5.4.026 6.378L16 16V8.395H7.278zM16 0 7.33 1.244v6.414H16V0z"/>
   </svg> key on your keyboard to open the **Activities** overview. Then, type `wifi`.
1. Click **Wi-Fi** to open the **Wi-Fi** panel in **GNOME Settings**.

{{% alert title="Tip" color="success" %}}
The
<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-windows" viewBox="0 0 16 16">
  <path d="M6.555 1.375 0 2.237v5.45h6.555V1.375zM0 13.795l6.555.933V8.313H0v5.482zm7.278-5.4.026 6.378L16 16V8.395H7.278zM16 0 7.33 1.244v6.414H16V0z"/>
</svg> key on your keyboard is located between the **Ctrl** and **Alt** keys.

<img src="super-key.svg" width="203" height="108" alt="">
{{% /alert %}}

Your network settings will likely automatically be configured using DHCP once
you successfully connect to your Wi-Fi network.

You should see <img src="nm-signal-100-symbolic.svg" alt=""> at the top-right
of your screen once you're connected to your Wi-Fi network.

{{% alert title="Note" color="info" %}}
Some networks require you to log in before you can access the network. If
you're asked to log into your network, you need to contact your network
administrator for the required credentials.
{{% /alert %}}

## Configuring a static IP address

DHCP, or _Dynamic Host Configuration Protocol_, assigns an IP address that
might change from time to time. If your IP address changes, it might be
difficult to remotely access your Vector.

If you plan to remotely access your Vector, you should ask your network
administrator to configure a static DHCP lease so that your IP address doesn't
change.

As an alternative to configuring a static DHCP lease, your network
administrator might provide you with settings that you can use to manually
configure a static IP address.

To manually configure a static IP address:

1. Press the
   <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-windows" viewBox="0 0 16 16">
     <path d="M6.555 1.375 0 2.237v5.45h6.555V1.375zM0 13.795l6.555.933V8.313H0v5.482zm7.278-5.4.026 6.378L16 16V8.395H7.278zM16 0 7.33 1.244v6.414H16V0z"/>
   </svg> key on your keyboard to open the **Activities** overview. Then, type `network`.
1. Click **Network** to open the **Network** panel in **GNOME Settings**.
1. If you're connected to your network using Ethernet, click the
   <img src="settings-symbolic.svg" alt=""> next to your wired connection.

   If you're connected to your network using Wi-Fi, click the
   <img src="settings-symbolic.svg" alt=""> next to your Wi-Fi connection.
1. Click **IPv4**. For **IPv4 Method**, choose **Manual**.

   Fill in the fields with the network settings provided to you by your
   network administrator.

   Next to **DNS**, switch off **Automatic**. In the field, enter the DNS
   server IP addresses provided by your network administrator, separated by a
   `,`.

   Next to **Routes**, switch off **Automatic**.

   Fill in the fields with the network settings provided to you by your
   network administrator.
1. Click **Apply** to enable your changes.
