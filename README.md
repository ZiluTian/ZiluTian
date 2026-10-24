# Hi, I'm Zilu Tian

**AI inference engineer.** I make models run fast on hardware that wasn't built for them: custom CUDA kernels, compiler toolchains, and quantization, backed by a PhD in database systems (EPFL) and publications at SIGMOD, ASPLOS, and ICDT.

Currently a Senior AI Engineer building fused operators and end-to-end compiler toolchains (TVM / LLVM / PyTorch) for specialized accelerators. I also trained in actuarial science (3rd prize, Travelers Actuarial Competition 2015), which is why I like risk models and anomaly detection as much as kernels.

📫 [LinkedIn](#) · [Google Scholar](#) · [Email](#)

---

## Highlights

**[it-assistant](https://github.com/ZiluTian/it-assistant): a 27B LLM copilot on two 10-year-old GPUs**
Self-hosted Qwen3.8-27B on 2× GTX 1080 Ti, on end-of-life Ubuntu 18.04 with no sudo (userspace gcc-8 + CUDA 11.4, llama.cpp built from source for SM_61). It streams on-demand fleet health reports, and the telemetry never leaves the box.
- **26.1 tok/s vs. 15.4 baseline (1.7×)** using the checkpoint's own co-trained MTP head.
- A separate 4B draft model made decoding *slower* (11.2 tok/s) on this bandwidth-bound setup. Full A/B methodology and bandwidth math: [BENCHMARKS.md](https://github.com/ZiluTian/it-assistant/blob/main/BENCHMARKS.md).

**[watup-llm](https://github.com/ZiluTian/watup-llm): the decode hot path, kernel by kernel**
A 12-kernel CUDA GEMV ladder for transformer decode on an RTX 5090, **up to 89× faster than a naive GEMV**, plus a batched-decode sweep and a cache-cold measurement methodology that holds up under real-world noise.

**[RegularPathQuery](https://github.com/ZiluTian/RegularPathQuery): a C++ graph query engine**
Output-sensitive evaluation of regular path queries with parallel execution, built to cut latency under high-concurrency analytical workloads (ICDT 2026).

**[torch-hostdev-lint](https://github.com/ZiluTian/torch-hostdev-lint): find per-iteration CPU↔GPU syncs without running your code**
A static, no-execution linter that walks PyTorch source via the AST and flags the closed set of host↔device sync/transfer APIs (`.item()`, `.cpu()`, `.to(device)`, `torch.*(..., device=)`) with loop-context severity — a `.item()` inside a `for` is HIGH with a concrete "accumulate on device, sync once" fix, while one-shot setup calls are down-graded to LOW. Stdlib-only, CI exit codes, JSON output, pre-commit hook, 45 tests — plus a measured benchmark showing ruff (no plugin API) catches 0 of the patterns while a ~80-line DIY hook covers ~17% of the finding space.

**[gitlab-mr-tracker](https://github.com/ZiluTian/gitlab-mr-tracker): live-track a GitLab MR's CI pipeline and comments from your terminal**
A zero-dependency Python CLI that renders an auto-refreshing dashboard of a merge request's CI run — every job with a color-coded status and duration, a `x/y done` progress line, and failed-job trace links — while following the MR's *current* head, so a new push tracks the new pipeline automatically. It surfaces new comments from others (with a deep link to each note), replies threaded or top-level with `@mentions` (`--dry-run` to preview), and `--watch` keeps monitoring after CI finishes. The GitLab token is read from `GITLAB_TOKEN` at run time and never stored; works with any instance, self-hosted or gitlab.com.

---

## What I work on

- **LLM inference & deployment:** decode optimization, quantization, speculative decoding, and deployment on constrained hardware, from edge devices to HPC clusters.
- **AI compilers:** operator fusion, graph-level optimization, and kernel development in Triton, CUDA, LLVM, and MLIR.
- **Performance engineering:** perf, VTune, flame graphs, and microarchitecture analysis to tell bandwidth-bound from compute-bound, then fix the right one.
- **Databases & query processing:** output-sensitive algorithms, parallel and distributed query execution, memory-hierarchy and data-locality optimization (up to 1000× over Spark/GraphX on simulation workloads).

**Toolbox:** CUDA · Triton · LLVM / MLIR · TVM · PyTorch · llama.cpp · C++ · Scala

---

## More projects

- [BSPModel](https://github.com/ZiluTian/BSPModel): typed model and staged compiler for parallel stateful computation (SIGMOD 2025)
- [SIGMOD23Experiments](https://github.com/ZiluTian/SIGMOD23Experiments): simulation workloads on Spark, GraphX, Giraph, Flink, and a custom runtime (SIGMOD 2023, GPCE 2023)
- [DifferentiableABS](https://github.com/ZiluTian/DifferentiableABS): differentiable, staged agent-based simulation in Scala
- [DesignConceptsInPL](https://github.com/ZiluTian/DesignConceptsInPL): mini-languages implemented in Scala 3
- [latex-tutorial-chinese](https://github.com/ZiluTian/latex-tutorial-chinese): a systematic Chinese-language LaTeX tutorial (★ 18)
- [scheduleForMe](https://github.com/ZiluTian/scheduleForMe): a personal scheduling app in Scala

---

## Selected publications

- M. Abo Khamis, A.-M. Hurjui, A. Kara, D. Olteanu, D. Suciu, **Z. Tian**. *Output-sensitive evaluation of acyclic conjunctive regular path queries.* **ICDT 2026**.
- **Z. Tian**, D. Olteanu, C. Koch. *Using process calculus for optimizing data and computation sharing in complex stateful parallel computations.* **SIGMOD 2025**.
- **Z. Tian**, P. Lindner, M. Nissl, C. Koch, V. Tannen. *Generalizing bulk-synchronous parallel processing for data science: From data to threads and agent-based simulations.* **SIGMOD 2023**.
- **Z. Tian**. *Multi-stage vertex-centric programming for agent-based simulations.* **GPCE 2023**.
- A. Pourhabibi Zarandi, S. Gupta, H. Kassir, M. Sutherland, **Z. Tian**, M. P. Drumond, B. Falsafi, C. Koch. *Optimus Prime: accelerating data transformation in servers.* **ASPLOS 2020**.
- **Z. Tian**, H. Ajallooiean. *CloudSuite tutorial.* **ISPASS 2019**.

Patent: hardware acceleration of data transformation (WO2021037341 / US11748254).

## Side projects

- [latex-tutorial-chinese](https://github.com/ZiluTian/latex-tutorial-chinese) — a systematic Chinese-language LaTeX tutorial (★ 18)
- [scheduleForMe](https://github.com/ZiluTian/scheduleForMe) — a personal scheduling app in Scala
