---
title: "How do I create a Python virtual environment?"
type: docs
---

1. Create a Python virtual environment using the `venv` module by running:

   ```bash
   python -m venv --system-site-packages NAME
   ```

   Replace **NAME** with the name you want to give to your virtual
   environment.

   {{% alert title="Note" color="info" %}}
   The command, above, creates a virtual environment that has access to Lambda
   Stack packages and packages installed from Ubuntu repositories.

   To create a virtual environment that _doesn't_ have access to Lambda Stack
   and Ubuntu packages, omit the `--system-site-packages` option.
   {{% /alert %}}

1. Activate the virtual environment by running:

   ```bash
   . NAME/bin/activate
   ```

   Replace **NAME** with the name you gave your virtual environment in the
   previous step.

   Python packages you install in your virtual environment are isolated from
   the base environment and other virtual environments.

{{% alert title="Note" color="info" %}}
Locally installed packages can conflict with packages installed in virtual
environments. For this reason, it's recommended to uninstall locally installed
packages by running:

To uninstall packages installed locally for your user only, run:

```bash
pip uninstall -y $(pip -v list | grep ${HOME}/.local | awk '{printf "%s ", $1}')
```

To uninstall packages installed locally, system-wide (for all users), run:

```bash
sudo pip uninstall -y $(pip -v list | grep /usr/local | awk '{printf "%s ", $1}')
```
{{% /alert %}}

{{% alert title="Warning" color="warning" %}}
**Don't run the above uninstall commands on Lambda GPU Cloud on-demand
instances!**

The above uninstall commands remove all locally installed packages and, on
on-demand instances, break programs including pip and JupyterLab.
{{% /alert %}}

{{% alert title="Tip" color="success" %}}
See the
[Python venv module documentation](https://docs.python.org/3/library/venv.html)
to learn more about Python virtual environments.
{{% /alert %}}
