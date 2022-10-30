---
title: "Why can't my program find the NVIDIA cuDNN library?"
type: docs
---

Unfortunately, the
[NVIDIA cuDNN license](https://docs.nvidia.com/deeplearning/cudnn/sla/index.html)
limits how cuDNN can be used on our instances.

On our instances, cuDNN can only be used by the PyTorch framework and
TensorFlow library installed as part of
[Lambda Stack](https://lambdalabs.com/lambda-stack-deep-learning-software).

Other software, including PyTorch and TensorFlow installed outside of Lambda
Stack, won't be able to find and use the cuDNN library installed on our
instances.
