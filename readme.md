# Awesome AI Hardware [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

> Curated list of AI hardware resources, accelerators, architectures, tools, and research.


## Contents

- [Hardware Platforms](#hardware-platforms)
- [Compilers & Runtimes](#compilers--runtimes)
- [Benchmarks & Profiling](#benchmarks--profiling)
- [Tutorials & Courses](#tutorials--courses)
- [Papers](#papers)
- [Books](#books)
- [Community](#community)


## Hardware Platforms

### GPUs

- [NVIDIA CUDA](https://developer.nvidia.com/cuda-toolkit) - NVIDIA's parallel computing platform and programming model.
- [AMD ROCm](https://rocm.docs.amd.com/) - Open-source GPU compute platform for AMD hardware.
- [Intel oneAPI](https://www.intel.com/content/www/us/en/developer/tools/oneapi/overview.html) - Unified programming model for CPUs, GPUs, and FPGAs.

### AI Accelerators

- [Google TPU](https://cloud.google.com/tpu/docs/intro-to-tpu) - Google's Tensor Processing Units for ML workloads.
- [Cerebras WSE](https://www.cerebras.net/) - Wafer-scale engine designed for deep learning.
- [Groq LPU](https://groq.com/) - Language Processing Units optimized for LLM inference.
- [Graphcore IPU](https://www.graphcore.ai/) - Intelligence Processing Units for AI compute.
- [SambaNova SN](https://sambanova.ai/) - Reconfigurable dataflow architecture for AI.
- [Tenstorrent](https://tenstorrent.com/) - Open-source AI hardware and software stack.
- [Etched Sohu](https://www.etched.com/) - ASIC designed specifically for transformer inference.

### Edge & Embedded

- [Apple Neural Engine](https://developer.apple.com/documentation/coreml) - On-device ML acceleration via Core ML.
- [Qualcomm AI Engine](https://www.qualcomm.com/developer/software/qualcomm-ai-engine-direct-sdk) - Mobile AI inference SDK.
- [NVIDIA Jetson](https://developer.nvidia.com/embedded/jetson) - Edge AI computing platform.
- [Hailo](https://hailo.ai/) - Dedicated AI processors for edge devices.


## Compilers & Runtimes

- [XLA](https://openxla.org/) - Accelerated Linear Algebra compiler for ML models.
- [MLIR](https://mlir.llvm.org/) - Multi-Level Intermediate Representation for compiler infrastructure.
- [Triton](https://triton-lang.org/) - Open-source GPU programming language and compiler.
- [TVM](https://tvm.apache.org/) - Open deep learning compiler stack.
- [IREE](https://iree.dev/) - Intermediate Representation Execution Environment for ML.
- [TensorRT](https://developer.nvidia.com/tensorrt) - NVIDIA's high-performance deep learning inference optimizer.
- [ONNX Runtime](https://onnxruntime.ai/) - Cross-platform ML inference and training accelerator.
- [OpenVINO](https://docs.openvino.ai/) - Intel toolkit for optimizing and deploying AI inference.


## Benchmarks & Profiling

- [MLPerf](https://mlcommons.org/benchmarks/) - Industry-standard ML performance benchmarks.
- [AI-Benchmark](https://ai-benchmark.com/) - Deep learning benchmark for mobile and desktop hardware.
- [LLM Inference Benchmarks](https://github.com/ray-project/llmperf) - Benchmarking LLM inference throughput and latency.
- [NVIDIA Nsight Systems](https://developer.nvidia.com/nsight-systems) - System-wide performance analysis tool.
- [NVIDIA Nsight Compute](https://developer.nvidia.com/nsight-compute) - Interactive kernel profiler for CUDA applications.
- [PyTorch Profiler](https://pytorch.org/tutorials/recipes/recipes/profiler_recipe.html) - Built-in profiler for PyTorch models.
- [Perfetto](https://perfetto.dev/) - Production-grade tracing and profiling platform.


## Tutorials & Courses

- [GPU Puzzles](https://github.com/srush/GPU-Puzzles) - Learn GPU programming by solving puzzles.
- [CUDA MODE](https://github.com/cuda-mode/lectures) - Community lectures on CUDA and GPU programming.
- [Triton Tutorials](https://triton-lang.org/main/getting-started/tutorials/index.html) - Writing custom GPU kernels with OpenAI Triton.
- [TVM Tutorial](https://tvm.apache.org/docs/tutorial/index.html) - End-to-end introduction to the TVM compiler stack.
- [TPU Research Cloud Colab](https://sites.research.google/trc/about/) - Access to TPUs for research and learning.


## Papers

### Architectures

- [In-Datacenter Performance Analysis of a Tensor Processing Unit](https://arxiv.org/abs/1704.04760) - Google's original TPU paper.
- [A Domain-Specific Supercomputer for Training Deep Neural Networks](https://dl.acm.org/doi/10.1145/3360307) - Google TPU v3 and the system around it.
- [Cerebras CS-2 and Weight Streaming](https://arxiv.org/abs/2308.03029) - Wafer-scale architecture for neural network training.

### Memory & Bandwidth

- [Roofline Model](https://dl.acm.org/doi/10.1145/1498765.1498785) - Visual performance model for multicore architectures.
- [FlashAttention](https://arxiv.org/abs/2205.14135) - Fast and memory-efficient attention with IO-awareness.
- [FlashAttention-2](https://arxiv.org/abs/2307.08691) - Better parallelism and work partitioning for attention.

### Compilers & Scheduling

- [Ansor: Generating High-Performance Tensor Programs for Deep Learning](https://arxiv.org/abs/2006.06762) - Auto-scheduling for TVM.
- [Triton: An Intermediate Language and Compiler for Tiled Neural Network Computations](https://dl.acm.org/doi/10.1145/3315508.3329973) - OpenAI Triton language paper.
- [MLIR: Scaling Compiler Infrastructure for Domain Specific Computation](https://ieeexplore.ieee.org/document/9370308) - MLIR compiler design.

### Inference Efficiency

- [Stream-K](https://arxiv.org/abs/2301.03598) - Work-centric parallel decomposition for dense matrix multiplication.
- [Efficiently Scaling Transformer Inference](https://arxiv.org/abs/2211.05100) - Analysis of inference scaling and hardware utilization.
- [LLM.int8()](https://arxiv.org/abs/2208.07339) - 8-bit matrix multiplication for large language models.


## Books

- [Programming Massively Parallel Processors](https://www.sciencedirect.com/book/9780323912310/programming-massively-parallel-processors) - Hands-on approach by Kirk & Hwu.
- [Efficient Deep Learning](https://efficientdlbook.com/) - Techniques for efficient training and inference.


## Community

- [CUDA MODE Discord](https://discord.gg/cudamode) - Active community for GPU kernel hackers.
- [NVIDIA Developer Forums](https://forums.developer.nvidia.com/c/accelerated-computing/cuda/206) - Official CUDA community forum.
- [MLCommons](https://mlcommons.org/) - Open engineering consortium advancing ML hardware and software.
- [r/MachineLearning](https://www.reddit.com/r/MachineLearning/) - Reddit community covering ML research and hardware.
- [Chip Design & Architecture (SemiAnalysis)](https://semianalysis.com/) - Deep dives into AI chip architecture and industry trends.


## Contributing

Contributions welcome! Read the [contribution guidelines](contributing.md) first.
