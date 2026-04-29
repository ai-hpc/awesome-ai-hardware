# Awesome AI Hardware [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> AI accelerators, edge inference devices, compilers, runtimes, benchmarks, and research for building and evaluating machine-learning systems.

## Contents

- [Hardware Platforms](#hardware-platforms)
- [Edge and Embedded Hardware](#edge-and-embedded-hardware)
- [Silicon and Product Families](#silicon-and-product-families)
- [Compilers and Runtimes](#compilers-and-runtimes)
- [Benchmarking and Profiling](#benchmarking-and-profiling)
- [Open-Source Deployment Projects](#open-source-deployment-projects)
- [Mobile and AI PC Inference](#mobile-and-ai-pc-inference)
- [Research Papers](#research-papers)
- [Books and Courses](#books-and-courses)
- [Community](#community)

## Hardware Platforms

- [NVIDIA CUDA](https://developer.nvidia.com/cuda-toolkit) - Parallel programming platform for NVIDIA GPUs and accelerators.
- [AMD ROCm](https://rocm.docs.amd.com/) - Open GPU compute stack for AMD accelerators.
- [Intel oneAPI](https://www.intel.com/content/www/us/en/developer/tools/oneapi/overview.html) - Cross-architecture programming model for CPUs, GPUs, FPGAs, and accelerators.
- [Google TPU](https://cloud.google.com/tpu/docs/intro-to-tpu) - Tensor Processing Units for training and serving large machine-learning workloads.
- [Cerebras WSE](https://www.cerebras.net/technology/) - Wafer-scale accelerator architecture for dense neural network compute.
- [Groq LPU](https://groq.com/technology/) - Inference processor architecture designed around deterministic token generation.
- [Tenstorrent](https://tenstorrent.com/) - RISC-V based AI processor company with open software tools and developer boards.
- [SambaNova](https://sambanova.ai/) - Reconfigurable dataflow systems for enterprise AI training and inference.
- [Etched Sohu](https://www.etched.com/) - Transformer-focused inference ASIC for high-throughput language model serving.

## Edge and Embedded Hardware

- [NVIDIA Jetson](https://developer.nvidia.com/embedded/jetson) - Edge AI modules for robotics, vision systems, industrial automation, and local inference.
- [Qualcomm AI Engine Direct SDK](https://www.qualcomm.com/developer/software/qualcomm-ai-engine-direct-sdk) - Low-level access to Qualcomm Hexagon, CPU, and GPU inference paths.
- [Hailo-8](https://hailo.ai/products/ai-accelerators/hailo-8-ai-accelerator/) - M.2 and mini-PCIe accelerator family for low-power computer vision inference.
- [Google Coral](https://coral.ai/products/) - Edge TPU modules and boards for quantized TensorFlow Lite workloads.
- [Luxonis OAK-D](https://shop.luxonis.com/products/oak-d) - Depth camera with on-device neural inference through the DepthAI stack.
- [Kneron KL720](https://www.kneron.com/products/kl720) - Low-power neural processing unit for USB modules and embedded vision products.
- [Raspberry Pi AI Kit](https://www.raspberrypi.com/products/ai-kit/) - Raspberry Pi 5 M.2 accelerator kit built around the Hailo inference processor.
- [AMD Versal AI Edge](https://www.amd.com/en/products/adaptive-socs-and-fpgas/versal/ai-edge.html) - Adaptive SoC family combining programmable logic, CPU cores, and AI Engines.
- [STMicroelectronics STM32N6](https://www.st.com/en/microcontrollers-microprocessors/stm32n6-series.html) - Microcontroller series with an integrated neural acceleration block for edge AI.
- [Espressif ESP32-P4](https://www.espressif.com/en/products/socs/esp32-p4) - Application processor for vision, display, and AI-enabled embedded products.

## Silicon and Product Families

- [Apple Core ML](https://developer.apple.com/documentation/coreml) - Model deployment framework for Apple Neural Engine, GPU, and CPU execution.
- [Qualcomm Snapdragon X Series](https://www.qualcomm.com/products/mobile-compute) - Laptop-class Arm processors with integrated Hexagon NPU acceleration.
- [Intel Core Ultra](https://www.intel.com/content/www/us/en/products/details/processors/core-ultra.html) - AI PC processor family with integrated Intel AI Boost NPU blocks.
- [AMD Ryzen AI](https://www.amd.com/en/products/processors/consumer/ryzen-ai.html) - Consumer processor family with XDNA neural processing units.
- [MediaTek NeuroPilot](https://www.mediatek.com/technology/artificial-intelligence) - Mobile AI platform for Dimensity and related MediaTek SoCs.
- [Samsung Exynos](https://semiconductor.samsung.com/processor/mobile-processor/) - Mobile processor family with integrated neural processing units.
- [Arm Ethos-U](https://www.arm.com/products/silicon-ip-cpu/ethos/ethos-u) - MicroNPU IP for Cortex-M and Cortex-A edge inference designs.
- [Synaptics Astra](https://www.synaptics.com/products/astra) - Edge AI processor platform for vision, audio, and multimodal embedded systems.
- [SiMa.ai MLSoC](https://www.sima.ai/products/mlsoc) - Machine-learning SoC platform aimed at industrial edge deployment.
- [Axelera Metis](https://www.axelera.ai/products/metis-ai-platform) - Edge AI platform built around the Metis accelerator architecture.

## Compilers and Runtimes

- [XLA](https://openxla.org/xla) - Accelerated Linear Algebra compiler for TensorFlow, JAX, and other ML frameworks.
- [MLIR](https://mlir.llvm.org/) - Multi-Level Intermediate Representation for reusable compiler infrastructure.
- [Triton](https://triton-lang.org/) - Python-like language and compiler for writing custom GPU kernels.
- [Apache TVM](https://tvm.apache.org/) - Open deep-learning compiler stack for CPUs, GPUs, and accelerators.
- [IREE](https://iree.dev/) - Intermediate Representation Execution Environment for deploying ML programs.
- [NVIDIA TensorRT](https://developer.nvidia.com/tensorrt) - Inference optimizer and runtime for NVIDIA GPUs and Jetson modules.
- [ONNX Runtime](https://onnxruntime.ai/) - Cross-platform inference runtime with provider backends for multiple accelerators.
- [OpenVINO](https://docs.openvino.ai/) - Intel toolkit for optimizing and deploying inference on CPUs, GPUs, and NPUs.
- [Vitis AI](https://github.com/Xilinx/Vitis-AI) - Compiler, runtime, and model zoo for AMD adaptive SoCs and Alveo cards.
- [HailoRT](https://github.com/hailo-ai/hailort) - Runtime and driver stack for Hailo AI accelerators.
- [LiteRT](https://github.com/google-ai-edge/LiteRT) - Google runtime for on-device inference across mobile and embedded targets.
- [ExecuTorch](https://github.com/pytorch/executorch) - PyTorch runtime for deploying models to phones, wearables, and embedded devices.

## Benchmarking and Profiling

- [MLPerf](https://mlcommons.org/benchmarks/) - Industry-standard benchmark suites for training, inference, storage, and edge ML systems.
- [AI-Benchmark](https://ai-benchmark.com/) - Deep-learning benchmark suite for mobile, desktop, and accelerator comparisons.
- [Geekbench AI](https://browser.geekbench.com/ai-benchmarks) - Cross-platform inference score browser with CPU, GPU, and NPU results.
- [LLMPerf](https://github.com/ray-project/llmperf) - Benchmark harness for large language model serving throughput and latency.
- [NVIDIA Nsight Systems](https://developer.nvidia.com/nsight-systems) - System-wide performance analysis tool for CPU, GPU, and operating-system timelines.
- [NVIDIA Nsight Compute](https://developer.nvidia.com/nsight-compute) - Interactive CUDA kernel profiler for occupancy, memory, and instruction analysis.
- [PyTorch Profiler](https://pytorch.org/tutorials/recipes/recipes/profiler_recipe.html) - Built-in profiler for PyTorch model execution and operator-level timing.
- [Perfetto](https://perfetto.dev/) - Production-grade tracing and profiling platform for systems performance analysis.

## Open-Source Deployment Projects

- [Jetson Containers](https://github.com/NVIDIA-AI-IOT/jetson-containers) - Containerized CUDA, PyTorch, ROS, and ML stacks for NVIDIA Jetson development.
- [Jetson Inference](https://github.com/dusty-nv/jetson-inference) - End-to-end classification, detection, pose, and segmentation examples for Jetson modules.
- [DeepStream Python Apps](https://github.com/NVIDIA-AI-IOT/deepstream_python_apps) - Python bindings and examples for multi-camera DeepStream pipelines.
- [Isaac ROS Common](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common) - Docker and build infrastructure for NVIDIA Isaac ROS acceleration packages.
- [Hailo Model Zoo](https://github.com/hailo-ai/hailo_model_zoo) - Pretrained models, compilation scripts, and deployment flows for Hailo accelerators.
- [Hailo Raspberry Pi 5 Examples](https://github.com/hailo-ai/hailo-rpi5-examples) - Reference pipelines for Raspberry Pi 5 systems using Hailo AI modules.
- [Edge TPU](https://github.com/google-coral/edgetpu) - Userspace runtime, tests, and examples for Google Coral Edge TPU devices.
- [RKNN Model Zoo](https://github.com/airockchip/rknn_model_zoo) - Deployment examples and model zoo for Rockchip NPU boards.
- [Texas Instruments TIDL Tools](https://github.com/TexasInstruments/edgeai-tidl-tools) - Model conversion and deployment tools for TI deep-learning accelerators.
- [OpenVINO Notebooks](https://github.com/openvinotoolkit/openvino_notebooks) - Practical notebooks for model conversion, optimization, and inference on Intel hardware.
- [Qualcomm Linux Sample Apps](https://github.com/quic/sample-apps-for-qualcomm-linux) - Detection and classification examples for Qualcomm Linux evaluation kits.
- [Qualcomm Intelligent Development Kit](https://github.com/quic/qidk) - Android samples using the Qualcomm AI Engine and QNN stack.
- [Ryzen AI Software](https://github.com/amd/RyzenAI-SW) - AMD examples and deployment tools for XDNA and XDNA 2 NPUs.
- [OpenVINO Toolkit](https://github.com/openvinotoolkit/openvino) - Open-source runtime, model optimizer, and samples for Intel inference deployment.
- [LeRobot](https://github.com/huggingface/lerobot) - Robot learning library for imitation learning and reinforcement learning on local hardware.
- [MLCommons Tiny](https://github.com/mlcommons/tiny) - TinyML benchmark suite for keyword spotting, image classification, and anomaly detection.
- [TensorFlow Lite Micro](https://github.com/tensorflow/tflite-micro) - Microcontroller inference runtime with optimized kernels for embedded targets.
- [Edge Impulse Standalone Inferencing](https://github.com/edgeimpulse/example-standalone-inferencing) - Portable C++ inference examples generated from Edge Impulse projects.
- [ESP-WHO](https://github.com/espressif/esp-who) - Face detection, recognition, and camera AI examples for ESP32 devices.
- [ESP-DL](https://github.com/espressif/esp-dl) - Quantization and inference library for deploying neural networks on Espressif chips.
- [OpenMV](https://github.com/openmv/openmv) - MicroPython machine-vision firmware and examples for camera microcontroller boards.
- [MaixPy](https://github.com/sipeed/MaixPy) - MicroPython AI framework for Sipeed K210, K230, and related RISC-V boards.
- [Openpilot](https://github.com/commaai/openpilot) - Open-source driver assistance stack running production workloads on automotive AI hardware.
- [Autoware](https://github.com/autowarefoundation/autoware) - ROS 2 autonomous driving stack used for research and industrial vehicle development.
- [Apollo](https://github.com/ApolloAuto/apollo) - Autonomous driving platform with perception, planning, simulation, and deployment examples.

## Mobile and AI PC Inference

- [ncnn](https://github.com/Tencent/ncnn) - Mobile neural network inference framework optimized for Arm CPUs and Vulkan GPUs.
- [MNN](https://github.com/alibaba/MNN) - Lightweight mobile inference engine used in Alibaba production applications.
- [Tencent TNN](https://github.com/Tencent/TNN) - Cross-platform inference framework for Android, iOS, and embedded deployments.
- [Xiaomi MACE](https://github.com/XiaoMi/mace) - Mobile AI compute engine for heterogeneous CPU, GPU, DSP, and NPU execution.
- [llama.cpp](https://github.com/ggml-org/llama.cpp) - Portable C and C++ inference engine for quantized language models.
- [MLX](https://github.com/ml-explore/mlx) - Array framework for Apple silicon with unified-memory model execution.
- [Core ML Tools](https://github.com/apple/coremltools) - Conversion and compression tools for packaging models into Core ML format.
- [MediaPipe](https://github.com/google-ai-edge/mediapipe) - Cross-platform graph framework for on-device vision, audio, and multimodal pipelines.
- [Transformers.js](https://github.com/huggingface/transformers.js) - Browser and server-side transformer inference through WebAssembly and WebGPU.
- [Candle](https://github.com/huggingface/candle) - Minimal Rust ML framework for small binaries and local inference applications.
- [Ollama](https://github.com/ollama/ollama) - Local language model runner for CPU and GPU backends.
- [LocalAI](https://github.com/mudler/LocalAI) - Self-hosted OpenAI-compatible API server for local text, audio, and vision models.
- [Open WebUI](https://github.com/open-webui/open-webui) - Local-first chat and retrieval interface commonly paired with Ollama.

## Research Papers

- [In-Datacenter Performance Analysis of a Tensor Processing Unit](https://arxiv.org/abs/1704.04760) - Original Google TPU paper describing datacenter inference acceleration.
- [A Domain-Specific Supercomputer for Training Deep Neural Networks](https://dl.acm.org/doi/10.1145/3360307) - Google TPU v3 system paper covering large-scale training infrastructure.
- [Cerebras CS-2 and Weight Streaming](https://arxiv.org/abs/2308.03029) - Wafer-scale architecture and execution model for neural network training.
- [Roofline Model](https://dl.acm.org/doi/10.1145/1498765.1498785) - Visual performance model for reasoning about compute and memory bottlenecks.
- [FlashAttention](https://arxiv.org/abs/2205.14135) - IO-aware attention algorithm for faster and more memory-efficient transformers.
- [FlashAttention-2](https://arxiv.org/abs/2307.08691) - Improved attention parallelism and work partitioning for GPUs.
- [Ansor](https://arxiv.org/abs/2006.06762) - Auto-scheduling approach for generating high-performance tensor programs.
- [Triton Paper](https://dl.acm.org/doi/10.1145/3315508.3329973) - Intermediate language and compiler for tiled neural network computations.
- [MLIR Paper](https://ieeexplore.ieee.org/document/9370308) - Compiler infrastructure for domain-specific computation.
- [Stream-K](https://arxiv.org/abs/2301.03598) - Work-centric parallel decomposition for dense matrix multiplication.
- [Efficiently Scaling Transformer Inference](https://arxiv.org/abs/2211.05100) - Analysis of inference scaling and hardware utilization for transformer models.
- [LLM.int8()](https://arxiv.org/abs/2208.07339) - 8-bit matrix multiplication method for large language model inference.

## Books and Courses

- [Dive into Deep Learning](https://d2l.ai/) - Open textbook with runnable notebooks for modern deep-learning workloads.
- [Efficient Deep Learning](https://efficientdlbook.com/) - Practical techniques for efficient model training and inference.
- [GPU Puzzles](https://github.com/srush/GPU-Puzzles) - Puzzle-based introduction to GPU programming concepts.
- [CUDA MODE](https://github.com/cuda-mode/lectures) - Community lecture series on CUDA, GPU kernels, and accelerator programming.
- [Triton Tutorials](https://triton-lang.org/main/getting-started/tutorials/index.html) - Hands-on examples for writing custom kernels with Triton.
- [TVM Tutorial](https://tvm.apache.org/docs/tutorial/) - End-to-end introduction to model compilation with Apache TVM.
- [TPU Research Cloud](https://sites.research.google/trc/about/) - Program for researchers and learners to access Google TPU resources.

## Community

- [CUDA MODE Discord](https://discord.gg/cudamode) - Community for GPU kernel programming, profiling, and performance engineering.
- [NVIDIA Developer Forums](https://forums.developer.nvidia.com/c/accelerated-computing/cuda/206) - Official forum for CUDA development and troubleshooting.
- [MLCommons](https://mlcommons.org/) - Engineering consortium for ML benchmarks, datasets, and best practices.
- [r/MachineLearning](https://www.reddit.com/r/MachineLearning/) - Research community covering ML systems, models, and hardware trends.
- [SemiAnalysis](https://semianalysis.com/) - Technical analysis of AI chips, datacenter systems, and semiconductor supply chains.
- [tinyML Foundation](https://www.tinyml.org/) - Community for ultra-low-power machine learning on embedded devices.

## Contributing

Contributions welcome! Read the [contribution guidelines](contributing.md) first.
