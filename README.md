# Zilu Tian

AI inference engineer with 8+ years of experience across LLM deployment,
compiler optimization, and database systems — from fused operators for
specialized accelerators down to memory-bus-level analysis of the LLM
decode hot path. PhD in Computer Science (EPFL); first-author publications
at SIGMOD, ASPLOS, and ICDT. Trained in actuarial science, with applied
experience in insurance risk modeling and risk/fraud analytics.

Currently a Senior AI Engineer designing fused AI operators and end-to-end
compiler toolchains (TVM / LLVM / PyTorch) for specialized accelerators.

## Focus

- **LLM inference & deployment** — taking models from framework to the wire
  across data centers, edge devices, and HPC clusters: decode hot-path
  optimization (custom CUDA GEMV kernels, up to 89× vs. naive),
  quantization, speculative decoding, and full-stack deployment on
  constrained hardware (EOL OS, no sudo, userspace toolchains)
- **AI compiler infrastructure** — fused operators, operator fusion,
  graph-level optimization, and Triton/CUDA kernel development; end-to-end
  toolchains (TVM / LLVM / PyTorch) for specialized accelerators
- **Compilers** — optimization passes, IR transformations, and code
  generation in LLVM, MLIR, and Triton; compiler formalisms for static
  analysis and transformation of stateful parallel computation (SIGMOD'25)
- **Databases & query optimization** — query engines, output-sensitive
  algorithms, and parallel/distributed query execution; 10–1000x
  performance gains via memory-hierarchy and data-locality optimization
- **Systems & profiling** — full-stack performance engineering: perf,
  VTune, flame graphs, microarchitecture analysis, memory-subsystem
  bottleneck identification (bandwidth-bound vs. compute-bound regimes);
  10–1000x speedups through compiler-driven parallelism, memory-hierarchy
  optimization, and hardware-aware scheduling
- **Actuarial science & risk analytics** — formal training in actuarial
  science (life contingency, probability, stochastic processes, loss
  distributions, insurance risk modeling); statistical/quantitative
  modeling for risk assessment and pricing; large-scale anomaly detection
  adapted to fraud, claims-outlier, and operational-risk scenarios; 3rd
  prize, Travelers Actuarial Competition (2015)

## LLM & AI Inference

- **Decode hot path** — a 12-kernel CUDA GEMV ladder for transformer
  decode on RTX 5090, up to 89× vs. a naive GEMV, with a cache-cold
  measurement methodology that survives real-world noise
  ([watup-llm](https://github.com/ZiluTian/watup-llm))
- **Speculative decoding, measured** — on bandwidth-bound consumer GPUs a
  separate 4B draft model *slows* decoding down (it shares the memory bus
  with the target); the checkpoint's own co-trained MTP head delivers
  1.7× (26.1 vs. 15.4 tok/s on Qwen3.8-27B). Full A/B methodology and the
  bandwidth math:
  [it-assistant/BENCHMARKS.md](https://github.com/ZiluTian/it-assistant/blob/main/BENCHMARKS.md)
- **Deployment engineering on constrained hardware** — a self-hosted 27B
  LLM copilot on two ten-year-old GTX 1080 Ti: EOL Ubuntu 18.04, no sudo,
  full userspace toolchain (gcc-8 + CUDA 11.4), llama.cpp built from source
  for SM_61, even dual-GPU tensor split, on-demand streamed health reports
  — telemetry never leaves the box
  ([it-assistant](https://github.com/ZiluTian/it-assistant))
- **Fused operators & end-to-end toolchains** — current work: fused AI
  operators and compiler toolchains (TVM / LLVM / PyTorch) for specialized
  accelerators, from quantization and operator fusion to graph-level
  optimization

## Databases & Query Optimization

Building and optimizing query engines and distributed data-processing systems:

- **Query optimization** — output-sensitive algorithms and query-optimization techniques for acyclic conjunctive regular path queries, aligning computation cost with output size and decision impact (ICDT'26)
- **C++ query engines** — high-performance graph-database engine using output-sensitive algorithms and parallel execution, with significant latency reduction under high-concurrency, large-scale analytical workloads ([RegularPathQuery](https://github.com/ZiluTian/RegularPathQuery))
- **Distributed & parallel query execution** — shared-nothing architecture, barrier-less execution, and automatic data partitioning / communication minimization for cloud-scale query processing; a compiler formalism for data and computation sharing (SIGMOD'25, [BSPModel](https://github.com/ZiluTian/BSPModel))
- **Data-systems benchmarking** — simulation workloads on Spark, GraphX, Giraph, Flink, and a custom runtime, up to 1000x speedup over Apache Spark/GraphX (SIGMOD'23, GPCE'23, [SIGMOD23Experiments](https://github.com/ZiluTian/SIGMOD23Experiments))

## Selected repositories

- [it-assistant](https://github.com/ZiluTian/it-assistant) — self-hosted LLM IT copilot: Qwen3.8-27B on 2× GTX 1080 Ti (llama.cpp, no sudo, EOL Ubuntu 18.04) with 1.7× MTP speculative decode, plus a stdlib-only fleet monitor that streams on-demand health reports — telemetry never leaves the box
- [watup-llm](https://github.com/ZiluTian/watup-llm) — LLM inference engineering: a 12-kernel CUDA GEMV ladder for the decode hot path (up to 89× vs. naive), batched-decode sweep, and cache-cold measurement methodology (RTX 5090)
- [RegularPathQuery](https://github.com/ZiluTian/RegularPathQuery) — C++ graph query engine; output-sensitive evaluation of regular path queries (ICDT'26)
- [BSPModel](https://github.com/ZiluTian/BSPModel) — typed model + staged compiler for parallel stateful computation (SIGMOD'25)
- [SIGMOD23Experiments](https://github.com/ZiluTian/SIGMOD23Experiments) — simulation workloads on Spark / GraphX / Giraph / Flink / CloudCity, one self-contained repo (SIGMOD'23, GPCE'23)
- [DifferentiableABS](https://github.com/ZiluTian/DifferentiableABS) — differentiable, staged agent-based simulation in Scala
- [DesignConceptsInPL](https://github.com/ZiluTian/DesignConceptsInPL) — mini-languages implemented in Scala 3

## Publications (selected)

- M. Abo Khamis, A.-M. Hurjui, A. Kara, D. Olteanu, D. Suciu, **Z. Tian**. *"Output-sensitive evaluation of acyclic conjunctive regular path queries."* ICDT 2026 (to appear).
- **Z. Tian**, D. Olteanu, C. Koch. *"Using process calculus for optimizing data and computation sharing in complex stateful parallel computations."* Proc. ACM Manag. Data (SIGMOD) 2025.
- **Z. Tian**, P. Lindner, M. Nissl, C. Koch, V. Tannen. *"Generalizing bulk-synchronous parallel processing for data science: From data to threads and agent-based simulations."* Proc. ACM Manag. Data (SIGMOD) 2023.
- **Z. Tian**. *"Multi-stage vertex-centric programming for agent-based simulations."* GPCE 2023.
- A. Pourhabibi Zarandi, S. Gupta, H. Kassir, M. Sutherland, **Z. Tian**, M. P. Drumond, B. Falsafi, C. Koch. *"Optimus Prime: accelerating data transformation in servers."* ASPLOS 2020.
- **Z. Tian**, H. Ajallooiean. *"CloudSuite tutorial."* ISPASS 2019.

Plus a patent on hardware acceleration of data transformation (WO2021037341 / US11748254).

## Side projects

- [latex-tutorial-chinese](https://github.com/ZiluTian/latex-tutorial-chinese) — a systematic Chinese-language LaTeX tutorial (★ 18)
- [scheduleForMe](https://github.com/ZiluTian/scheduleForMe) — a personal scheduling app in Scala
