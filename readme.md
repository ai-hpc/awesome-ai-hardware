# Awesome AI Hardware [![Awesome](https://awesome.re/badge.svg)](https://awesome.re) [![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

> Curated list of AI hardware resources, accelerators, architectures, tools, and research.


## Contents

- [Hardware Platforms](#hardware-platforms)
  - [GPUs](#gpus)
  - [AI Accelerators](#ai-accelerators)
  - [Edge & Embedded](#edge--embedded)
- [Edge AI Chip Landscape (2026)](#edge-ai-chip-landscape-2026)
  - [Consumer & mobile](#consumer--mobile)
  - [Laptop-class NPUs](#laptop-class-npus)
  - [USB & M.2 Accelerators](#usb--m2-accelerators)
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
- [Retail & Supermarket AI](#retail--supermarket-ai)
- [Smart Home AI](#smart-home-ai)
- [Mobile Phone AI](#mobile-phone-ai)
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

Vendor TOPS, *AI-Benchmark*, and *Geekbench AI* scores measure different things; use the same suite when comparing SKUs.


### Laptop-class NPUs

> Laptop NPU TOPS are INT8 peak on the NPU block only unless stated; real throughput depends on DRAM bandwidth, compiler support, and driver maturity. Cross-vendor comparisons require the same workload and framework.

- [Intel Core Ultra 100/200 (Meteor Lake / Arrow Lake)](https://www.intel.com/content/www/us/en/products/details/processors/core-ultra.html) - Intel AI Boost NPU, ~11 TOPS on Meteor Lake and ~13 TOPS on Arrow Lake (INT8, NPU-only; Intel-stated). Target via OpenVINO or ONNX Runtime with the OpenVINO execution provider.
- [Intel Core Ultra 200V (Lunar Lake)](https://www.intel.com/content/www/us/en/products/details/processors/core-ultra.html) - Intel AI Boost NPU 2, ~48 TOPS (NPU-only; Intel-stated). Ships in thin-and-light Copilot+ PC designs.
- [AMD Ryzen AI 300 / AI Max (Strix Point, XDNA 2)](https://www.amd.com/en/products/processors/laptop.html) - AMD NPU XDNA 2, ~50 TOPS. First AMD part to reach Copilot+ PC tier; use ONNX Runtime with the DirectML or AMD execution provider.
- [AMD Ryzen AI 7040 / 8040 (Phoenix / Hawk Point, XDNA)](https://www.amd.com/en/products/processors/laptop.html) - AMD NPU XDNA, ~16 TOPS. Earlier Ryzen AI generation; improving coverage via ROCm and ONNX Runtime XDNA paths.
- [Qualcomm Snapdragon X Elite / X Plus](https://www.qualcomm.com/products/mobile-compute) - Hexagon NPU, 45 TOPS (Qualcomm-stated). Windows on Snapdragon Copilot+ PC; use vendor QNN tests or WoS ONNX Runtime entries for comparable numbers.
- [Apple M-series Neural Engine (M3 / M4)](https://developer.apple.com/documentation/coreml) - 16-core Neural Engine, ~15.8 TOPS on M3 and ~38 TOPS on M4 (Apple-stated). Accessible via Core ML and mlx; not exposed via ONNX Runtime or DirectML.


### USB & M.2 Accelerators

> These cards add dedicated INT8 inference capacity to any host with USB 3 or M.2/PCIe. Peak TOPS is for the accelerator die only; USB overhead and host memory transfers significantly reduce effective throughput.

- [Hailo-8 (M.2 / mini-PCIe / USB)](https://hailo.ai/products/ai-accelerators/hailo-8-ai-accelerator/) - Hailo, 26 INT8 TOPS. Popular M.2 form factor on Raspberry Pi 5 AI Kit; models compiled via Hailo Dataflow Compiler from ONNX or TFLite.
- [Hailo-8L (M.2)](https://hailo.ai/products/ai-accelerators/) - Hailo, 13 INT8 TOPS. Lower-power variant of Hailo-8; same compiler toolchain, suited for tighter power budgets.
- [Coral Edge TPU (USB / M.2 / PCIe)](https://developers.google.com/coral) - Google, ~4 INT8 TOPS (module docs). Pairs with LiteRT models compiled for the Edge TPU; in maintenance mode but runtime still updated.
- [Luxonis OAK-D (USB)](https://shop.luxonis.com/products/oak-d) - Luxonis, ~4 TOPS (Intel Myriad X). USB depth-stereo AI camera; runs inference on-device via the DepthAI SDK.
- [Kneron KL720 (USB / M.2)](https://www.kneron.com/) - Kneron, ~0.5–1 TOPS INT8. Ultra-low-power USB and M.2 module for always-on TinyML and smart-camera nodes.


### Small boards & maker / prototyping

- [Raspberry Pi 5 + AI Kit](https://www.raspberrypi.com/products/ai-kit/) - Raspberry Pi Foundation, 13 TOPS via Hailo-8L M.2 module. The de-facto hobbyist AI board; the entire Hailo community ecosystem and tutorial base centers on this configuration.
- [NVIDIA Jetson Orin Nano / NX](https://developer.nvidia.com/embedded/jetson-orin) - NVIDIA modules, 20–100 TOPS class. Common robotics and vision proofs of concept; performance depends on power mode and thermal design.
- [Qualcomm Dragonwing RB3 Gen 2 / RB5](https://www.qualcomm.com/products/iot) - Qualcomm IoT EVKs with Hexagon AI Engine (QCS6490 / QCS8550 class). Active ROS 2 ecosystem via qualcomm-qrb-ros; target for Android and Qualcomm Linux embedded AI.
- [Hailo-8 / Hailo-8L M.2](https://hailo.ai/products/ai-accelerators/hailo-8-ai-accelerator/) - Hailo M.2 accelerator modules, 13–26 TOPS. Drop into any M.2 host; Hailo Dataflow Compiler compiles ONNX / TFLite to `.hef` runtime packages.
- [Radxa Rock 5B](https://radxa.com/products/rock5/5b/) - Rockchip RK3588 SBC, ~6 TOPS NPU. Strong community and driver coverage; same RKNN model-zoo ecosystem as Orange Pi 5.
- [Orange Pi 5 (RK3588 / S)](http://www.orangepi.org/html/hardWare/computerAndMicrocontrollers/details/Orange-Pi-5.html) - Rockchip RK3588 SBC, ~6 TOPS NPU. Budget-friendly alternative with a usable integrated NPU.
- [Khadas VIM4](https://www.khadas.com/vim4) - Amlogic A311D2 SBC, ~5 TOPS NPU. Compact form-factor; popular for lightweight demo pipelines.
- [Coral Dev Board / Dev Board Mini](https://coral.ai/products/dev-board/) - Google boards with Edge TPU, ~4 INT8 TOPS. Small-scale LiteRT deployment; in maintenance mode.
- [BeagleBone AI-64](https://www.beagleboard.org/ai-64) - BeagleBoard.org SBC, ~8 TOPS class. Open hardware-friendly TI Jacinto 7 edge-AI SoC; good for industrial prototyping.

### Automotive & transportation

- [NVIDIA DRIVE Thor](https://developer.nvidia.com/drive) - NVIDIA automotive SoC, ~1000 INT8 TOPS (NVIDIA-quoted) / ~2000 FP4-class (vendor framing). Targets cockpit-plus-AD fusion on a single chip; do not equate INT8 and FP4 TOPS figures.
- [Qualcomm Snapdragon Ride / Flex](https://www.qualcomm.com/products/automotive) - Qualcomm automotive platforms, hundreds to 1000+ TOPS depending on SKU. Ride targets ADAS/AD; Flex targets cockpit. SA8155P / SA8255P powers the comma 3X device running [openpilot](https://github.com/commaai/openpilot), a 300+ vehicle L2+ open-source deployment.
- [Texas Instruments TDA4VM / TDA4VH (Jacinto 7)](https://www.ti.com/product/TDA4VM) - TI ADAS SoC, 8–32 TOPS class. Designed for L2+ surround-view, sensor fusion, and radar processing; widely deployed in automotive camera and domain ECUs.
- [Renesas R-Car V4H / V4M](https://www.renesas.com/en/products/automotive-products/automotive-system-chips-socs) - Renesas ADAS SoC, ~32 TOPS CV engine class. Common in Tier-1 camera and domain modules in Japan and Europe.
- [Mobileye EyeQ Ultra](https://www.mobileye.com/technology/) - Intel / Mobileye vision SoC, ~500+ TOPS class. Purpose-built for end-to-end vision; EyeQ chips deployed in tens of millions of vehicles.
- [Hailo-10H](https://hailo.ai/products/ai-accelerators/hailo-10h-ai-accelerator/) - Hailo automotive-grade vision co-processor, ~40 TOPS. Paired alongside a domain controller SoC for perception offload.
- [Samsung Exynos Auto V920](https://semiconductor.samsung.com/processor/) - Samsung automotive SoC, ~88 TOPS class. Cockpit and ADAS tier; selected for BMW and Hyundai vehicle programs.
- [Ambarella CV3-AD](https://www.ambarella.com/products/) - Ambarella central-domain ADAS SoC, ~400+ TOPS class. Multi-camera perception and sensor fusion targeting L2+/L3 systems.

When reading marketing sheets, clarify INT8 versus FP8 or FP4, single versus dual chip, and AD versus cockpit domain.

### Industrial & robotics

- [NVIDIA Jetson AGX Orin / Jetson Thor modules](https://developer.nvidia.com/embedded/jetson-modules) - NVIDIA edge modules, ~275 INT8 TOPS on AGX Orin 64 GB up to ~1000-class on Thor SKUs. Standard platform for AMRs, surgical robots, and industrial inspection; always match the module datasheet.
- [Qualcomm Robotics RB series (QCS families)](https://www.qualcomm.com/products/iot) - Qualcomm IoT and robotics SoCs, 50+ TOPS class. Drones, AMRs, and connected industrial machines; active ROS 2 and PX4 flight-controller support.
- [Texas Instruments AM62A / AM67A](https://www.ti.com/product/AM62A3) - TI industrial edge AI SoC, 1–4 TOPS class. Low-power vision for industrial cameras, AGVs, and building automation; paired with TIDL runtime.
- [AMD Versal AI Edge](https://www.amd.com/en/products/adaptive-socs-and-fpgas/versal.html) - AMD adaptive SoC, 100+ TOPS class depending on series. FPGA + AI engine for industrial inspection, defense, and reconfigurable edge inference.
- [Axelera AI Metis](https://www.axelera.ai/) - Axelera AI platform, ~214 INT8 TOPS. High-throughput industrial vision on M.2 and PCIe; Voyager SDK targets ONNX and PyTorch models.
- [SiMa.ai MLSoC](https://sima.ai/) - SiMa.ai vision inference silicon, 50+ TOPS class. Low-power embedded vision for factory inspection and robotics payloads.
- [Renesas RZ/V2L (DRP-AI)](https://www.renesas.com/en/products/microcontrollers-microprocessors/rz-mpus) - Renesas edge AI MPU, ~1 TOPS DRP-AI class. Industrial vision and HMI applications in smart-factory and AGV endpoints.

Bandwidth and compiler support often limit real throughput before peak TOPS.

### Ultra-low-power NPUs & IoT ASICs

- [Syntiant NDP120 / NDP200](https://www.syntiant.com/ndp120) - Syntiant Neural Decision Processor, <1 mW active inference. Purpose-built for always-on audio (wake word, VAD, keyword spotting) and tiny-vision; sub-milliwatt operation enables coin-cell and energy-harvesting designs.
- [Arm Ethos-U55 / U65](https://developer.arm.com/Processors/Ethos-U) - Arm NPU licensed for Cortex-M MCUs, 0.5–4 TOPS class. SRAM budget and operator coverage matter more than peak TOPS; paired with TFLM and CMSIS-NN.
- [STM32 + X-CUBE-AI](https://www.st.com/en/development-tools/x-cube-ai.html) - STMicroelectronics toolkit that converts Keras / ONNX / TFLite to optimized C for STM32 MCUs. Most widely deployed TinyML toolchain on bare-metal Cortex-M devices.
- [Nordic nRF54H20](https://www.nordicsemi.com/Products/nRF54H20) - Nordic Semiconductor multi-core SoC with BLE / Wi-Fi and ML-capable DSP. Low-power sensor node for gesture, audio, and vital-sign inference at the edge.
- [Google Edge TPU (embedded modules)](https://developers.google.com/coral) - Google, ~4 INT8 TOPS. PCB-mounted module; system power depends on host board and duty cycle.
- [Kneron KL730](https://www.kneron.com/) - Kneron edge NPU, few TOPS class. TinyML and smart-camera nodes with USB and SPI interfaces.
- [Synaptics Astra SL1680](https://www.synaptics.com/) - Synaptics embedded platform, ~12 TOPS class. MCU plus NPU for voice and vision endpoint integration.
- [Espressif ESP32-S3](https://www.espressif.com/en/products/socs/esp32-s3) - Espressif, dual-core Xtensa LX7 at 240 MHz with vector extensions for ML. Wi-Fi + BLE; popular for always-on camera AI (face detection, gesture) and audio keyword spotting in battery-powered devices.
- [Espressif ESP32-P4](https://www.espressif.com/en/products/socs/esp32-p4) - Espressif, dual-core RISC-V HP at 400 MHz with dedicated AI instructions, H.264 encode/decode, and large PSRAM support. Higher-performance edge AI than S3; targets local video analytics and richer on-device inference.
- [Sipeed Maix boards (K210 / K230)](https://www.sipeed.com/) - Sipeed RISC-V SoC with KPU neural processor, 0.5–2 TOPS class. Powers M5StickV, Maixduino, and Bit boards; MaixPy makes object detection and face recognition accessible from MicroPython.

For wake word, VAD, and tiny-vision workloads, SRAM size, operator coverage, and duty cycle matter more than peak TOPS.

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
- **AMD Ryzen AI (XDNA / XDNA 2 NPU).** [amd/RyzenAI-SW](https://github.com/amd/RyzenAI-SW) - Official AMD Ryzen AI software stack, model examples, and deployment guide for XDNA and XDNA 2 NPU on Ryzen AI series laptops.
- **Coral Edge TPU (USB / M.2 / PCIe).** [google-coral/edgetpu](https://github.com/google-coral/edgetpu) - Edge TPU userspace, tests, and examples (Coral is in maintenance mode but repos remain the reference). [google-coral/tflite](https://github.com/google-coral/tflite) - TensorFlow Lite tree with Edge TPU delegate integration.

#### Small boards and maker kits

- **NVIDIA Jetson Orin Nano / NX.** [dusty-nv/jetson-inference](https://github.com/dusty-nv/jetson-inference) - End-to-end vision demos (classification, detection, pose, segmentation) on Jetson. [NVIDIA-AI-IOT/jetson-containers](https://github.com/NVIDIA-AI-IOT/jetson-containers) - CUDA, PyTorch, ROS 2, and other ML stacks as containers for Jetson.
- **Qualcomm Dragonwing / robotics kits.** [quic/sample-apps-for-qualcomm-linux](https://github.com/quic/sample-apps-for-qualcomm-linux) - Object detection and classification samples on Qualcomm Linux EVKs and Dragonwing-class kits. [qualcomm-qrb-ros/qrb_ros_transport](https://github.com/qualcomm-qrb-ros/qrb_ros_transport) - Zero-copy ROS 2 transport on Qualcomm robotics boards.
- **Hailo-8 / Hailo-8L.** [hailo-ai/hailo_model_zoo](https://github.com/hailo-ai/hailo_model_zoo) - Pretrained models, compilation scripts, and HailoRT deployment for Hailo-8 family accelerators. [hailo-ai/hailo-rpi5-examples](https://github.com/hailo-ai/hailo-rpi5-examples) - Raspberry Pi 5 plus Hailo-8 reference pipelines (popular real-world integration pattern).
- **Coral Dev Board / Dev Board Mini.** [google-coral/edgetpu](https://github.com/google-coral/edgetpu) - Same Edge TPU stack as the modules above; Mendel-era board bring-up and tests live alongside the runtime sources.
- **Orange Pi 5 (Rockchip RK3588 NPU).** [airockchip/rknn_model_zoo](https://github.com/airockchip/rknn_model_zoo) - RKNN model zoo and deployment examples for Rockchip NPU boards including Orange Pi 5.
- **BeagleBone AI-64 (TI Jacinto / TIDL).** [TexasInstruments/edgeai-tidl-tools](https://github.com/TexasInstruments/edgeai-tidl-tools) - Edge AI ModelZoo and tools for TI deep-learning accelerators on SoCs used on BeagleBone AI-64.
- **Raspberry Pi 5 + Hailo — real-world NVR deployment.** [blakeblackshear/frigate](https://github.com/blakeblackshear/frigate) - NVR with always-on object detection for Home Assistant; supports Coral Edge TPU and Hailo-8/8L natively. One of the most widely deployed real-world uses of M.2 AI accelerators on maker boards, with tens of thousands of active home installations. [hailo-ai/hailo-rpi5-examples](https://github.com/hailo-ai/hailo-rpi5-examples) - Official Hailo Raspberry Pi 5 reference pipelines.

#### Automotive and ADAS — open-source deployments and SDK cousins

> Several of the most deployed open-source autonomy stacks run directly on the chips in this section. OEM DriveOS / Ride application code is typically closed; the projects below are the public face of automotive AI hardware in practice.

- **openpilot (Qualcomm SA8155P / SA8255P) — production L2+ success story.** [commaai/openpilot](https://github.com/commaai/openpilot) - comma.ai's open-source ADAS suite running on Snapdragon automotive SoCs in the comma 3X device. Active L2 autonomy on 300+ car makes with hundreds of thousands of real-world users. The full model, training pipeline, and SNPE/QNN inference stack are public — the clearest open example of end-to-end production AI on Qualcomm silicon.
- **Apollo (NVIDIA DRIVE / x86 + GPU).** [ApolloAuto/apollo](https://github.com/ApolloAuto/apollo) - Baidu's open-source autonomous driving platform targeting NVIDIA DRIVE hardware and GPU workstations. Large model and sensor zoo; widely used in Chinese robotaxi and L4 R&D programs.
- **Autoware (NVIDIA Jetson / x86, ROS 2).** [autowarefoundation/autoware](https://github.com/autowarefoundation/autoware) - Leading open-source ROS 2 AV stack; runs on Jetson Orin AGX and x86 NVIDIA hosts. Used in open-road L4 research programs worldwide.
- **NVIDIA DRIVE / Isaac ROS cousins.** [NVIDIA-AI-IOT/deepstream_python_apps](https://github.com/NVIDIA-AI-IOT/deepstream_python_apps) - Multi-camera DeepStream pipelines in Python. [NVIDIA-ISAAC-ROS/isaac_ros_common](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common) - Isaac ROS build infra shared by robotics and automotive perception stacks.
- **Qualcomm automotive Linux samples.** [quic/sample-apps-for-qualcomm-linux](https://github.com/quic/sample-apps-for-qualcomm-linux) - Object detection and classification samples for Qualcomm Linux EVKs; closest maintained public entry point to Ride/Flex platform development.
- **TI Jacinto / TDA4VM cousins.** [TexasInstruments/edgeai-tidl-tools](https://github.com/TexasInstruments/edgeai-tidl-tools) - TI deep-learning runtime and model zoo for Jacinto SoC families; same tools underpin production automotive camera ECUs.
- **Hailo-10H (in-vehicle).** [hailo-ai/hailo_model_zoo](https://github.com/hailo-ai/hailo_model_zoo) - Same HailoRT and model-zoo workflow as Hailo-8 family; automotive integrations wrap these pipelines in OEM middleware.
- **Mobileye, Samsung Exynos Auto, Ambarella, Renesas R-Car.** Application reference code is **not typically public**; development goes through each vendor's partner SDK portal.

#### Industrial and robotics — open-source stacks and hardware

- **ROS 2 Navigation — hardware-agnostic, widely runs on Jetson and x86.** [ros-navigation/navigation2](https://github.com/ros-navigation/navigation2) - Nav2; the standard mobile robot navigation stack for AMRs, used on Jetson Orin and x86 NVIDIA hosts. [huggingface/lerobot](https://github.com/huggingface/lerobot) - HuggingFace robot learning library for imitation and RL; runs on Jetson and x86 GPU platforms.
- **PX4 / ArduPilot (Qualcomm RB series + bare-metal).** [PX4/PX4-Autopilot](https://github.com/PX4/PX4-Autopilot) - Open-source UAV flight controller; Qualcomm RB5 and RB3 are supported companion-compute targets. [ArduPilot/ardupilot](https://github.com/ArduPilot/ardupilot) - Alternative UAV stack running from bare MCUs through Jetson-class companions.
- **NVIDIA Jetson AGX Orin / Thor — Isaac ROS.** [NVIDIA-ISAAC-ROS/isaac_ros_common](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common) - Docker-based Isaac ROS build infra; base for all Isaac perception packages. [NVIDIA-ISAAC-ROS/isaac_ros_object_detection](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_object_detection) - GPU-accelerated object detection on Jetson for industrial and warehouse robotics. [NVIDIA-AI-IOT/ros2_deepstream](https://github.com/NVIDIA-AI-IOT/ros2_deepstream) - Multi-stream DeepStream pipelines under ROS 2.
- **Qualcomm robotics SoCs (RB / QCS families).** [qualcomm-qrb-ros/qrb_ros_transport](https://github.com/qualcomm-qrb-ros/qrb_ros_transport) - Zero-copy ROS 2 transport for Qualcomm robotics boards. [quic/sample-apps-for-qualcomm-linux](https://github.com/quic/sample-apps-for-qualcomm-linux) - Detection and classification samples on Qualcomm Linux EVKs.
- **TI AM62A / Jacinto (TIDL).** [TexasInstruments/edgeai-tidl-tools](https://github.com/TexasInstruments/edgeai-tidl-tools) - TI deep-learning runtime and model zoo for AM62A and Jacinto SoC families; covers factory automation and AGV vision use cases.
- **AMD Versal AI Edge (Vitis AI).** [Xilinx/Vitis-AI](https://github.com/Xilinx/Vitis-AI) - Models, compiler, and runtime for AMD adaptive SoCs and Alveo cards; primary OSS path for Versal AI Engine workflows.
- **Axelera Metis.** [axelera-ai-hub/voyager-sdk](https://github.com/axelera-ai-hub/voyager-sdk) - Official Voyager SDK, samples, and model zoo for Metis hardware.
- **SiMa.ai MLSoC.** [SiMa-ai/models](https://github.com/SiMa-ai/models) - ONNX and PyTorch models with SiMa.ai deployment scripts.

#### Ultra-low-power NPUs and IoT

- **Benchmarks (hardware-agnostic).** [mlcommons/tiny](https://github.com/mlcommons/tiny) - MLCommons TinyMLperf; standardized benchmarks for keyword spotting, image classification, visual wake words, and anomaly detection across MCU-class hardware.
- **Arm Ethos-U / Cortex-M (TFLM + CMSIS-NN).** [tensorflow/tflite-micro](https://github.com/tensorflow/tflite-micro) - TFLite Micro with Ethos-U kernels; the primary inference engine for Arm MCU AI. [ARM-software/ML-examples](https://github.com/ARM-software/ML-examples) - Deployment notebooks including Ethos-U55 Corstone-300 virtual-platform flows.
- **STM32 + X-CUBE-AI.** [STMicroelectronics/stm32ai-modelzoo](https://github.com/STMicroelectronics/stm32ai-modelzoo) - Official STM32 AI model zoo; covers image classification, object detection, and keyword spotting for Cortex-M devices.
- **Cross-platform MCU / NPU (Edge Impulse).** [edgeimpulse/example-standalone-inferencing](https://github.com/edgeimpulse/example-standalone-inferencing) - Standalone C++ inference from Edge Impulse Studio; runs on Arduino Nano 33 BLE, STM32, nRF, Syntiant NDP, and other targets without an OS.
- **Espressif ESP32-S3 / ESP32-P4 camera AI.** [espressif/esp-who](https://github.com/espressif/esp-who) ★2k — Face detection, recognition, and pedestrian detection demo apps built on ESP-DL; canonical starting point for camera AI on ESP32-S3. [espressif/esp-dl](https://github.com/espressif/esp-dl) ★900+ — Official ONNX-to-ESP32 quantization and inference library; compiles INT8 models to run on ESP32-S3 vector units and ESP32-P4 AI instructions.
- **OpenMV (STM32H7 / RP2040 / ESP32 camera boards).** [openmv/openmv](https://github.com/openmv/openmv) ★2.7k — MicroPython machine-vision library for microcontrollers; runs on OpenMV Cam H7, Arduino Nicla Vision, and RP2040-class targets; built-in TFLite Micro inference and a large example library covering object detection, classification, face recognition, and optical flow.
- **Sipeed MaixPy (K210 / K230).** [sipeed/MaixPy](https://github.com/sipeed/MaixPy) ★700+ — MicroPython AI framework for Maix boards; face recognition, object detection, and keyword spotting in under 10 lines of Python on a low-cost RISC-V module.
- **Google Edge TPU (embedded).** [google-coral/edgetpu](https://github.com/google-coral/edgetpu) - Same runtime as Coral dev boards; used for soldered-down module deployments.
- **Kneron KL730 and related.** [kneron/ONNX_Convertor](https://github.com/kneron/ONNX_Convertor) - ONNX conversion and optimization scripts for Kneron hardware toolchains.
- **Synaptics Astra (SL1680).** [synaptics-synap/examples](https://github.com/synaptics-synap/examples) - Official demos for vision, speech, and LLM-style inference on Astra-class kits.

### Technical trends (2026)

- Mobile SoCs still ship the largest volume of NPUs; AI PCs and software-defined vehicles are high-ASP growth segments.
- INT8 remains the default for CNNs at the edge; INT4, FP4, and FP8 are spreading for transformers where vendor kernels exist.
- Strong stacks partition work across NPU, GPU, DSP, and CPU; compiler and operator support often decide real-world wins.
- Packaging and near-compute memory bandwidth frequently cap throughput before raw MAC counts.


## Retail & Supermarket AI

> Edge AI in retail combines a detector, a tracker, and a pipeline tool — deployed on Jetson, Hailo, or Intel NPU hardware. No single high-star repo is dedicated purely to retail; the stack is assembled from the projects below. Cashierless-store stacks (Amazon Just Walk Out, Standard AI) remain largely proprietary.

### Detection & Tracking

- [Ultralytics YOLO (v8/v11)](https://github.com/ultralytics/ultralytics) ★55k — Real-time object detection backbone for shelf scanning, product recognition, self-checkout item detection, queue person-counting, and loss prevention. First-class export to Jetson (TensorRT), Hailo, Coral (TFLite), and OpenVINO.
- [Roboflow Supervision](https://github.com/roboflow/supervision) ★37k — Reusable CV primitives — zone-based counting, tracker wrappers, line crossing, heatmaps — used as the standard glue layer for retail pipelines on top of any YOLO detector.
- [ByteTrack](https://github.com/ifzhang/ByteTrack) ★10k — High-accuracy multi-object tracker; used for queue length measurement, customer dwell analysis, and item association in cashierless store prototypes. Runs on Jetson with TensorRT backends.
- [SORT](https://github.com/abewley/sort) ★4k — Minimal real-time tracker; the lightweight backbone in footfall counters and queue systems on Raspberry Pi, Jetson Nano, and Coral-paired boards.

### Anomaly Detection & Shelf Monitoring

- [Anomalib](https://github.com/open-edge-platform/anomalib) ★5.5k — Anomaly detection library used for shelf gap / out-of-stock detection, damaged-packaging identification, and distribution-center quality control. Explicit OpenVINO optimization for edge deployment on Intel NPU and Jetson.

### Multi-Camera Analytics

- [NVIDIA DeepStream Reference Apps](https://github.com/NVIDIA-AI-IOT/deepstream_reference_apps) ★1.3k — GStreamer-based multi-stream analytics on Jetson; covers people tracking, zone dwell time, and inventory monitoring for retail production deployments.
- [OpenDataCam](https://github.com/opendatacam/opendatacam) ★1.7k — Turnkey object counting and tracking for footfall analytics, queue monitoring, and zone counting; originally built for NVIDIA Jetson with no cloud dependency.
- [Viseron](https://github.com/roflcoopter/viseron) ★2.7k — Self-hosted NVR with integrated object detection, motion, and face recognition for small retailers; runs locally on Raspberry Pi and Jetson.

### Product Data

- [OpenFoodFacts](https://github.com/openfoodfacts/openfoodfacts-server) ★1k — Open product database (barcode → product metadata); foundation layer for self-checkout product lookup, inventory enrichment, and product recognition training data.


## Smart Home AI

> The smart home AI stack runs on low-power edge hardware — Raspberry Pi, ESP32, Jetson Nano, or a mini-PC — entirely without cloud dependency. The projects below cover the full pipeline: device firmware → camera AI → local voice (wake word → STT → LLM → TTS) → protocol bridging.

### Platform & Orchestration

- [Home Assistant](https://github.com/home-assistant/core) ★86k — Dominant open-source home automation platform; local-first, privacy-focused. Natively integrates Frigate (camera AI), Whisper (local STT), and Piper (local TTS) via the Wyoming protocol for a fully offline voice assistant.
- [Node-RED](https://github.com/node-red/node-red) ★23k — Flow-based visual programming for wiring IoT sensors, AI APIs, and devices; runs on Raspberry Pi and any Node.js host.
- [openHAB](https://github.com/openhab/openhab-core) ★1.1k — Vendor-neutral Java-based home automation runtime with a strong rules engine and large device binding ecosystem.

### Device Firmware (ESP32 / MCU)

- [ESPHome](https://github.com/esphome/esphome) ★10.8k — Config-file-driven firmware for ESP32 / ESP8266 / RP2040; first-class Home Assistant integration; supports on-device wake-word detection and sensor ML.
- [Tasmota](https://github.com/arendst/Tasmota) ★24k — Alternative ESP8266/ESP32 firmware with web UI, OTA, and MQTT; entirely local, no cloud. Widely used for smart plugs, lights, and DIY sensors.

### Camera AI & Streaming

- [Frigate](https://github.com/blakeblackshear/frigate) ★31k — NVR with always-on local object detection; natively supports Coral Edge TPU and Hailo-8/8L M.2 for hardware-accelerated inference. (Also listed in Small boards section.)
- [go2rtc](https://github.com/AlexxIT/go2rtc) ★12.7k — High-performance camera streaming hub supporting RTSP, WebRTC, HomeKit, and MSE; the standard camera bridge layer used with Frigate and Home Assistant.
- [Scrypted](https://github.com/koush/scrypted) ★5.6k — Video integration and home automation platform with AI plugins; bridges cameras from any vendor into HomeKit, Google Home, and Home Assistant with local object detection.

### Local Voice Pipeline

- [whisper.cpp](https://github.com/ggerganov/whisper.cpp) ★48k — C/C++ inference of OpenAI Whisper ASR; optimized for Raspberry Pi, Apple Silicon, and x86 edge hosts. The local STT engine inside Home Assistant Assist.
- [Piper](https://github.com/rhasspy/piper) ★10.7k — Fast local neural text-to-speech; default TTS in Home Assistant Assist and offline voice assistants; runs in real time on a Raspberry Pi.
- [openWakeWord](https://github.com/dscripka/openWakeWord) ★2k — Audio wake-word and phrase detection for triggering local voice pipelines on always-on edge hardware without cloud.
- [Rhasspy](https://github.com/rhasspy/rhasspy) ★2.7k — Fully offline voice assistant supporting 20+ languages; intent recognition and speech pipeline run on Raspberry Pi with no cloud service.

### Local LLM Integration

- [Ollama](https://github.com/ollama/ollama) ★167k — Run LLaMA, Mistral, Gemma, Phi, and other LLMs locally on any hardware; increasingly used as the natural-language reasoning backend in Home Assistant automations.
- [LocalAI](https://github.com/mudler/LocalAI) ★44k — Local AI engine running LLMs, vision models, STT, and TTS via an OpenAI-compatible API; no GPU required; bridges multiple AI functions into home automation platforms.

### Protocol & Device Integration

- [Zigbee2MQTT](https://github.com/Koenkk/zigbee2mqtt) ★15k — Bridges 3000+ Zigbee devices (sensors, lights, locks, buttons) to MQTT without a proprietary hub; eliminates cloud dependency for the most common smart home sensor protocol.


## Mobile Phone AI

> On-device inference on phones runs against tight memory, power, and thermal limits — frameworks below are designed for ARM CPUs, mobile GPUs (Adreno, Mali), DSPs, and dedicated NPUs (Apple Neural Engine, Hexagon, Dimensity APU). All projects run inference locally with no cloud dependency.

### Mobile Inference Engines

- [ncnn](https://github.com/Tencent/ncnn) ★23k — Tencent's neural network inference framework designed from the ground up for mobile ARM/Vulkan; used in WeChat, QQ, and production apps serving billions of users. No dependencies, runs on Android and iOS.
- [MNN](https://github.com/alibaba/MNN) ★14.7k — Alibaba's battle-tested mobile inference engine; supports Android/iOS and on-device LLMs. Powers Taobao, Tmall, and Youku AI features in production.
- [Tencent TNN](https://github.com/Tencent/TNN) ★4.6k — Tencent's mobile-first inference framework deployed in QQ, Weishi, and Pitu; optimized for iOS and Android with quantization and heterogeneous compute support.
- [Xiaomi MACE](https://github.com/XiaoMi/mace) ★5k — Xiaomi's deep learning inference framework optimized for mobile heterogeneous compute (CPU/GPU/DSP/APU); tuned for Snapdragon and MediaTek SoCs.
- [ExecuTorch](https://github.com/pytorch/executorch) ★4.5k — PyTorch's official on-device inference runtime for Android, iOS, and embedded; includes documented backends for Apple Neural Engine, Qualcomm QNN, MediaTek, and Arm Ethos.
- [LiteRT](https://github.com/google-ai-edge/LiteRT) ★2k — Google's successor to TensorFlow Lite; high-performance on-device inference on Android and iOS with NNAPI, CoreML, and GPU delegate backends.

### LLM on Phone

- [llama.cpp](https://github.com/ggerganov/llama.cpp) ★101k — Pure C/C++ quantized LLM inference; runs LLaMA, Mistral, Phi, and Gemma on Android and iOS CPU/GPU with no runtime dependencies. The foundation of most mobile LLM apps.
- [mlc-llm](https://github.com/mlc-ai/mlc-llm) ★22k — Compiles LLMs to native Android and iOS packages via ML compilation (TVM); achieves GPU-accelerated token generation on Snapdragon Adreno and Apple Neural Engine.
- [llamafile](https://github.com/Mozilla-Ocho/llamafile) ★24k — Packages entire LLMs as single self-contained executables that run on any device including mobile-class ARM hardware; no install, no dependencies.

### Vision & Multimodal Pipelines

- [MediaPipe](https://github.com/google-ai-edge/mediapipe) ★34.5k — Google's cross-platform on-device ML pipeline library; covers face detection, hand tracking, pose estimation, object detection, and on-device LLM inference for Android and iOS.
- [ONNX Runtime](https://github.com/microsoft/onnxruntime) ★19.7k — Cross-platform ONNX inference with Android NNAPI and iOS CoreML execution providers; the portable deployment target for models trained in any framework.
- [Candle](https://github.com/huggingface/candle) ★19.8k — Minimalist Rust ML framework; lightweight binary footprint and no Python dependency makes it suitable for mobile and WASM targets.
- [Transformers.js](https://github.com/xenova/transformers.js) ★15.7k — Hugging Face Transformers running entirely in-browser or on-device via WASM and WebGPU; no server required; supports vision, NLP, and audio models on mobile browsers.

### Apple Neural Engine

- [MLX](https://github.com/ml-explore/mlx) ★25k — Apple's own array and ML framework for Apple Silicon; exploits the Neural Engine and unified memory on iPhone, iPad, and Mac; used for on-device fine-tuning and inference.
- [coremltools](https://github.com/apple/coremltools) ★5.2k — Official Apple model conversion and compression pipeline; converts PyTorch/TensorFlow/ONNX models to Core ML format targeting the Neural Engine on iPhone and iPad.
- [ai-edge-torch](https://github.com/google-ai-edge/ai-edge-torch) ★976 — Converts PyTorch models to LiteRT format for on-device deployment on Android Neural Engine paths and iOS.


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
