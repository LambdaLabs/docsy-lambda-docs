---
title: "How do I upgrade Ubuntu and Lambda Stack?"
type: docs
tags:
- Ubuntu
- Lambda Stack
aliases:
- guides/upgrade-ubuntu-and-lambda-stack
---

Follow these instructions to upgrade Ubuntu and
[Lambda Stack](https://lambdalabs.com/lambda-stack-deep-learning-software) to
the latest versions.

1. Uninstall (purge) the existing Lambda Stack by running:

   ```bash
   sudo rm -f /etc/apt/sources.list.d/{graphics,nvidia,cuda}* && \
   dpkg -l | \
   awk '/cuda|lib(accinj64|cu(blas|dart|dnn|fft|inj|pti|rand|solver|sparse)|magma|nccl|npp|nv[^p])|nv(idia|ml)|tensor(flow|board)|torch/ { print $2 }' | \
   sudo xargs -or apt -y remove --purge
   ```

1. Run `sudo do-release-upgrade` to upgrade Ubuntu.

1. Install the latest Lambda Stack by running
   `wget -nv -O- https://lambdalabs.com/install-lambda-stack.sh | sh -`.

1. Run `sudo reboot` to reboot your computer.
