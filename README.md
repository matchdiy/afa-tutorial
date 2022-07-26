# AI Software Stack Tutorial

This is an introduction to AI heterogeneous software stacks for project managers or project leaders. We will start with a simple application and step by step into the internals of the software stack. This tutorial will focus on the performance of the problems encountered in the AI application layer in the software stack, while the lower-level AI accelerator hardware SOC and ISA will be covered in one stroke.

## Tensorflow

```mermaid
gantt
title Tensorflow-XLA-MLIR
dateFormat  YYYY-MM-DD

section App
tf rn50 training : task1, 2022-07-25, 7d

section XLA
xla hlo semantic : task2, after task1, 10d
dump mnist hlo   : task3, after task1, 3d
hlo graph        : task4, after task3, 7d

section Operator
xla hlo semantic  : task6, after task2, 7d

section MLIR
MLIR Toy Tutorial : task5, after task4, 7d

```

Task:

* 安装 Anaconda + Tensorflow115-gpu。
  * RTX3060+Ubuntu22.04+Anaconda+TensorFlow 1.15+cuda11.7
  * [参考链接](https://www.pugetsystems.com/labs/hpc/How-To-Install-TensorFlow-1-15-for-NVIDIA-RTX30-GPUs-without-docker-or-CUDA-install-2005/)
* 使用Tensorflow构建RN50模型，并且进行训练。
  * 阅读模型源码，了解每一步的计算
  * GPU开profiler （Nsight）生成timeline ，观察各计算的性能
* 将模型加载到XLA-CPU或者XLA-GPU上，并且dump xla hlo graph
* 学习 [XLA算子语义](https://www.tensorflow.org/xla/operation_semantics)
* 理解静态模型

Task:

* 了解MLIR

## TVM

```mermaid
gantt
title TVM (Option)
dateFormat  YYYY-MM-DD

section App
TODO      :a1, 2022-07-25, 7d

section IRModule
TODO      :a1, 2022-07-25, 7d

section AutoSchedule
TODO      :a1, 2022-07-25, 7d

section AutoTVM
TODO      :a1, 2022-07-25, 7d
```
