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

{{% alert title="Tip" color="success" %}}
Software outside of Lambda Stack usually looks for the cuDNN library files in
`/usr/lib/x86_64-linux-gnu`. However, on our instances, the cuDNN library
files are in `/usr/lib/python3/dist-packages/tensorflow`.

Creating symbolic links, or "symlinks," for the cuDNN library files might
allow your program to find the cuDNN library on our instances.

Run the following command to create symlinks for the cuDNN library files:

```bash
for cudnn_so in /usr/lib/python3/dist-packages/tensorflow/libcudnn*; do
  sudo ln -s "$cudnn_so" /usr/lib/x86_64-linux-gnu/
done
```
{{% /alert %}}
