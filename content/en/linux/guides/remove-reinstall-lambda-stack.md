---
title: "Remove and reinstall Lambda Stack"
type: docs
tags:
- Lambda Stack
---

To remove and reinstall
[Lambda Stack](https://lambdalabs.com/lambda-stack-deep-learning-software):

1. Uninstall (purge) the existing Lambda Stack by running:

   ```bash
   sudo rm -f /etc/apt/sources.list.d/{graphics,nvidia,cuda}* && \
   dpkg -l | \
   awk '/cuda|lib(accinj64|cu(blas|dart|dnn|fft|inj|pti|rand|solver|sparse)|magma|nccl|npp|nv[^p])|nv(idia|ml)|tensor(flow|board)|torch/ { print $2 }' | \
   sudo xargs -or apt -y remove --purge
   ```

1. Install the latest Lambda Stack by running:

   - If you're installing on a
     [Vector](https://lambdalabs.com/gpu-workstations/vector) or
     [Tensorbook](https://lambdalabs.com/deep-learning/laptops/tensorbook):

     ```bash
     sudo apt -y update && sudo apt -y install lambda-stack-cuda
     ```

   - If you're installing on a
     [Hyperplane](https://lambdalabs.com/deep-learning/servers/hyperplane-a100)
     or [Scalar](https://lambdalabs.com/products/blade):

     ```bash
     sudo apt -y update && \
     sudo apt -y install --no-install-recommends lambda-server && \
     sudo apt -y install --no-install-recommends nvidia-headless-470-server && \
     sudo apt -y install --no-install-recommends nvidia-fabricmanager-470 && \
     sudo apt -y install lambda-stack-cuda
     ```
