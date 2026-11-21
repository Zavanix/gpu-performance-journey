# GPU Performance Journey

Learning GPU performance engineering, one measured experiment at a time.

**Background:** PhD in mechanical engineering, Statistics, Maths, FEA validation and Medical Devices Hardware/Software.
**Goal:** GPU kernel optimization and performance engineering for AI systems.

## Hardware

| | |
|---|---|
| GPU | NVIDIA Tesla T4 (Google Colab), Turing architecture |
| CUDA cores / Tensor cores | 2,560 / 320 |
| GPU memory | 16 GB GDDR6 (15 GiB visible in Colab) |
| Peak fp32 compute | 8.1 TFLOPS |
| Peak fp16 (tensor cores) | 65 TFLOPS |
| Memory bandwidth | 300 GB/s |
| Source | NVIDIA T4 datasheet |

## Roofline note

Machine balance = peak compute / memory bandwidth.
- fp32: 8,100 GFLOPS / 300 GB/s = 27 FLOPs per byte
- fp16 (tensor cores): 65,000 GFLOPS / 300 GB/s ≈ 217 FLOPs per byte

Programs doing fewer operations per byte than this are memory-bound; programs doing more can become compute-bound.
- **Week 1:** CPU and GPU matrix multiplication baselines (in progress)
