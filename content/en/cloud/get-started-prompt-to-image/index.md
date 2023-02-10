---
title: "How do I get started generating images from prompts?"
type: docs
tags:
- benchmarking
- Lambda Stack
- PyTorch
---

With [Lambda GPU Cloud](https://lambdalabs.com/service/gpu-cloud), you can
begin generating images from prompts without having to buy expensive GPUs and
other computer hardware.

{{< imgproc elon-musk-sd Resize "256x" >}}{{< /imgproc >}}
{{< imgproc mahatma-gandhi-sd Resize "256x" >}}{{< /imgproc >}}
{{< imgproc woman-sd Resize "256x" >}}{{< /imgproc >}}

In this tutorial, you'll learn how to set up
[AUTOMATIC1111](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
(Stable Diffusion) and
[Dream Factory](https://github.com/rbbrdckybk/dream-factory) on a Lambda GPU
Cloud on-demand instance—and start generating images right away.

## Sign up for a Lambda GPU Cloud account

[Sign up for a Lambda GPU Cloud account](https://cloud.lambdalabs.com/sign-up)
if you don't have one already.

You won't have to enter payment information when you sign up. However, you'll
need to enter payment information before you can launch any instances.

## Launch an on-demand instance

From the dashboard,
[launch an instance]({{< relref "cloud-dashboard#launch-instances" >}}).

{{% alert title="Tip" color="success" %}}
For maximum performance, it's recommended that you use a multi-GPU instance
type, such as an **8x A100 (80 GB SXM4)** or **8x A100 (40 GB SXM4)**. With a
multi-GPU instance, you're able to generate images on each GPU at the same
time.
{{% /alert %}}

## Configure firewall rules for your account

Use the
[Firewall feature]({{< relref "get-started-firewall" >}}) to allow your
computer to access Dream Factory once it's running on your instance.

1. Learn your computer's IP address by visiting
   [What Is My IP Address](https://ifconfig.me/) from your computer.

1. In the dashboard, click **Firewall**. Then, under **Inbound Rules**, click
   **Edit**.

1. In the **Edit inbound rules** dialog, click **Add rule**.

1. In the newly created rule, set **Protocol** to **TCP** and enter the
   following information:

   - **Port range**: `8080`
   - **Source**: `YOUR-IP-ADDRESS`
   - **Description**: Dream Factory

   Replace **YOUR-IP-ADDRESS** with your computer's actual IP address.

1. Click **Update** to enable the firewall rule you just created.

## Log into your instance

To log into your instance using Jupyter Notebook:

1. [Open Jupyter Notebook]({{< relref "open-jupyter-notebook" >}}).

1. Under **Other**, click **Terminal**.

   {{< imgproc jupyter-terminal-button Resize "100x" >}}{{< /imgproc >}}

You now have a terminal open that you'll use to run various commands, below.

## Install AUTOMATIC1111

Once you're logged into your instance, copy and paste the following command
into the terminal:

```bash
bash <(wget -qO- https://raw.githubusercontent.com/AUTOMATIC1111/stable-diffusion-webui/master/webui.sh)
```

Then, press **Enter** to run the command.

This command will download and install
[AUTOMATIC1111](https://github.com/AUTOMATIC1111/stable-diffusion-webui)
directly to your instance. The download and install will take a few minutes to
complete.

When the installation completes, you'll see the following message:

```
Can't run without a checkpoint. Find and place a .ckpt or .safetensors file into any of those locations. The program will exit.
```

You can safely disregard this message. In the next step of this tutorial,
you'll install a model checkpoint.

## Download a Stable Diffusion prompt-to-image model

Next, download the
[Realistic Vision V1.3](https://civitai.com/models/4201/realistic-vision-v13)
prompt-to-image model directly to your instance.

To download the model directly to your instance, copy and paste the following
command into your terminal, then press **Enter**:

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

[Anaconda](https://www.anaconda.com/) is used to create virtual environments
and manage packages. Virtual environments can be separated from each other and
manage different versions of Python and packages.

Install Anaconda by running:

```bash
wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh && \
bash Anaconda3-2022.10-Linux-x86_64.sh
```

You'll be asked to review a license agreement before you can continue. Press
**Enter** to see the license agreement. Press **Spacebar** until you reach the
end of the license agreement.

When you're asked whether or not you accept the license terms, type `yes` to
accept the license terms. Then, press **Enter**.

You'll now see:

```
Anaconda3 will now be installed into this location:
/home/ubuntu/anaconda3

  - Press ENTER to confirm the location
  - Press CTRL-C to abort the installation
  - Or specify a different location below

[/home/ubuntu/anaconda3] >>>
```

Press **Enter** to proceed with the installation.

Once the installation completes, you'll see:

```
Do you wish the installer to initialize Anaconda3
by running conda init? [yes|no]
[no] >>>
```

Type `yes`, then press **Enter**.

When the installation completes and you're back at the command prompt, copy
and paste the following command into the terminal, then press **Enter**:

```bash
source .bashrc
```

Your command prompt should now look like:

```
(base) ubuntu@INSTANCE-IP-ADDRESS:~$
```

This command prompt indicates you're in the base conda environment. In the
next step, you'll create and activate a virtual environment in which you'll
run Dream Factory.

## Create, activate, and set up a conda virtual environment

In this step, you'll create, activate, and set up a conda virtual environment
that you'll use to run
[Dream Factory](https://github.com/rbbrdckybk/dream-factory).

1. To create a conda virtual environment, copy and paste the following command
   into your terminal, then press **Enter**:

   ```bash
   conda create --name dream-factory python=3.9
   ```

   You'll see `The following NEW packages will be INSTALLED:` followed by
   a list of packages.

   Following the list of packages, you'll see `Proceed ([y]/n)?`.

   Press **Enter** to proceed with the creation of the conda virtual
   environment.

   When creation of the conda virtual environment completes, you'll be back at
   the command prompt.

1. To activate the conda virtual environment you just created, copy and paste
   the following command into your terminal, then press **Enter**:

   ```bash
   conda activate dream-factory
   ```

   The command prompt in your terminal should now look like:

   ```
   (dream-factory) ubuntu@INSTANCE-IP-ADDRESS:~$
   ```

   This command prompt indicates you're in the `dream-factory` virtual
   environment that you'll use to run Dream Factory.

1. To install packages needed to install Dream Factory, copy and paste the
   following command into your terminal, then press **Enter**:

   ```bash
   conda install -c anaconda git urllib3
   ```

   At the `Proceed ([y]/n)?` prompt, press **Enter**.

## Install, configure, and run Dream Factory

1. Copy and paste the following command into your terminal, then press
   **Enter**:

   ```bash
   git clone https://github.com/rbbrdckybk/dream-factory && \
   cd dream-factory && \
   python setup.py
   ```

   This command installs Dream Factory. Installation of Dream Factory can take
   up to 10 minutes.

   When the installation completes, you should see the following message:

   ```
   All done! - don't forget to add your automatic1111 repo location to config.txt!
   ```

1. In the left sidebar of Jupyter Notebook, double-click the **dream-factory**
   folder to open the folder. Then, double-click the **config.txt** file to
   open the file.

   {{< imgproc open-config-txt Resize "250x" >}}{{< /imgproc >}}

   Change line 7 so it reads:

   ```
   SD_LOCATION = /home/ubuntu/stable-diffusion-webui
   ```

   This change tells Dream Factory where to find the stable-diffusion-webui
   you installed at the beginning of this tutorial.

   Change line 46 so it reads:

   ```
   WEBSERVER_NETWORK_ACCESSIBLE = yes
   ```

   This change tells Dream Factory to allow connections over the Internet,
   such as from your computer.

   Close the tab and click **Save** to save your changes.

   {{< imgproc close-config-txt Resize "200x" >}}{{< /imgproc >}}

1. To run Dream Factory, copy and paste the following command into the
   terminal, then press **Enter**.

   ```bash
   python dream-factory.py
   ```

   You'll be able to access Dream Factory from your web browser once you see
   the following message:

   ```
   [controller] >>> starting webserver (http://localhost:8080/) as a background process...
   ```

## Access Dream Factory from your web browser

In your web browser, go to `http://INSTANCE-IP-ADDRESS:8080`.

Replace **INSTANCE-IP-ADDRESS** with the actual IP address of your instance.

{{% alert title="Tip" color="success" %}}
You can find your instance's IP address in the
[GPU instances dashboard](https://cloud.lambdalabs.com/instances). Click the
IP address to copy it to your clipboard.
{{% /alert %}}

You'll be taken to the Dream Factory status monitor, where you can see the
activity of each of your instance's GPUs.

{{< imgproc multi-gpu-image-generation Resize "800x" >}}{{< /imgproc >}}

{{% alert title="Note" color="info" %}}
The screenshot, above, shows Dream Factory running on all 8 GPUs of an **8x
A100 (40 GB SXM4)** instance.
{{% /alert %}}

To begin generating images from example prompts:

1. Click **Control Panel**.
1. Under **Prompt File**, in the **Choose a prompt file** drop-down menu,
   choose either **example-random** or **example-standard**.

Dream Factory will begin continuously generating images, which you can view by
clicking **Gallery** in the top navigation bar.

To learn how to create your own prompt files,
[read Dream Factory's usage documentation](https://github.com/rbbrdckybk/dream-factory#usage).

If you have questions about this tutorial, post them in the
[Lambda community forum](https://deeptalk.lambdalabs.com/).

{{% alert title="Warning" color="warning" %}}
Don't forget to
[terminate your instance]({{< relref "cloud-dashboard#terminate-instances" >}})
when you're done using it!

[You're billed for all time your instance is running]({{< relref "on-demand-instance-invoicing" >}}).
{{% /alert %}}
