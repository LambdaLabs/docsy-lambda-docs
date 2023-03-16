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

## Install NVIDIA drivers outside of Lambda Stack, with CUDA

To install NVIDIA drivers outside of Lambda Stack, _with_ CUDA, run:

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-keyring_1.0-1_all.deb && \
sudo dpkg -i cuda-keyring_1.0-1_all.deb && \
sudo apt update && \
sudo apt -y install cuda-drivers
```

## Install NVIDIA drivers outside of Lambda Stack, without CUDA

To install NVIDIA drivers outside of Lambda Stack, _without_ CUDA, run:

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-keyring_1.0-1_all.deb && \
sudo dpkg -i cuda-keyring_1.0-1_all.deb && \
sudo apt update && \
sudo apt -y install nvidia-headless-525 nvidia-utils-525 nvidia-fabricmanager-525
```
