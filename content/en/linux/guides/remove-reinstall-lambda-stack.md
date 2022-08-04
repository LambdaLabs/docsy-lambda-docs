---
title: "Remove and reinstall Lambda Stack"
type: docs
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

   ```bash
   sudo apt -y update && sudo apt -y install lambda-stack-cuda
   ```

{{% alert title="Note" color="info" %}}
For [Hyperplane](https://lambdalabs.com/deep-learning/servers/hyperplane-a100)
and [Scalar](https://lambdalabs.com/products/blade), additionally run the
following commands to install the packages specific to Lambda servers:

```bash
sudo apt -y install --no-install-recommends lambda-server && \
sudo apt -y install --no-install-recommends nvidia-headless-470-server && \
sudo apt -y install --no-install-recommends nvidia-fabricmanager-470
```
{{% /alert %}}
