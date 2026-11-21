# GPU Performance Journey

Learning GPU performance engineering, one measured experiment at a time.

**Background:** PhD in mechanical engineering, Statistics, Maths, FEA validation and Medical Devices Hardware/Software.
**Goal:** GPU kernel optimization and performance engineering for AI systems.

## Hardware

| | |
|---|---|
| GPU | NVIDIA Tesla T4 (Google Colab) |
| GPU memory | 15 GB |
| Peak fp32 compute | ~8 TFLOPS (verify against NVIDIA datasheet) |
| Peak fp16 (tensor cores) | ~65 TFLOPS (verify against NVIDIA datasheet) |
| Memory bandwidth | ~320 GB/s (verify against NVIDIA datasheet) |
| CPU | (fill in later) |

## Roofline note

Machine balance = peak compute / memory bandwidth = 8,000 GFLOPS / 320 GB/s ≈ 25 FLOPs per byte.
Programs doing fewer than about 25 operations per byte moved are memory-bound on this GPU;
programs doing more can become compute-bound.

## Log

- **Week 1:** CPU and GPU matrix multiplication baselines (in progress)
