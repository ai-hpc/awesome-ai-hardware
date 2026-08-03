

# Hardware de IA Destacado [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Aceleradores de IA, dispositivos de inferencia en el borde, compiladores, tiempos de ejecución, conjuntos de referencia (benchmarks) e investigación para construir y evaluar sistemas de aprendizaje automático.

## Contenido

- [Plataformas de Hardware](#hardware-platforms)
- [Hardware de Borde y Embebido](#edge-and-embedded-hardware)
- [Familias de Silicio y Productos](#silicon-and-product-families)
- [Silicio de IA Emergente](#emerging-ai-silicon)
- [Compiladores y Tiempos de Ejecución](#compilers-and-runtimes)
- [Benchmarks y Perfilado](#benchmarking-and-profiling)
- [Proyectos de Despliegue de Código Abierto](#open-source-deployment-projects)
- [Inferencia en Móviles y PCs de IA](#mobile-and-ai-pc-inference)
- [Artículos de Investigación](#research-papers)
- [Libros y Cursos](#books-and-courses)
- [Comunidad](#community)

## Plataformas de Hardware

- [NVIDIA CUDA](https://developer.nvidia.com/cuda-toolkit) - Plataforma de programación paralela para GPUs y aceleradores NVIDIA.
- [AMD ROCm](https://rocm.docs.amd.com/) - Pila de computación GPU de código abierto para aceleradores AMD.
- [Intel oneAPI](https://www.intel.com/content/www/us/en/developer/tools/oneapi/overview.html) - Modelo de programación multiarquitectura para CPUs, GPUs, FPGAs y aceleradores.
- [Google TPU](https://cloud.google.com/tpu/docs/intro-to-tpu) - Unidades de procesamiento de tensores para el entrenamiento y servicio de grandes cargas de trabajo de aprendizaje automático.
- [Microsoft Azure Maia](https://blogs.microsoft.com/blog/2026/01/26/maia-200-the-ai-accelerator-built-for-inference/) - Aceleradores de inferencia de primera parte de Microsoft para Azure, que sirven a Copilot y la familia de modelos MAI internos.
- [Cerebras WSE](https://www.cerebras.net/technology/) - Arquitectura de acelerador a escala de oblea para computación de redes neuronales densas.
- [Groq LPU](https://groq.com/technology/) - Arquitectura de procesador de inferencia diseñada alrededor de la generación determinista de tokens.
- [Tenstorrent](https://tenstorrent.com/) - Empresa de procesadores de IA basados en RISC-V con herramientas de software abiertas y placas para desarrolladores.
- [SambaNova](https://sambanova.ai/) - Sistemas de flujo de datos reconfigurables para entrenamiento e inferencia de IA empresarial.
- [Etched Sohu](https://www.etched.com/) - ASIC de inferencia centrado en transformadores para el servicio de modelos de lenguaje de alto rendimiento.

## Hardware de Borde y Embebido

- [NVIDIA Jetson](https://developer.nvidia.com/embedded/jetson) - Módulos de IA en el borde para robótica, sistemas de visión, automatización industrial e inferencia local.
- [Qualcomm AI Engine Direct SDK](https://www.qualcomm.com/developer/software/qualcomm-ai-engine-direct-sdk) - Acceso de bajo nivel a las rutas de inferencia de Hexagon, CPU y GPU de Qualcomm.
- [Hailo-8](https://hailo.ai/products/ai-accelerators/hailo-8-ai-accelerator/) - Familia de aceleradores M.2 y mini-PCIe para inferencia de visión por computadora de bajo consumo.
- [Google Coral](https://coral.ai/products/) - Módulos y placas Edge TPU para cargas de trabajo cuantizadas de TensorFlow Lite.
- [Luxonis OAK-D](https://shop.luxonis.com/products/oak-d) - Cámara de profundidad con inferencia neuronal en el dispositivo a través de la pila DepthAI.
- [Kneron KL720](https://www.kneron.com/products/kl720) - Unidad de procesamiento neuronal de bajo consumo para módulos USB y productos de visión embebida.
- [Raspberry Pi AI Kit](https://www.raspberrypi.com/products/ai-kit/) - Kit acelerador M.2 para Raspberry Pi 5 construido alrededor del procesador de inferencia Hailo.
- [AMD Versal AI Edge](https://www.amd.com/en/products/adaptive-socs-and-fpgas/versal/ai-edge.html) - Familia de SoC adaptativos que combinan lógica programable, núcleos CPU y Motores de IA.
- [STMicroelectronics STM32N6](https://www.st.com/en/microcontrollers-microprocessors/stm32n6-series.html) - Serie de microcontroladores con un bloque de aceleración neuronal integrado para IA en el borde.
- [Espressif ESP32-P4](https://www.espressif.com/en/products/socs/esp32-p4) - Procesador de aplicaciones para visión, pantalla y productos embebidos con capacidades de IA.
- [Arduino UNO Q](https://store.arduino.cc/products/uno-q) - Placa híbrida de IA en el borde que combina un procesador Linux Qualcomm Dragonwing QRB2210 con un microcontrolador en tiempo real STM32U585 en formato UNO.

## Familias de Silicio y Productos

- [Apple Core ML](https://developer.apple.com/documentation/coreml) - Marco de despliegue de modelos para la ejecución en Apple Neural Engine, GPU y CPU.
- [Qualcomm Snapdragon X Series](https://www.qualcomm.com/products/mobile-compute) - Procesadores Arm de clase portátil con aceleración NPU Hexagon integrada.
- [Intel Core Ultra](https://www.intel.com/content/www/us/en/products/details/processors/core-ultra.html) - Familia de procesadores para PCs de IA con bloques NPU Intel AI Boost integrados.
- [AMD Ryzen AI](https://www.amd.com/en/products/processors/consumer/ryzen-ai.html) - Familia de procesadores de consumo con unidades de procesamiento neuronal XDNA.
- [MediaTek NeuroPilot](https://www.mediatek.com/technology/artificial-intelligence) - Plataforma de IA móvil para Dimensity y otros SoC relacionados de MediaTek.
- [Samsung Exynos](https://semiconductor.samsung.com/processor/mobile-processor/) - Familia de procesadores móviles con unidades de procesamiento neuronal integradas.
- [Arm Ethos-U](https://www.arm.com/products/silicon-ip-cpu/ethos/ethos-u) - IP MicroNPU para diseños de inferencia en el borde Cortex-M y Cortex-A.
- [Synaptics Astra](https://www.synaptics.com/products/astra) - Plataforma de procesador de IA en el borde para sistemas embebidos de visión, audio y multimodales.
- [SiMa.ai MLSoC](https://www.sima.ai/products/mlsoc) - Plataforma SoC de aprendizaje automático orientada al despliegue industrial en el borde.
- [Axelera Metis](https://www.axelera.ai/products/metis-ai-platform) - Plataforma de IA en el borde construida alrededor de la arquitectura de acelerador Metis.

## Silicio de IA Emergente

- [Furiosa AI](https://furiosa.ai/) - Arquitectura de procesador de contracción de tensores para inferencia de transformadores, con microarquitectura publicada y pila de compiladores abierta.
- [Rebellions](https://rebellions.ai/) - Aceleradores de IA ATOM y REBEL orientados a la inferencia en centros de datos con una pila de software programable.
- [Lightmatter](https://lightmatter.com/) - Plataforma de computación fotónica e interconexión chip-a-chip para cargas de trabajo de redes neuronales a gran escala.
- [d-Matrix](https://www.d-matrix.ai/product/) - Empresa respaldada por Microsoft que comercializa el acelerador de computación digital en memoria Corsair para inferencia de IA generativa de baja latencia.
- [MatX](https://matx.com/) - Silicio personalizado para el entrenamiento de grandes modelos de lenguaje, diseñado alrededor de un modelo de programación de núcleos nativos (bare-metal).
- [Lemurian Labs](https://www.lemurianlabs.com/) - Arquitectura de procesador espacial codiseñada con una pila de compiladores de hardware definido por software.
- [Tensordyne Napier](https://www.tensordyne.ai/silicon-and-math) - Chip de inferencia de 3 nm que utiliza una arquitectura de matemáticas logarítmicas propietarias en lugar de multiplicación en punto flotante; las afirmaciones de rendimiento frente a Blackwell del fabricante esperan benchmarks independientes.

## Compiladores y Tiempos de Ejecución

- [XLA](https://openxla.org/xla) - Compilador de Álgebra Lineal Acelerada para TensorFlow, JAX y otros marcos de aprendizaje automático.
- [MLIR](https://mlir.llvm.org/) - Representación Intermedia Multi-Nivel para infraestructura de compiladores reutilizable.
- [Triton](https://triton-lang.org/) - Lenguaje y compilador tipo Python para escribir kernels de GPU personalizados.
- [Apache TVM](https://tvm.apache.org/) - Pila de compiladores de aprendizaje profundo de código abierto para CPUs, GPUs y aceleradores.
- [IREE](https://iree.dev/) - Entorno de Ejecución de Representación Intermedia para desplegar programas de aprendizaje automático.
- [NVIDIA TensorRT](https://developer.nvidia.com/tensorrt) - Optimizador y tiempo de ejecución de inferencia para GPUs y módulos Jetson de NVIDIA.
- [ONNX Runtime](https://onnxruntime.ai/) - Tiempo de ejecución de inferencia multiplataforma con backends de proveedor para múltiples aceleradores.
- [OpenVINO](https://docs.openvino.ai/) - Kit de herramientas de Intel para optimizar y desplegar inferencia en CPUs, GPUs y NPUs.
- [Vitis AI](https://github.com/Xilinx/Vitis-AI) - Compilador, tiempo de ejecución y zoo de modelos para SoC adaptativos AMD y tarjetas Alveo.
- [HailoRT](https://github.com/hailo-ai/hailort) - Pila de tiempo de ejecución y controladores para aceleradores de IA Hailo.
- [LiteRT](https://github.com/google-ai-edge/LiteRT) - Tiempo de ejecución de Google para inferencia en el dispositivo en objetivos móviles y embebidos.
- [ExecuTorch](https://github.com/pytorch/executorch) - Tiempo de ejecución de PyTorch para desplegar modelos en teléfonos, wearables y dispositivos embebidos.

## Benchmarks y Perfilado

- [MLPerf](https://mlcommons.org/benchmarks/) - Conjuntos de referencia (benchmarks) estándar de la industria para entrenamiento, inferencia, almacenamiento y sistemas de aprendizaje automático en el borde.
- [AI-Benchmark](https://ai-benchmark.com/) - Suite de benchmarks de aprendizaje profundo para comparaciones móviles, de escritorio y de aceleradores.
- [Geekbench AI](https://browser.geekbench.com/ai-benchmarks) - Navegador de puntuaciones de inferencia multiplataforma con resultados de CPU, GPU y NPU.
- [LLMPerf](https://github.com/ray-project/llmperf) - Entorno de benchmark para el rendimiento y la latencia de servicio de grandes modelos de lenguaje.
- [NVIDIA Nsight Systems](https://developer.nvidia.com/nsight-systems) - Herramienta de análisis de rendimiento a nivel de sistema para líneas de tiempo de CPU, GPU y sistema operativo.
- [NVIDIA Nsight Compute](https://developer.nvidia.com/nsight-compute) - Perfilador interactivo de kernels CUDA para análisis de ocupación, memoria e instrucciones.
- [PyTorch Profiler](https://pytorch.org/tutorials/recipes/recipes/profiler_recipe.html) - Perfilador integrado para la ejecución de modelos PyTorch y el cronometraje a nivel de operador.
- [Perfetto](https://perfetto.dev/) - Plataforma de traza y perfilado de grado producción para análisis de rendimiento de sistemas.

## Proyectos de Despliegue de Código Abierto

- [Jetson Containers](https://github.com/NVIDIA-AI-IOT/jetson-containers) - Pila CUDA, PyTorch, ROS y ML en contenedores para el desarrollo en NVIDIA Jetson.
- [Jetson Inference](https://github.com/dusty-nv/jetson-inference) - Ejemplos de extremo a extremo de clasificación, detección, postura y segmentación para módulos Jetson.
- [DeepStream Python Apps](https://github.com/NVIDIA-AI-IOT/deepstream_python_apps) - Enlaces y ejemplos de Python para pipelines de DeepStream multicámara.
- [Isaac ROS Common](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common) - Infraestructura Docker y de compilación para paquetes de aceleración NVIDIA Isaac ROS.
- [Hailo Model Zoo](https://github.com/hailo-ai/hailo_model_zoo) - Modelos preentrenados, scripts de compilación y flujos de despliegue para aceleradores Hailo.
- [Hailo Raspberry Pi 5 Examples](https://github.com/hailo-ai/hailo-rpi5-examples) - Pipelines de referencia para sistemas Raspberry Pi 5 que utilizan módulos de IA Hailo.
- [Edge TPU](https://github.com/google-coral/edgetpu) - Tiempo de ejecución en espacio de usuario, pruebas y ejemplos para dispositivos Google Coral Edge TPU.
- [RKNN Model Zoo](https://github.com/airockchip/rknn_model_zoo) - Ejemplos de despliegue y zoo de modelos para placas NPU Rockchip.
- [Texas Instruments TIDL Tools](https://github.com/TexasInstruments/edgeai-tidl-tools) - Herramientas de conversión y despliegue de modelos para aceleradores de aprendizaje profundo de TI.
- [OpenVINO Notebooks](https://github.com/openvinotoolkit/openvino_notebooks) - Cuadernos prácticos para conversión, optimización e inferencia de modelos en hardware Intel.
- [Qualcomm Linux Sample Apps](https://github.com/quic/sample-apps-for-qualcomm-linux) - Ejemplos de detección y clasificación para kits de evaluación Linux de Qualcomm.
- [Qualcomm Intelligent Development Kit](https://github.com/quic/qidk) - Muestras de Android que utilizan el Qualcomm AI Engine y la pila QNN.
- [Ryzen AI Software](https://github.com/amd/RyzenAI-SW) - Ejemplos de AMD y herramientas de despliegue para NPUs XDNA y XDNA 2.
- [OpenVINO Toolkit](https://github.com/openvinotoolkit/openvino) - Tiempo de ejecución, optimizador de modelos y muestras de código abierto para despliegue de inferencia Intel.
- [LeRobot](https://github.com/huggingface/lerobot) - Biblioteca de aprendizaje para robots para aprendizaje por imitación y aprendizaje por refuerzo en hardware local.
- [MLCommons Tiny](https://github.com/mlcommons/tiny) - Suite de benchmarks TinyML para detección de palabras clave, clasificación de imágenes y detección de anomalías.
- [TensorFlow Lite Micro](https://github.com/tensorflow/tflite-micro) - Tiempo de ejecución de inferencia para microcontroladores con kernels optimizados para objetivos embebidos.
- [Edge Impulse Standalone Inferencing](https://github.com/edgeimpulse/example-standalone-inferencing) - Ejemplos portátiles de inferencia en C++ generados a partir de proyectos de Edge Impulse.
- [ESP-WHO](https://github.com/espressif/esp-who) - Ejemplos de IA de cámara, detección y reconocimiento facial para dispositivos ESP32.
- [ESP-DL](https://github.com/espressif/esp-dl) - Biblioteca de cuantización e inferencia para desplegar redes neuronales en chips Espressif.
- [OpenMV](https://github.com/openmv/openmv) - Firmware y ejemplos de visión artificial para placas de microcontrolador de cámara basadas en MicroPython.
- [MaixPy](https://github.com/sipeed/MaixPy) - Marco de IA MicroPython para placas RISC-V Sipeed K210, K230 y relacionadas.
- [Openpilot](https://github.com/commaai/openpilot) - Pila de asistencia al conductor de código abierto que ejecuta cargas de trabajo de producción en hardware de IA automotriz.
- [Autoware](https://github.com/autowarefoundation/autoware) - Pila de conducción autónoma ROS 2 utilizada para investigación y desarrollo industrial de vehículos.
- [Apollo](https://github.com/ApolloAuto/apollo) - Plataforma de conducción autónoma con ejemplos de percepción, planificación, simulación y despliegue.

## Inferencia en Móviles y PCs de IA

- [ncnn](https://github.com/Tencent/ncnn) - Marco de inferencia de redes neuronales móviles optimizado para CPUs Arm y GPUs Vulkan.
- [MNN](https://github.com/alibaba/MNN) - Motor de inferencia móvil ligero utilizado en aplicaciones de producción de Alibaba.
- [Tencent TNN](https://github.com/Tencent/TNN) - Marco de inferencia multiplataforma para despliegues en Android, iOS y embebidos.
- [Xiaomi MACE](https://github.com/XiaoMi/mace) - Motor de cómputo de IA móvil para ejecución heterogénea en CPU, GPU, DSP y NPU.
- [llama.cpp](https://github.com/ggml-org/llama.cpp) - Motor de inferencia portátil en C y C++ para modelos de lenguaje cuantizados.
- [MLX](https://github.com/ml-explore/mlx) - Marco de arrays para silicio Apple con ejecución de modelos de memoria unificada.
- [Core ML Tools](https://github.com/apple/coremltools) - Herramientas de conversión y compresión para empaquetar modelos en formato Core ML.
- [MediaPipe](https://github.com/google-ai-edge/mediapipe) - Marco de gráficos multiplataforma para pipelines de visión, audio y multimodales en el dispositivo.
- [Transformers.js](https://github.com/huggingface/transformers.js) - Inferencia de transformadores en navegador y lado del servidor a través de WebAssembly y WebGPU.
- [Candle](https://github.com/huggingface/candle) - Marco de aprendizaje automático mínimo en Rust para binarios pequeños y aplicaciones de inferencia local.
- [Ollama](https://github.com/ollama/ollama) - Ejecutor local de modelos de lenguaje para backends de CPU y GPU.
- [LocalAI](https://github.com/mudler/LocalAI) - Servidor API autoalojado compatible con OpenAI para modelos locales de texto, audio y visión.
- [Open WebUI](https://github.com/open-webui/open-webui) - Interfaz de chat y recuperación local-first comúnmente emparejada con Ollama.

## Artículos de Investigación

- [In-Datacenter Performance Analysis of a Tensor Processing Unit](https://arxiv.org/abs/1704.04760) - Artículo original de Google TPU que describe la aceleración de inferencia en centros de datos.
- [A Domain-Specific Supercomputer for Training Deep Neural Networks](https://dl.acm.org/doi/10.1145/3360307) - Artículo del sistema Google TPU v3 que cubre infraestructura de entrenamiento a gran escala.
- [Cerebras CS-2 and Weight Streaming](https://arxiv.org/abs/2308.03029) - Arquitectura a escala de oblea y modelo de ejecución para entrenamiento de redes neuronales.
- [Roofline Model](https://dl.acm.org/doi/10.1145/1498765.1498785) - Modelo visual de rendimiento para razonar sobre cuellos de botella de cómputo y memoria.
- [FlashAttention](https://arxiv.org/abs/2205.14135) - Algoritmo de atención consciente de E/S para transformadores más rápidos y eficientes en memoria.
- [FlashAttention-2](https://arxiv.org/abs/2307.08691) - Paralelismo de atención y particionamiento de trabajo mejorados para GPUs.
- [Ansor](https://arxiv.org/abs/2006.06762) - Enfoque de programación automática para generar programas de tensores de alto rendimiento.
- [Triton Paper](https://dl.acm.org/doi/10.1145/3315508.3329973) - Lenguaje intermedio y compilador para computaciones de redes neuronales en bloques (tiled).
- [MLIR Paper](https://ieeexplore.ieee.org/document/9370308) - Infraestructura de compiladores para computación específica de dominio.
- [Stream-K](https://arxiv.org/abs/2301.03598) - Descomposición paralela centrada en el trabajo para multiplicación de matrices densas.
- [Efficiently Scaling Transformer Inference](https://arxiv.org/abs/2211.05100) - Análisis de la escalabilidad de inferencia y utilización de hardware para modelos transformadores.
- [LLM.int8()](https://arxiv.org/abs/2208.07339) - Método de multiplicación de matrices de 8 bits para inferencia de grandes modelos de lenguaje.

## Libros y Cursos

- [Dive into Deep Learning](https://d2l.ai/) - Libro de texto abierto con cuadernos ejecutables para cargas de trabajo modernas de aprendizaje profundo.
- [Efficient Deep Learning](https://efficientdlbook.com/) - Técnicas prácticas para entrenamiento y inferencia eficientes de modelos.
- [GPU Puzzles](https://github.com/srush/GPU-Puzzles) - Introducción basada en acertijos a los conceptos de programación GPU.
- [CUDA MODE](https://github.com/cuda-mode/lectures) - Serie de conferencias comunitarias sobre CUDA, kernels GPU y programación de aceleradores.
- [Triton Tutorials](https://triton-lang.org/main/getting-started/tutorials/index.html) - Ejemplos prácticos para escribir kernels personalizados con Triton.
- [TVM Tutorial](https://tvm.apache.org/docs/tutorial/) - Introducción de extremo a extremo a la compilación de modelos con Apache TVM.
- [TPU Research Cloud](https://sites.research.google/trc/about/) - Programa para investigadores y estudiantes para acceder a recursos TPU de Google.

## Comunidad

- [CUDA MODE Discord](https://discord.gg/cudamode) - Comunidad para programación de kernels GPU, perfilado e ingeniería de rendimiento.
- [NVIDIA Developer Forums](https://forums.developer.nvidia.com/c/accelerated-computing/cuda/206) - Foro oficial para desarrollo y resolución de problemas de CUDA.
- [MLCommons](https://mlcommons.org/) - Consorcio de ingeniería para benchmarks, conjuntos de datos y mejores prácticas de aprendizaje automático.
- [r/MachineLearning](https://www.reddit.com/r/MachineLearning/) - Comunidad de investigación que cubre sistemas de aprendizaje automático, modelos y tendencias de hardware.
- [SemiAnalysis](https://semianalysis.com/) - Análisis técnico de chips de IA, sistemas de centros de datos y cadenas de suministro de semiconductores.
- [tinyML Foundation](https://www.tinyml.org/) - Comunidad para aprendizaje automático de ultra bajo consumo en dispositivos embebidos.

## Contribuir

¡Agradecemos las contribuciones! Lee primero las [guías de contribución](contributing.md).
