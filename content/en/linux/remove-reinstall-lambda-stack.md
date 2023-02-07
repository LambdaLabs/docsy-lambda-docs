---
title: "How do I remove and reinstall Lambda Stack?"
type: docs
tags:
- Lambda Stack
aliases:
- guides/remove-reinstall-lambda-stack
---

To remove and reinstall
[Lambda Stack](https://lambdalabs.com/lambda-stack-deep-learning-software):

Uninstall (purge) the existing Lambda Stack by running:

```bash
sudo rm -f /etc/apt/sources.list.d/{graphics,nvidia,cuda}* && \
dpkg -l | \
awk '/cuda|lib(accinj64|cu(blas|dart|dnn|fft|inj|pti|rand|solver|sparse)|magma|nccl|npp|nv[^p])|nv(idia|ml)|tensor(flow|board)|torch/ { print $2 }' | \
sudo xargs -or apt -y remove --purge
```

Then, install the latest Lambda Stack by running
`wget -nv -O- https://lambdalabs.com/install-lambda-stack.sh | sh -`.
