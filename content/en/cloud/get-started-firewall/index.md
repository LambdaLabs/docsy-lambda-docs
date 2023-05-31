---
title: "How do I get started using the Firewall feature?"
type: docs
tags:
- network
- SSH
---

The [Firewall feature](https://cloud.lambdalabs.com/firewall) allows you to
configure firewall rules to restrict incoming traffic to your instances.

{{% alert title="Note" color="info" %}}
Firewall rules configured using the Firewall feature apply to all of your
instances outside of the Texas, USA (us-south-1) region.
{{% /alert %}}

To use the Firewall feature:

1. Click **Firewall** in the left sidebar of the dashboard to open your
   firewall settings.

   {{< imgproc firewall-settings Resize "400x" >}}{{< /imgproc >}}

   Under **General Settings**, use the toggle next to **Allow ICMP traffic
   (ping)** to allow or restrict incoming ICMP traffic to your instances.

   {{% alert title="Note" color="info" %}}
   For network diagnostic tools such as `ping` and `mtr` to be able to reach
   your instances, you need to allow incoming ICMP traffic.
   {{% /alert %}}

1. Next to **Inbound Rules**, click **Edit** to configure incoming TCP and UDP
   traffic rules.

   {{< imgproc inbound-rules Resize "800x" >}}{{< /imgproc >}}

   In the drop-down menu under **Type**, select:

   - **Custom TCP** to manually configure a rule to allow incoming TCP traffic.
   - **Custom UDP** to manually configure a rule to allow incoming UDP traffic.
   - **HTTPS** to automatically configure a rule to allow incoming HTTPS traffic.
   - **SSH** to automatically configure a rule to allow incoming SSH traffic.
   - **All TCP** to automatically configure a rule to allow all incoming TCP traffic.
   - **All UDP** to automatically configure a rule to allow all incoming UDP traffic.

   {{% alert title="Warning" color="warning" %}}
   If you don't have a rule to allow incoming traffic to port TCP/22, **you
   won't be able to access your instances using SSH**.
   {{% /alert %}}

   In the **Source** field, either:

   - Click the 🔎 to automatically enter your current IP address.
   - Enter a single IP address, for example, `203.0.113.1`.
   - Enter an IP address range in CIDR notation, for example,
     `203.0.113.0/24`.

   To allow incoming traffic from any source, enter `0.0.0.0/0`.

   If you choose **Custom TCP** or **Custom UDP**, enter a **Port range**.

   **Port range** can be:

   - A single port, for example, `8080`.
   - A range of ports, for example, `8080-8081`.

1. (Optional) Enter a **Description** for the rule.

1. (Optional) Click **Add rule** to add additional rules.

1. (Optional) Click the <span style="color:red;font-weight:bold">x</span> next
   to any rule you want to delete.

1. Click **Update** to apply your changes.
