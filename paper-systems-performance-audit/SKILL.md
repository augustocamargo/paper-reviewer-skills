---
name: paper-systems-performance-audit
description: >
  Audit systems, software, database, networking, GPU, compiler, distributed, or
  HPC performance claims. Use when a paper reports latency, throughput, speedup,
  scalability, memory, energy, cost, resource utilization, or deployment results.
---

# Systems performance audit

## Measurement checks
1. Warmup, repetitions, variance, confidence intervals, outlier policy, and
   benchmark harness are stated.
2. Hardware/software stack is complete: CPU/GPU, memory, storage, network,
   compiler, drivers, CUDA/cuDNN, kernel, container, precision, batch size.
3. Baselines use comparable optimization effort, hardware, parallelism,
   batching, caching, IO, compilation, and precision.
4. Separate cold-start, steady-state, data loading, preprocessing, compilation,
   communication, synchronization, and kernel time.
5. Use realistic workloads and scaling dimensions; avoid only toy microbenchmarks
   unless the contribution is explicitly microarchitectural.
6. Report bottlenecks and failure regimes, not only best-case speedups.
7. For energy/cost, measure directly when possible and state meter/tool overhead.

## Reviewer traps
- Geometric mean hides catastrophic regressions.
- Speedup without absolute latency can be meaningless.
- Throughput gains may come from larger batches that violate latency constraints.
- CPU/GPU comparisons can be unfair if one side is under-optimized.
- Cloud instance variability and co-tenancy can dominate small effects.

## Output
- Performance-claim table: `claim | measurement support | fairness risk | fix`.
- Missing setup details reviewers will demand.
- Claims to rephrase from universal speedup to regime-specific speedup.
- Minimal rerun plan for the most fragile performance claims.
