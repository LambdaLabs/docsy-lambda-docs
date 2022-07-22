---
title: "Upgrade Ubuntu and Lambda Stack"
type: docs
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

1. Run `sudo do-release-upgrade`.

1. Install the latest Lambda Stack by running:

   ```bash
   sudo apt-get -y update && sudo apt-get -y install lambda-stack-cuda
   ```
