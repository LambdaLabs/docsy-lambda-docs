---
title: "How do I get started generating images from prompts?"
type: docs
tags:
- benchmarking
- Lambda Stack
- PyTorch
---

Lambda GPU Cloud makes it quick and easy to set up Stable Diffusion to turn
prompts into images like the ones, below.

{{< imgproc elon-musk-sd Resize "256x" >}}{{< /imgproc >}}
{{< imgproc mahatma-gandhi-sd Resize "256x" >}}{{< /imgproc >}}
{{< imgproc woman-sd Resize "256x" >}}{{< /imgproc >}}

As part of this tutorial, you'll:

1. Sign up for a Lambda GPU Cloud account.
1. Launch an on-demand instance.
1. Configure firewall rules for your account.
1. Log into your instance.
1. Install AUTOMATIC1111/stable-diffusion-webui
1. Download a prompt-to-image model directly to your instance.
1. Create a Python virtual environment.
1. Set up Stable Diffusion for continuous image generation.
1. Begin generating images from prompts.

## Sign up for a Lambda GPU Cloud account

[Sign up for a Lambda GPU Cloud account](https://cloud.lambdalabs.com/sign-up)
if you don't have one already.

You won't have to enter payment information when you sign up. However, you'll
need to enter payment information before you can launch any instances.

## Launch an on-demand instance

From the dashboard,
[launch an instance]({{< relref "cloud-dashboard/#launch-restart-and-terminate-instances" >}}).

{{% alert title="Tip" color="success" %}}
You can also
[use the Cloud API to launch an instance]({{< relref "launch-instance-api" >}}).
{{% /alert %}}

{{% alert title="Tip" color="success" %}}
For maximum performance, it's recommended that you use a multi-GPU instance
type, such as an **8x A100 (80 GB SXM4)** or **8x A100 (40 GB SXM4)**. With a
multi-GPU instance, you're able to generate images on each GPU at the same
time.
{{% /alert %}}

## Configure firewall rules for your account

It's recommended to use the
[Firewall feature]({{< relref "get-started-firewall" >}}) to restrict access
to your instance to your computer only. To do this:

1. Learn your IP address by visiting
   [What Is My IP Address](https://ifconfig.me/).

1. In the dashboard, click **Firewall**. Then, under **Inbound Rules**, click
   **Edit**.

1. In the **Edit inbound rules** dialog, click **Add rule**.

1. In the newly created rule, set **Protocol** to **TCP** and enter the
   following information:

   - **Port range**: `8080`
   - **Source**: `YOUR-IP-ADDRESS`
   - **Description**: Dream Factory

   Replace **YOUR-IP-ADDRESS** with your actual IP address.

1. Click **Update** to enable the firewall rule you just created.

## Log into your instance

For new or inexperienced Linux users, it is recommended to use Jupyter
Notebook to log into your instance.

To log into your instance using Jupyter Notebook:

1. [Open Jupyter Notebook]({{< relref "open-jupyter-notebook" >}}).
1. Under **Other**, click **Terminal**.

   {{< imgproc jupyter-terminal-button Resize "100x" >}}{{< /imgproc >}}

{{% alert title="Tip" color="success" %}}
Experienced Linux users can use SSH to log into their instance.
{{% /alert %}}

## Install stable-diffusion-webui

Once you're logged into your instance, copy and paste the following command
into your terminal:

```bash
git clone https://github.com/AUTOMATIC1111/stable-diffusion-webui.git
```

Then, press **Enter** to run the command.

This command will download
[stable-diffusion-webui](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
directly to your instance.

## Download a Stable Diffusion prompt-to-image model

Next download the
[Realistic Vision V1.3](https://civitai.com/models/4201/realistic-vision-v13)
prompt-to-image model by copy and pasting the following command into your
terminal then pressing **Enter**:

```bash
wget -O /home/ubuntu/stable-diffusion-webui/models/Stable-diffusion/realisticVisionV13.LtFu.safetensors \
https://civitai.com/api/download/models/6987
```

{{% alert title="Note" color="info" %}}
Realistic Vision V1.3 is the model used to generate the images displayed at
the beginning of this tutorial. However, you can use other models to generate
images.
{{% /alert %}}

## Install Anaconda

```bash
wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh && \
bash Anaconda3-2022.10-Linux-x86_64.sh
```

## Install and run Dream Factory

Install [Dream Factory](https://github.com/rbbrdckybk/dream-factory)

## Connect to Dream Factory and begin generating images
