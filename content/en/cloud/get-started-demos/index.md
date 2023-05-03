---
title: "How do I get started using the Demos feature?"
type: docs
tags:
- Demos
---

The Demos feature allows you to easily share your
[Gradio](https://gradio.app/) machine learning app (demo) both publicly and
privately.

To get started using the Demos feature, you need to:

1. [Add a demo to your Lambda GPU Cloud account]({{< relref "#add-a-demo-to-your-lambda-gpu-cloud-account" >}}).
1. [Host your demo on a new instance]({{< relref "#host-your-demo-on-a-new-instance" >}}).

{{% alert title="Note" color="info" %}}
It currently isn't possible to host a demo on an existing instance.
{{% /alert %}}

{{% alert title="Note" color="info" %}}
The new instance hosting your demo can be used like any other Lambda GPU Cloud
on-demand instance. For example, you can SSH into the instance and
[open Jupyter Notebook]({{< relref "open-jupyter-notebook" >}}) on the
instance.

As with other Lambda GPU Cloud on-demand instances,
[you're billed for all of the time the instance for your demo is running]({{< relref "on-demand-instance-invoicing" >}}).
{{% /alert %}}

{{% alert title="Note" color="info" %}}
The Demos feature can be hosted on multi-GPU instance types. However, Demos
uses only one of the GPUs.
{{% /alert %}}

## Add a demo to your Lambda GPU Cloud account

1. In the left sidebar of the
   [dashboard](https://cloud.lambdalabs.com/instances), click **Demos**. Then,
   click the **Add demo** button at the top-right of the dashboard.

   The **Add a demo** dialog will appear.

   {{< imgproc add-a-demo Resize "400x" >}}{{< /imgproc >}}

1. Under **Demo Source URL**, enter the URL of the Git repository containing
   your demo's source code.

   {{% alert title="Note" color="info" %}}
   The Demos feature looks in your Git repository for a file named
   `README.md`. If the file doesn't exist, or if the file doesn't contain the
   required properties, you'll receive a **Demo misconfigured** error.

   {{< imgproc demo-misconfigured Resize "300x" >}}{{< /imgproc >}}

   The `README.md` _must_ have at the top a YAML block containing the
   following:

   ```yaml
   ---
   sdk: gradio
   sdk_version: GRADIO-VERSION
   app_file: PATH-TO-APP-FILE
   ---
   ```

   Replace **GRADIO-VERSION** with the version of Gradio your demo is built
   with, for example, `3.24.1`.

   Replace **PATH-TO-APP-FILE** with the path to your Gradio application file
   (the file containing the Gradio
   [interface code](https://gradio.app/docs/#interface)),
   relative to the root of your Git repository. For example, if your Gradio
   application file is named `app.py` and is located in the root directory of
   your Git repository, replace **PATH-TO-APP-FILE** with `app.py`.

   Properties other than `sdk`, `sdk_version`, and `app_file` are ignored by
   the Demos feature.
   {{% /alert %}}

   {{% alert title="Tip" color="success" %}}
   If you don't yet have your own demo, you can try the Demos feature using
   the
   [demos created by Lambda's Machine Learning team](https://huggingface.co/lambdalabs).
   Demos created by Lambda's Machine Learning team include:

   - [Stable Diffusion Image Variations](https://huggingface.co/spaces/lambdalabs/stable-diffusion-image-variations)
   - [Image Mixer](https://huggingface.co/spaces/lambdalabs/image-mixer-demo)
   - [Avatar text to image](https://huggingface.co/spaces/lambdalabs/text-to-avatar)
   {{% /alert %}}

1. Under **Visibility**, choose:

   - **Public** if you want to list your demo in the
     [library of public models shared by the Lambda community](https://cloud.lambdalabs.com/demos).
   - **Unlisted** if you want your demo accessible only by those who know your
     demo's URL.

1. Under **Name**, give your demo a name. If you choose to make your demo
   public, the name of your demo will appear in the Lambda library of public
   models. The name of your demo will also appear in your demo's URL.

1. (Optional) Under **Description**, enter a description for your demo.

   The description shows under the name of your demo in your library of demos.
   If your demo is public, the description also shows under the name of your
   demo in the Lambda library of public models.

   {{% alert title="Note" color="info" %}}
   You can't change the name or description of your demo once you add it.
   However, you can delete your demo then add it again.
   {{% /alert %}}

1. Click **Add demo** to save your demo to your Lambda GPU Cloud account.

## Host your demo on a new instance

1. In the [Demos dashboard](https://cloud.lambdalabs.com/edit-demos), find the
   row containing the demo you want to host, then click **Host**. Follow the
   prompts to launch a new instance.

   [Your new instance will take several minutes to launch]({{< relref "how-long-instance-launch" >}})
   and for your demo to become accessible.

   {{% alert title="Note" color="info" %}}
   The link to your demo might temporarily appear in the Instances dashboard,
   then disappear. This is expected behavior and doesn't mean your instance or
   demo is broken.

   The models used by demos are often several gigabytes in size, and can take 5
   to 15 minutes to download and load.
   {{% /alert %}}

1. Once your instance is launched and your demo is accessible, a link with
   your demo's name will appear under the **Demo** column. Click the link to
   access your demo.

   {{% alert title="Tip" color="success" %}}
   To see a gallery of all of your demos, at the top-right of the Demos
   dashboard, click the **See your demos** button.

   {{< imgproc see-your-demos Resize "300x" >}}{{< /imgproc >}}
   {{% /alert %}}

## Troubleshooting demos

If you experience trouble accessing your demo, the Demos logs can be helpful
for troubleshooting.

For example, this log shows that the demo's `README.md` file doesn't have the
required `sdk`, `sdk_version`, and `app_file` properties:

```
### BEGIN /home/demo/bootstrap.log

Cloning into '/home/demo/source'...
Traceback (most recent call last):
  File "<stdin>", line 17, in <module>
  File "<stdin>", line 15, in load
  File "pydantic/main.py", line 526, in pydantic.main.BaseModel.parse_obj
  File "pydantic/main.py", line 341, in pydantic.main.BaseModel.__init__
pydantic.error_wrappers.ValidationError: 3 validation errors for Metadata
sdk
  field required (type=value_error.missing)
sdk_version
  field required (type=value_error.missing)
app_file
  field required (type=value_error.missing)
Created symlink /etc/systemd/system/multi-user.target.wants/lambda-demos-error-server.service → /etc/systemd/system/lambda-demos-error-server.service.
Bootstrap failed: misconfigured

### END /home/demo/bootstrap.log
```

This log shows that the demo isn't a Gradio app:

```
### BEGIN /home/demo/bootstrap.log

Cloning into '/home/demo/source'...
Traceback (most recent call last):
  File "<stdin>", line 17, in <module>
  File "<stdin>", line 15, in load
  File "pydantic/main.py", line 526, in pydantic.main.BaseModel.parse_obj
  File "pydantic/main.py", line 341, in pydantic.main.BaseModel.__init__
pydantic.error_wrappers.ValidationError: 2 validation errors for Metadata
sdk
  unexpected value; permitted: 'gradio' (type=value_error.const; given=docker; permitted=('gradio',))
sdk_version
  field required (type=value_error.missing)
Created symlink /etc/systemd/system/multi-user.target.wants/lambda-demos-error-server.service → /etc/systemd/system/lambda-demos-error-server.service.
Bootstrap failed: misconfigured

### END /home/demo/bootstrap.log
```

To view the Demos log files, SSH into your instance or open a terminal in
[Jupyter Notebook]({{< relref "open-jupyter-notebook" >}}), then run:

```bash
sudo bash -c 'for f in /root/virt-sysprep-firstboot.log ~demo/bootstrap.log; do printf "### BEGIN $f\n\n"; cat $f; printf "\n### END $f\n\n"; done > demos_debug_logs.txt; printf "### BEGIN journalctl -u lambda-demos.service\n\n$(journalctl -u lambda-demos.service)\n\n### END journalctl -u lambda-demos.service" >> demos_debug_logs.txt'
```

This command will produce a file named `demos_debug_logs.txt` containing the
logs for the Demos feature. You can review the logs from within your instance
by running `less demos_debug_logs.txt`. Alternatively, you can download the
file locally to review or share.
