---
title: "How do I create and run a Docker container?"
type: docs
tags:
- Docker
- NVIDIA
- TensorFlow
---

To create and run a Docker container:

1. Install Docker and
   [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/overview.html)
   by running:

   ```bash
   sudo apt -y update && sudo apt -y install docker.io nvidia-container-toolkit && \
   sudo systemctl daemon-reload && \
   sudo systemctl restart docker
   ```

1. Add your user to the `docker` group by running:

   ```bash
   sudo adduser "$(id -un)" docker
   ```

   Then, exit and reopen a shell (terminal) so that your user can create and
   run Docker containers.

1. Locate the Docker image for the container you want to create. For example,
   the [NVIDIA NGC Catalog](https://catalog.ngc.nvidia.com) has
   [images for creating TensorFlow NGC containers](https://catalog.ngc.nvidia.com/orgs/nvidia/containers/tensorflow/tags).

1. Create a container from the Docker image, and run a command in the
   container, by running:

   ```bash
   docker run --gpus all -it --rm IMAGE COMMAND
   ```

   Replace **IMAGE** with the URL to the image for the container you want to
   create.

   Replace **COMMAND** with the command you want to run in the container.

   For example, to create a
   [TensorFlow NGC container](https://catalog.ngc.nvidia.com/orgs/nvidia/containers/tensorflow)
   and run a command to get the container's TensorFlow build information, run:

   ```bash
   docker run --gpus all -it --rm nvcr.io/nvidia/tensorflow:23.05-tf2-py3 python -c "import tensorflow as tf ; sys_details = tf.sysconfig.get_build_info() ; print(sys_details)"
   ```

   You should see output similar to the following:

   ```
   ================
   == TensorFlow ==
   ================
   
   NVIDIA Release 23.05-tf2 (build 59341886)
   TensorFlow Version 2.12.0
   
   Container image Copyright (c) 2023, NVIDIA CORPORATION & AFFILIATES. All rights reserved.
   Copyright 2017-2023 The TensorFlow Authors.  All rights reserved.
   
   Various files include modifications (c) NVIDIA CORPORATION & AFFILIATES.  All rights reserved.
   
   This container image and its contents are governed by the NVIDIA Deep Learning Container License.
   By pulling and using the container, you accept the terms and conditions of this license:
   https://developer.nvidia.com/ngc/nvidia-deep-learning-container-license
   
   NOTE: CUDA Forward Compatibility mode ENABLED.
     Using CUDA 12.1 driver version 530.30.02 with kernel driver version 525.85.12.
     See https://docs.nvidia.com/deploy/cuda-compatibility/ for details.
   
   NOTE: The SHMEM allocation limit is set to the default of 64MB.  This may be
      insufficient for TensorFlow.  NVIDIA recommends the use of the following flags:
      docker run --gpus all --ipc=host --ulimit memlock=-1 --ulimit stack=67108864 ...
   
   2023-06-08 17:09:50.643793: I tensorflow/core/util/port.cc:110] oneDNN custom operations are on. You may see slightly different numerical results due to floating-point round-off errors from different computation orders. To turn them off, set the environment variable `TF_ENABLE_ONEDNN_OPTS=0`.
   2023-06-08 17:09:50.680974: I tensorflow/core/platform/cpu_feature_guard.cc:183] This TensorFlow binary is optimized to use available CPU instructions in performance-critical operations.
   To enable the following instructions: SSE3 SSE4.1 SSE4.2 AVX, in other operations, rebuild TensorFlow with the appropriate compiler flags.
   OrderedDict([('cpu_compiler', '/opt/rh/devtoolset-9/root/usr/bin/gcc'), ('cuda_compute_capabilities', ['sm_52', 'sm_60', 'sm_61', 'sm_70', 'sm_75', 'sm_80', 'sm_86', 'compute_90']), ('cuda_version', '12.1'), ('cudnn_version', '8'), ('is_cuda_build', True), ('is_rocm_build', False), ('is_tensorrt_build', True)])
   ```

{{% alert title="Tip" color="success" %}}
See the [Docker documentation](https://docs.docker.com/) to learn more about
using Docker.

You can also check out the Lambda blog post:
[NVIDIA NGC Tutorial: Run A PyTorch Docker Container Using Nvidia-Container-Toolkit On Ubuntu](https://lambdalabs.com/blog/nvidia-ngc-tutorial-run-pytorch-docker-container-using-nvidia-container-toolkit-on-ubuntu).
{{% /alert %}}
