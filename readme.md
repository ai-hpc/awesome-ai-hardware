# Awesome AI Hardware [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

> Curated list of AI hardware resources, accelerators, architectures, tools, and research.


## Contents

- [Hardware Platforms](#hardware-platforms)
  - [GPUs](#gpus)
  - [AI Accelerators](#ai-accelerators)
  - [Edge & Embedded](#edge--embedded)
- [Edge AI Chip Landscape (2026)](#edge-ai-chip-landscape-2026)
  - [Consumer & mobile](#consumer--mobile)
  - [Small boards & maker / prototyping](#small-boards--maker--prototyping)
  - [Automotive & transportation](#automotive--transportation)
  - [Industrial & robotics](#industrial--robotics)
  - [Ultra-low-power NPUs & IoT ASICs](#ultra-low-power-npus--iot-asics)
  - [Open-source projects by platform](#open-source-projects-by-platform)
    - [Consumer and laptop](#consumer-and-laptop)
    - [Small boards and maker kits](#small-boards-and-maker-kits)
    - [Automotive and ADAS (public SDK cousins)](#automotive-and-adas-public-sdk-cousins)
    - [Industrial and robotics modules](#industrial-and-robotics-modules)
    - [Ultra-low-power NPUs and IoT](#ultra-low-power-npus-and-iot)
  - [Technical trends (2026)](#technical-trends-2026)
- [Compilers & Runtimes](#compilers--runtimes)
- [Benchmarks & Profiling](#benchmarks--profiling)
- [Tutorials & Courses](#tutorials--courses)
- [Papers](#papers)
  - [Architectures](#architectures)
  - [Memory & Bandwidth](#memory--bandwidth)
  - [Compilers & Scheduling](#compilers--scheduling)
  - [Inference Efficiency](#inference-efficiency)
- [Books](#books)
- [Community](#community)
- [Contributing](#contributing)


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

- [NVIDIA Jetson](https://developer.nvidia.com/embedded/jetson) - Edge AI computing platform.
- [Qualcomm AI Engine](https://www.qualcomm.com/developer/software/qualcomm-ai-engine-direct-sdk) - Mobile AI inference SDK.
- [Hailo](https://hailo.ai/) - Dedicated AI processors for edge devices.
- [Apple Neural Engine](https://developer.apple.com/documentation/coreml) - On-device ML acceleration via Core ML.


## Edge AI Chip Landscape (2026)

Representative edge AI silicon, ordered by combined reach and visibility (not strict market share).

> Vendor "AI TOPS" usually means INT8-class MAC throughput under ideal kernels, not end-to-end latency; some parts quote FP4 or FP8 throughput separately. Check precision and workload. Power figures are typically whole SoC or module TDP.

### Consumer & mobile

Lines are sorted by **vendor AI TOPS** (claimed or assumed; see snapshot table and blockquote)—**highest first**. At the same **TOPS** class, **Snapdragon 8 Elite Gen 5** is listed before **Dimensity 9500**, and **9400+** before **9400**. *AI-Benchmark* figures are SoC-level from the [mobile SoC ranking](https://ai-benchmark.com/ranking_processors.html) (composite AI score and subscores). **Reported notes** are short, paraphrased vendor and third-party narrative (AnTuTu-class synthetics, review roundups, Qualcomm/MediaTek positioning)—not additional benchmark runs. *Geekbench AI* [GPU chart](https://browser.geekbench.com/ai-benchmarks) half and quantized columns are from the same row as SP on each reference device; bullet order no longer follows Geekbench **single-precision** rank. The two suites use different scales; do not rank across them. A **vendor AI TOPS** table after the bullets mirrors this sort order (same caveats as the blockquote above—not comparable to *AI-Benchmark* or *Geekbench AI* numbers).

**Phone and tablet SoCs (vendor AI TOPS, high → low; one device per chip; *AI-Benchmark* then *Geekbench AI GPU*)**

- [Apple A19 Pro](https://www.apple.com/iphone-air/) — **16-core Neural Engine** aimed at intensive on-device AI; Apple-facing materials cite **~160 TOPS** (TOPS definitions and measurement scope vary—see vendor TOPS blockquote above). **iPhone 17 Pro** and **iPhone 17 Pro Max** are primary phone carriers (**iPhone Air** also uses an A19 Pro-class design). Reported notes: Strong perceived single-thread responsiveness; stack tuned for Apple Intelligence and first-party ML. *AI-Benchmark: AI **7005**, INT8 CNN **290**, INT8 transformer **2373**, FP16 CNN **906**, FP16 transformer **2525**; table year **2025**. Geekbench AI GPU: SP **9046**, half **16736**, quantized **17429**.* **iPhone 17 Pro**.
- [Snapdragon 8 Elite Gen 5](https://www.qualcomm.com/smartphones/products/8-series/snapdragon-8-elite-gen-5) — **Hexagon DSP / HTP Gen 5**. Reported notes: **2025–2026** flagship-cycle coverage often places it ahead of peers in *AI-Benchmark*-style testing, with **~100 TOPS** class figures quoted in some summaries (not the same units as the composite **AI score** below). Qualcomm also stresses efficiency and on-device LLM **/** generative AI. *AI-Benchmark: AI **16226**, INT8 CNN **1531**, INT8 transformer **9004**, FP16 CNN **1553**, FP16 transformer **3559**; table year **2025**. Geekbench AI GPU: SP **2989**, half **4665**, quantized **3958**.* **Honor Magic8 Pro**.
- [MediaTek Dimensity 9500](https://www.mediatek.com/dimensity-9500) — **9th Gen NPU 990**; MediaTek markets **~100 TOPS** and **~2×** prior-generation AI throughput for generative **/** agentic on-device workloads (vendor-defined). Reported notes: Often leads broad synthetics (e.g. AnTuTu-class totals); sustained AI can depend on phone power limits. *AI-Benchmark: AI **17628**, INT8 CNN **1574**, INT8 transformer **8555**, FP16 CNN **2141**, FP16 transformer **4219**; table year **2025**. Geekbench AI GPU: SP **1495**, half **2040**, quantized **1707**.* **Oppo Find X9 Pro**.
- [Snapdragon 8 Elite](https://www.qualcomm.com/smartphones/products/8-series/snapdragon-8-elite-mobile-platform) — **Hexagon DSP / HTP Gen 4**; Qualcomm cites **~45%** faster Hexagon NPU than **8 Gen 3** (**~73 TOPS** **AI Engine** on **8 Gen 3**). This list assumes **~90 TOPS** as a prior-gen **AI Engine** class figure—**below** press **/** vendor **~100 TOPS** narratives for **8 Elite Gen 5** and **above** **8 Gen 3** (assumed ordering only; see blockquote). Reported notes: Prior Elite generation; reviews often cite roughly **20–30%** class gap behind the newest Elite in heavy multi-threaded AI-style workloads. *AI-Benchmark: AI **9453**, INT8 CNN **1185**, INT8 transformer **4425**, FP16 CNN **1107**, FP16 transformer **2187**; table year **2024**. Geekbench AI GPU: SP **1844**, half **2947**, quantized **2607**.* **Samsung Galaxy S25 Ultra**.
- [Snapdragon 8 Gen 3](https://www.qualcomm.com/smartphones/products/8-series/snapdragon-8-gen-3-mobile-platform) — **Hexagon DSP / HTP Gen 3**; Qualcomm **AI Engine** widely cited at **~73 TOPS** peak (heterogeneous stack—vendor-defined; see blockquote). Reported notes: Reliable prior-gen flagship baseline; third-party writeups often quote on the order of **~40%** lower AI throughput vs latest **Elite Gen 5** class (suite-dependent). *AI-Benchmark: AI **7113**, INT8 CNN **931**, INT8 transformer **3389**, FP16 CNN **792**, FP16 transformer **1668**; table year **2023**. Geekbench AI GPU: SP **1371**, half **2020**, quantized **1646**.* **OnePlus 13R**.
- [Snapdragon 8s Gen 4](https://www.qualcomm.com/smartphones/products/8-series/snapdragon-8s-gen-4-mobile-platform) — **Hexagon DSP / HTP plus Adreno GPU** in *AI-Benchmark* table; third-party spec roundups often list **~60 TOPS** (public product brief omits a **TOPS** line—treat as indicative). Reported notes: Mid-premium tier; composite *AI-Benchmark* here is far below **8 Gen 3** / Elite in this same list—compare within price class, not vs top flagships. *AI-Benchmark: AI **3713**, INT8 CNN **711**, INT8 transformer **2670**, FP16 CNN **148**, FP16 transformer **50**; table year **2025**. Geekbench AI GPU: SP **1448**, half **2297**, quantized **1924**.* **Xiaomi Poco F7**.
- [MediaTek Dimensity 9400+](https://www.mediatek.com/products/smartphones/mediatek-dimensity-9400-plus) — **8th Gen NPU 890**; MediaTek cites **~50 TOPS** theoretical AI throughput (vendor TOPS—see blockquote above). **April 2025**-era flagship 5G SoC pitched against high-end APs; marketing stresses **agentic AI** and on-device **AI video generation**, claiming **~20%** faster agentic AI vs **Dimensity 9400** via **Speculative Decoding+ (SpD+)** and the **Dimensity Agentic AI Engine (DAE)**. Other positioning: on-device **LoRA** training, **LLM** support including **DeepSeek-R1-Distill** (1.5B **/** 7B **/** 8B), **Imagiq 1090** “Gen-AI Super Zoom” **/** full-range HDR zoom stories, and **MediaTek Frame Rate Converter 2.0+** (AI frame boost **/** efficiency claims in gaming). Reported notes: Clear step from **9300**; efficiency is a common theme; broad peak-AI summaries still often sit **~15–20%** behind **Dimensity 9500** class. *AI-Benchmark: AI **8516**, INT8 CNN **861**, INT8 transformer **3888**, FP16 CNN **1085**, FP16 transformer **1977**; table year **2025**. Geekbench AI GPU: SP **1404**, half **1866**, quantized **1566**.* **Samsung Galaxy Tab S11 Ultra**.
- [MediaTek Dimensity 9400](https://www.mediatek.com/products/smartphones/mediatek-dimensity-9400) — **8th Gen NPU 890**; MediaTek cites **~50 TOPS** theoretical AI throughput (same **NPU 890** generation as **9400+**; vendor-defined). Reported notes: Balanced flagship AI; similar story to **9400+** with slightly lower clock headroom in vendor positioning. *AI-Benchmark: AI **8074**, INT8 CNN **796**, INT8 transformer **3780**, FP16 CNN **1039**, FP16 transformer **1839**; table year **2024**. Geekbench AI GPU: SP **1108**, half **1341**, quantized **1233**.* **Oppo Find X8**.
- [Google Tensor G4](https://www.androidcentral.com/phones/google-tensor-g4) — **Google Tensor TPU 2.0** (**Pixel 9** series). Vendor **/** press summaries often quote **~45 TOPS** for on-device **Gemini Nano**-class work, stressing efficiency and multimodal **/** Pixel-first features; peak-TOPS narratives often place raw throughput below **Snapdragon 8 Gen 3** **~73 TOPS**-class marketing (vendor-defined; see blockquote above—not the composite scores below). Reported notes: Camera and Assistant-class ML remain the headline story; *AI-Benchmark* totals here are not the design goal. *AI-Benchmark: AI **895**, INT8 CNN **140**, INT8 transformer **253**, FP16 CNN **202**, FP16 transformer **120**; table year **2024**. Geekbench AI GPU: SP **911**, half **1262**, quantized **1046**.* **Google Pixel 9 Pro**.
- [MediaTek Dimensity 9300+](https://www.mediatek.com/products/smartphones/mediatek-dimensity-9300-plus) — **APU 790** (higher clocks **/** NeuroPilot vs **9300**); vendor copy rarely states **TOPS** vs **NPU 890**'s **~50**—this list assumes **~39 TOPS** (~**10%** above **9300** in line with MediaTek’s AI uplift story; assumed class only; see blockquote). Reported notes: Efficient for its generation; the heaviest on-device models tend to favor newer **NPU 890** / **9th Gen** parts. *AI-Benchmark: AI **6276**, INT8 CNN **630**, INT8 transformer **3017**, FP16 CNN **843**, FP16 transformer **1291**; table year **2023**. Geekbench AI GPU: SP **1257**, half **1610**, quantized **1494**.* **Samsung Galaxy Tab S10+**.
- [MediaTek Dimensity 9300](https://www.mediatek.com/products/smartphones/mediatek-dimensity-9300) — **APU 790**; primary launch materials emphasize tokens **/** s and model size rather than **TOPS**—this list assumes **~35 TOPS** as a sub-**NPU 890** (**~50**) class placeholder (assumed only; see blockquote). Reported notes: Still-capable prior flagship tier; oldest Dimensity in this set versus **9300+** / **9400** / **9500**. *AI-Benchmark: AI **6244**, INT8 CNN **635**, INT8 transformer **3014**, FP16 CNN **847**, FP16 transformer **1282**; table year **2023**. Geekbench AI GPU: SP **1026**, half **1234**, quantized **1251**.* **Oppo Find X7**.
- [Samsung Exynos 2400](https://semiconductor.samsung.com/processor/mobile-processor/exynos-2400/) — **Integrated NPU**; Samsung cites up to **~32 TOPS** NPU throughput, **~14.7×** AI uplift vs **Exynos 2200**, and a **17K MAC** **2-GNPU + 2-SNPU** layout aimed at generative **/** on-device AI (vendor TOPS—see blockquote above). Typical positioning: real-time speech, text-to-image, vision, enhancement. **Xclipse 940 GPU** (*Geekbench AI* row uses GPU path). Reported notes: Regional **Galaxy S24** variant; in this list’s *AI-Benchmark* snapshot it still sits well below contemporary Snapdragon flagships. *AI-Benchmark: AI **652**, INT8 CNN **55**, INT8 transformer **160**, FP16 CNN **183**, FP16 transformer **64**; table year **2023**. Geekbench AI GPU: SP **1457**, half **2007**, quantized **1731**.* **Samsung Galaxy S24** (Exynos SKU).

**Vendor AI TOPS snapshot** (same chips and order as bullets; vendor **/** press where stated, **assumed** where marked—see blockquote—not *AI-Benchmark* or *Geekbench AI*):

| SoC | Typical claimed TOPS | Notes |
| --- | --- | --- |
| Apple A19 Pro | ~160 | Neural Engine |
| Snapdragon 8 Elite Gen 5 | ~100 | Press / suite-dependent summaries |
| MediaTek Dimensity 9500 | ~100 | NPU 990 |
| Snapdragon 8 Elite | ~90 | **Assumed** between **~73** (**8 Gen 3**) and **~100** (**8 Elite Gen 5**); not a Qualcomm rollup |
| Snapdragon 8 Gen 3 | ~73 | Qualcomm **AI Engine** |
| Snapdragon 8s Gen 4 | ~60 | Common in spec aggregators; Qualcomm brief omits **TOPS** |
| MediaTek Dimensity 9400+ | ~50 | NPU 890 theoretical |
| MediaTek Dimensity 9400 | ~50 | NPU 890 theoretical |
| Google Tensor G4 | ~45 | Pixel **/** Gemini Nano framing |
| MediaTek Dimensity 9300+ | ~39 | **Assumed** (~**10%** over **9300**; APU 790) |
| MediaTek Dimensity 9300 | ~35 | **Assumed** class below **NPU 890** **~50**; APU 790 |
| Samsung Exynos 2400 | ~32 | NPU |

**Laptop-class NPUs (not the phone SoC table above)**

- [Intel Core Ultra (Meteor Lake through Arrow Lake)](https://www.intel.com/content/www/us/en/products/details/processors/core-ultra.html) - Intel AI Boost NPU; compare on AI-Benchmark [desktop / deep learning](https://ai-benchmark.com/ranking_deeplearning.html) or OpenVINO workloads, not the mobile SoC list.
- [Snapdragon X Elite / X Plus](https://www.qualcomm.com/products/laptops-and-tablets/snapdragon-x-series) - 45 NPU TOPS (Qualcomm-stated for Hexagon NPU on X series). Use Windows on Snapdragon AI-Benchmark entries or vendor ONNX / QNN tests for apples-to-apples numbers.

**USB / M.2 AI accelerator (not an application processor)**

- [Coral Edge TPU (M.2 / USB / PCIe)](https://coral.ai/products/) - Google add-in, ~4 INT8 TOPS peak (module docs); see [IoT ranking](https://ai-benchmark.com/ranking_IoT.html) on AI-Benchmark for class devices, not mobile SoC table.

Vendor TOPS, *AI-Benchmark*, and *Geekbench AI* scores measure different things; use the same suite when comparing SKUs.

### Small boards & maker / prototyping

- [NVIDIA Jetson Orin Nano / NX](https://developer.nvidia.com/embedded/jetson-orin) - NVIDIA modules, ~20-100 TOPS class. Common robotics and vision proofs of concept; effective performance depends on power mode.
- [Qualcomm Dragonwing / robotics dev kits](https://www.qualcomm.com/products/iot) - IoT and robotics kits (e.g. Dragonwing QCS6490-class) with integrated Qualcomm AI Engine for embedded Linux vision and robotics prototypes.
- [Hailo-8 / Hailo-8L](https://hailo.ai/products/hailo-8-ai-accelerator/) - Hailo M.2 and USB accelerators, ~13-26 TOPS class. Popular gumstick and module form factors.
- [Coral Dev Board / Dev Board Mini](https://coral.ai/products/dev-board/) - Google boards with Edge TPU, ~4 INT8 TOPS. Small-scale LiteRT deployment and USB or M.2 accelerator ecosystem.
- [Orange Pi 5 (RK3588 / S)](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/details/Orange-Pi-5.html) - Rockchip RK3588 SBC, ~6 TOPS class NPU. Budget board with a usable integrated NPU.
- [BeagleBone AI-64](https://beagleboard.org/ai-64) - BeagleBoard.org SBC, ~8 TOPS class. Open hardware-friendly TI edge-AI SoC.

- [LiteRT](https://ai.google.dev/edge/litert) - Google's edge inference runtime; pairs with MediaPipe and on-device Gemini paths and often reflects toolchain choice as much as chip vendor across NPUs.
- [MediaPipe](https://ai.google.dev/edge/mediapipe/solutions/guide) - Google's cross-platform ML pipelines for vision, audio, and more on edge devices.

### Automotive & transportation

- [NVIDIA DRIVE Thor](https://developer.nvidia.com/drive) - NVIDIA automotive SoC, ~1000 INT8 TOPS (NVIDIA-quoted) and ~2000 FP4-class effective throughput (vendor framing). Do not equate INT8 TOPS and FP4 figures without reading definitions.
- [Qualcomm Snapdragon Ride / Flex](https://www.qualcomm.com/products/automotive) - Qualcomm automotive platforms, hundreds to 1000+ TOPS class depending on SKU. Scalable ADAS through higher automation tiers.
- [Hailo-10H](https://hailo.ai/products/hailo-10h-ai-accelerator/) - Hailo automotive and edge accelerator, ~40 TOPS class. In-vehicle and edge vision.
- [Mobileye EyeQ (Ultra+ class)](https://www.mobileye.com/products/eyeq-chip/) - Intel / Mobileye vision SoC, ~500+ class. Vision-centric stacks; definitions vary by generation.
- [Samsung Exynos Auto](https://semiconductor.samsung.com/processor/) - Samsung automotive-tier silicon, ~200+ class depending on tier. Select OEM programs.
- [Ambarella CV3](https://www.ambarella.com/product/cv3-ai-domain-controller/) - Ambarella perception SoCs, tens of TOPS class. Multi-camera automotive and edge vision.

When reading marketing sheets, clarify INT8 versus FP8 or FP4, single versus dual chip, and driving versus cockpit domain.

### Industrial & robotics

- [NVIDIA Jetson AGX Orin / Jetson Thor modules](https://developer.nvidia.com/embedded/jetson-modules) - NVIDIA edge modules, ~275 INT8 TOPS on AGX Orin 64 GB up to ~1000-class on Thor SKUs. Robotics, AMR, and medical edge; always match the module datasheet.
- [Qualcomm Robotics platforms](https://www.qualcomm.com/products/iot) - Qualcomm IoT and robotics SoCs, 50+ class. Drones, AMRs, and connected industrial machines.
- [AMD Versal AI Edge](https://www.amd.com/en/products/adaptive-socs-and-fpgas/versal.html) - AMD adaptive SoC, 100+ class depending on series. FPGA plus AI engine for industrial and defense flexibility.
- [Axelera AI Metis](https://www.axelera.ai/) - Axelera AI platform, ~200+ TOPS class. High-throughput industrial vision.
- [SiMa.ai MLSoC](https://sima.ai/) - SiMa.ai vision inference silicon, 50+ class. Low-power embedded vision.

Bandwidth and compiler support often limit real throughput before peak TOPS.

### Ultra-low-power NPUs & IoT ASICs

- [Google Edge TPU (embedded modules)](https://coral.ai/products/) - Google, ~4 INT8 TOPS. Small modules; system power depends on board and duty cycle.
- [Arm Ethos-U](https://developer.arm.com/Processors/Ethos-U) - Arm licensed NPU for MCUs, ~0.5-4 TOPS class. Energy per inference matters more than peak TOPS.
- [Kneron KL730](https://www.kneron.com/) - Kneron edge NPU, few TOPS class. TinyML and smart-camera nodes; Maix boards are a common hobby ecosystem.
- [Synaptics Astra SL1680](https://www.synaptics.com/products/embedded-solutions/astra-sl1680) - Synaptics embedded platform, ~12 TOPS class. MCU plus NPU integration.
- [GrAI VIP](https://www.graimatterlabs.ai/) - GrAI Matter Labs, 4-14 TOPS class. Event-driven and sparse inference; compare assumptions to frame-based CNN accelerators.

For wake word, VAD, and tiny vision, SRAM, utilization, and duty cycle usually matter more than peak TOPS.

### Open-source projects by platform

Representative GitHub projects that exercise each vendor stack in practice. Stars and activity change over time; some automotive and OEM programs ship mostly under NDA, so those rows point to the closest **public** SDK or sample family.

#### Consumer and laptop

- **NVIDIA Jetson (edge modules with PC-class host workflows).** [NVIDIA-AI-IOT/jetson-containers](https://github.com/NVIDIA-AI-IOT/jetson-containers) - Build and flash containerized CUDA and ML stacks on Jetson while iterating from a laptop or desktop host.
- **Qualcomm Snapdragon (Hexagon / QNN, phones, Windows on Snapdragon, and Snapdragon X laptops).** [quic/qidk](https://github.com/quic/qidk) - Android sample apps using the Qualcomm AI Engine and QNN on recent Snapdragon flagships. [qualcomm/snapdragon-compute-samples](https://github.com/qualcomm/snapdragon-compute-samples) - ONNX Runtime with the QNN execution provider for WoS, Snapdragon X Elite / X Plus laptops, and related targets. [quic/ai-engine-direct-helper](https://github.com/quic/ai-engine-direct-helper) - Simplified wrappers and examples around AI Engine Direct.
- **Hailo-8 / Hailo-8L (M.2, USB, and companion SBC setups).** [hailo-ai/hailo_model_zoo](https://github.com/hailo-ai/hailo_model_zoo) - Pretrained models, compilation scripts, and HailoRT deployment for Hailo-8 family accelerators. [hailo-ai/hailo-rpi5-examples](https://github.com/hailo-ai/hailo-rpi5-examples) - Reference pipelines often used with laptop-hosted tooling plus edge boards.
- **Apple Neural Engine / Core ML.** [ml-explore/mlx](https://github.com/ml-explore/mlx) - NumPy-style arrays and NN primitives tuned for Apple silicon unified memory. [apple/coremltools](https://github.com/apple/coremltools) - Model conversion, compression, and Core ML packaging for on-device deployment.
- **MediaTek Dimensity (NeuroPilot).** [MediaTek-NeuroPilot/tflite-neuron-delegate](https://github.com/MediaTek-NeuroPilot/tflite-neuron-delegate) - TensorFlow Lite delegate for MediaTek NPUs on supported phones. [pytorch/executorch](https://github.com/pytorch/executorch) - ExecuTorch includes a documented MediaTek backend path for on-device PyTorch models.
- **Samsung Exynos (mobile).** [android/nn-samples](https://github.com/android/nn-samples) - Android NNAPI samples that run on many vendor drivers, including typical Exynos retail devices (not Exynos-specific, but the usual OSS entry point).
- **Google Tensor (Pixel).** [google-ai-edge/mediapipe](https://github.com/google-ai-edge/mediapipe) - Production-style graphs for vision, audio, and genai-style demos on Android, including Pixel-first workflows. [google-ai-edge/LiteRT](https://github.com/google-ai-edge/LiteRT) - LiteRT runtime and tooling used across Google edge devices.
- **Intel Core Ultra (CPU / GPU / NPU via OpenVINO).** [openvinotoolkit/openvino](https://github.com/openvinotoolkit/openvino) - OpenVINO toolkit, notebooks, and model zoo targeting Intel NPU, GPU, and CPU on Core Ultra class PCs.
- **Coral Edge TPU (USB / M.2 / PCIe).** [google-coral/edgetpu](https://github.com/google-coral/edgetpu) - Edge TPU userspace, tests, and examples (Coral is in maintenance mode but repos remain the reference). [google-coral/tflite](https://github.com/google-coral/tflite) - TensorFlow Lite tree with Edge TPU delegate integration.

#### Small boards and maker kits

- **NVIDIA Jetson Orin Nano / NX.** [dusty-nv/jetson-inference](https://github.com/dusty-nv/jetson-inference) - End-to-end vision demos (classification, detection, pose, segmentation) on Jetson. [NVIDIA-AI-IOT/jetson-containers](https://github.com/NVIDIA-AI-IOT/jetson-containers) - CUDA, PyTorch, ROS 2, and other ML stacks as containers for Jetson.
- **Qualcomm Dragonwing / robotics kits.** [quic/sample-apps-for-qualcomm-linux](https://github.com/quic/sample-apps-for-qualcomm-linux) - Object detection and classification samples on Qualcomm Linux EVKs and Dragonwing-class kits. [qualcomm-qrb-ros/qrb_ros_transport](https://github.com/qualcomm-qrb-ros/qrb_ros_transport) - Zero-copy ROS 2 transport on Qualcomm robotics boards.
- **Hailo-8 / Hailo-8L.** [hailo-ai/hailo_model_zoo](https://github.com/hailo-ai/hailo_model_zoo) - Pretrained models, compilation scripts, and HailoRT deployment for Hailo-8 family accelerators. [hailo-ai/hailo-rpi5-examples](https://github.com/hailo-ai/hailo-rpi5-examples) - Raspberry Pi 5 plus Hailo-8 reference pipelines (popular real-world integration pattern).
- **Coral Dev Board / Dev Board Mini.** [google-coral/edgetpu](https://github.com/google-coral/edgetpu) - Same Edge TPU stack as the modules above; Mendel-era board bring-up and tests live alongside the runtime sources.
- **Orange Pi 5 (Rockchip RK3588 NPU).** [airockchip/rknn_model_zoo](https://github.com/airockchip/rknn_model_zoo) - RKNN model zoo and deployment examples for Rockchip NPU boards including Orange Pi 5.
- **BeagleBone AI-64 (TI Jacinto / TIDL).** [TexasInstruments/edgeai-tidl-tools](https://github.com/TexasInstruments/edgeai-tidl-tools) - Edge AI ModelZoo and tools for TI deep-learning accelerators on SoCs used on BeagleBone AI-64.

#### Automotive and ADAS (public SDK cousins)

- **NVIDIA DRIVE (Thor class and stack family).** OEM DriveOS application code is usually closed; public cousins include [NVIDIA-AI-IOT/deepstream_python_apps](https://github.com/NVIDIA-AI-IOT/deepstream_python_apps) - Multi-camera DeepStream samples in Python, and [NVIDIA-ISAAC-ROS/isaac_ros_common](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common) - Isaac ROS build infrastructure used in many robotics and perception stacks that share tooling with NVIDIA's automotive SDK lineage.
- **Qualcomm Snapdragon Ride / Flex and automotive Linux.** [quic/sample-apps-for-qualcomm-linux](https://github.com/quic/sample-apps-for-qualcomm-linux) - Sample apps and models for Qualcomm Linux platforms used in automotive and industrial lines; not a full Ride stack drop but a maintained public entry point.
- **Hailo-10H (in-vehicle and edge).** [hailo-ai/hailo_model_zoo](https://github.com/hailo-ai/hailo_model_zoo) - Same HailoRT and model-zoo workflow as Hailo-8 family accelerators; automotive integrations usually wrap these pipelines in OEM middleware.
- **Mobileye EyeQ, Samsung Exynos Auto, Ambarella CV3.** Widely deployed stacks, but **application reference code is not typically published on GitHub**; development flows go through each vendor's partner SDK portals rather than a single star-count OSS repo.

#### Industrial and robotics modules

- **NVIDIA Jetson AGX Orin / Jetson Thor.** [NVIDIA-AI-IOT/ros2_deepstream](https://github.com/NVIDIA-AI-IOT/ros2_deepstream) - ROS 2 integration examples for DeepStream on Jetson. [NVIDIA-ISAAC-ROS/isaac_ros_common](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common) - Docker-based build and test infrastructure shared by Isaac ROS perception stacks on Jetson and x86.
- **Qualcomm robotics SoCs (RB / QCS families).** [qualcomm-qrb-ros/qrb_ros_transport](https://github.com/qualcomm-qrb-ros/qrb_ros_transport) - Zero-copy ROS 2 transport tuned for Qualcomm robotics boards. [quic/sample-apps-for-qualcomm-linux](https://github.com/quic/sample-apps-for-qualcomm-linux) - Object detection and classification samples on Qualcomm Linux EVKs used in robotics kits.
- **AMD Versal AI Edge (Vitis AI).** [Xilinx/Vitis-AI](https://github.com/Xilinx/Vitis-AI) - Models, compiler, and runtime targeting AMD adaptive SoCs and Alveo accelerators; primary OSS path for Versal AI Engine workflows.
- **Axelera Metis.** [axelera-ai-hub/voyager-sdk](https://github.com/axelera-ai-hub/voyager-sdk) - Official Voyager SDK, samples, and model zoo for Metis hardware.
- **SiMa.ai MLSoC.** [SiMa-ai/models](https://github.com/SiMa-ai/models) - ONNX and PyTorch models with scripts aimed at SiMa.ai compilation and deployment flows.

#### Ultra-low-power NPUs and IoT

- **Google Edge TPU (embedded).** [google-coral/edgetpu](https://github.com/google-coral/edgetpu) - Same runtime as Coral modules; typical for USB and PCIe Edge TPU deployments.
- **Arm Ethos-U.** [tensorflow/tflite-micro](https://github.com/tensorflow/tflite-micro) - TensorFlow Lite Micro with Ethos-U integration paths. [ARM-software/ML-examples](https://github.com/ARM-software/ML-examples) - Training and deployment notebooks including Ethos-U Corstone-300 flows.
- **Kneron KL730 and related.** [kneron/ONNX_Convertor](https://github.com/kneron/ONNX_Convertor) - ONNX conversion and optimization scripts maintained for Kneron hardware toolchains.
- **Synaptics Astra (e.g. SL1680).** [synaptics-synap/examples](https://github.com/synaptics-synap/examples) - Official example apps for vision, speech, and LLM-style demos on Synaptics Astra-class kits.
- **GrAI VIP.** GrAIFlow and board support are **primarily distributed through vendor kits and partner channels** rather than a flagship public application repository on GitHub; treat marketing repos with care and verify license and chip revision.

### Technical trends (2026)

- Mobile SoCs still ship the largest volume of NPUs; AI PCs and software-defined vehicles are high-ASP growth segments.
- INT8 remains the default for CNNs at the edge; INT4, FP4, and FP8 are spreading for transformers where vendor kernels exist.
- Strong stacks partition work across NPU, GPU, DSP, and CPU; compiler and operator support often decide real-world wins.
- Packaging and near-compute memory bandwidth frequently cap throughput before raw MAC counts.


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
- [Geekbench AI](https://browser.geekbench.com/ai-benchmarks) - Geekbench AI inference scores with CPU, GPU, and NPU charts on Geekbench Browser (user-submitted; minimum sample count per device).
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

- [Dive into Deep Learning](https://d2l.ai/) - Open-access textbook with runnable notebooks; builds models from fundamentals through modern architectures in PyTorch, widely used in courses and aligned with how workloads map to accelerators.
- [Efficient Deep Learning](https://efficientdlbook.com/) - Techniques for efficient training and inference.


## Community

- [CUDA MODE Discord](https://discord.gg/cudamode) - Active community for GPU kernel hackers.
- [NVIDIA Developer Forums](https://forums.developer.nvidia.com/c/accelerated-computing/cuda/206) - Official CUDA community forum.
- [MLCommons](https://mlcommons.org/) - Open engineering consortium advancing ML hardware and software.
- [r/MachineLearning](https://www.reddit.com/r/MachineLearning/) - Reddit community covering ML research and hardware.
- [Chip Design & Architecture (SemiAnalysis)](https://semianalysis.com/) - Deep dives into AI chip architecture and industry trends.


## Contributing

Contributions welcome! Read the [contribution guidelines](contributing.md) first.
