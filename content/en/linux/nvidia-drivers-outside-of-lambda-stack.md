---
title: "Can I install NVIDIA drivers outside of Lambda Stack?"
type: docs
tags:
- Ubuntu
- NVIDIA
- Lambda Stack
---

You can install NVIDIA drivers outside of Lambda Stack by running the
following commands:

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2004/x86_64/cuda-keyring_1.0-1_all.deb && \
sudo dpkg -i cuda-keyring_1.0-1_all.deb && \
sudo apt update && \
sudo apt -y install nvidia-headless-525 nvidia-utils-525 nvidia-fabricmanager-525
```
