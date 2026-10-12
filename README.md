# Zilu Tian

Compiler and systems engineer with 8+ years of experience in query and compiler optimization, parallel computing, and AI inference acceleration. PhD in Computer Science (EPFL); first-author publications at SIGMOD, ASPLOS, and ICDT. Trained in actuarial science, with applied experience in insurance risk modeling and risk/fraud analytics.

Currently a Senior AI Engineer designing fused AI operators and end-to-end compiler toolchains (TVM / LLVM / PyTorch) for specialized accelerators.

## Focus

- **AI inference** — taking models from framework to efficient deployment across data centers, edge devices, and HPC clusters: quantization, operator fusion, graph-level optimization, Triton/CUDA kernel development
- **Compilers** — optimization passes, IR transformations, and code generation in LLVM, MLIR, and Triton; compiler formalisms for static analysis and transformation of stateful parallel computation (SIGMOD'25)
- **Systems & profiling** — full-stack performance engineering: perf, VTune, flame graphs, microarchitecture analysis, memory-subsystem bottleneck identification; 10–1000x speedups through compiler-driven parallelism, memory-hierarchy optimization, and hardware-aware scheduling
- **Actuarial science & risk analytics** — formal training in actuarial science (life contingency, probability, stochastic processes, loss distributions, insurance risk modeling); statistical/quantitative modeling for risk assessment and pricing; large-scale anomaly detection adapted to fraud, claims-outlier, and operational-risk scenarios; 3rd prize, Travelers Actuarial Competition (2015)

## Selected repositories

- [watup-llm](https://github.com/ZiluTian/watup-llm) — LLM fine-tuning & low-latency inference pipeline (work in progress)
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
