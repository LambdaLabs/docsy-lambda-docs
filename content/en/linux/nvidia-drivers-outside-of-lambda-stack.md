---
title: "Can I install NVIDIA drivers outside of Lambda Stack?"
type: docs
tags:
- Ubuntu
- NVIDIA
- Lambda Stack
---

You can install NVIDIA drivers:

- [As part of Lambda Stack]({{< relref "#install-nvidia-drivers-as-part-of-lambda-stack" >}}).
- [Outside of Lambda Stack, with CUDA]({{< relref "#install-nvidia-drivers-outside-of-lambda-stack-with-cuda" >}}).
- [Outside of Lambda Stack, without CUDA]({{< relref "#install-nvidia-drivers-outside-of-lambda-stack-without-cuda" >}}).

There are pros & cons to each option for installing NVIDIA drivers.

## Install NVIDIA drivers as part of Lambda Stack

### Pros

- Entirely non-interactive, for easy deployment.
- Installs a full suite of common machine learning libraries, at versions that
  are both kept very up-to-date and known to work well together.
- Easy to upgrade to the latest drivers and machine learning libraries with
  “sudo apt update && sudo apt upgrade”
- Tested on the specific hardware configuration you will be using.
- Brings in zero Xorg dependencies

### Cons

- Difficult to reproduce the exact same configuration in the future. If you
  want to add new instances to your cluster in 6 months, it will be a
  challenge to get the exact same versions of the Lambda Stack packages as
  you’ll get today. If that’s important to you, that could be a deal breaker.
  - You could work around this by backing up the Lambda Stack packages from
    /var/cache/apt/archives/ into a tarball, and then installing them on new
    machines with “sudo dpkg -i dir/with/packages/*.deb”. If you do this, I
    recommend installing on one instance via install-lambda-stack.sh and then
    using this tarball method for the others to confirm that you’re not
    missing any packages.

## Install NVIDIA drivers outside of Lambda Stack, with CUDA

To install NVIDIA drivers outside of Lambda Stack, _with_ CUDA, run:

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-keyring_1.0-1_all.deb && \
sudo dpkg -i cuda-keyring_1.0-1_all.deb && \
sudo apt update && \
sudo apt -y install cuda-drivers
```

### Pros

- Installs CUDA, but so does Lambda Stack

### Cons

- Doesn’t install CUDnn
- Will, like Lambda Stack, depend on the latest driver version.
  - Even if you “sudo apt install cuda-12-0” you’re going to get the latest
    driver version.
  - Also not easily reproducible.
- Brings in a few X dependencies. Doesn’t really hurt anything, but feels
  wrong.
  - Also, it’s surprising how often innocent ML packages will bring in all of
    GNOME, so it’s good to look for and be wary of accidental GUI
    dependencies. GDM on headless servers has been known to cause problems.

## Install NVIDIA drivers outside of Lambda Stack, without CUDA

To install NVIDIA drivers outside of Lambda Stack, _without_ CUDA, run:

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-keyring_1.0-1_all.deb && \
sudo dpkg -i cuda-keyring_1.0-1_all.deb && \
sudo apt update && \
sudo apt -y install nvidia-headless-525 nvidia-utils-525 nvidia-fabricmanager-525
```

### Pros

- The same commands will install the 525 versions of these packages 6 months from now.
  - With Lambda Stack, this would upgrade you to the latest version even if
    you specify 525.
- Brings in zero Xorg dependencies

### Cons

- Doesn’t install CUDA or CUDnn at all.
- Depending on how you use pip / conda this might be OK, but probably not.
- You’ll need to find some other way to get CUDA / CUDnn
