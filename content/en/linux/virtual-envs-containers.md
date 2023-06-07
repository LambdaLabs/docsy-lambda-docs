---
title: "How do I use virtual environments and containers?"
type: docs
tags:
- Ubuntu
---

You can use [Miniconda3](https://docs.conda.io/en/latest/miniconda.html) to
create conda virtual environments, and Docker to create containers, to install
and maintain different versions of software packages and their respective
dependencies.

## Conda virtual environments

### Download and install Miniconda3

1. Download the latest version of Miniconda3 by running:

   ```bash
   curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
   ```

   Then, install Miniconda3 by running the command:

   ```bash
   sh Miniconda3-latest-Linux-x86_64.sh
   ```

   Follow the installer prompts. Install Miniconda3 in the default location.
   Allow the installer to initialize Miniconda3.

1. If you want to create a conda virtual environment immediately after
   installing Miniconda3, you need to load the changes made to your `.bashrc`.

   You can either:

   - Exit and reopen your shell (terminal).
   - Run `source ~/.bashrc`.

   {{% alert title="Tip" color="success" %}}
   For compatibility with the
   [Python venv module](https://docs.python.org/3/library/venv.html), it's
   recommended that you disable automatic activation of the conda base
   environment by running:

   ```bash
   conda config --set auto_activate_base false
   ```
   {{% /alert %}}
