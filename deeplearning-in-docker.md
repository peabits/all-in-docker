
# Deep Learning in Docker

检测 GPU：

```bash
docker run --rm --gpus all ubuntu nvidia-smi
```

输出：

```txt
Tue Mar 19 21:34:56 2024
+-----------------------------------------------------------------------------------------+
| NVIDIA-SMI 550.60.01              Driver Version: 551.76         CUDA Version: 12.4     |
|-----------------------------------------+------------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
|                                         |                        |               MIG M. |
|=========================================+========================+======================|
|   0  NVIDIA GeForce RTX 4060 ...    On  |   00000000:01:00.0  On |                  N/A |
| N/A   35C    P5              7W /  140W |     841MiB /   8188MiB |      0%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+

+-----------------------------------------------------------------------------------------+
| Processes:                                                                              |
|  GPU   GI   CI        PID   Type   Process name                              GPU Memory |
|        ID   ID                                                               Usage      |
|=========================================================================================|
|    0   N/A  N/A     22452      C   /python3.10                                 N/A      |
+-----------------------------------------------------------------------------------------+
```

## PyTorch 

[https://hub.docker.com/r/pytorch/pytorch/tags](https://hub.docker.com/r/pytorch/pytorch/tags)

```bash
TAG="2.2.1-cuda12.1-cudnn8-runtime"

docker pull pytorch/pytorch:$TAG

docker run -itd \
           --name pytorch-$TAG \
           --gpus=all \
           pytorch/pytorch:$TAG
```

## TensorFlow

[https://hub.docker.com/r/tensorflow/tensorflow/tags](https://hub.docker.com/r/tensorflow/tensorflow/tags)

```bash
TAG="2.16.1-gpu"

docker pull tensorflow/tensorflow:$TAG

docker run -itd \
           --name tensorflow-$TAG \
           --gpus=all \
           tensorflow/tensorflow:$TAG
```